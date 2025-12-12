#

You can't assign an empty object in TS.

{} as an assignment means any value that's not null or undefined.

So this works:

```typescript
let val: {} = "text";
```

This doesn't:

```typescript
let val: {} = null;
```
