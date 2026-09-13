Day 25: Array Element Deletion in JavaScript & the DOM

This project demonstrates various methods for removing elements from JavaScript arrays—focusing on built-in array methods (shift, pop, splice), index deletion behavior, and real-time deletion based on user input from the DOM.

📌 Core Concepts Covered

1. Array Deletion Methods

delete array[index]: Deletes the value at the target index but does not re-index the array. It leaves an empty spot (undefined), keeping the array's original length unchanged.

array.shift(): Removes the first element (index 0) and automatically shifts all subsequent elements down, decreasing the length by 1.

array.pop(): Removes the last element of the array and decreases the length by 1.

array.splice(start, deleteCount): Mutates the array by removing deleteCount elements starting from the start index. It dynamically re-indexes the remaining elements.

2. Event-Driven Array Mutation
onblur Event: Triggers the deleteElement() function when the user enters a value into the <input> element and moves focus away.

Validation Check (pos > users.length - 1): Ensures the entered position exists within the valid array bounds before attempting deletion, triggering an alert if the index is out of bounds.

⚙️ How the Code Functions
An initial array users = ["peter", "Sam", "Alice", "Bob"] is initialized.

The input field collects an index position from the user.

Upon losing focus (onblur), the deleteElement function:

Captures the input string and compares it to users.length - 1.

Displays an alert "Invalid position" if the index is out of range.

Calls users.splice(pos, 1) to remove 1 element at position pos if valid.

Outputs the modified users array to the browser console.

📝 Revision & Self-Assessment Questions


Q1: What is the difference between delete users[0] and users.shift()?

Answer: delete users[0] sets index 0 to undefined without changing the array length. users.shift() completely removes the item at index 0, re-indexes the remaining items, and reduces users.length by 1.

Q2: What happens if users.splice(1, 2) is executed on ["peter", "Sam", "Alice", "Bob"]?

Answer: It removes 2 elements starting at index 1 ("Sam" and "Alice"), leaving users as ["peter", "Bob"].

Q3: What bug occurs in the code if a user types a negative number (e.g., -1) into the input field?

Answer: splice(-1, 1) in JavaScript counts backward from the end of the array, removing the last element ("Bob") instead of failing validation. A robust check should ensure pos >= 0 && pos < users.length.

Q4: How does pop() differ from shift() in terms of performance?Answer: pop() operates in $O(1)$ time because it only removes the last element. shift() operates in $O(n)$ time because every remaining element must be re-indexed in memory.