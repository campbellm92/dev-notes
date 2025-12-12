# never type

When you want to explicitly state that a function will never return sth

```typescript
function logAndThrow(errorMessage: string): never {
  console.log(errorMessage);
  throw new Error(errorMessage);
}
```

This function cannot be used somewhere where a value is expected
