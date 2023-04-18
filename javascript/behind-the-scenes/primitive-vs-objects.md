# **Javascript**

## **Primitives**

* Primitives or **Primitive Types**:
  * Number
  * String
  * Boolean
  * Undefined
  * Null
  * Symbol (ES2015)
  * BigInt (ES2020)
* **Primitives** are **stored** in the **call stack** (actually in the execution contexts where they are declared)
* A primitive actually holds a **memory address**, which points to a place where the value is stored
* So, when we **change** the **value** of a **variable**, a **new memory address** is allocated because memory adresses are immutable
* That is why, the below code works as expected

```javascript
let age = 30;
let oldAge = age;   // has the value of same memory address as age
age = 31;
console.log(age);   // 31
console.log(oldAge);    // 30
```

## **Objects**

* Objects or **Reference Types**:
  * Object literal
  * Arrays
  * Functions
  * Many more...
* **Objects** are **stored** on the **heap**
* Object types also hold a memory address, but in this case it points to **another memory address** [^1]
* This memory address points to the address (location) of the actual **object value stored on the heap**
* So, when we change a property value of the object, the **original memory address** is **not changed**.
* That is why, the below code changes the `name` property value for the `me` object as well because `me` contains the **reference** to the object `{ name: 'Asad' }` and not the **actual value** as in the case of a **primitive**

```javascript
const me = {
  name: 'Asad'
};
const friend = me;   // has the value of same memory address as age
friend.name = 'Friend Name';

console.log(friend);   // { name: 'Friend Name' }
console.log(me);    // { name: 'Friend Name' }
```

[^1]: Objects might be too large to store in the stack. Instead they are stored in the heap, which is like an almost unlimited memory pool. The stack just keeps a reference of where the object is actually stored in the heap.
