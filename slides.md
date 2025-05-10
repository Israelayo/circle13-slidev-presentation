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

.team-heading{
  font-size: 2rem;
  font-weight: 700;
  text-transform: uppercase;
  color: #1f2937;
  margin-bottom: 0.5rem;
  border-bottom: 2px solid #4f46e5; 
  display: inline-block;
  padding-bottom: 4px;
  letter-spacing: 1px;
}
  

.team-names{
  font-size: 1.8rem;
  font-weight: 600;
  color: #4f46e5;
  margin-top: 1rem;
  letter-spacing: 0.5px;
}

.thank-you {
    font-size: 3rem;
    font-weight: bold;
    text-align: center;
    color: #4f46e5; 
    margin-top: 4rem;
    text-shadow: 1px 1px 5px rgba(0, 0, 0, 0.1);
    letter-spacing: 2px;
  }
</style>

# Welcome to Circle 13 Presentation
This presentation covers our journey so far in Semester 2, with detailed learning highlights.

---

<span class="team-heading">Team Members</span>

<span class="team-names">1. Israel Olubode</span>

<span class="team-names">2. ⁠Mercy Gatwiri</span>

<span class="team-names">3. ⁠Arowolo Mutmahinat Feyisara</span>

<span class="team-names">4. ⁠Yakubu Ibrahim Endurance</span>

<span class="team-names">5. ⁠Flora Nwakpa</span>

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

<span class="gradient-heading">Month 1 - Week 3: JavaScript (API Calls & Authentication)</span>

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
```js
fetch('https://api.github.com/users/oluwasetemi')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

*Explanation:*
- The URL is the *endpoint*.
- .then(res => res.json()) converts the response into a JavaScript-readable format.
- .catch() handles any error if the call fails.

---

## *POST Request Example:*

Imagine you're signing up with *email and password*:
```js
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
```

---

## *Token Authentication Flow:*
1. You send your email and password to the API (with a POST request).
2. The server checks and sends back a *token* (usually a JWT).
3. You store the token (e.g., in localStorage).
4. For subsequent requests, you add the token to the *Authorization header* to stay logged in.

```js
fetch('https://example.com/profile', {
  method: 'GET',
  headers: {
    'Authorization': `Bearer ${yourToken}`
  }
})
```

---

<span class="section-heading">2. Understanding Tokens (JWT - JSON Web Tokens)</span>

- JWTs are encrypted strings that store user identity details.
- They look like this: *eyJhbGciOiJIUzI1NiIsInR...*
- You can paste your token into:
  - *[jwt.io](https://jwt.io)* – Decodes JWT into readable info.
  - *[token.dev](https://token.dev)* – Shows expiry, payload, header, etc.

## *Token Sections:*
- *Header* – Specifies the algorithm used.
- *Payload* – Contains user info (like ID, role).
- *Signature* – A secure hash that validates the token.

---

<span class="section-heading">3. Encryption vs Decryption</span>
- *Encryption* is turning readable data into a coded format.
- *Decryption* is converting it back to readable format.
- JWTs are encrypted to protect user identity.

---

## *Tools to Test APIs*

### **1. Postman**
- A visual tool to test GET, POST, PUT, DELETE requests.
- You can:

<v-clicks>

  - Paste an endpoint URL
  - Choose request type (GET/POST)
  - Add headers (e.g., Authorization)
  - Add body content (e.g., JSON payload)

</v-clicks>

---

## **Postman Usage Example:**
- URL: https://example.com/login
- Method: POST
- Body (JSON):
```js
{
  "email": "test@example.com",
  "password": "123456"
}
```

- Click "Send"
- View response (e.g., token)

---

### **2. JSON Server (Mock Backend)**

If you don’t have a backend developer, you can create a *fake API* using JSON Server.

#### *Setup Steps:*
1. Install JSON Server:
```bash
npm install -g json-server
```

2. Create a db.json file:
```json
{
  "todos": [
    { "id": 1, "task": "Learn JavaScript", "completed": false }
  ]
}
```


3. Start the server:
```bash
json-server --watch db.json
```

---

4. Use it like a real API:
- GET todos: http://localhost:3000/todos
- POST new todo:
```js
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
```

---

## **Summary**
- *GET* = Fetch data
- *POST* = Send data
- *Tokens* help with user authentication
- Use tools like *Postman* and *JSON Server* for testing APIs
- Tokens can be decoded using *jwt.io* or *token.dev*
- JSON Server helps simulate backend API for learning or frontend testing

---

<span class="gradient-heading">Month 1 - Week 4: DOM, Events, and JavaScript Core Concepts</span>

## **Learning Reminder**

<v-clicks>

- Continue watching “Learning How to Learn” videos.
- Core JavaScript is foundational before diving into React.

</v-clicks>

---

<span class="section-heading">JavaScript Execution with HTML: The defer Attribute</span>

## **What is defer?**
When adding a script tag in HTML:

```html
<script src="script.js" defer></script>
```

<v-clicks>

- **defer** tells the browser to load the script after the HTML is fully parsed.
- Prevents blocking page rendering.
- Best used when script manipulates DOM elements.

</v-clicks>

---

## **Event Timing:**
- DOMContentLoaded: Fired when the initial HTML document is completely loaded and parsed (before images/styles).
- load: Fired when the whole page (including images, styles, etc.) is fully loaded.

## **Event Handling Methods**

### *1. HTML Attribute Method:*
```html
<button onclick="sayHello()">Click Me</button>

<script>
  function sayHello() {
    alert("Hello from HTML attribute!");
  }
</script>
```

---

### *2. DOM Property Method:*
```html
<button id="btn">Click Me</button>

<script>
  const btn = document.getElementById('btn');
  btn.onclick = function () {
    alert("Hello from DOM property!");
  };
</script>
```

---

### *3. addEventListener Method (Preferred):*
```html
<button id="btn">Click Me</button>

<script>
  const btn = document.getElementById('btn');
  btn.addEventListener('click', () => {
    alert("Hello from addEventListener!");
  });
</script>
```

---

<span class="section-heading">The Big Four: window, DOM, CSSOM, and BOM</span>

## **1. window**
- Global object in the browser.
- Represents the browser window/tab.
- Contains document, console, alert, etc.

## **2. DOM (Document Object Model)**
- Represents HTML elements as *JavaScript objects*.
- Tree-like structure.
- Everything you see on a webpage is part of the document.

---

## **3. CSSOM (CSS Object Model)**
- JavaScript representation of CSS styles.
- Allows reading/changing styles dynamically.

## **4. BOM (Browser Object Model)**
- Provides methods to interact with the browser (outside the document).
- Includes window, navigator, location, history, alert, etc.

---

<span class="section-heading">DOM Tree and Navigation</span>

## **DOM Tree**
A nested tree-like structure representing HTML elements:
```html
<html>
  <body>
    <div>
      <p>Hello</p>
    </div>
  </body>
</html>
```

## **Accessing DOM Elements**
```js
document.getElementById('id');
document.querySelector('.class');
document.getElementsByTagName('p');
```

---

## **DOM Tree Navigation**
- parentNode – Go to the parent element.
- childNodes – Get child elements (includes text nodes).
- firstChild / lastChild
- nextSibling / previousSibling

---

## **DOM Node Properties**

### *Three Key Node Properties:*
- nodeType: Number representing the type of node (1 = element, 3 = text)
- nodeName: Name of the node (e.g. DIV, P, TEXT)
- nodeValue: Text content if it's a text node

```js
const node = document.getElementById('demo');
console.log(node.nodeType);   // 1
console.log(node.nodeName);   // DIV
console.log(node.nodeValue);  // null
```

---

## *NodeList vs HTMLCollection*

### *NodeList*
- Returned by querySelectorAll.
- Can use .forEach().
- Static (does not update with changes in DOM).

### *HTMLCollection*
- Returned by getElementsByClassName, etc.
- Live collection (updates when DOM changes).
- Cannot use .forEach() directly.

---

## **Modifying the DOM**

### *Create New Elements:*
```js
const newDiv = document.createElement('div');
newDiv.textContent = "Hello!";
document.body.appendChild(newDiv);
```

### *Change Style:*
```js
newDiv.style.color = "blue";
newDiv.style.backgroundColor = "lightgrey";
```

### *Change Class:*
```js
newDiv.classList.add('highlight');
newDiv.classList.remove('highlight');
```

---

## **Bonus: Using HTML in JS**
```js
const container = document.getElementById('app');
container.innerHTML = "<h1>Welcome to DOM!</h1>";
```

> Use innerHTML carefully to avoid XSS (Cross-Site Scripting) issues.

---

## **Summary:**
- Use defer to delay script execution until HTML is ready.
- Three event attachment methods: inline, DOM property, and addEventListener.
- DOM is the backbone of web manipulation.
- CSSOM allows styling control.
- BOM provides interaction with the browser environment.
- Learn to navigate and manipulate the DOM tree.
- NodeList vs HTMLCollection – know the difference for iteration and updates.

---

<span class="gradient-heading">Month 2, Week 1 – DOM Searching, Manipulation, and JavaScript Events</span>

<span class="section-heading">1. DOM Searching and Live Demo Lesson</span>

We started with a short live tutorial to reinforce how to search the DOM. The goal was to select an element with the ID of app.

## **Task:**
*Find the element with ID app and assign it to a variable named element.*

```javascript
// Using querySelector
const element = document.querySelector("#app");

// Using getElementById
const element = document.getElementById("app");
```

You can also access the element directly in the browser using just:
```javascript
app // works because IDs can be used as global variables in the browser environment
```

---

## **Manipulating the Element**
After selecting the element, you can change its styles or content.

```javascript
element.style.color = "red"; // changes the text color
element.style.fontSize = "24px"; // increases font size
```

---

<span class="section-heading">2. Changing Inner HTML Content</span>

You can update the content using innerHTML:

```javascript
element.innerHTML = "<div>Hello World, Circle 13 just updated this.</div>";
```

This replaces the current content inside the element with a new div.

---

<span class="section-heading">3. Adding New Elements (Creating + Inserting)</span>

You can create elements using JavaScript like this:

```javascript
const newElement = document.createElement("h1");
const textContent = document.createTextNode("Hello World, this is Circle 13");

newElement.appendChild(textContent);
element.appendChild(newElement); // Adds the new h1 into #app from our previous example
```

## *Explanation:*
- createElement("h1") makes a new h1 tag.
- createTextNode(...) creates text inside the tag.
- appendChild(...) attaches the text to the h1 and then attaches the h1 to the parent #app.

---

<span class="section-heading">4. Placing Elements Before, After, Inside</span>

## **Insert Methods:**

```javascript
element.prepend(newElement); // Adds at the start of the element
element.append(newElement); // Adds at the end (similar to appendChild)

element.before(newElement); // Inserts before the element (sibling)
element.after(newElement);  // Inserts after the element (sibling)
```

## *insertAdjacent... Methods*
```javascript
element.insertAdjacentHTML("beforebegin", "<p>Paragraph</p>");
element.insertAdjacentHTML("afterbegin", "<p>Paragraph</p>");
element.insertAdjacentHTML("beforeend", "<p>Paragraph</p>");
element.insertAdjacentHTML("afterend", "<p>Paragraph</p>");
```
This gives you more control over where you insert HTML around your target element without replacing the element itself.

---

<span class="section-heading">5. Creating Comments and Removing Elements</span>

## *Add a Comment in HTML*

```javascript
const comment = document.createComment("This is a comment");
element.appendChild(comment);
```

## *Removing an Element*
```javascript
element.remove(); // Be cautious, this permanently removes the element
```

## *Replacing a Child*
```javascript
const replacement = document.createElement("p");
replacement.textContent = "Replacement content";
element.replaceChild(replacement, element.firstChild); // Replaces the first child
```

---

<span class="section-heading">6. Example on Updating innerHTML on Click</span>

*Goal:* Every time a button is clicked, update the counter.

```html
<button id="clickBtn">Click me</button>
<div id="counter">0</div>
```

```javascript
let count = 0;
const button = document.getElementById("clickBtn");
const counter = document.getElementById("counter");

button.addEventListener("click", () => {
  count++;
  counter.innerHTML = count;
});
```

---

<span class="section-heading">7. Starting React Projects with Vite</span>

Instead of using Create React App, the instructor recommended using:

```bash
npm create vite@latest
```

This gives faster setup and better performance.

---

<span class="section-heading">8. Using Bolt.new</span>

- A tool for instantly creating full-stack projects.
- Can be used to build apps like a To-Do app without complicated setup.
- Very beginner-friendly and helpful for practice.

---

<span class="section-heading">9. JavaScript Events – Quick Recap</span>

```javascript
element.addEventListener(eventType, handler, options);
```

- eventType: e.g., "click", "mouseover"
- handler: the function to run when the event happens
- options: e.g., { once: true, capture: false }

## **Common options Explained Simply:**

- once: listener runs just once.
- capture: set to true if you want the event to run during the capturing phase.
- passive: says you won’t call preventDefault() (helps with performance).
- signal: used with AbortController to remove listeners.

---

<span class="section-heading">10. AbortSignal in Async Operations</span>

Helps stop things like fetch requests or event listeners.

```javascript
const controller = new AbortController();

button.addEventListener("click", handler, {
  signal: controller.signal,
});

// Later you can stop the listener
controller.abort();
```

---

<span class="section-heading">11. Event Phases – Bubbling vs Capturing</span>

*Capturing phase:* event moves *from parent to child*  
*Bubbling phase:* event moves *from child to parent* (this is the default)

```javascript
parent.addEventListener("click", handler, true); // Capturing
child.addEventListener("click", handler); // Bubbling
```

## *Useful Event Properties*
- event.target: The actual element clicked.
- event.currentTarget: The element currently handling the event.
- event.stopPropagation(): Stops the event from bubbling or capturing further.
- event.stopImmediatePropagation(): Stops all other handlers from running.

---

<span class="section-heading">12. Event Delegation</span>

Instead of adding event listeners to each child, we can add *one* to their parent.

```html
<ul id="list">
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

```javascript
document.getElementById("list").addEventListener("click", function (e) {
  if (e.target.tagName === "LI") {
    alert("Clicked: " + e.target.textContent);
  }
});
```

*Why use this?*
- Saves memory
- Works well for dynamic content (new li added later still works)

---

<span class="gradient-heading">Month 2 - Week 2 Notes: Building a todo list with HTML ,CSS and Javascript</span>

 ## Form Submission Event and Methods
It lets users send data to a server for processing Javascript handles this by:
- Using the submit Event
- Using the form.submit () method
Forms are submitted by:

<v-clicks> 

-Clicking the submit button

-Pressing enter while focused on an input field

</v-clicks>

---

## **Features in a To- do App**
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

## **Delete Todo**
```js
    function add() {
      let li = document.createElement("li");
      li.textContent = document.getElementById("task").value;
      li.onclick = () => li.remove(); // Click task to delete
      document.getElementById("list").appendChild(li);
      document.getElementById("task").value = "";
    }
```

---

<span class="gradient-heading">Month 2 - Week 3 & Extra class 1: Modules & Bundlers</span>

Modules help to import and export different sections of code from different files into other files.

## **Benefits of modules**
- Improve code organization
- Easier maintainance and debugging
- Reusability across projects

---

<span class="section-heading">Bundlers</span>

A bundler is a dev tool that takes multiple Javascript files and combines them into a single file. improving load speed and efficiency for web applications.

## *Popular bundlers*
1. Webpack
2. Vite
3. Parcel
4. Rollup

---

<span class="section-heading">Imports and Exports</span>

1. **Named export**

```js 
// math.js
export function add(a, b) {
  return a + b;
}
```

2. **Renamed Export**

It lets you change the name of an import or export when needed.

3. **Dynamic Import**

It lets you load a module when its needed.

---

<span class="section-heading">ECMA Script Modules (ESM)</span>

It is the standardized module system for Javascript 

It is supported in modern browsers and Node.js

## *How to enable ESM in node.js*
Use the .mjs file extension or

add "type":"module" in package.json

---

<span class="section-heading">Package .json</span>

It defines your project details, depedencies and scripts

  ## *It's Uses*
- Track and install packages
- Run Scripts
- Share projection configuration

---

<span class="gradient-heading">Month 2 - Week 4: From Pure JavaScript to React-Like Thinking</span>

<span class="section-heading">1. Transitioning from Pure JavaScript to a React-like Approach</span>

In this session, we mimicked how React components work by creating a utility function in JavaScript called makeElem. It helps generate HTML elements with properties, event listeners, and children—just like JSX in React.

## **makeElem Function Breakdown**

```javascript
const makeElem = (elemType, props, children) => {
  const elem = document.createElement(elemType);

  if (props) {
    for (const [key, value] of Object.entries(props)) {
      if (key.startsWith("on")) {
        // For example: onClick, onDblClick
        const eventType = key.slice(2).toLowerCase();
        elem.addEventListener(eventType, value, { once: true }); // 'once: true' means the event will only run once
      } else {
        elem[key] = value;
      }
    }
  }

  if (children) {
    elem.prepend(...children); // Adds child elements or text
  }

  return elem;
};
```

---

<span class="section-heading">2. Building a Simple Todo Component</span>

Let’s use makeElem() to build a simple todo item with a span for text and a button to remove it.

```javascript
const createTodo = (todo) => {
  const text = makeElem("span", {
    style: "flex: 1",
    ondblclick: () => alert("edit")
  }, [todo.text]);

  const x = makeElem("button", {
    onclick: () => alert("remove")
  }, ["x"]);

  const item = makeElem("li", {
    style: "display: flex;"
  }, [text, x]);

  return item;
};
```

## *Explanation:*
- We're mimicking a component by using a function that returns a full element (li) made up of other nested elements (span, button).
- This shows how you can *compose UI* using *functions*, just like in React.

---

<span class="section-heading">3. Additional Notes and Concepts</span>

#### a. **How to View an Element Like an Object**
Use console.dir(element) instead of console.log.  
This lets you explore the DOM element's properties like an object.

#### b. **Turning Objects to Arrays (and Back)**

```javascript
const obj = { name: "Circle 13", level: "Month 2" };

// Convert object to array
const entries = Object.entries(obj); 
console.log(entries); // [['name', 'Circle 13'], ['level', 'Month 2']]

// Convert back to object
const backToObj = Object.fromEntries(entries);
console.log(backToObj); // { name: "Circle 13", level: "Month 2" }
```

---

#### c. **Understanding prepend**

You can insert elements or text at the beginning of another element:

```javascript
const container = document.querySelector("#container");
const newParagraph = document.createElement("p");
newParagraph.textContent = "This is prepended";

container.prepend(newParagraph); // inserts at the top of container
```

#### d. **Events with { once: true }**

This ensures the event listener only fires once:

```javascript
button.addEventListener("click", () => {
  console.log("Clicked once!");
}, { once: true });
```

---

## **Summary**

- The makeElem function is a helpful way to build HTML elements with JavaScript in a more React-like, reusable style.
- DOM elements can be treated like objects (using dot notation).
- We can explore DOM structure better using console.dir().
- JavaScript lets us work flexibly with elements, props, and events just like React does under the hood.
- Event listeners are best added with addEventListener, and { once: true } ensures they only fire once.
- Object.entries() and Object.fromEntries() help in converting between objects and arrays.

---

<span class="gradient-heading">Month 3 - Week 1: Understanding JSX & Embedding JavaScript in JSX</span>

## **What is JSX?**
- *JSX* stands for *JavaScript XML*.
- It allows writing HTML-like syntax directly inside JavaScript (used mainly in React).
- Although it looks like HTML, *JSX is not HTML*—it’s syntactic sugar for React.createElement().

```jsx
const element = <h1>Hello</h1>;
// Becomes:
React.createElement("h1", null, "Hello")
```

---

<span class="section-heading">Rules of JSX</span>

### *1. JSX Must Have a Single Parent Element*

```jsx
// ❌ Invalid
return (
  <h1>Hello</h1>
  <p>World</p>
);

// ✅ Valid using <div>
return (
  <div>
    <h1>Hello</h1>
    <p>World</p>
  </div>
);

// ✅ Cleaner with React Fragment
return (
  <>
    <h1>Hello</h1>
    <p>World</p>
  </>
);
```

---

### **2. Use className Instead of class**

```jsx
// ✅ Correct in JSX
<div className="container">Hello</div>
```

---

### **3. Use CamelCase for Attributes and Event Handlers**

```jsx
<input type="text" onChange={handleChange} />
<label htmlFor="username">Username</label>
```

---

### **4. Self-Closing Tags Must Be Closed Properly**

```jsx
// ✅ Correct
<img src="logo.png" alt="Logo" />
<br />
```

---

### **5. JavaScript Expressions Must Be in {}**

```jsx
const name = "Feyisara";

// ✅ Correct
<h1>Hello, {name}</h1>

// ❌ Incorrect
{ if (true) console.log("Hey") }
```

---

### **6. JavaScript Statements Must Go Outside JSX**

```jsx
function Greeting() {
  const isLoggedIn = true;
  const message = isLoggedIn ? "Welcome back!" : "Please log in.";

  return <h1>{message}</h1>;
}
```

---

<span class="section-heading">Embedding JavaScript in JSX</span>

You can embed *JavaScript expressions* inside {}. But remember: **statements like if, for, while aren’t allowed inside JSX directly.**

## *1. Embedding Variables*

```jsx
const name = "Feyisara";
return <h2>Hello, {name}!</h2>;
```

---

### **2. Embedding Function Calls**

```jsx
function greet(user) {
  return `Welcome, ${user}`;
}
return <p>{greet("Feyisara")}</p>;
```

### **3. Embedding Math**

```jsx
const a = 10;
const b = 5;
return <p>The sum is: {a + b}</p>;
```

---

### **4. Conditional Rendering with Ternary Operator**

```jsx
const isOnline = true;
return <p>{isOnline ? "You are online" : "You are offline"}</p>;
```

### **5. Conditional Rendering with &&**

```jsx
const hasNotifications = true;
return (
  <div>
    <h2>Dashboard</h2>
    {hasNotifications && <p>You have new messages</p>}
  </div>
);
```

---

### **6. Rendering Lists with .map()**

```jsx
const fruits = ["Apple", "Banana", "Mango"];
return (
  <ul>
    {fruits.map((fruit, index) => (
      <li key={index}>{fruit}</li>
    ))}
  </ul>
);
```

### **7. Inline Styles as JS Objects**

```jsx
const styles = {
  color: "blue",
  fontSize: "18px"
};

return <h2 style={styles}>Styled Text</h2>;
```

---

<span class="gradient-heading">Summary on Refactoring UI – Key Principles for Better Design</span>

<span class="section-heading">1. Start from Scratch – Focus on What Matters First</span>

- *Design features first, not layouts*: Start with what users will interact with (e.g., a form, button, or list) rather than empty containers like navbars.
  - Example: Build a working search bar before designing a fancy header.

- *Avoid obsessing over details early*: Use simple sketches or wireframes to plan layout quickly. Tools like pen and paper or Figma’s low-fidelity mode work well.

- *Iterate in cycles*: Don’t try to perfect your design in one go. Build → test → improve.

- *Prioritize MVP (Minimal Viable Product)*: Only include essential features. Fancy animations or dropdowns can come later.

- *Give your design a personality*: Choose fonts, colors, and tone of voice intentionally. These give your design identity.

---

<span class="section-heading">2. Visual Hierarchy is Key</span>

- *Not everything should stand out*: Use font weight, color contrast, and size to guide the user's attention.
  - Example: Make the “Submit” button bold and colored, but keep helper text light and small.

- *Reduce noise around main actions*: Give breathing space around important elements.

- *Use fewer labels*: If the context is obvious, labels may be redundant.
  - Example: A calendar icon next to a date doesn’t need a “Date” label.

---

<span class="section-heading">3. Layout and Spacing</span>

- *Start with more whitespace than necessary*: It's easier to reduce later.
- *Use a spacing system*: Stick to a scale like 4px, 8px, 16px, 32px. Avoid arbitrary values like 13px.
- *Don’t fill the screen for the sake of it*: Sometimes a centered, narrow layout is more readable.
- *Use grid systems wisely*: Don’t force everything into columns. If an element looks better with a fixed width, go with that.
- *Avoid relative sizing traps*: Don’t let everything resize with screen width. Some items (e.g., buttons) should have fixed sizes for consistency.

---

<span class="section-heading">4. Typography That Works</span>

- *Define a font scale*: Limit yourself to a few font sizes (e.g., 12px, 16px, 24px, 32px).
- *Use legible fonts*: Google Fonts like Inter, Roboto, or Lato are great. Avoid overly stylized fonts.
- *Ideal line length = 45 to 75 characters*: Helps reading comfort.
- *Text alignment matters*: Most text should be left-aligned. For multiple font sizes, align by baseline, not middle.
- *Line height (spacing between lines)*:
  - Big text = tighter spacing
  - Small text = looser spacing

---  

<span class="section-heading">5. Working with Color</span>

- *Prefer HSL over Hex*: HSL (Hue, Saturation, Lightness) lets you tweak shades more easily.
  - Example: To make a lighter version of a blue, just increase the lightness.
- *Use more color shades than you think*: Especially greys. Don’t rely on just black and white.
- *Define your palette early*: Create 5–7 shades for each primary color. Reuse them for consistency.
- *Maintain saturation*: Light colors shouldn’t always be dull. Keep them vivid by increasing saturation.

---

# <span class="thank-you">Thank You!</span>
