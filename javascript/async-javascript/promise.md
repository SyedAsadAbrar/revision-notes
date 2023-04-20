# **Javascript**

## **Promise**

* Object that is used as a **placeholder** for the **future result** of an **async operation** - **Promise**
  * A lottery ticket can be considered a metaphor for promise i.e. we may get a prize and we may not, a lottery ticket is a "promise" of a prize which may get fulfilled or not (rejected)
* We **NO** longer need to **rely on events** and **callbacks** passed into async functions to handle async results
* Instead of nesting callbacks, we can **chain promises** for a sequence of async operations **escaping callback hell**
* Promises are an **ES6** feature (2016)

### **Promise Lifecycle**

![Promise lifecycle](../images/promise-lifecycle.png)

### **Consuming Promises**

```javascript
const getCountryData = country =>
  fetch(`${baseUrl}/name/${country}`)
    .then(response => response.json())
    .then(data => renderCountry(data[0]));

getCountryData('Pakistan');
```

> Using promises get rid of callback hell, not callbacks

### **Promise Chaining**

```javascript
const getCountryData = country =>
  fetch(`${baseUrl}/name/${country}`)
    .then(response => response.json())
    .then(data => {
      renderCountry(data[0]);
      console.log(data[0]);
      const neighbour = data[0].borders?.[0];

      if (!neighbour) return;

      return fetch(`${baseUrl}/alpha/${neighbour}`);    // Returning a promise from promise
    })
    .then(response => response.json())    // Consumed here
    .then(data => renderCountry(data, 'neighbour'));

getCountryData('Pakistan');
```

### **Handling Rejected Promises**

* Either we can use a `catch` method or pass a second argument to the `then` method to handle `rejected` promises

```javascript
const getCountryData = country =>
  fetch(`${baseUrl}/name/${country}`)
    .then(response => response.json())
    .then(data => renderCountry(data[0]))
    .catch(err => console.log(err));      // Method 1

getCountryData('Pakistan');
```

```javascript
const getCountryData = country =>
  fetch(`${baseUrl}/name/${country}`)
    .then(
      response => response.json(),
      err => console.log('err', err)      // Method 2
    )
    .then(data => renderCountry(data[0]));

getCountryData('Pakistan');
```
