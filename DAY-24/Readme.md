Day 24: Array Basics, Traversal & Sparsity in JavaScript    

This module covers the core fundamentals of JavaScript arrays: creation, indexing, deletion side-effects, dynamic element assignment, and array traversal techniques.

📌 Core Concepts Covered
1. Array Creation & Heterogeneity
JavaScript arrays are ordered, zero-indexed collections that can hold multiple values under a single variable.

Literal Syntax (Preferred): let users = ["peter", "Sam", "Anil"];

Constructor Syntax: let users = new Array("peter", "Sam", "Anil");

2. Deletion Side-Effects (delete)
Using the delete operator on an array element (delete users[0]) removes the value at that index, but leaves a hole (empty slot).

Accessing users[0] after deletion returns undefined.

The length of the array (users.length) remains unchanged.

3. Dynamic Assignment
Arrays in JavaScript are dynamic. Adding an item to a specific index (users[3] = "apple") extends the array length automatically without throwing an out-of-bounds error.

4. Array Traversal Techniques
Standard for Loop: Traditional index-based iteration (for(let i = 0; i < users.length; i++)). Ideal when the index position is needed.

for...of Loop: Iterates directly over iterable values (for(let element of users)).


🎯 Quick Revision Questions

Q1: What is the difference between for...in and for...of when looping over an array?

for...in iterates over the array keys/indexes (as strings), while for...of iterates directly over the values.

Q2: What happens to users.length when you execute delete users[1] on an array of length 3?

Nothing. users.length stays 3, and index 1 becomes an empty slot (undefined).

Q3: What would happen if you assign users[10] = "Bob" when users only has 3 elements?

JavaScript creates a sparse array. It places "Bob" at index 10 and fills indexes 3 through 9 with empty slots.