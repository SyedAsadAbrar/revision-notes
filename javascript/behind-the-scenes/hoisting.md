# **Javascript**

## **Hoisting**

* Makes some types of variables accessible/usable in the code before they are actually declared - **Hoisting**
* **Before execution**, code is scanned for variable declarations, and for each variable, a new property is created in the **variable environment object**

|| Hoisted? | Initial Value | Scope |
| ------------- | ------------- | ------------- | ------------- |
| **function declarations** | YES  | Actual function | Block
| **`var` variables** | YES  | `undefined` | Function
| **`let` and `const` variables** | NO [^1]   | `<uninitialized>`, TDZ [^2] | Block

> **function expressions and arrows** - Depends if using `var` or `let`/`const`, because they are essentially variables

[^1]: Technically, yes. But not in practice.
[^2]: Temporal Dead Zone

#### Why Hoisting?

* To **use functions before actual declaration**
* **`var` hoisting** is a just a **byproduct**

### **Temporal Dead Zone (TDZ)**

* Each `let` and `const` variable get their own TDZ that starts at the beginning of the scope until the line where it is defined
* Until then, if we access a `let` or `const` variable, we will get a `ReferenceError`; slightly different from the error caused by an `undefined` variable

```javascript
console.log(`Jonas is a ${job}`);   // ReferenceError: Cannot access 'job' before initialization
const age = 2037 - 1989;
console.log(age);
const job = 'teacher';
console.log(x);   // ReferenceError: x is not defined
```

#### Why TDZ?

* TDZ makes it **easier to avoid and catch errors**
  *  accessing variables before declaration is bad practice and should be avoided
* **Makes `const` variables actually work**
  * const variables should never be reassigned so they cannot be `undefined` at first and then assigned real values later
  * Only assigned when execution actually reaches the declaration
  * Makes it impossible to use the variable before
