# JavaScript Request Cookbook

In this repository I will try to collect the most common use cases of sending request using JavaScript.

I will give examples for the following approaches:

* [XMLHttpRequest API](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)
* [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
* [jQuery Ajax](https://api.jquery.com/jquery.ajax/)
* [Axios](https://github.com/axios/axios)


I will use [JSONPlaceholder](https://jsonplaceholder.typicode.com/) service for requests testing and [CodePen](https://codepen.io/) for code examples (open Console Panel)

## Table of Contents

* [Requirements](#requirements)
* [Installation](#installation)
* [Basics](#basics)
    * [HTTP Request methods](#http-request-methods)
    	* [GET method](#get-method)

## Basics

### HTTP Request methods

#### GET method

XMLHttpRequest API

[[example](https://codepen.io/andriichuk/pen/YzXzwjY?editors=0012)]

```js
let request = new XMLHttpRequest();

request.addEventListener("load", function () {
  console.log(
    JSON.parse(this.responseText)
  );
});

request.open("GET", "https://jsonplaceholder.typicode.com/todos/1");
request.send();
```

Fetch API

[[example](https://codepen.io/andriichuk/pen/zYGYrWq?editors=0012)]

```js
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => response.json())
  .then(json => console.log(json))
```

jQuery Ajax

[[example](https://codepen.io/andriichuk/pen/KKpKVrP?editors=0012)]

```js
$.get('https://jsonplaceholder.typicode.com/todos/1', function (response) {
  console.log(response);
});
```

Axios

[[example](https://codepen.io/andriichuk/pen/RwPwrdJ?editors=0012)]

```js
axios.get('https://jsonplaceholder.typicode.com/todos/1')
  .then(function (response) {
    console.log(response.data);
  });
```

<details><summary>Response</summary>
<p>

```json
Object {
  completed: false,
  id: 1,
  title: "delectus aut autem",
  userId: 1
}
```

</p>
</details>
