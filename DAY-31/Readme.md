Key Topics Covered

Function Declaration Syntax & Structure
Hoisting Behavior in Declarations
Default Parameters
The length Property of Functions
Function Types & Objects ( typeof and instanceof )
Rest Parameters ( ... )

1. What is a Function Declaration?
A Function Declaration (also known as a function statement) is defined using the function keyword followed by
an explicit name and parameter list.
function greet(name) {
console.log("Hello " + name);
}
greet("Faraz"); // Output: Hello Faraz

2. Hoisting in Function Declarations
Function declarations are fully hoisted to the top of their scope during execution setup. This allows you to invoke
the function before its definition appears in the code.
// Calling the function BEFORE definition works perfectly!
fruit("Apple");
function fruit(item, item2 = 'no other fruit') {
console.log(item, item2); // Output: Apple no other fruit
}

3. Default Parameters
Default parameter values can be assigned directly inside the function signature. If an argument is omitted or passed
as undefined , the default value takes effect.
function fruit(item, item2 = 'no other fruit') {
console.log(item, item2);
}
fruit("Apple"); // Output: Apple no other fruit
•
•
•
•
•
•


4. Function Property: .length
The .length property of a function returns the count of expected formal positional parameters defined in its
signature (excluding default values and rest parameters).
function fruit(item, a, b, c) {
console.log(item);
}
console.log(fruit.length); // Output: 4

5. Function Types & instanceof
In JavaScript, functions are first-class objects under the hood.
typeof fn evaluates to "function" .
fn instanceof Object evaluates to true because functions inherit from Object.prototype .
function fruit() {}
console.log(typeof fruit); // Output: "function"
console.log(fruit instanceof Object); // Output: true

6. Rest Parameters ( ... )
The Rest Parameter syntax allows a function to accept an arbitrary number of arguments represented as a true
JavaScript Array.
Note: Rest parameters do not count toward a function's .length property since they dynamically handle
variable argument lists.

function fruit(...item) {
// 'item' is an array holding all passed arguments
console.log(item[4]); // Accesses element at index 4
}
fruit("apple", "banana", "papaya", "orange", "grapes");
// Output: grapes
•
•



Complete Day 31 Code Walkthrough

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Function Declaration</title>
</head>
<body>
<h1>Function Declaration</h1>
<script>
// 1. Hoisting Example
// fruit("Apple");
// 2. Default Parameters
// function fruit(item, item2 = 'no other fruit'){
// console.log(item, item2);
// }
// 3. Parameter Count via .length
// function fruit(item, a, b, c){
// console.log(item);
// }
// console.log(fruit.length); // Output: 4
// 4. Checking Data Type & Object Instance
// console.log(typeof fruit); // "function"
// console.log(fruit instanceof Object); // true
// 5. Rest Parameter Execution
function fruit(...item){
console.log(item[4]); // Output: grapes
}
fruit("apple", "banana", "papaya", "orange", "grapes");
</script>
</body>
</html>

Summary Takeaways
Hoisting: Declarations are accessible anywhere within their scope before definition.
Function Length: Reflects positional parameters; ignores defaults and rest params.
First-Class Objects: Functions are callable objects inheriting from Object .
Rest Parameters: Collect remaining arguments into a single clean array.