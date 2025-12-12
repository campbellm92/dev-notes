# Partial matches

You can search for partial matches in a mongodb query using a regex pattern.

See here:

```mongodb
db.products.find({name: /NAME/i})
    .projection({})
    .sort({})
    .limit(0)
```
