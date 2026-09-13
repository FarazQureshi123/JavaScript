Day 23: JavaScript Array Iteration & Index Manipulation

This module focuses on how JavaScript handles array keys vs. values, element deletion behavior, dynamic sparse allocation, and iterating over array elements.

📌 Core Concepts Covered

1. Loop Differences: for...in vs. for...of
When working with arrays, choosing the right loop depends on whether you need the indexes or the values:

for...in (Keys / Indexes): Iterates over enumerable properties (indexes). In arrays, these indexes are returned as strings ("0", "1", "2"). It can also pick up custom added non-numeric properties.

for...of (Values): Iterates directly over the element values ("peter", "Sam", "Anil"). It is designed specifically for iterable collections like arrays.

let arr = ["A", "B"];

for (let key in arr) {
    console.log(key, typeof key); // Outputs: "0" string, "1" string
}

for (let val of arr) {
    console.log(val); // Outputs: "A", "B"
}


2. Array Deletion Behavior (delete)
The delete operator in JavaScript deletes the value bound to an index, but does not re-index the array or alter its structure.

users.length remains unchanged.

The slot becomes empty (accessing it returns undefined).

Creates what is known as a sparse array.

3. Sparse Arrays & Out-of-Bounds Assignment
JavaScript arrays automatically grow when elements are added to non-sequential indexes.

Assigning a value to an index far past the current length (e.g., users[10] = "Bob") causes JavaScript to fill all intermediate indexes (3 through 9) with empty slots.

Memory is allocated dynamically, but sparse arrays can lead to unintended performance or iteration side-effects.


Quick Revision Questions
Q1: Why is for...in generally discouraged for iterating over standard arrays?

Because for...in iterates over all enumerable properties (including custom properties added to the array object), returns indexes as strings instead of numbers, and does not guarantee iteration order.

Q2: What is the output of console.log(arr.length) after running let arr = [10, 20, 30]; delete arr[0];?

3. The delete operator removes the value at index 0 but does not change the total length.

Q3: How do for...in and for...of handle empty slots created by delete or sparse assignment?

for...in skips empty slots entirely, whereas for...of includes them and yields undefined for those positions.