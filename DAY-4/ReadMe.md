# JavaScript Notes & Code Snippets - Functions

Welcome to the JavaScript Learning Series! This repository section focuses on **Functions in JavaScript**, how they work, their types, and practical examples using HTML event triggers (like button clicks).

---

## 📌 What is a Function?

A **function** is a reusable block of code designed to perform a specific task. Instead of writing the same code repeatedly, you can define a function once and execute (or call) it whenever needed.

### Key Benefits:
- **Code Reusability**: Write code once and use it multiple times.
- **Maintainability**: Makes your code organized, clean, and easier to debug.
- **Modular Design**: Breaks complex problems into smaller, manageable pieces.

---

## 📚 Types of Functions in JavaScript

JavaScript functions are broadly divided into **Built-in Functions** and **User-Defined Functions**.

### 1. Built-in (Predefined) Functions
Provided natively by JavaScript or web browsers. Examples include:
- `alert()` — Displays a popup dialog box.
- `console.log()` — Outputs messages to the developer console.
- `prompt()`, `parseInt()`, `Math.random()`, etc.

### 2. User-Defined Functions
Functions created by developers to perform specific tasks. Common types include:
- **Function Declaration**: Standard function defined using the `function` keyword.
- **Function Expression**: Storing a function inside a variable.
- **Arrow Function (`() => {}`)**: Compact syntax introduced in ES6.
- **Anonymous Function**: A function without a name.
- **Named Function Expression**: A function expression that includes a name.
- **IIFE (Immediately Invoked Function Expression)**: Executes as soon as it is defined.
- **Callback Function**: A function passed as an argument into another function.
- **Constructor Function**: Used with the `new` keyword to instantiate objects.
- **Generator Function**: Functions that can be paused and resumed using `yield`.
- **Async Function**: Returns a Promise and supports `await` for handling asynchronous operations.
- **Method**: A function defined as a property inside an object.

---

Q1. What is a function in JavaScript?

Answer: A function is a self-contained, reusable block of code that executes a specific set of statements when invoked/called.

Q2. How do you create a simple function in JavaScript?

// Function definition
function greet() {
    console.log("Hello, World!");
}

// Function call
greet();


Q3. How do you trigger a JavaScript function on a button click?

you can bind a function to a button using the onclick event attribute in HTML:

<!-- <button onclick="showAlert()">Click Me</button>

<script>
    function showAlert() {
        alert("Button was clicked!");
    }
</script> -->

Q4. What is Hoisting in Functions?

 Function declarations in JavaScript are hoisted to the top of their scope before code execution. This means you can call a declared function before defining it in your script.

 sayHello(); // Works fine because of hoisting!

function sayHello() {
    console.log("Hello!");
}

Q5. What is the difference between Function Declaration and Function Expression?

Function Declaration: Standard syntax, fully hoisted.
function add(a, b) { return a + b; }

Function Expression: Function assigned to a variable, not hoisted in the same way.

const add = function(a, b) { return a + b; };