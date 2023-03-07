# **Javascript**

## **Functions**

* Piece of code which can be reused over and over again

```javascript
function logger(str) {
  console.log('Logger function called' + str);
}

logger('abc');   /// calling / running / invoking a function
```

> Functions are great for implementing `DRY` principle

### **Function Declarations vs Expressions**

* Function declaration defines a function with specified parameters
  * The functons are hoisted at the top so they can be used before they are declared

> In above example, `logger` is the ***function name***, `str` is the ***parameter*** and `'abc'` is the ***argument***.

* A function expression is very similar to and has almost the same syntax as a function declaration
  * The main difference between a function expression and a function declaration is the function name, which can be omitted in function expressions to create anonymous functions.
  * Function expressions are not hoisted so cannot be used before creation
  * Can also be used as IIFE (Immediately Invoked Function Expression) which runs as soon as it is defined
  * Essentially a function value stored in a variable

  ```javascript
  (function () {
    console.log("Code runs!");
  })();

  // or

  !function () {
    console.log("Code runs!");
  }();
  ```

### **Arrow Functions**

* Just like a normal function but has different syntax
* Great for one-liner functions
* Does not have access to `this` variable

```javascript
const func = (param) => param + 1;
```
