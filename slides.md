---
theme: seriph
background: https://cover.sli.dev
title: Circle 13 - Semester Progress (Sample)
info: |
  ## AltSchool Africa - Frontend Track
  Summary of our learning journey so far.

class: text-center

drawings:
  persist: false
transition: slide-left

---

# Welcome to Circle 13 Presentation
This presentation covers our journey so far in Semester 2, with detailed learning highlights.

---

# Month 1 Week 1: Journey Continues with Frontend Engineering

## Key Introductions

- Deeper Dive into the *Frontend Engineering*
- Tools and resources recommended:
  - Learning How to Learn course on Coursera
  - Frontend Handbook by Cody Lindley
  - Refactoring UI by Tailwind creators

These laid the foundation for how we approach coding, design decisions, and learning strategies this semester.

---

# Deep Dive into JavaScript Basics

Before jumping into React, we began a deeper dive into JavaScript concepts.

## Functions and the return Statement

- Every function should return a result.
- Without return, the function returns undefined.
- You can return:
  - A single value
  - An object
  - An array
  - Or even another function!

---

# Arrays in JavaScript

## Declaration

```js
const arr = ['a', 'b', 'c'];
```

	•	Arrays store multiple values in a single variable.
	•	Use [] brackets and comma-separated values to easily identify Arrays.

Useful Array Methods include:
	
  .push(), .pop(), .slice(), .filter(), .find(), etc.

---

# Spread Operator

The ... spread operator expands or copies the contents of an array or object.

## Example with Array:
```js
const arr = ['a', 'b', 'c'];
const copy = [...arr]; // spreads values into a new array
```

## Example with Object:
```js
const obj = { name: 'Ojo', age: 12 };
const copy = { ...obj, name: 'Ola' };
```

	•	It clones and allows overriding values during the copy.

---

# Rest Parameters

The rest syntax allows us to accept any number of arguments as an array.

```js
function add(...numbers) {
  return numbers.reduce((a, b) => a + b, 0);
}

add(10, 50, 80, 70); // 210
```

How does reduce() work? 
It takes a callback and a starting value and adds each value in the array to a running total.

```js
(a, b) => a + b
```

This means: keep adding each b to a.

---

# Callback Functions

## What is a Callback?

A callback is a function passed into another function to run later.

Example:

```js

function ask(question, yesFn, noFn) {
  const result = confirm(question);
  if (result) yesFn();
  else noFn();
}

ask(
  "Do you have a boyfriend?",
  () => console.log("Yes"),
  () => console.log("No")
);

```

	If you click OK, the yesFn() runs. If Cancel, noFn() runs.
This is useful for user input and asynchronous code like APIs and event handlers.

---

# Week 1 Summary
	We strengthened our foundation in:
	•	JavaScript Functions
	•	Arrays and Operators
	•	Spread & Rest syntax
	•	Callback functions

	Week 1 gave us the building blocks we’ll need for more advanced topics.

---


# Month 1 Week 2: From Callbacks to Promises

## Revisiting Callback Functions

We continued from last week’s topic on callbacks.

### Callback with sort()

```js
const numbers = [4, 2, 9, 1];
numbers.sort((a, b) => a - b); // ascending sort
```

	sort() method uses a callback that takes two parameters 
  It then compares each pair to determine order.



### Callback with filter() and find()
```js
const ages = [12, 18, 20, 15, 30];

const adults = ages.filter(age => age >= 18);
const firstAdult = ages.find(age => age >= 18);
```

The filter() method returns all items that pass the test while find() returns the first item that passes the test.

---

# Working with the DOM
## DOM Overview
	-	JavaScript converts HTML elements into objects called the DOM.
	-	You can inspect DOM objects using console.dir().

Example:
```html
<button id="myBtn">Click Me</button>
```

```js
const btn = document.getElementById("myBtn");
console.dir(btn); // Shows all properties of the button
```

It is important to note that IDs act like powerful hooks and can be used as variables.
 Also, the onclick and addEventListener() expect a callback function.

---

# Promises in JavaScript

## What is a Promise?

A Promise is an object representing the result of an async task.
	-	States: pending, fulfilled, or rejected
	-	Unlike callbacks, we don’t know when the action completes.

### Creating a Promise
```js
const myPromise = new Promise((resolve, reject) => {
  let success = true;
  if (success) resolve("Done!");
  else reject("Failed!");
});
```
---

# Using .then() and .catch()
```js
myPromise
  .then(result => console.log(result))   // logs "Done!"
  .catch(error => console.error(error)); // logs "Failed!"
  ```
	-	.then() handles the resolved value.
	-	.catch() handles errors if the promise fails.

## Using fetch() with Promises
```js

fetch("https://api.github.com/users/oluwasetemi")
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(error => console.error("Error:", error));
  ```

	-	fetch() returns a Promise.
	-	.then() parses the response into JSON.
	-	.catch() captures network or parsing errors.


--- 

# Async & Await

## Making Async Code Easier
```js
async function getUser() {
  try {
    const res = await fetch("https://api.github.com/users/oluwasetemi");
    const data = await res.json();
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}
```

	-	async turns a function into a promise.
	-	await pauses execution until the promise resolves.
	-	try/catch helps handle errors gracefully.

---

# IIFE – Immediately Invoked Function Expression

An IIFE is a function that runs as soon as it’s defined.
```js
(function () {
  console.log("I ran immediately!");
})();
```

	It is wrapped in parentheses and followed by ().

---

# Closures

Closures allow functions to access outer scope variables even after the outer function has finished.

Example:
```js
function outer() {
  let count = 0;
  return function inner() {
    count++;
    console.log(count);
  };
}

const counter = outer();
counter(); // 1
counter(); // 2
```

	- The inner function “remembers” the outer variable count.

---

# Week 2 Summary
	-	Callback functions with sort, filter, and find
	-	DOM and how JS sees elements as objects
	-	Promises and async/await
	-	Error handling with .catch() and try/catch
	-	IIFEs and closures — key to advanced JavaScript behavior

---

# Month 1 Week 3: Making API Calls & Understanding Tokens

## Recap

- Reviewed *Learning How to Learn* and *Refactoring UI*
- Continued building on API usage from Week 2

---

# What Are API Calls?

An *API (Application Programming Interface)* allows frontend apps to talk to a backend server.

- Think of it as asking a waiter (the API) to take your order (a request) to the kitchen (backend), and return your food (a response).

---

# GET vs POST

## GET Request

- Used to *fetch data* from the server.
- Doesn’t send data — just asks for it.

```js
fetch("https://api.example.com/users")
  .then(res => res.json())
  .then(data => console.log(data));
  ```


## POST Request
	-	Used to send data to the server — usually for login, signup, or creating something.
```js
fetch("https://api.example.com/signup", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    email: "olubode@altschool.com",
    password: "password123"
  })
})
.then(res => res.json())
.then(data => console.log(data));
```

	-	In response, the server usually returns a token.

---

# What is a Token?
	-	A token is a unique string that confirms your identity.
	-	It’s like a digital ID card.
	-	After login, you’ll get a token which you’ll send back for future requests.

## Using a Token in Headers

After receiving a token from a POST login/signup request:
```js
fetch("https://api.example.com/user-data", {
  headers: {
    Authorization: Bearer ${token}
  }
});
```

	This tells the backend: “Here’s my identity, now show me my data.”

---

# Checking Tokens with Tools

## jwt.io
Use jwt.io to decode JWT tokens. You can paste your token to see:
	-	Payload (user info)
	-	Expiration time
	-	Encryption type

## token.dev
You can also paste your token into token.dev to easily view:
	-	Expiry
	-	Encoded vs Decoded info
	-	Signature type

---

# Encryption vs Decryption
	-	Encryption = securing data so only someone with a key can read it.
	-	Decryption = using the key to turn it back into readable info.
	Most websites (like Twitter, Gmail) store your session using encrypted tokens.

---

# Using Postman for API Testing

## What is Postman?
	A GUI tool for testing APIs without writing code.

Steps:
	1.	Open Postman
	2.	Set method to POST
	3.	Enter URL (e.g. https://api.example.com/signup)
	4.	Go to Body > choose raw > select JSON
	5.	Enter data:
```js 
{
  "email": "circle13@altschool.com",
  "password": "password123"
}
```

	6.	Hit Send
	7.	View the response — your token!

---

# Using json-server to Fake an API
If you don’t have a backend, you can use json-server to create fake endpoints.

Steps:
	1.	Install:
```js
npm install -g json-server
```

	2.	Create a db.json file:
  ```js

{
  "todos": [
    { "id": 1, "task": "Build UI" },
    { "id": 2, "task": "Call API" }
  ]
}
```

	3.	Run server:
  ```js

json-server --watch db.json
```

	-	Visit: (http://localhost:3000/todos)

You can now use GET, POST, DELETE etc. on this fake API.

---

# Week 3 Summary
	-	Learned how APIs connect frontend and backend
	-	Understood GET vs POST
	-	Handled tokens for authentication
	-	Explored token tools like jwt.io and token.dev
	-	Practiced with Postman and json-server

---

# Month 2 Week 2

 ## Building a todo list with HTML ,CSS and Javascript
 ### Form Submission Event and Methods
It lets users send data to a server for processing Javascript handles this by:
- Using the submit Event
- Using the form.submit () method
Forms are submitted by:
<v-clicks> 

-Clicking the submit button

-Pressing enter while focused on an input field

</v-clicks>

---

## Features in a To- do App
- 1. Update To do 
```js
    function addTask() {
    const input = document.getElementById("taskInput");
    const li = document.createElement("li");

     const span = document.createElement("span");
     span.textContent = input.value;
      span.onclick = () => {
      const newText = prompt("Edit task:", span.textContent);
      if (newText) span.textContent = newText;
       };

      const btn = document.createElement("button");
      btn.textContent = "Remove";
      btn.onclick = () => li.remove();

      li.appendChild(span);
      li.appendChild(btn);
      document.getElementById("taskList").appendChild(li);
      input.value = "";}
```

---

## Delete Todo
```js
    function add() {
      let li = document.createElement("li");
      li.textContent = document.getElementById("task").value;
      li.onclick = () => li.remove(); // Click task to delete
      document.getElementById("list").appendChild(li);
      document.getElementById("task").value = "";
    }
</body>
```

---

# Month 2 Week 4 & Extra class 1

---

## Modules
Modules help to import and export different sections of code from different files into other files.

### Benefits of modules
* Improve code organization
* Easier maintainance and debugging
* Reusability across projects

---

## 2 .Bundlers
A bundler is a dev tool that takes multiple Javascript files and combines them into a single file. improving load speed and efficiency for web applications.

### Popular bundlers
1. Webpack
2. Vite
3. Parcel
4. Rollup

---

## 3. Imports and Exports
(a) Named export

```js 
// math.js
export function add(a, b) {
  return a + b;
}
```

---

(b) Renamed Export

It lets you change the name of an import or export when needed.

(c) Dynamic Import

It lets you load a module when its needed.

---

## 4. ECMA Script Modules (ESM)
It is the standardized module system for Javascript 

It is supported in modern browsers and Node.js

## How to enable ESM in node.js
Use the .mjs file extension or

add "type":"module" in package.json

---

## 5. Package .json
It defines your project details, depedencies and scripts

  ### It's Uses
* Track and install packages
* Run Scripts
* Share projection configuration
   







 


