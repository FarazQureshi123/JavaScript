Day 18: JavaScript for...in Loop & Object Iteration
Today's focus is on mastering the for...in loop in JavaScript—a loop specifically designed to iterate over the keys (properties) of an object.

Key Concepts
for...in Loop: Iterates over all enumerable properties (key names) of an object.

Property Access: During each iteration, the loop variable receives the key name (as a string). To access the corresponding value, use bracket notation: object[key].

Control Statements: Works seamlessly with break and continue to control iteration flow.

Code Breakdown & Explanation
JavaScript
let user = {
    name: "Anil",
    age: "20",
    email: "Anil@gmail.com"
};

for (let key in user) {
    if (key == 'age') {
        continue; // Skips the 'age' property
    }
    console.log(key, user[key]);
}
How it works:

The for...in loop starts scanning the user object property by property (name, age, email).

First iteration: key is "name". It logs name Anil.

Second iteration: key is "age". The condition key == 'age' evaluates to true, triggering continue. The rest of the loop block is skipped.

Third iteration: key is "email". It logs email Anil@gmail.com.

Console Output:

Plaintext
name Anil
email Anil@gmail.com


Similarities
All three control repetitive tasks and support loop flow controls (break and continue).

All can process collections of data sequentially.

All accept standard block statements {} to execute logic on each pass.

Key Differences & Why Each is Better in Its Scope
Why for...in is better for Objects: Plain JavaScript objects are not iterable by default, meaning for...of throws a TypeError if used directly on {}. for...in is built specifically to extract key names from key-value pairs without manual setup.

Why for...of is better for Arrays & Strings: It extracts values directly without needing index bracket syntax. Unlike for...in, it ignores custom object properties added to array prototypes, preventing unexpected bugs when working with list-based data.

Why Traditional for is better for Custom Ranges & Performance: It allows exact control over step counts (e.g., i += 2, reverse loops i--), middle start/stop positions, and complex index manipulation that neither for...of nor for...in can handle natively.