# **Javascript**

## **OOP Overview**

* **Class** is a 'blueprint', **instance** is an object created from the class - **Class-instance** model
* **Four principles** of OOP:
  * **Abstraction** - Ignoring or hiding details that **don't matter**, operating as a **black box**, allowing us to get a **overview** persepctive of the *thing* we're implementing
  * **Encapsulation** - Keeping properties and methods **private** inside the class, so they are **not accessible from outside the class**
    * Some methods can be **exposed** as a public interface (API)
    * This prevents external code from manipulating internal properties/states
    * Allows to change internal implementation without the risk of breaking external code
  * **Inheritance** - Establishes a **child-parent** relationship, making all proerties and methods of a certain class **available to a child class**, forming a hierarchiacal relationship between classes.
    * This allows us to **reuse common logic** and to model real-world relationships
  * **Polymorphism** - A child can **overwrite** a method it inherited from a parent class

### **OOP in Javascript**

* Javascript has **Prototypes** and **Objects**, objects are **linked** to a prototype object
  * **Prototype** - contains methods
  * **Object** - can access those methods
* The prototype contains methods (behavior) that are **accessible to all objects linked to that prototype** - **Prototypal Inheritance**
* Behavior is delegated to the linked prototype object

![Prototypal Inheritance](/javascript/images/prototypal-inheritance.png)

#### **Prototypal Inheritance in Javascript**

* Three ways of implementing it:
  * **Constructor Functions**:
    * Technique to create objects from a function
    * This is how built-in objects like Arrays, Maps or Sets are actually implemented
  * **ES6 Classes**
    * Modern alternative to constructor function syntax
    * "Syntactic sugar": behind the scenes, ES6 classes work **exactly** like constructor functions
    * ES6 classes do **NOT** behave like classes in "classical OOP"
  * **`Object.create()`**
    * The easiest and most straightforward way of linking an object to a prototype object

##### **Constructor Functions**

* Can be **defined** using a **function expression or declaration**, not an arrow function because it doesn't have `this` keyword
* By convention, **constructor functions start** with a **capital letter**
* To add a **method** to this "class", **use** the **`prototype` object**
  * This way there would only be **one "copy"** of that method
  * If it is defined in the constructor function, the same copy would persist in all instances of that class which is a bad way of doing it

```javascript

const Person = function(firstName, birthYear) {
  this.firstName = firstName;
  this.birthYear = birthYear;

  // Never do this
  // Instance method
  // this.calcAge = function() {
  //   console.log(2037 - this.birthYear);
  // };
};

// 1. New {} is created
// 2. function is called, this = {}
// 3. {} is linked to prototype
// 4. function automatically returns {}

const jonas = new Person('Jonas', 1991);
console.log(jonas);   // Person {firstName: "Jonas", birthYear: 1991}
console.log(jonas instanceof Person);   // true

// Prototypes
// Right way to add a method
Person.prototype.calcAge = function() {
  console.log(2037 - this.birthYear);
};

jonas.calcAge();    // 46
```