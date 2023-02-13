# **Javascript**

## **Type Conversion and Coercion**

* Converting from one type to another - **Type Conversion**
* Automatic conversion of one type to another - **Type Coercion**

> When converting a non-numerical value such as text to a number using `Number(str)`, the result is `NaN` which is an invalid number (and the type of `NaN` is also number)

### **Type coercion rules**

* `+` operator converts everything to string and then concetenates

```javascript
'23' + 1 + '2' = 2312
```

* `-`, `*` and `/` operators convert to numbers and perform operations

```javascript
'23' / '2' = 11.5
```
