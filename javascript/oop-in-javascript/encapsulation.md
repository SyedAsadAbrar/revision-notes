# **Javascript**

## **Encapsulation in Javascript**

* "Real" Encapsulation isn't supported in Javascript (yet)
* We add an `_` before **"protected" properties or methods**
  * This is a **convention** and it still allows us to access the specific property or method (it isn't binding)

```javascript
class BankAccount {
  constructor(pin, currency = 'PKR', amount = 0) {
    // protected property
    this._pin = pin;
    this.movements = [];
    this.currency = currency;
    this.amount = amount;
  }

  deposit(val) {
    this.movements.push(val);
  }

  withdraw(val) {
    this.deposit(-val);
  }

  getPin() {
    return this._pin;
  }
}

const asad = new BankAccount(1234, 'PKR', 10000);

console.log(asad._pin); // 1234
console.log(asad.getPin()); // 1234
```

* We add an `#` before **"private" properties or methods**
* `static` keyword is used for static methods or properties
* To define public fields, we simply define/initialize them with value or declare them

```javascript
class BankAccount {
  // public fields (instances)
  locale = navigator.language;

  // private fields (instances)
  #pin;

  constructor(pin, currency = 'PKR', amount = 0) {
    // private property
    this.#pin = pin;
    this.movements = [];
    this.currency = currency;
    this.amount = amount;
  }

  // public method
  deposit(val) {
    this.movements.push(val);
  }

  // public method
  withdraw(val) {
    this.deposit(-val);
  }

  // public method
  requestLoan(val) {
    if (this.#approveLoan(val)) {
      this.deposit(val);
      console.log(`Loan Approved`);
    }
  }

  // public method or interface
  getPin() {
    return this.#pin;
  }

  // private method
  #approveLoan(val) {
    return true;
  }

  static helper() {
    console.log('Helper method called');
  }
}

const asad = new BankAccount(1234, 'PKR', 10000);

// console.log(asad.#pin); // Uncaught SyntaxError: Private field '#pin' must be declared in an enclosing class (at script.js:300:17)
console.log(asad.getPin());   // 1234
asad.requestLoan(1000);   // Loan Approved
BankAccount.helper();   // Helper method called
```