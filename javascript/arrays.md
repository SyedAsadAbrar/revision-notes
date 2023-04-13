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