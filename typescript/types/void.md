# Void

For when you want to specify that a function doesn't return anything

```typescript
function log(message: string): void {
  console.log(message);
}
```

Good for functions with side effects only:

```typescript
type User = {
  id: number;
  email: string;
  isActive: boolean;
};

function deactivateUser(user: User): void {
  user.isActive = false;
  console.log(`User ${user.email} has been deactivated`);
}
```
