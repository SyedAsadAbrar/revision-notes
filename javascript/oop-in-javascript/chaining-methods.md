# **Javascript**

## **Chaining Methods**

* Simply returning the object in a method will allow us to chain methods

```javascript
class BankAccount {
  constructor(pin, currency = 'PKR', amount = 0) {
    this.movements = [];
    this.currency = currency;
    this.amount = amount;
  }

  deposit(val) {
    this.movements.push(val);
    return this;
  }

  withdraw(val) {
    return this.deposit(-val);
  }
}

const account = new BankAccount(1234, 'PKR', 10000);

account.deposit(1000).withdraw(1000).deposit(100000);

console.log(account.movements);   // [1000, -1000, 100000]
```