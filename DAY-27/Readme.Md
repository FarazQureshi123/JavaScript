JavaScript Objects store data as key-value pairs, where keys are strings (or Symbols) and values can be any data type, including primitive types, arrays, functions, or nested objects.

Notes & Core Concepts
1. Dot Notation vs. Bracket Notation
Access, update, or create properties using dot notation or bracket notation:

Dot Notation: userDetails.name (used when property names are valid identifiers).

Bracket Notation: userDetails["name"] or userDetails[key] (required when using variables or special character keys).

2. CRUD Operations on Objects
Create/Add: Assign a value to a new key (userDetails.email = "anil@gmail.com").

Read: Access existing properties (console.log(userDetails.name)).

Update: Reassign an existing key (userDetails.name = "Anil Sidhu").

Delete: Remove a key-value pair using the delete operator (delete userDetails.city). Accessing a deleted key returns undefined

3. Nested Objects
Objects can contain other objects. Access nested values by chaining dot operators:

JavaScript
console.log(userDetails.address.houseNo); // 111


4. Object Iteration (for...in loop)
The for...in loop iterates over all enumerable string properties of an object:

JavaScript
for (let key in userDetails) {
  console.log(key + ": " + userDetails[key]); // Use bracket notation for dynamic keys
}
Key Observations in Your Code
Bracket Notation in Loops: In your loop console.log(userDetails[key]), bracket notation is correctly used because key is a variable holding property names during iteration. userDetails.key would look for a literal property named "key" and fail.

Nested Object Iteration: The for...in loop prints the nested address object as an whole object standard output [object Object] unless handled recursively or with JSON.stringify().

Practice Questions & Answers
Q1: How do you access the sector property inside the nested address object in userDetails?

Answer: Use dot chaining: console.log(userDetails.address.sector); or bracket chaining console.log(userDetails["address"]["sector"]);.

Q2: What is the output of console.log("city" in userDetails); after running delete userDetails.city;?

Answer: false, because the property was completely removed from the object.

Q3: Why can't you use userDetails.key inside a for...in loop?

Answer: Dot notation looks for a literal property named "key". Bracket notation userDetails[key] evaluates the variable key dynamically on each iteration.

Q4: How can you retrieve all the keys of userDetails as an array without using a for...in loop?

Answer: Use the built-in static method Object.keys(userDetails).