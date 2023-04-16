# **Javascript**

## **Hoisting**

* Makes some types of variables accessible/usable in the code before they are actually declared - **Hoisting**
* **Before execution**, code is scanned for variable declarations, and for each variable, a new property is created in the **variable environment object**

|| Hoisted? | Initial Value | Scope |
| ------------- | ------------- | ------------- | ------------- |
| **function declarations** | YES  | Actual function | Block
| **`var` variables** | YES  | `undefined` | Function
| **`let` and `const` variables** | NO [^1]   | `<uninitialized>`, TDZ [^2] | Block

> **function expressions and arrows** - Depends if using `var` or `let`/`const`

[^1]: Technically, yes. But not in practice.
[^2]: Temporal Dead Zone