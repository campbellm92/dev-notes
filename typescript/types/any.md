# Any type

For situations where you need more flexibility in type.

The following fails because of type inferencing:

```typescript
let age = 33;

age = "45";
```

The following allows the var to accept any kind of value:

```typescript
let age: any = 33;

age = "45";
age = false;
age = [];
```

Generally not a good idea to use any -- defeats the idea of TS. Use it as a last resort.

Better alterative: see union-types.md
