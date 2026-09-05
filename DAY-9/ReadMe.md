# JavaScript Notes - Day 9: Conditional Statements

Welcome to **Day 9** of the JavaScript Learning Series! Today's session covers **Conditional Statements** in JavaScript—how programs make decisions based on specific conditions using `if`, `if...else`, `else if`, and `switch` blocks.

---

## 📌 What are Conditional Statements?

**Conditional statements** allow your JavaScript code to execute different actions depending on whether a given condition evaluates to `true` or `false`.

---

## 📚 Types of Conditional Statements Learned

### 1. `if...else` Statement
Executes one code block if the condition is `true`, and another block if it is `false`.

```javascript
let age = prompt("Enter Age");

if (age >= 18 && age <= 100) {
    alert("You can vote");
} else {
    alert("You cannot Vote");
}


2. if...else if...else Ladder
Used to check multiple conditions sequentially. JavaScript evaluates each condition from top to bottom; as soon as one condition evaluates to true, its corresponding block executes, skipping the rest.

JavaScript
const marks = prompt("Enter your Marks to Know Your Grades");

if (marks >= 80) {
    console.log("Grade A");
} else if (marks >= 60 && marks < 80) {
    console.log("Grade B");
} else if (marks >= 45 && marks < 60) {
    console.log("Grade C");
} else {
    console.log("Grade D");
}



3. switch Statement
An efficient alternative to multiple else if statements when evaluating a single variable against multiple discrete values using strict equality (===).

JavaScript
let day = Number(prompt("Enter the Number of Day"));

switch(day) {
    case 1: console.log("Monday"); break;
    case 2: console.log("Tuesday"); break;
    case 3: console.log("Wednesday"); break;
    case 4: console.log("Thursday"); break;
    case 5: console.log("Friday"); break;
    case 6: console.log("Saturday"); break;
    case 7: console.log("Sunday"); break;
    default: console.log("Wrong Input"); break;
}


💡 Key Takeaways
Comparison & Logical Operators: Conditional expressions frequently combine comparison operators (>=, <) and logical operators (&&) to evaluate ranges.

Execution Flow: In an if...else if chain, once a condition matches, execution stops for subsequent else if conditions.

Input Casting: Always use Number() when working with switch statements involving numeric inputs from prompt(), because prompt() returns a string by default.