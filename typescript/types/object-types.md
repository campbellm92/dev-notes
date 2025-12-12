# Object types

TS will infer this:

```typescript
let user = {
    name: "name"
    age: 98
}
```

Explicit w/ type definitions:

```typescript
let user: {
  name: string;
  age: number | string;
  hobbies: string[];
  role: {
    description: string;
    id: number;
  };
} = {
  name: "name",
  age: 98,
  hobbies: ["Reading", "Languages"],
  role: {
    description: "admin",
    id: "131",
  },
};
```
