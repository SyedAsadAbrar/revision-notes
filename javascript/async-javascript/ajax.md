# **Javascript**

## **AJAX**

* **Asynchronous Javascript and XML** - AJAX
* It allows us to communicate with remote web servers in an **async way**
* With AJAX, we can **request data** from web servers dynamically
* There are a lot of ways to make an AJAX request including **XMLHttpRequest**

```javascript
const baseUrl = 'https://restcountries.com/v2/';

const request = new XMLHttpRequest();
request.open('GET', `${baseUrl}/name/Pakistan`);
request.send();

request.addEventListener('load', function () {
  const [data] = JSON.parse(this.responseText);
  console.log(data);    // {name: 'Pakistan', topLevelDomain: Array(1), alpha2Code: 'PK', alpha3Code: 'PAK', callingCodes: Array(1), …}
});
```
