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
  * Only checks value i.e. `18` and `'18'` would return a **truthy** value
  * This performs **type conversion** under the hood
* `===` - strict equality
  * Checks value and type so `18` and `'18'` would return a **falsy** value

> `switch` statement uses strict equality

Similarly, we also have 'inequality' operators:

* `!=`
* `!==`

## **Logic Operators**

* `&&` - `AND` - Both must be true
* `||` - `OR` - Either one of the two variables must be true
* `!` - `NOT` - Inverts boolean value

> `NOT` operator has more preference than `AND` or `OR`
