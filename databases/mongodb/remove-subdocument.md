# Remove a subdocument

For example, if you've accidentally carried out an update where there's a false value:

1. set up a filter
2. set up the update object
   -> use the $pull method
   -> include the fields that would identify the document you want to remove
3. use updateOne for the update (removal) of the record

```mongodb

        const filter = { "code": code };

        const update = {
          $pull: {
            suppliers: {
              field: new ObjectId(00000000000000),
              other_field: "string",
            },
          },
        };

        const result = await collection.updateOne(filter, update);
        if (result.modifiedCount > 0) {
          console.log(`Removed X from ${code}`);
        } else {
          console.log(`No matching X found for ${code}`);
        }

```
