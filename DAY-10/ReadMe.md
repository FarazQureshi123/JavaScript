# JavaScript Notes - Day 10: Ternary Operator (`? :`)

Welcome to **Day 10** of the JavaScript Learning Series! Today's session covers the **Ternary Operator**—a clean, concise shorthand for writing `if...else` and `if...else if...else` statements in JavaScript.

---

## 📌 What is the Ternary Operator?

The **ternary operator** is the only JavaScript operator that takes **three operands**:
1. A **condition** followed by a question mark (`?`)
2. An **expression to execute if condition is true**, followed by a colon (`:`)
3. An **expression to execute if condition is false**

### Basic Syntax
```javascript
condition ? expressionIfTrue : expressionIfFalse;


📚 Comparisons & Examples
1. Basic if...else vs. Single Ternary Operator
Using if...else:
JavaScript
let age = prompt("Enter your Age");
let message = "";

if (age >= 18) {
    message = "You are an adult";
} else {
    message = "You are a minor";
}
console.log(message);


Using Ternary Operator:
JavaScript
let age = prompt("Enter your Age");
let message = age >= 18 ? "You are an adult" : "You are a minor";
console.log(message);

2. Nested if...else if...else vs. Chained Ternary Operator
Using if...else if...else:
JavaScript
let score = Number(prompt("Enter your Score for Grades"));

if (score > 80) {
    console.log("Grade A");
} else if (score > 60) {
    console.log("Grade B");
} else if (score > 45) {
    console.log("Grade C");
} else {
    console.log("Grade D");
}


Using Chained Ternary Operator:
JavaScript
let score = Number(prompt("Enter your Score for Grades"));

let grade = score > 80 ? "Grade A" 
          : score > 60 ? "Grade B" 
          : score > 45 ? "Grade C" 
          : "Grade D";

console.log(grade);


💡 Key Takeaways & Best Practices
Syntax Reduction: The ternary operator significantly reduces boilerplate code and makes simple inline assignments much cleaner.

Performance Myth: The ternary operator is not faster in execution compared to standard if...else statements; its benefit lies purely in concise syntax and readability.

Readability Warning: Avoid deeply nesting ternary operators in production code as it can quickly become hard to read and maintain. For complex logic with many conditions, standard if...else if or switch statements are preferred.