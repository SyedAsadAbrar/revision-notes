# **Javascript**

## **```let```, ```const``` and ```var```**

* Variables defined using ```let``` can be reassigned
* Variables defined using ```const``` cannot be reassigned

> When defining variable using ```let```, we may or may not give it an initial value but when defining using ```const``` we HAVE to give it an initial value (since it can't be reassigned later)

### ```var```

* Variables defined can be reassigned
* Should be avoided
* Used before ES6
* It is block-scoped as compared to function-scoped (which ```let``` is)

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