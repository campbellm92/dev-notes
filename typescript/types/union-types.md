# Union types

String types with |

For when you want flexibility but not the chaos of any

```typescript
let age: string | number | boolean = 33;

age = "34"; // assignable
age = 35; // assignable
age = true; // assignable
age = []; // not assignable
```
