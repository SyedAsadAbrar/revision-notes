# **Javascript**

## **```let```, ```const``` and ```var```**

* Variables defined using ```let``` can be **reassigned**
* Variables defined using ```const``` **cannot** be **reassigned**

> When defining variable using ```let```, we may or may not give it an initial value but when defining using ```const``` we HAVE to give it an initial value (since it can't be reassigned later)

### ```var```

* Variables defined can be **reassigned**
* Should be **avoided** [^1]
* Used before ES6
* It is **function-scoped** as compared to block-scoped (which ```let``` and ```const``` are)
* **Unique** behaviour of `var` in `for` loop when **`setTimeout`** is used [^2] [^3]
  * This is due to the fact that `var` is function-scoped, is **hoisted** to the top of the function and is **accessible outside the loop**
  * Since **`setTimeout`** accepts a **callback** which is called after the loop is completed, it see the **final value** of `index` which it tries to access it which in the case of `var` is `5`
  * When **declared** using `let` keyword, it has **block scope**, and is only accessible **within the loop**
  * Each **iteration** of the loop creates a **new block scope**, so each `setTimeout` function gets its own copy of `index` with the **correct** value

```javascript
for (let index = 0; index < 5; index++) {
  setTimeout(() => {
    console.log(index);     // 0, 1, 2, 3, 4
  }, 0);
}

for (var index = 0; index < 5; index++) {
  setTimeout(() => {
    console.log(index);     // 5, 5, 5, 5, 5
  }, 0);
}
```

### **Dynamic Typing**

* Javascript is a **loosely typed** language
* No need to **specify** data type
* Value can be updated after initialization - **dynamic typing**

### **Global Variables**

* Variables declared outside of any function - **Global Variables**
* Variables initialized without `let`, `var` or `const` act as **global** variables

```javascript
function myfunction(){
    msg = "Hello JavaScript!"; 
}

myfunction();
alert(msg); // msg becomes global variable so can be accessed here
```

[^1]: [Variable Declaration in JavaScript: var, let or const?](!https://dev.to/zhiyueyi/variable-declaration-in-javascript-var-let-or-const-1789)
[^2]: [How the let, const, and var Keywords Work in JavaScript](!https://www.freecodecamp.org/news/understanding-let-const-and-var-keywords/)
[^3]: [Why let and var bindings behave differently using setTimeout function?](!https://stackoverflow.com/questions/31285911/why-let-and-var-bindings-behave-differently-using-settimeout-function)
