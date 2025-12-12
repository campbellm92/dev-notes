### TypeError: expected string or bytes-like object, got 'NAType'

Arises when something is not respecting pd.NA, for example if you only check for strings like this:

```python
if not isinstance(value, str):
    return value
```

If using pandas, better to do this:

```python
if pd.isna(value):
    return value

```
