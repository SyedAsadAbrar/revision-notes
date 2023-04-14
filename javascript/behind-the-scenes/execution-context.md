# **Javascript**

## **Execution Context**

* Environment in which a piece of Javascript is executed
* It stores all the necessary information for some code to be excuted

> Pizza coming in a delivery box with receipt and cutlery is a metaphor of execution context where pizza is the javascript code and the rest is the execution context

* There is exactly **one** global execution context; created for `top-level code`

> **Top-level code** - Code which is not inside any function

* Each function call has a new execution context created for it, which all together form the `call stack`