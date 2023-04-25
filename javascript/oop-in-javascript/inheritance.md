# **Javascript**

## **Inheritance in Javascript**

* Using **Constructor Functions**

```javascript
const Person = function(firstName, birthYear) {
  this.firstName = firstName;
  this.birthYear = birthYear;
}

Person.prototype.calcAge = function () {
  console.log(2037 - this.birthYear);
}

const Student = function(firstName, birthYear, course) {
  // sets `this` object and calls constructor function as well
  Person.call(this, firstName, birthYear);
  this.course = course;
}

// Linking prototypes
// The prototype of a student will be the prototype of Person now
Student.prototype = Object.create(Person.prototype);

Student.prototype.introduce = function () {
  console.log(`My name is ${this.firstName} and I study ${course}`);
}

Student.prototype.constructor = Student;

const mike = new Student('Mike', 2020, 'Computer Science');
mike.calcAge();   // 17
mike.introduce();   // My name is Mike and I study Computer Science
```