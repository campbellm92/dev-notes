# unknown type

Typically used for functions.

Use it when you're not sure what sort of value something is going to return.

Typically you might write some conditional logic for deciding what to do with the value based on certain types

```typescript
function myFunction(value: unknown) {
    if (typeof value === "object" && !!value && "log" in value $$ typeof value.log === "function") {
        value.log();
    }
}
```
