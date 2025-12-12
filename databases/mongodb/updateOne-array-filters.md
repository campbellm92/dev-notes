# updating when there are nested vals:

```mongodb / python
            update = UpdateOne(
                {"_id": object_id},
                {
                    "$set": {
                        "nested.$[elem].code": code
                    }
                },
                array_filters=[{"elem.code": original_code}]
            )
```
