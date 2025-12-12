# Record types

Generic type - meant to work with other types

When you want a var to be an object but don't know what key-value pairs it's going to have yet:

This means that this var must be an object

```typescript
let data: Record<string, number | string>;

data = {
  entry1: 2,
  entry2: "text",
};
```

... the left side tells you what kind of value the key needs to be, the right side the value
