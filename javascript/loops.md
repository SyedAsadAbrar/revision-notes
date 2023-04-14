# **Javascript**

## **Loops**

* To do repetitive tasks
* Used to implement **DRY** - Don't Repeat Yourself

### **`for` loop**

* for loop keeps running while condition is `true`

```javascript
console.log(`Lifting weights repetition 1 🏋🏼‍♀️`);
console.log(`Lifting weights repetition 2 🏋🏼‍♀️`);
console.log(`Lifting weights repetition 3 🏋🏼‍♀️`);
console.log(`Lifting weights repetition 4 🏋🏼‍♀️`);
console.log(`Lifting weights repetition 5 🏋🏼‍♀️`);

// or

for (let rep = 1; rep <= 5; rep++) {
  console.log(`Lifting weights repetition ${rep} 🏋🏼‍♀️`);
}
```

* `continue` statement - to skip an iteration
* `break` statement - completely terminate the loop

### **`while` loop**

* while loop keeps running while condition is `true`

```javascript
let rep = 1;
while(rep <= 5) {
  console.log(`Lifting weights repetition ${rep} 🏋🏼‍♀️`);
  rep++;
}
```
