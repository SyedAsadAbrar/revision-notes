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

