# **Javascript**

## **First-Class Functions**

* Javscript treats functions as **first-class citizens**
* This means that functions are **simply values**
* Functions are just another **"type" of object**
  * Functions can be **stored as variables or properties**

  ```javascript
  const add = (a, b) => a + b;

  const counter = {
    value: 1,
    inc: function() {
      this.value++;
    }
  };
  ```

  * Pass **functions as arguments** to **OTHER functions** i.e. callbacks of event listeners
  * Return **functions FROM functions**
  * Call **methods on functions**

  ```javascript
  counter.inc.bind(someOtherObj);
  ```

## **Higher-Order Functions (HOCs)**

* A function that **receives** another function as an argument, that **returns** a new function, or **both**
  * Function that **receives another function** e.g. an event listener is an HOC because it receives a callback function
  * Function that **returns new function**

  ```javascript
  function count() {
    let counter = 0;
    return function() {
      counter++;
    }
  };

  // count is a HOC here
  ```

* This is only possible because of first-class functions
  * i.e. this is a practical implementation of **First-Class Functions** (which is a theoretical concept)
