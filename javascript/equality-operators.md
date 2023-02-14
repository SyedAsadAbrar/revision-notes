# **Javascript**

## **Equality Operators**

Values which are converted to false when converted to boolean:

* `0` - number
* `''` - string
* `undefined` - undefined
* `null` - object
* `NaN` - number

> All other values will be converted to a `truthy` value, and obviously `false` is falsy

There are two kinds of equality operators:

* `==` - loose equality
  * Only checks value i.e. `18` and `'18'` would return a truthy value with this
* `===` - strict equality
  * Checks value and type so `18` and `'18'` would not return a truthy value

Similarly, we also have 'inequality' operators:

* `!=`
* `!==`