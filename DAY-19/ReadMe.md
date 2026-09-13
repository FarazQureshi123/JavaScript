Day 19: DOM Manipulation — Working with Input Fields in JavaScript

Today's focus is on basic DOM (Document Object Model) Manipulation using JavaScript. You will learn how to read, update, clear, and transfer values between HTML <input> fields and heading tags using button click events.

Key Concepts
document.getElementById(id): Selects an HTML element on the page using its unique id.

.value Property: Gets or sets the current text typed inside an HTML <input> field.

.innerText Property: Gets or sets the visible text content inside an HTML tag (like <h1>, <p>, or <span>).

onclick Event: An event listener attribute added to <button> elements that triggers a JavaScript function when clicked.

Code Breakdown & Explanation
1. getInputValue() — Reading & Displaying Input
JavaScript
function getInputValue() {
    let InputValue = document.getElementById("name").value;
    document.getElementById("heading").innerText = InputValue;
    console.log(InputValue);
}
How it works: Reads the text typed inside the #name input field, assigns it to InputValue, updates the text inside <h1 id="heading">, and logs the value to the browser console.

2. SetInputValue() — Programmatically Setting Input Text
JavaScript
function SetInputValue() {
    let value = "code step by step";
    document.getElementById("name").value = value;
}
How it works: Fills the #name input box programmatically with the string "code step by step".

3. removeInputValue() — Clearing an Input Field
JavaScript
function removeInputValue() {
    document.getElementById("name").value = "";
}
How it works: Clears out the #name input field by assigning an empty string "" to its .value property.

4. CopyInputFieldValue() — Transferring Values Between Inputs
JavaScript
function CopyInputFieldValue() {
    let whovalue = document.getElementById("who").value;
    document.getElementById("name").value = whovalue;
}
How it works: Grabs the text typed inside the #who input box and copies it directly into the #name input box.

Bug Alert: Case Sensitivity Fix ⚠️
In the HTML provided, the button event call has a slight typo in letter casing:

HTML Button: onclick="CopyInputfieldValue()" (lowercase f)

JavaScript Function: function CopyInputFieldValue() (uppercase F)

Because JavaScript is case-sensitive, clicking the Copy Value button will throw an Uncaught ReferenceError.

Fixed HTML:
HTML
<button onclick="CopyInputFieldValue()">Copy Value</button>
DOM Properties Quick Reference
Property	Used For	Example
.value	Reading or modifying <input>, <textarea>, or <select> values	inputElem.value = "Hello"
.innerText	Reading or updating human-readable text inside HTML tags	h1Elem.innerText = "Welcome"
onclick	Binding a click interaction to run a JS function	<button onclick="myFunc()">


