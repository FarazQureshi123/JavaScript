Displaying Array Items in DOM
When rendering an array in the browser UI using JavaScript, the standard approach involves targeting a parent HTML container (like a <ul> or <div>), clearing its existing content to avoid duplicates, looping through the array elements, and dynamically appending HTML strings or elements.

Notes & Core Concepts
1. DOM Selection (document.getElementById)
To manipulate HTML elements with JavaScript, access them by their id:

JavaScript
let list = document.getElementById("list");
let inputVal = document.getElementById("value").value;


2. Clearing Previous Content (innerHTML = "")
Before re-rendering an updated array, reset the container’s innerHTML to an empty string. Without this step, every click would re-append the entire array onto the previous list items.

3. Iterating Arrays (for...of loop)
The for...of loop directly retrieves each value from the array without needing an index tracking variable:

JavaScript
for (let user of users) {
  list.innerHTML += "<li>" + user + "</li>";
}


4. Array Insertion (splice)
The splice() method modifies an array in place by removing or replacing existing elements and/or adding new elements:

JavaScript
// Syntax: array.splice(index, deleteCount, item1)
users.splice(pos, 0, val); // Inserts 'val' at index 'pos' without deleting anything
Key Observations in Your Code
Initial Load: The list stays empty when the page first loads until you click the Display Items button. Call displayElement() outside the function once at the bottom of your <script> to show the initial array immediately.

Input Types: document.getElementById('position').value returns a string. Passing a string to splice() usually coerces to a number, but parsing it explicitly with parseInt(pos) prevents unexpected edge cases.

Practice Questions & Answers
Q1: How can you make the default array items display automatically when the web page loads?
Answer: Call displayElement(); at the bottom of your <script> tag outside of any function body, or attach it to window.onload = displayElement;.

Q2: What happens if you remove list.innerHTML = "" inside the displayElement() function?
Answer: Every time you click the button, the whole list duplicates on the UI instead of refreshing to show the updated array once.

Q3: How do you append a new element to the very end of an array without specifying an index position?
Answer: Use users.push(val);.

Q4: How can you rewrite the rendering loop using modern template literals instead of string concatenation?
Answer:

JavaScript
for (let user of users) {
  list.innerHTML += `<li>${user}</li>`;
}