# **Javascript**

## **Default Parameters**

* Sometimes we need **parameters by default** so we don't have to **pass them manually** in the case we don't want to **change the default**

```javascript
const funcA = function (param) {
  console.log(param);   // will be undefined if not specified in function call
};

funcA();

// with default parameters
const funcB = function (param = "test") {
  console.log(param);   // test
};

funcB();
```

* These default parameters can also be **"transformed"**

```javascript
// with default parameters
const func = function (name, num = 1, price = 100 * num) {
  return {
    name,
    num,
    price
  }
};

func("Asad", 10);   // { name: "Asad", num: 10, price: 1000 }
func("Not Asad", 5, 200);   // { name: "Not Asad", num: 5, price: 200 }
```

> This "transformation" of default parameters can only include parameters listed before and not after i.e. num = price / 10 would give an error
