# never type

When you want to explicitly state that a function does not return.

```typescript
function logAndThrow(errorMessage: string): never {
  console.log(errorMessage);
  throw new Error(errorMessage);
}
```

This function cannot be used somewhere where a value is expected.

Never should be used when a function:

- always throws an exception
- always redirects
- always terminates execution
- represents an impossible state

```typescript
function redirect(url: string): never {
  window.location.href = url;
  throw new Error("redirecting");
}
```
