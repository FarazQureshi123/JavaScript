Day 22: Form Input Validation in JavaScript
This project demonstrates real-time DOM-based input validation triggered by user focus events using Vanilla JavaScript.

📌 Core Concepts Covered
1. Focus Events (onblur)
Definition: The blur event fires when an element loses focus (for example, when a user clicks outside an input field or tabs away from it).

Usage: It is ideal for validating user input after they finish typing in a specific field, preventing intrusive error messages while typing.

2. Event Handling (event.target)
event.target: Refers to the specific DOM element that triggered the event (in this case, the <input> element).

event.target.value: Accesses the current string entered into the input field.

3. DOM Manipulation & Conditional Logic
document.getElementById(): Retrieves specific HTML elements (#user-message) to dynamically update UI feedback.

textContent: Safely updates or clears text nodes inside an element without rendering arbitrary HTML.

style.display: Controls visibility dynamically—switching between "block" to display error feedback and "none" to collapse the message when validation passes.

⚙️ How the Validation Logic Works
The function enforces a username length rule of 4 to 12 characters:

Length ≤ 3: Displays "min valid length is 4".

Length > 12: Displays "max valid length is 12".

Length between 4 and 12: Clears the message text and hides the error container.

🚀 How to Run
Save the code as index.html.

Open index.html in any modern web browser.

Click into the input field, type a value, and click outside (or press Tab) to trigger the validation logic.