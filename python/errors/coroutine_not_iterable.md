# TypeError("'coroutine' object is not iterable")

**Error found in**: ATP application

**Error context**: Trying to make asynchronous requests to the Spotify API using Python's async features + httpx

**Problem**: I had handled the logic correctly in the two main helper functions that make requests to the Spotify API but not in the top level router that consumes them.

**Solution**: This was a simple matter of remembering to add async/await in the top level router.

## Code examples

A helper function:

```python
async def resolve_artist_id(artist_name, access_token):
    key = artist_name.lower().strip()

    if key in ARTIST_ID_CACHE:
        return ARTIST_ID_CACHE[key]

    endpoint = "https://api.spotify.com/v1/search"
    headers = {"Authorization": f"Bearer {access_token}"}
    params = {
        "q": artist_name,
        "type": "artist",
        "limit": 1
    }

    async with httpx.AsyncClient(timeout=5) as client:
        response = await client.get(endpoint, headers=headers, params=params)

    if response.status_code != 200:
        ARTIST_ID_CACHE[key] = None
        return None

    data = response.json()

    items = data["artists"]["items"]
    if not items:
        ARTIST_ID_CACHE[key] = None
        return None

    artist_id = items[0]["id"]
    ARTIST_ID_CACHE[key] = artist_id

    return artist_id
```

The router function:

```python
@router.get("/play")
async def play(request: Request):
    access_token = request.cookies.get("access_token")

    if not access_token:
        return RedirectResponse(url=REDIRECT)

    authenticated = bool(request.cookies.get("access_token"))

    if not authenticated:
        return RedirectResponse(url=REDIRECT)

    artists = generate_random_artists()

    if not artists:
        raise HTTPException(status_code=404, detail="No artists returned in response.")

    response = []
    seen = set()

    for artist_id, artist_name in artists:
        key = artist_name.lower().strip()

        if key in seen:
            continue

        spotify_artist_id = await resolve_artist_id(artist_name, access_token)
        if not spotify_artist_id:
            continue

        track_uri = await resolve_artist_to_track_uri(spotify_artist_id, access_token)
        if not track_uri:
            continue

        response.append({
            "artist_id": artist_id,
            "artist_name": artist_name,
            "track_uri": track_uri
        })

    return response
```

## Notes

### Coroutines

Coroutines are a way of pausing the execution of a function to allow other tasks to happen.

Coroutines pause at the await keyword. This is why it was important to use it in the example above, cited again here:

```python
spotify_artist_id = await resolve_artist_id(artist_name, access_token)
if not spotify_artist_id:
    continue

track_uri = await resolve_artist_to_track_uri(spotify_artist_id, access_token)
if not track_uri:
    continue
```

That is, it's imported to 'pause' while awaiting a response from the Spotify API

### The "not iterable" part

A coroutine is a task, not something that can be iterated over like a list of numbers. The list of numbers is the thing you need to await to be iterated over.
