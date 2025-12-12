# Assining types to function paramaters

```typescript
function add(a: number, b: number) {
  return a + b;
}
```

For default values you might not assign the value a type:

```typescript
function add(a: number, b = 5) {
  return a + b;
}
```
