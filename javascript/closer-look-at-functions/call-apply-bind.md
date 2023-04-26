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

* Similar to `call` and `bind` but it **does NOT immediately call the function**, only **creates a new function with `this` keyword** and **arguments applied** (if any)
  * Giving some arguments to the `bind` method is known as **Partial Application**

```javascript
const greeterFunc = function (greeting) {
  console.log(`${greeting}, my name is ${this.name}!`);
};

const person = {
  name: 'Asad',
};

const greetAsad = greeterFunc.bind(person);

greetAsAsad('Hello');   // Hello, my name is Asad!

// arguments example
const complexGreeterFunc = function (greeting, question) {
  console.log(`${greeting}, my name is ${this.name}! ${question}`);
};

const greetAsAsadWithHelloQuestion = complexGreeterFunc.bind(person, 'Hello');

greetAsAsadWithHelloQuestion('How are you?');   // Hello, my name is Asad! How are you?
```

* This is also used with **event listeners**

  ```javascript
  const counter = {
    count: 0,
    inc() {
      console.log(this);    // <button class=​"increment">​+​</button>​
      this.count++;
      console.log(this.count);
    },
  };

  // assuming DOM has a button element with class 'increment'
  document.querySelector('.increment').addEventListener('click', counter.inc);
  ```

  * Clicking the button shows us that when the `addEventListener` function is called on a DOM element, the `callback` function is provided with a **reference** to the **DOM element**
  * So here, we will use `bind` function to provide the **appropriate reference** to the `counter` object

  ```javascript
    document.querySelector('.increment').addEventListener('click', counter.inc.bind(counter));
  ```

  * Now, the function will work as expected

* Another example of **partial explanation**

```javascript
const addTax = (rate, value) => value + value * rate;

const addVAT = addTax.bind(null, 0.23);

console.log(addVAT(23));    // 28.29
```
