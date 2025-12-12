# find()

Returns the first element of an array that satisfied a specified condition. It stops iterating as soon as it has found a match. If no match is found it returns undefined.

# find() vs filter()

Filter is like find but it returns all the matching elements

In this example, find is appropriate because you only need one match

```js
if (!brand && brandCode) {
  brand = allBrands.find((brand) => brand.code === brandCode.padStart(3, "0"));
}
```

The function that this lives in (getBrand()), is applied to a loop where all rows are accessed:

```js
    for (const row of rows) {
      const brand = await getBrand(
        row["Product Brand"],
        row["Tecdoc Brand ID"],
        allBrands
      );
```
