# **Javascript**

## **Async/Await**

* Introduced in **ES2017**
* **Syntactic sugar** over consuming **promises**

```javascript
const whereAmI = async function (country) {
  const res = await fetch(`https://restcountries.com/v3.1/name/${country}`);
  console.log(res);
};

whereAmI('Pakistan');
```

* Function runs **asynchronously** in background but looks as if it is **synchronous** code, no **callbacks** or **`then`** functions
* It returns a **promise** and is equivalent to

```javascript
const whereAmI = function (country) {
  fetch(`https://restcountries.com/v3.1/name/${country}`).then(res =>
    console.log(res)
  );
};

whereAmI('Pakistan');
```

> Basically, instead of using `then` (chaining of promises), we can use `async` and `await` keyword

* The function in which `await` keyword is used must be an `async` function i.e. it must have `async` keyword before definition
* We can use a `try..catch` block to replace `catch` and `finally` methods on promises

```javascript
checkMail()
  .then((mail) => {
    console.log(mail);
  })
  .catch((err) => {
    console.error(err);
  })
  .finally(() => {
    console.log('Experiment completed');
  });

// becomes

(async function() {
    try {
    const mail = await checkMail();
    }
    catch (err) {
        console.error(err);
    }
    console.log('Experiment completed';)
})()
```