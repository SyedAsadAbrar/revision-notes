# **Javascript**

## **Scope**

* ***Scoping*** - Defines how a program's variables are **organized** and **accessed**
* ***Lexical Scoping*** - Scoping is controlled by **placement** of functions and blocks in the code (this is a javascript concept)
* ***Scope*** - Space or environment in which a certain variable is **declared** (variable environment in case of functions)
  * There are 3 kinds of scope; **global**, **function** and **block**
* **Scope of a variable** - Region of our code where a certain variable can be **accessed**

### 1. **Global Scope**

* Outside of **any** function or block
* Variables declared in global scope are accessible **everywhere** - so are called **global variables**

```javascript
const me = 'Jonas';
const job = 'teacher';
const year = 1989;
```

### 2. **Function Scope**

* Variables are accessible only **inside function, NOT** outside
* Also called local scope
* **All** kind of functions have function scope; **function declarations**, **function expressions** and **arrow functions**

> Function variable environment === function scope

```javascript
function calcAge(birthYear) {
  const now = 2037;
  const age = now - birthYear;
  return age;
}

console.log(now);   // ReferenceError
```

### 3. **Block Scope**

* Variables are accessible only **inside block** (block scoped)
* **HOWEVER**, this only applies to `let` and `const` variables
  * `var` variables are function scoped; they can still be accessible outside block and are scoped to current function or global scope
* Functions are **also block scoped** (only in strict mode)

```javascript
function calcAge(birthYear) {
  const now = 2037;
  const age = now - birthYear;
  return age;
}

console.log(now);   // ReferenceError
```

## **Scope Chain**

* Inner scope trying to access variable not found in its scope and looks up variable in parent (or outer) scopes until it finds it - **variable lookup**
* This can only happen in **one direction** that is outer scope cannot access the variables of inner scope
  * Two inner scopes (siblings) cannot access variables of each other as well
  * This is due to the rules defined by **Lexical Scoping**
* Also the variables are not **copied** but only **referenced**
* Also