# **Javascript**

## **Closures**

* The ability of a function in javascript to **access the variable environment** of the **execution context** in which the **function was created** - **Closure**
  * Formally, a closure is the closed-over **variable environment** of the execution context **in which a function was created**, even ***after*** that execution context is gone
  * In other words, a closure gives a function access to all the variables **of its parent function**, even ***after*** that parent function has returned. The function keeps a **reference** to its outer scope, which ***preserves*** the scope chain throughout time.

```javascript
let f;

const g = function() {
  const a = 23;
  f = function() {
    console.log(a * 2);
  }
}

g();    // After this line, the variable environment of `g` is no longer there as the execution context has been destroyed, yet `f` still has access to `a` variable defined inside of `g` function
f();    // 46
```

* **Closure** has **priority** over **scope chain**
* `async` functions also form a **closure**

> We cannot manually create closures, this happens automatically

> A closure is **NOT** a tangible Javascript object
