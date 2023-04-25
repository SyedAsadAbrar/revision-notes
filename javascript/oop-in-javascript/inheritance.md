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

* Using **ES6 Classes**

```javascript
class Person {
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
Person.prototype.greet = function () {
  console.log(`Hey ${this.firstName}`);
}

class Student extends Person {
  constructor(fullName, birthYear, course) {
    // Always needs to happen first!
    // `this` is set in this line
    super(fullName, birthYear);
    this.course = course;
  }

  introduce() {
    console.log(`My name is  ${this.fullName} and I study ${this.course}`);
  }

  // polymorphism - overridden fucntion
  calcAge() {
    console.log(`I'm ${2037 - this.birthYear} old but I feel 35 years old`);
  }
}

const martha = new Student('Martha Jones', 2012, 'Computer Science');
martha.introduce();   // My name is  Martha Jones and I study Computer Science
martha.calcAge();   // I'm 25 old but I feel 35 years old
```

* Using **`Object.create`**

```javascript
const PersonProto = {
  calcAge() {
    console.log(2037 - this.birthYear);
  },
  init(firstName, birthYear) {
    this.firstName = firstName;
    this.birthYear = birthYear;
  },
};

const steven = Object.create(PersonProto);

// Linking Prototypes
const StudentProto = Object.create(PersonProto);

// Overriding methods
StudentProto.init = function (firstName, birthYear, course) {
  PersonProto.init.call(this, firstName, birthYear);
  this.course = course;
};

StudentProto.introduce = function () {
  console.log(`My name is ${this.firstName} and I study ${this.course}`);
};

const jay = Object.create(StudentProto);

jay.init('Jay', 2010, 'Computer Science');
console.log(jay);   // {firstName: 'Jay', birthYear: 2010, course: 'Computer Science'}
jay.introduce();    // My name is Jay and I study Computer Science
```