# **Javascript**

## **`Object.create`**

* Another way of implementing OOP in Javascript
* e.g. `create` is a static method on `Object`


<details>

<summary>Static Methods</summary>

* Method defined on a class, not instance of class - **Static Method**
* For Javascript, a **method defined** on the **constructor** behaves like a static method
* These are **NOT** available on **instances**, only on **prototypes**

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
</details>

```javascript
const PersonProto = {
  calcAge() {
    console.log(2037 - this.birthYear);
  },

  init(firstName, birthYear) {
    this.firstName = firstName;
    this.birthYear = birthYear;
  }
};

const steven = Object.create(PersonProto);
console.log(steven);
steven.init('Steven', 2002);
steven.calcAge();   // 35
```

### **How `Object.create` works**

* By using this syntax, we are **manually** setting the **prototype** of that object to the passed object
* The prototype chain functions as before, however there is no **constructor function** (and also no `prototype` property)