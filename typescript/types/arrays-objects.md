# Arrays - objects

TypeScript automatically infers when there are two types, i.e. here with an array of strings:

```typescript
let hobbies = ["Reading", "Learning languages"]; // type-inferred as an array of strings

hobbies.push(10); // not assignable
```
