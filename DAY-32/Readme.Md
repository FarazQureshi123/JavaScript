# Day 32: Function Expressions in JavaScript

Welcome to Day 32 of the JavaScript learning journey! Today's focus is on **Function Expressions**, how they work, how they differ from standard Function Declarations, and key concepts like Hoisting, Named vs. Anonymous Function Expressions, and the Rest Operator (`...`).

---

## 📌 Table of Contents
1. [What is a Function Expression?](#1-what-is-a-function-expression)
2. [Function Declaration vs. Function Expression](#2-function-declaration-vs-function-expression)
3. [Key Differences & Visual Comparison](#3-key-differences--visual-comparison)
4. [Hoisting Behavior](#4-hoisting-behavior)
5. [Named vs. Anonymous Function Expressions](#5-named-vs-anonymous-function-expressions)
6. [Function Properties: `length` & Rest Operator (`...`)](#6-function-properties-length--rest-operator-)
7. [Code Examples & Walkthrough](#7-code-examples--walkthrough)
8. [Summary](#8-summary)

---

## 1. What is a Function Expression?

In JavaScript, a **Function Expression** occurs when you define a function and assign it to a variable (`let`, `const`, or `var`). 

Once assigned, the variable acts as the function itself and is used to invoke/call the function.

```javascript
// Function Expression
const greet = function(name) {
    return `Hello, ${name}!`;
};

// Invoking using the variable name
console.log(greet("Faraz")); // Output: Hello, Faraz!
```

---

## 2. Function Declaration vs. Function Expression

* **Function Declaration:** A standard way of defining a function using the `function` keyword directly followed by the function name. It is hoisted to the top of its scope.
  ```javascript
  function sayHi() {
      console.log("Hi!");
  }
  ```

* **Function Expression:** Creating a function (either named or anonymous) inside an expression, typically assigning it to a variable. It is **not** hoisted as a usable function call.
  ```javascript
  let sayHiExpression = function() {
      console.log("Hi!");
  };
  ```

---

## 3. Key Differences & Visual Comparison

| Feature | Function Declaration | Function Expression |
| :--- | :---: | :---: |
| **Hoisted** | **Yes (fully)** | **No** |
| **Can call before definition** | **Yes** | **No** |
| **Stored in variable** | **No** | **Yes** |
| **Can be anonymous** | **No** | **Yes** |
| **Used in callbacks** | **Rarely** | **Very common** |
| **Preferred in modern JS** | **Less** | **More** |

---

## 4. Hoisting Behavior

**Hoisting** is JavaScript's default behavior of moving declarations to the top of the current scope before code execution.

### Function Declarations (Hoisted Fully)
You can invoke a function declaration *before* its definition in the code:
```javascript
// Works fine!
sayHello(); 

function sayHello() {
    console.log("Hello from Declaration!");
}
```

### Function Expressions (Not Hoisted for Invocation)
If you try to invoke a function expression *before* assigning it to a variable, JavaScript will throw a `ReferenceError` (or `TypeError` depending on `var`/`let`/`const` declaration):
```javascript
// ❌ Uncaught ReferenceError: Cannot access 'fruitExpression' before initialization
fruitExpression("Apple");

let fruitExpression = function(item) {
    console.log(item);
};
```

---

## 5. Named vs. Anonymous Function Expressions

### Anonymous Function Expression
A function expression without a name.
```javascript
let logMessage = function(msg) {
    console.log(msg);
};
```

### Named Function Expression
A function expression with an internal name. The internal name is useful for recursion inside the function scope or debugging stack traces.
```javascript
let fruitExpression = function fruit(item) {
    console.log(item);
};
```

---

## 6. Function Properties: `length` & Rest Operator (`...`)

### The `length` Property
The `.length` property of a function returns the number of **expected formal parameters** declared in its signature.

### The Rest Operator (`...`)
The rest operator collects multiple individual arguments into a single array parameter.
* **Note:** Rest parameters (`...val`) do **not** contribute to the function's `.length` property because they handle dynamic numbers of arguments.

```javascript
let recursionX = function recursion(...val) {
    // Expected formal parameters defined in signature = 0
    console.log(recursion.length); // Output: 0
};

recursionX(10, 20, 30);
```

---

## 7. Code Examples & Walkthrough

Here is the breakdown of the HTML and JavaScript code studied on Day 32:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Function Expression</title>
</head>
<body>
    <h1>Function Expression in JS is when you create a function and assign it to a Variable</h1>

    <script>
        // -------------------------------------------------------------
        // 1. Hoisting Test with Function Expression (Will fail if uncommented)
        // -------------------------------------------------------------
        // fruitExpression("This will throw an error if called before declaration!");

        // -------------------------------------------------------------
        // 2. Named Function Expression
        // -------------------------------------------------------------
        let fruitExpression = function fruit(item) {
            console.log(item);
        };
        fruitExpression("Mango"); // Output: Mango


        // -------------------------------------------------------------
        // 3. Rest Operator & Function Length Property
        // -------------------------------------------------------------
        let recursionX = function recursion(...val) { 
            // 'val' collects all passed arguments into an array.
            // 'recursion.length' checks expected positional parameters (excludes rest parameter).
            console.log("Expected parameters (length):", recursion.length); 
            console.log("Passed arguments (val):", val);
        };

        recursionX(10, 20, 30); 
        // Output:
        // Expected parameters (length): 0
        // Passed arguments (val): [10, 20, 30]
    </script>
</body>
</html>
```

---

## 8. Summary

1. **Assignment:** A function expression involves assigning a function directly to a variable.
2. **No Early Invocation:** Unlike function declarations, function expressions cannot be called before they are defined in code execution.
3. **Modern Practice:** Function expressions (including arrow functions) are preferred in modern JavaScript, especially as callbacks and module exports.
4. **Rest Operator:** `...val` allows functions to accept an arbitrary number of arguments stored as an array.