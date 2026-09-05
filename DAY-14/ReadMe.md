# Day 14: JavaScript `while` Loop Mechanics & Patterns

Welcome to Day 14! Today's focus is on the **`while` loop**—a fundamental control flow structure used to repeat execution as long as a specified condition remains `true`.

---

## 📌 What is a `while` Loop?

Unlike a `for` loop, which typically combines initialization, condition, and increment/decrement into a single line, a `while` loop separates these steps. It checks the condition **before** executing the code block.

```javascript
while (condition) {
    // Code block to execute
    // Update expression (increment/decrement)
}


📚 Code Analysis & Key Concepts
1. Standard Forward Iteration (0 to 10)
console.log before increment: Logs 0 through 10.

Increment before console.log: Logs 1 through 11 because the value updates before printing.

JavaScript
// Pattern A: Log then Increment
let i = 0;
while (i <= 10) {
    console.log(i); // Logs 0 to 10
    i++;
}

// Pattern B: Increment then Log
let i = 0;
while (i <= 10) {
    i++;
    console.log(i); // Logs 1 to 11
}
2. Event-Driven Loops with Dynamic Conditions (Math.random())
while loops excel when you don't know how many iterations are needed ahead of time, such as repeatedly generating random numbers until a target value is reached.

JavaScript
let val = Math.random();
while (val / 3 !== 1) {
    console.log(val);
    val = Math.floor(Math.random() * 10); // Generates 0–9 randomly
}
3. Nested while Loops
For every single iteration of the outer while loop, the inner while loop runs completely.

JavaScript
let i = 0;
while (i < 10) {
    i++;
    let x = 100;
    while (x < 105) {
        x++;
        console.log(x); // Logs 101 to 105
    }
    console.log("______");
}
4. Reverse Counting (Decrementing Loop)
Starting from a higher value and decrementing (x--) down to a stopping threshold.

JavaScript
let x = 10;
while (x > 0) {
    console.log(x); // Logs 10 down to 1
    x--;
}
⚡ Key Takeaways 
Infinite Loops: If you forget to update the variable (e.g., missing i++ or x--), the condition will never become false, causing the browser tab/process to freeze.

Scope Differences: Variables declared with let inside a while loop body are re-created on each iteration.

for vs while:

Use for loops when the number of iterations is known (e.g., array lengths, fixed ranges).

Use while loops when iterations depend on dynamic conditions (e.g., state checks, randomized stop rules, stream processing).