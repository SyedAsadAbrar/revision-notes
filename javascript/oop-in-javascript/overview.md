# **Javascript**

## **OOP Overview**

* **Class** is a 'blueprint', **instance** is an object created from the class
* **Four principles** of OOP:
  * **Abstraction** - Ignoring or hiding details that **don't matter**, operating as a **black box**, allowing us to get a **overview** persepctive of the *thing* we're implementing
  * **Encapsulation** - Keeping properties and methods **private** inside the class, so they are **not accessible from outside the class**
    * Some methods can be **exposed** as a public interface (API)
    * This prevents external code from manipulating internal properties/states
    * Allows to change internal implementation without the risk of breaking external code
  * **Inheritance** - Establishes a **child-parent** relationship, making all proerties and methods of a certain class **available to a child class**, forming a hierarchiacal relationship between classes.
    * This allows us to **reuse common logic** and to model real-world relationships
  * **Polymorphism** - A child can **overwrite** a method it inherited from a parent class