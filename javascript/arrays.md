# **Javascript**

## **Arrays**

* Used for contiguous data

```javascript
const arr = ['test', 'array', '1'];   // literal syntax

// or

const arr = new Array('test', 'array', '1');
```

* Accessed using a `bracket` syntax e.g. `arr[0]` would be `'test'` where `0` is the position or ***index*** of the element `'test'` in the array `arr`
* To get the number of elements in array

```javascript
const arr = ['test', 'array', '1'];   // literal syntax

console.log(arr.length);   // 3
```

* Member variables can have different types as well

```javascript
const arr = ['test', 1, []];
```

* `arr` variable cannot be redefined again but individual members can be replaced

```javascript
const arr = ['test', 1, []];

arr = [1];   // TypeError: Assignment to constant variable.

arr[1] = 2;   // arr = ['test', 2, []];
```

### **Array Operations (Methods)**

* Addition
  * `push` - Adds an element to end of array - `arr.push(1);`
  * `unshift` - Adds an element to start of array - `arr.unshift(1);`
  * Both methods return length after addition
* Removal
  * `pop` - Removes an element from end of array - `arr.pop();`
  * `shift` - Removes an element from start of array - `arr.shift();`
  * Both methods return element removed
* `indexOf` - Returns index of element in array or `-1` if element not found in array - `arr.indexOf(1)`
* `includes` - Returns a boolean value of the presence of an element in array - `arr.includes(1)`
  * `includes` is an ES6 method
  * It does strict checking and no type coercion
