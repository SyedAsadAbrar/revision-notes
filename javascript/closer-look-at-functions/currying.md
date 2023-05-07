# **Javascript**

## **Currying**

* Transformation of functions that translates a function from callable as `f(a, b, c)` into callable as `f(a)(b)(c)` - **Currying**
* It **doesn't call** a function, just **transforms** it
* Multi-argument function implementation
  * When we run this, there are two `if` execution branches:
    * If passed args count is the same or more than the original function has in its definition (`func.length`) , then just pass the call to it using `func.apply`
    * Otherwise, get a partial: we don’t call `func` just yet. Instead, another wrapper is returned, that will re-apply `curried` providing previous arguments together with the new ones
  * Then, if we call it, again, we’ll get either a new partial (if not enough arguments) or, finally, the result

```javascript
function curry(func) {
    return function curried(...args) {
        if (args.length >= func.length) {
            return func.apply(this, args);
        } else {
            return function(...args2) {
                return curried.apply(this, args.concat(args2));
            }
        }
    };
}

// how is it used
function sum(a, b, c) {
    return a + b + c;
}

let curriedSum = curry(sum);

alert(curriedSum(1, 2, 3)); // 6, still callable normally
alert(curriedSum(1)(2,3)); // 6, currying of 1st arg
alert(curriedSum(1)(2)(3)); // 6, full currying
```

> Currying requires the function to have a fixed number of arguments, so function with rest parameters `f(...args)` can't be curried this way

* Currying has [two use-cases](https://javascript.info/currying-partials#currying-what-for):
  * **Partial Application**
  * Original function can be used as before