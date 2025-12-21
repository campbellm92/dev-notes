# Using functions as types

In JS, functions are values that can be passed to variables and other functions.

In TS function types are defined like this:

```typescript
function logMessage(msg: string) {
  console.log(msg);
}

function myFunction(callback: (parameter: string) => void) {
  //
  callback("My function");
}

myFunction(logMessage);
```

"void" is the kind of return value you want to expect (return type).

Note the above is NOT the same as creating an arrow function in JS.


