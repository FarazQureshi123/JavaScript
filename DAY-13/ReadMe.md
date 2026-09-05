# JavaScript Notes: `for` Loop Fundamentals

Welcome to the **`for` Loop** module! This guide covers how loops work in JavaScript, breaking down basic iteration, custom step increments, nested loops, practical math applications, and reverse counting.

---

## 📌 What is a Loop?

A **loop** allows you to execute a block of code repeatedly as long as a specified condition evaluates to `true`. Loops eliminate code duplication and make handling repetitive tasks straightforward.

---

## ⚙️ Anatomy of a `for` Loop

The `for` loop consists of three main expressions separated by semicolons:

```javascript
for (initialization; condition; increment/decrement) {
    // Code to execute repeatedly
}

Initialization: Executed once before the loop begins (let i = 1).

Condition: Checked before every iteration. If true, the loop runs; if false, execution halts.

Increment / Decrement: Updates the loop variable after each block execution (i++).

📚 Core Patterns Learned
1. Basic Iteration
Instead of manually repeating statements, a loop automates sequential counting.

JavaScript
// Logs numbers 1 through 10
for (let i = 1; i <= 10; i++) {
    console.log(i);
}

2. Custom Step Increments
You aren't restricted to incrementing by 1. You can modify the step value using compound assignment operators like +=.

JavaScript
let a = 1;
for (a; a <= 10; a += 3) {
    console.log(a); // Logs: 1, 4, 7, 10
}

3. Nested Loops
A nested loop places one loop inside another. For every single iteration of the outer loop, the inner loop executes completely.

JavaScript
for (let i = 0; i <= 10; i++) {
    for (let j = 0; j <= 5; j++) {
        console.log("j:", j); // Runs 6 times (0 to 5) for every i loop iteration
    }
    console.log("_______");
}

4. Mathematical Calculations (Multiplication Tables)
Loops excel at generating mathematical tables dynamically using expressions.

JavaScript
// Prints the multiplication table of 17
for (let a = 1; a <= 10; a++) {
    console.log(a * 17); // Logs: 17, 34, 51 ... 170
}
5. Reverse Counting (Decrementing Loop)
By initializing with a high start value, checking for a minimum bound, and using a decrement operator (i--), you can loop backwards.

JavaScript
// Countdown from 10 down to 0
for (let i = 10; i >= 0; i--) {
    console.log(i); // Logs: 10, 9, 8 ... 0
}
💡 Types of Loops in JavaScript
for loop: Best when the exact number of iterations is known in advance.

while loop: Repeats code as long as a specified condition remains true.

do...while loop: Ensures the code block executes at least once before testing the condition.

for...of loop: Iterates over iterable objects like Arrays and Strings.

for...in loop: Iterates over enumerable properties of an Object.