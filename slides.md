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
transition: fade


---

<style>
.gradient-heading {
  font-size: 2em;
  font-weight: bold;
  background: linear-gradient(to right, #ff416c, #ff4b2b);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 20px;
}

.section-heading {
  font-size: 1.4em;
  color: #007cf0;
  margin-top: 20px;
  font-weight: 800;
}
</style>

# Welcome to Circle 13 Presentation
This presentation covers our journey so far in Semester 2, with detailed learning highlights.

---

<span class="gradient-heading">Month 1, Week 1 – Deep Dive into Frontend Engineering with JavaScript</span>

<span class="section-heading">1. Foundational Resources for Frontend Development</span>

Before diving fully into JavaScript and React, it’s important to follow some helpful guides and resources:

<v-clicks>

- *Learning How to Learn* (Coursera – 4-week course): Teaches smart ways to understand and retain new concepts.
- *Frontend Handbook* by Cody Lindley (Frontend Masters): Offers a detailed map of the frontend engineering landscape.
- *Refactoring UI*: Explains why some user interfaces (UIs) are better than others, and how to improve your design thinking.

 </v-clicks>

---

<span class="section-heading">2. JavaScript Functions</span>
- Every function **should end with a return statement**. This tells the function what to give back after it's done executing.
- You can return:

  - A single variable  
  - An object 
  - An array
  - Or even another *function* 

- A function *without a return statement* returns undefined by default.

*Example:*
```js
function greet(name) {
  return `Hello, ${name}`;
}

console.log(greet("Israel")); // Output: Hello, Israel
```


---

<span class="section-heading">3. JavaScript Arrays</span>
- Arrays are used to store *multiple values* in one variable.

- Syntax:
```js
let arr = ['a', 'b', 'c'];
```

- Arrays are enclosed in square brackets [] and the items are *comma-separated*.
- Arrays can store any data type (strings, numbers, objects, etc.).

### *Common Array Operations*

<v-clicks>

- push() – adds to the end
- pop() – removes from the end
- shift() – removes from the start
- unshift() – adds to the start
- slice() – copies part of an array
- filter(), find() – used to search and return specific elements

 </v-clicks>

---

<span class="section-heading">4. Spread Operator (...)</span>
- Used to *copy or "spread"* the contents of arrays or objects into a new one.
- Works on any *iterable* data type like:

<v-clicks>

  - Arrays
  - Strings
  - Sets
  - Maps

</v-clicks>

### *Example 1: Spread with Arrays*
```js
let arr = ['a', 'b', 'c'];
let newArr = [...arr];
console.log(newArr); // ['a', 'b', 'c']
```


### *Example 2: Spread with Objects*
```js
let obj = { name: "Ojo", age: 12 };
let copied = { ...obj };
console.log(copied); // { name: "Ojo", age: 12 }
```
---

## *Why Spread?*
To make *clones* or *copies* so you don’t modify the original data.

### *Example: Copy and Modify*
```js
let obj = { name: "Ojo", age: 12 };
let copied = { ...obj, name: "Ola" };
console.log(copied); // { name: "Ola", age: 12 }
```

## *Array Version of Copy and Modify*
```js
let arr = ['a', 'b', 'c'];
let copiedArr = [...arr, 'd'];
console.log(copiedArr); // ['a', 'b', 'c', 'd']
```

---

<span class="section-heading">5. Rest Parameter (...)</span>
- Rest parameters allow a function to accept *any number of arguments* as an array.

### *Example:*
```js
function add(...numbers) {
  console.log(numbers);
}

add(1, 2, 3, 4, 5); 
// Output: [1, 2, 3, 4, 5]
```

---

## *Use Case: Summing Numbers*
```js
function add(...nums) {  
  let result = 0;
  for (let i = 0; i < nums.length; i++) {
    result += nums[i]; //result = result + nums[i];
  }
  return result;
}

console.log(add(10, 50, 80, 70)); // Output: 210
```


### **Shorter Version Using reduce()**
```js
function add(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}

console.log(add(10, 50, 80, 70)); // Output: 210
```

---

## **What does reduce() do?**
- It *reduces* all items in an array to a single value (like adding all numbers together).
- It takes a *callback function* with:
  - a – the accumulated total so far
  - b – the current value
- 0 is the starting value.

---

<span class="section-heading">6. Callback Functions</span>

A *callback function* is a function that is passed as an argument to another function and *is called later (or back)* when needed.

### *Example:*
```js
function callbackEx(message, yesFn, noFn) {
  let result = confirm(message);

  if (result) {
    yesFn();  // If user clicks "OK"
  } else {
    noFn();   // If user clicks "Cancel"
  }
}

callbackEx(
  "Do you have a boyfriend?",
  () => console.log("Yes"),
  () => console.log("No")
);
```

---

## *Explanation:*
- confirm(message) shows a pop-up with “OK” and “Cancel” and returns:
  - true if OK is clicked
  - false if Cancel is clicked
- yesFn and noFn are callback functions.
- Depending on the user's choice, one of the callbacks is executed.

---

<span class="gradient-heading">MONTH 1, WEEK 2 - JavaScript Core Concepts</span>

<span class="section-heading">1. Callbacks (Continued)</span>

A *callback function* is a function passed as an argument to another function and is executed after some operation.

## **Callback with sort()**
```js
const numbers = [40, 100, 1, 5, 25, 10];

// Using a callback function to sort in ascending order
numbers.sort(function(a, b) {
  return a - b;
});

console.log(numbers); // [1, 5, 10, 25, 40, 100]
```

- The callback takes two parameters (a and b) and compares them.
- This callback determines the order by returning a negative (a before b), zero (no change), or positive (b before a).

---

## **Callback with filter()**
```js
const scores = [45, 90, 65, 100, 30];

const passed = scores.filter(function(score) {
  return score >= 50;
});

console.log(passed); // [90, 65, 100]
```


## **Callback with find()**
```js
const users = [
  { name: "Jane", age: 22 },
  { name: "Tom", age: 30 },
];

const result = users.find(function(user) {
  return user.age > 25;
});

console.log(result); // { name: "Tom", age: 30 }
```

---

<span class="section-heading">2. DOM and Event Handlers</span>

- The *DOM (Document Object Model)* is JavaScript’s way of interacting with your HTML.
- JavaScript converts each HTML element into an object.
- You can inspect any element's object form using console.dir(element).

## *Example: onclick and DOM*
```html
<button id="clickMe">Click Me</button>
```

```js
  const btn = document.getElementById("clickMe");

  btn.onclick = function() {
    alert("You clicked me!");
  };

  console.dir(btn); // Shows the full object representation of the button
```
  
- The id="clickMe" gives us direct access to the element using getElementById().
- Event handler onclick triggers a *callback function* when clicked.

---

<span class="section-heading">3. Promises</span>

A *Promise* is an object representing the eventual completion or failure of an asynchronous operation.

## *States of a Promise*
1. *Pending* – initial state
2. *Fulfilled* – operation completed successfully
3. *Rejected* – operation failed

### **Creating a Promise**
```js
const checkWeather = new Promise((resolve, reject) => {
  let isSunny = true;

  if (isSunny) {
    resolve("It’s sunny outside!");
  } else {
    reject("It's raining.");
  }
});
```
---

## **Using .then() and .catch()**
```js
checkWeather
  .then(response => {
    console.log("Success:", response);
  })
  .catch(error => {
    console.log("Failed:", error);
  });
```
- resolve() passes data to .then()
- reject() passes data to .catch()

---

<span class="section-heading">4. Truthy and Falsy Values</span>

In JavaScript, all values are *truthy* except these *falsy* ones:

<v-clicks>

- 0              
- "" (empty string) 
- null           
- undefined   
- NaN 

</v-clicks>

---

<span class="section-heading">5. Fetch and Promises</span>

The fetch() API is used to make network requests and works with promises.

## *Example:*
```js
fetch("https://api.github.com/users/oluwasetemi")
  .then(res => res.json()) // Convert response to JSON
  .then(data => console.log(data)) // Handle the data
  .catch(error => console.log("Error:", error)); // Catch any errors
```

---

<span class="section-heading">6. Async / Await</span>

The async keyword makes a function return a promise, and await is used to pause until a promise resolves.

## *Example:*
```js
async function fetchUser() {
  try {
    const response = await fetch("https://api.github.com/users/oluwasetemi");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.log("Error fetching user:", error);
  }
}
```

- async tells JavaScript to expect asynchronous operations inside.
- await pauses the function until the fetch promise is fulfilled.
- try...catch is used to handle errors gracefully.

---

<span class="section-heading">7. Immediately Invoked Function Expression (IIFE)</span>

An *IIFE* is a function that runs immediately after being defined.

## *Example:*
```js
(function () {
  console.log("This runs immediately!");
})();
```

- Useful for running setup code without polluting the global scope.

---

<span class="section-heading">8. Closures</span>

A *closure* is a function that remembers its outer variables, even after the outer function has finished running.

## *Example:*
```js
function outer() {
  let count = 0;

  return function inner() {
    count++;
    console.log("Count is:", count);
  };
}

const counter = outer();

counter(); // Count is: 1
counter(); // Count is: 2
```

- The inner() function has access to count even after outer() has finished.
- This is because of *closure* — the inner function "closes over" the variables it uses.

---

<span class="gradient-heading">Month 1 - Week 3 Notes: JavaScript (API Calls & Authentication)</span>

## **Recap**
We previously explored:
- Learning how to learn (Coursera)
- Refactoring UI (understanding why one UI is better than another)
- Working with *APIs* using fetch(), *Promises*, async/await.

---

<span class="section-heading">1. API Calls</span>

## **What is an API Call?**
An API (Application Programming Interface) is a way to *communicate with a backend server*. As a frontend engineer:
1. You build a pixel-perfect UI.
2. You connect that UI to external data or functionality using APIs.

## **Two Common API Methods:**
1. *GET* – Retrieve data from a server.
2. *POST* – Send data to a server, often used during signup/login.

---

## *GET Request Example (Using Fetch):*
javascript
fetch('https://api.github.com/users/oluwasetemi')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));


*Explanation:*
- The URL is the *endpoint*.
- .then(res => res.json()) converts the response into a JavaScript-readable format.
- .catch() handles any error if the call fails.

---

### *POST Request Example:*

Imagine you're signing up with *email and password*:
javascript
fetch('https://example.com/signup', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    email: 'test@example.com',
    password: '123456'
  })
})
.then(res => res.json())
.then(data => {
  const token = data.token; // Token returned by server
  console.log('User token:', token);
})
.catch(err => console.error('Signup failed', err));


### *Token Authentication Flow:*
1. You send your email and password to the API (with a POST request).
2. The server checks and sends back a *token* (usually a JWT).
3. You store the token (e.g., in localStorage).
4. For subsequent requests, you add the token to the *Authorization header* to stay logged in.

javascript
fetch('https://example.com/profile', {
  method: 'GET',
  headers: {
    'Authorization': `Bearer ${yourToken}`
  }
})


---

### *Understanding Tokens (JWT - JSON Web Tokens)*

- JWTs are encrypted strings that store user identity details.
- They look like this: eyJhbGciOiJIUzI1NiIsInR...
- You can paste your token into:
  - *[jwt.io](https://jwt.io)* – Decodes JWT into readable info.
  - *[token.dev](https://token.dev)* – Shows expiry, payload, header, etc.

### *Token Sections:*
- *Header* – Specifies the algorithm used.
- *Payload* – Contains user info (like ID, role).
- *Signature* – A secure hash that validates the token.

---

### *Encryption vs Decryption*
- *Encryption* is turning readable data into a coded format.
- *Decryption* is converting it back to readable format.
- JWTs are encrypted to protect user identity.

---

## *Tools to Test APIs*

### *1. Postman*
- A visual tool to test GET, POST, PUT, DELETE requests.
- You can:
  - Paste an endpoint URL
  - Choose request type (GET/POST)
  - Add headers (e.g., Authorization)
  - Add body content (e.g., JSON payload)

#### *Postman Usage Example:*
- URL: https://example.com/login
- Method: POST
- Body (JSON):
json
{
  "email": "test@example.com",
  "password": "123456"
}

- Click "Send"
- View response (e.g., token)

---

### *2. JSON Server (Mock Backend)*

If you don’t have a backend developer, you can create a *fake API* using JSON Server.

#### *Setup Steps:*
1. Install JSON Server:
bash
npm install -g json-server


2. Create a db.json file:
json
{
  "todos": [
    { "id": 1, "task": "Learn JavaScript", "completed": false }
  ]
}


3. Start the server:
bash
json-server --watch db.json


4. Use it like a real API:
- GET todos: http://localhost:3000/todos
- POST new todo:
javascript
fetch('http://localhost:3000/todos', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    task: 'Complete API lesson',
    completed: false
  })
})


---

### *Summary*
- *GET* = Fetch data
- *POST* = Send data
- *Tokens* help with user authentication
- Use tools like *Postman* and *JSON Server* for testing APIs
- Tokens can be decoded using *jwt.io* or *token.dev*
- JSON Server helps simulate backend API for learning or frontend testing

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
   







 


