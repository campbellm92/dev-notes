# Type casting

```typescript
const element = document.getElementById("element"); // html element

console.log(element?.value);
```

In the above example, TS does not know that .value should be accessible for the element in question so you need to cast it:

```typescript
const element = document.getElementById("element") as HTMLInputElement; // for example

console.log(element?.value);
```

