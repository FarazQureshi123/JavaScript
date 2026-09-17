Day 33: Anonymous Functions in JavaScriptWelcome to Day 33 of the JavaScript learning journey! Today's focus is on Anonymous Functions, how they differ from Named Function Expressions, passing functions as arguments (callbacks/higher-order functions), and using them with asynchronous timers like setTimeout and setInterval.📌 Table of ContentsWhat is an Anonymous Function?Named vs. Anonymous Function ExpressionsHigher-Order Functions & CallbacksAsynchronous Timers (setTimeout & setInterval)Code Examples & WalkthroughSummary1. What is an Anonymous Function?An Anonymous Function is a function created without an explicit name identifier. It is commonly stored in a variable, passed as an argument to another function, or returned from a function.JavaScript// Anonymous function assigned to a variable
const add = function(a, b) {
    return a + b;
};

console.log(add(5, 10)); // Output: 15
2. Named vs. Anonymous Function ExpressionsFeatureNamed Function ExpressionAnonymous Function ExpressionInternal Name✅ Yes❌ NoDebuggingBetter (Name appears in stack traces)Variable name shownRecursionSafe (Can call itself via internal name)Variable dependentScopeName accessible only inside functionNo internal name3. Higher-Order Functions & CallbacksIn JavaScript, functions are first-class citizens, meaning they can be passed around just like values (numbers, strings, objects).Callback Function: A function passed as an argument to another function.Higher-Order Function: A function that receives another function as a parameter or returns a function.JavaScriptlet add = function(a, b) {
    return a + b;
};

let sub = function(a, b) {
    return a - b;
};

// Higher-order function accepting a callback 'fun'
function Operation(fun) {
    let x = 10;
    let y = 20;
    console.log(fun(x, y));
}

Operation(add); // Output: 30
Operation(sub); // Output: -10
4. Asynchronous Timers (setTimeout & setInterval)Anonymous functions are heavily used in Web APIs like setTimeout and setInterval.setTimeoutExecutes a callback function once after a specified delay (in milliseconds).JavaScript// setTimeout takes a callback function and delay in ms
setTimeout(() => {
    console.log("Hello after 2 seconds");
}, 2000);
Common Pitfall Note: setTimeout returns a numeric Timer ID, not a callable function. Attempting to invoke the returned ID (e.g., onTime()) will throw a TypeError: onTime is not a function.setIntervalRepeatedly executes a callback function at specified time intervals.JavaScriptconst onTime = function() {
    console.log("hi");
};

// Runs onTime every 1000 milliseconds (1 second)
setInterval(onTime, 1000);
5. Code Examples & WalkthroughHere is the breakdown of the HTML and JavaScript code studied on Day 33:HTML<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Anonymous Function in JS</title>
</head>
<body>
    <h1>Anonymous Function in JS</h1>
    <script>
        // -------------------------------------------------------------
        // 1. Defining Anonymous Function Expressions
        // -------------------------------------------------------------
        let add = function(a, b) {
            return a + b;
        };

        let sub = function(a, b) {
            return a - b;
        };

        // -------------------------------------------------------------
        // 2. Passing Anonymous Functions as Callbacks
        // -------------------------------------------------------------
        function Operation(fun) {
            let x = 10;
            let y = 20;
            console.log(fun(x, y));
        }

        Operation(add); // Output: 30
        Operation(sub); // Output: -10

        // -------------------------------------------------------------
        // 3. Asynchronous Execution with setTimeout
        // -------------------------------------------------------------
        // setTimeout schedule execution after 2000ms
        setTimeout(() => {
            console.log("Hello");
        }, 2000);

        // -------------------------------------------------------------
        // 4. Repeated Execution with setInterval
        // -------------------------------------------------------------
        const onTime = function() {
            console.log("hi");
        };

        // Executes onTime every 1 second
        setInterval(onTime, 1000);
    </script>
</body>
</html>
6. SummaryAnonymous Structure: Anonymous functions do not have a name right after the function keyword.First-Class Functions: Anonymous functions can easily be passed as callback arguments into higher-order functions.Debugging & Recursion: Named function expressions offer better stack traces and safer self-referential recursion compared to pure anonymous functions.Timers: Ideal for quick inline operations in Web APIs like setTimeout and setInterval.