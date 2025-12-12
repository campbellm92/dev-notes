# Literal types

When you assign a string value as a type.

Often preferred to enums

```typescript
let userRole: "admin" | "editor" | "guest" = "admin";

userRole = "guest";
```
