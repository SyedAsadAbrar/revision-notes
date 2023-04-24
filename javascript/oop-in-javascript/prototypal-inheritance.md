# **Javascript**

## **Prototypal Inheritance**

* **Constructor function** is linked with **Prototype** using `prototype` object i.e. `Person` has `Person.prototype`
* **Prototype** is linked with **Constructor function** using `constructor` method on **Prototype** i.e. `Person.prototype` has `Person.prototype.constructor`
* When `new` keyword is used to create an **object** of a **prototype**
  * An empty object is created
  * `this` keyword in constructor functional call is set to the new object
  * The new object is linked (`__proto__` property) to the constructor function's prototype property
  * The new object is returned from the constructor function call
* If a method isn't present on an object, it will "look up" in the Prototype of the object and will call the method if found - **Prototypal Inheritance/Delegation** using **Prototypal chain**
  * `Object.prototype` is the "base class" of all prototypes so it is on the top of the prototype chain
  * A prototype is also an object so it also a prototype i.e. `Object.prototype`