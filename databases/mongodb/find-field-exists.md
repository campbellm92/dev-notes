# find if a particular field exists in documents in a particular collection

This you can use to see if documents have a field type / useful for limiting search results to only items that have a particular thing

```mongodb
db.products.find({ cross: { $exists: true } })
```

Limit results to more than 0:

```mongodb

db.products.find({
  cross: { $exists: true, $not: { $size: 0 } }
})


```
