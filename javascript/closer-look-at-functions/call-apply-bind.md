# **Javascript**

## **`call` Method**

* Used to supply a `this` object to a function and call the function simultaneously

```javascript
const greeterFunc = function (greeting) {
  console.log(`${greeting}, my name is ${this.name}!`);
};

const person = {
  name: 'Asad',
};

greeterFunc('Hello');   // Uncaught TypeError: Cannot read properties of undefined (reading 'name')

greeterFunc.call(person, 'Hello');    // Hello, my name is Asad!

// the first argument of call is the object which is the source of `this` and the rest are the arguments given to the calling function i.e. greeterFunc in this case
```

* Does **NOT** work with **arrow functions**
  * Function expression and declarations only

## **`apply` Method**

* Same as `call` but the **arguments** to calling function are **passed as an array**

```javascript
const greeterFunc = function (greeting) {
  console.log(`${greeting}, my name is ${this.name}!`);
};

const person = {
  name: 'Asad',
};

const arguments = ['Hello'];

greeterFunc.apply(person, arguments);    // Hello, my name is Asad!
```

## **`bind` Method**

* Similar to `call` and `bind` but it **does NOT call the function**, only **creates a new function with `this` keyword** and **arguments applied** (if any)