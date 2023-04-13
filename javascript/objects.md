# **Javascript**

## **Objects**

* Used for data that can be grouped together but in an un-ordered fashion

```javascript
const obj = {id: 2, name: "test"};   // literal syntax
```

* Retrieving property values from object

```javascript
console.log(obj.id);    // 2

// or

console.log(obj['id']);    // 2
```

> In simple cases, use `dot notation` (aka 'member access'). When there is a need to compute the property name, then use `bracket notation` (aka 'computed member access').

* Adding property values to object

```javascript
obj.number = 1;

// or

obj['number'] = 1;
```

### **Object Operations (Methods)**

* Object can also have properties with a function value

```javascript
obj.foo = () => console.log("foo");

// or

obj['foo'] = () => console.log("foo");
```

* `this` keyword can be accessed inside of these functions (only if [function declaration or expression](functions.md) is used)

```javascript
const person = {
  birthYear: 1997,
  calcAge: function () {
    this.age = 2023 - this.birthYear
    return this.age;
  }
}

console.log(jonas.calcAge());     // 26
console.log(jonas.age);     // 26
```