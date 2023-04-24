# **Javascript**

## **`Object.create`**

* Another way of implementing OOP in Javascript
* e.g. `create` is a static method on `Object`
* These are **NOT** available on **instances**, only on **prototypes**

### **Static Methods**

* Method defined on a class, not instance of class - **Static Method**
* For Javascript, a **method defined** on the **constructor** behaves like a static method

```javascript
// assuming User constructor (function) exists
User.hey = function () {
  console.log('Hey there 👋🏼');    // Hey there 👋🏼
  console.log(this);    // class User {
                        // constructor(fullName, birthYear) {
                        //   this.fullName = fullName;
                        //   this.birthYear = birthYear;
                        // }

                        // // This will be defined on the User's prototype
                        // calcAge() {
                        //   console.log(2037 - t…
};
User.hey();
```

* When using **ES6 syntax**

```javascript
class User {
  // rest of code
  static hey() {
    console.log('Hey there 👋🏼');    // Hey there 👋🏼
    console.log(this);    // class User {
                          // constructor(fullName, birthYear) {
                          //   this.fullName = fullName;
                          //   this.birthYear = birthYear;
                          // }

                          // // This will be defined on the User's prototype
                          // calcAge() {
                          //   console.log(2037 - t…
  }
}
User.hey();
```