# padStart(length, string)

Adds a string to the start of another string.

length = the amount of strings you want to add
string = the string you want to add

This adds three 0s to the start of the productRef:

```js
     { "suppliers.article_code": productRef.padStart(3, "0") },
```
