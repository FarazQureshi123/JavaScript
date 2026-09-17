Day 34: Arrow Functions in JavaScript
Welcome to Day 34 of the JavaScript learning journey! Today's focus is on Arrow Functions, introduced in ES6. 
We'll cover syntax shortcuts, implicit returns, returning object literals, hoisting limitations, and key differences between normal functions and arrow functions based on your code and reference slides.

📌 Table of ContentsWhat is an Arrow Function?Syntax Rules & Implicit ReturnsReturning Object LiteralsNormal Function vs. Arrow FunctionWhen to Use Arrow FunctionsCode Examples & WalkthroughSummary1. What is an Arrow Function?An Arrow Function provides a concise syntax for writing function expressions using the fat arrow (=>) token. Introduced in ES6, arrow functions streamline functional code and lexically bind the this value.JavaScript

// Standard Arrow Function
const add = () => {
    return 2 + 2;
};

console.log(add()); // Output: 4

2. Syntax Rules & Implicit ReturnsShortened Syntax & Implicit ReturnIf the function body consists of a single expression, you can omit both the curly braces {} and the return keyword:JavaScriptconst add = (a, b) => a + b;
console.log(add(100, 200)); // Output: 300

Single Parameter Parenthesis OmissionIf a function accepts exactly one parameter, the parentheses around the parameter are optional:JavaScriptconst square = num => num * num;
console.log(square(20)); // Output: 400

Multi-line Logic (Explicit Return Needed)When using curly braces {} for multi-line conditionals or operations, an explicit return statement is required:JavaScriptconst add = (a, b) => {
    if (typeof a === 'number' && typeof b === 'number') {
        return a + b;
    } else {
        return "not a valid input";
    }
};

console.log(add('100', "200")); // Output: "not a valid input"

3. Returning Object LiteralsTo implicitly return an object literal without writing the return keyword, wrap the object in parentheses (). This prevents JavaScript from treating the object's curly braces {} as a block scope statement:JavaScript// Wrap object in () for implicit return
const user = () => ({ name: "anil sidhu" });

console.log(user().name); // Output: "anil sidhu"


4. Normal Function vs. Arrow FunctionFeatureNormal FunctionArrow FunctionSyntaxLongShortHoistingYesNoOwn thisYesNoCan use new (Constructor)YesNoHas arguments ObjectYesNoCrucial Behavioral Differences:Hoisting: Arrow functions assigned to variables (const, let) are not hoisted like function declarations. Calling them before definition throws a ReferenceError.Arguments Object: Normal functions have access to the built-in arguments array-like object. Arrow functions do not have their own arguments object (use rest parameters ...args instead).Lexical this: Arrow functions do not define their own this context; they inherit this from the enclosing lexical scope.5. When to Use Arrow FunctionsArrow functions are ideal for:Callback functionsArray methods (map, filter, reduce)When you need lexical this (e.g., inside class methods or event listeners)Short utility functionsReact functional components (modern style)6.


 Code Examples & WalkthroughHere is the complete breakdown of the Day 34 script:HTML
 
 <!DOCTYPE html>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Arrow Function</title>
</head>
<body>
    <h1>Arrow functions</h1>
    <script>
        // 1. Basic Arrow Function
        const addBasic = () => {
            return 2 + 2;
        };
        console.log(addBasic()); // Output: 4

        // 2. Concise Syntax with Implicit Return
        const addShort = (a, b) => a + b;
        console.log(addShort(100, 200)); // Output: 300

        // 3. Multi-line Function with Type Checking
        const addChecked = (a, b) => {
            if (typeof a === 'number' && typeof b === 'number') return a + b;
            else return "not a valid input";
        };
        console.log(addChecked('100', "200")); // Output: "not a valid input"

        // 4. Single Parameter Omission of Parentheses
        const square = num => num * num;
        console.log(square(20)); // Output: 400

        // 5. Implicitly Returning an Object Literal
        // console.log(user().name); // ❌ ReferenceError: Cannot access 'user' before initialization (Hoisting fails)
        const user = () => ({ name: "anil sidhu" });
        console.log(user().name); // Output: "anil sidhu"

        // 6. Normal Function vs. Arrow Function (arguments object check)
        function getAll() {
            console.log(arguments); // Output: Arguments object containing ["green", "apple", "sunday"]
        }
        getAll("green", "apple", "sunday");
    </script>
</body>
</html>
7. SummaryShort Syntax: Arrow functions offer a clean syntax for single-expression operations and inline callbacks.Implicit Return: Omit {} and return for single-line expressions, or wrap {} in () when returning object literals.No Hoisting: Arrow functions must be declared before invocation.No Special Bindings: Arrow functions lack their own this, arguments, and cannot be instantiated with new.