# Custom types

Type aliases / custom types are useful for avoiding repetition

```typescript
type Role = "admin" | "guest" | "editor" | "reader";
```

Good for object types, which can get complex

```typescript
type User = {
  name: string;
  age: number;
  role: Role; // from above
  permissions: string[];
};
```
