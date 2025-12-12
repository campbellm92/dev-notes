# for...of

Example:

```js
    for (const row of rows)
```

This is the same as doing

```js
for (let i = 0; i < rows.length; i++) {
  const row = rows[i];
```

You could also do forEach, but it doesn't work well with async/await

```js
rows.forEach((row) => {
  // your logic here
});
```
