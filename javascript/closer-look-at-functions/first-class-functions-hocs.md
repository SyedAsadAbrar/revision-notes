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

## **First-Class Functions**