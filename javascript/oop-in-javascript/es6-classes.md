# **Javascript**

## **ES6 Classes**

* Syntatical sugar for **Constructor Functions**, both can be used
* Class Declarations

```javascript
class User {
  constructor(fullName, birthYear) {
    this.fullName = fullName;
    this.birthYear = birthYear;
  }

  // Methods will be added to .prototype property
  calcAge() {
    console.log(2037 - this.birthYear);
  }
}

// We can also do this
User.prototype.greet = function () {
  console.log(`Hey ${this.firstName}`);
}
```

* Class Expressions

```javascript
const User = class {
  // code
}
```

* Classes are **NOT** hoisted
* Classes are **first-class citizens** so can be passed as arguments
* Classes are executed in **strict mode**
* Classes also have **getters** or **setters** (as do objects in javascript)

```javascript
class User {
  // rest of code

  get age() {
    return 2037 - this.birthYear;
  }

  // Setting a property that already exists
  set fullName(name) {
    // This is a convention to avoid setting a property
    // which already exists. Using '_' creates another
    // variable and that is why we also used a getter to
    // get this value whenever we access 'fullName' property
    // on a User object. This setter is also called when
    // the constructor is called.
    this._fullName = name;
  }

  get fullName() {
    return this._fullName;
  }
}

const jonas = new User('Jonas', 20);

console.log(jonas.age);   // 20
jonas.fullName = 'Jonas LastName';
console.log(jonas);   // User {_fullName: 'Jonas LastName', birthYear: 20}
console.log(jonas.fullName);    // 'Jonas LastName'
```