# null and undefined types

null -> explicitly empty/intentionally no value
undefined -> not provided/not yet assigned

null is useful because it represents a meaningful "nothing" state: the field exists but there's no value/information available yet

null type can be useful when used in a union type.

```typescript
let x: null | string;
```

x can be a string or null (absence of data is possible)

In TS you can force not null with !

# null and undefined types

null type can be useful when used in a union type.

```typescript
const element = document.getElementById("element")!; // html element

console.log(element.value);
```

In this way, you 'convince' the compiler that the value is not null. This should be handled carefully because it can lead to runtime errors if a value is in fact null.

You can also use optional chaining (from JS)

```typescript
const element = document.getElementById("element"); // html element

console.log(element?.value);
```
