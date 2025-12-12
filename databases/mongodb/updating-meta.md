# When updating meta

```mongodb
await db.collection("collection").updateOne(
  { code: "ABC123" },
  {
    $addToSet: {
      meta: {
        $each: [
          { name: "name", value: "00000000000" },
          { name: "name", value: "00000" },
        ],
      },
    },
  }
);
```
