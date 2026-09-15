# Day 29: Dynamic Object Data Manipulation and UI Rendering in JavaScript

Welcome to Day 29 of the JavaScript Learning Series! Today's lesson focuses on dynamically reading input from users, updating object properties in real-time, and re-rendering the updated object properties onto the browser UI.

---

## 📌 Key Concepts Covered

### 1. Dynamic Object Property Assignment
When key names are determined dynamically (such as reading user input from an HTML input field), dot notation (`object.key`) cannot be used. Bracket notation (`object[key]`) must be used to dynamically assign or update property values on an object.

```javascript
let key = document.getElementById("key").value;
let value = document.getElementById("value").value;

// Dynamic assignment:
userDetails[key] = value;
```

---

### 2. Iterating & Rendering Objects to DOM
To render an object's contents into HTML, iterate over its keys using a `for...in` loop and construct HTML strings to append to a parent element (e.g., `<ul>`).

```javascript
function displayObjectData() {
    let userEl = document.getElementById('user-UL');
    userEl.innerHTML = ""; // Clear existing DOM elements to avoid duplicate rendering
    
    for (let key in userDetails) {
        userEl.innerHTML += "<li>" + key + " is " + userDetails[key] + "</li>";
    }
}
```

---

### 3. Immediate Rendering on Page Load
Invoking `displayObjectData()` at the end of the script ensures that initial object values are displayed instantly when the DOM is loaded, rather than waiting for an explicit user event.

```javascript
// Initial render call on script load
displayObjectData();
```

---

## 💻 Code Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Add and Display Object Data</title>
</head>
<body>
    <h1>Add and Display Object Data on UI</h1>
    <input type="text" id="key" placeholder="Enter key">
    <input type="text" id="value" placeholder="Enter Value">
    <button onclick="addNewData()">Add New Data</button>
    <ul id="user-UL"></ul>

    <script>
        let userDetails = {
            name: "Anil Sidhu",
            email: "anil@test.com",
            city: "Delhi"
        };

        function displayObjectData() {
            let userEl = document.getElementById('user-UL');
            userEl.innerHTML = "";
            for (let key in userDetails) {
                userEl.innerHTML += "<li>" + key + " is " + userDetails[key] + "</li>";
            }
        }

        function addNewData() {
            let key = document.getElementById("key").value;
            let value = document.getElementById("value").value;

            if (key && value) {
                userDetails[key] = value;
                displayObjectData();
            }
        }

        // Initial execution to populate UI on page load
        displayObjectData();
    </script>
</body>
</html>
```

---

## 📝 Practice Questions & Answers

### Q1: Why must bracket notation `userDetails[key]` be used instead of dot notation `userDetails.key` when adding new user input?
**Answer:** Dot notation `userDetails.key` looks for a literal key named `"key"` inside the object. Bracket notation `userDetails[key]` evaluates the variable `key` dynamically and attaches the actual string entered by the user.

### Q2: Why is `userEl.innerHTML = ""` required inside `displayObjectData()` before starting the loop?
**Answer:** Clearing `innerHTML` resets the parent container before looping. Without resetting it, every time `addNewData()` runs, all existing object keys will be duplicated on the UI alongside the newly added key.

### Q3: What happens if a user inputs an existing key name (e.g., `city`) with a new value (e.g., `Mumbai`)?
**Answer:** JavaScript objects cannot have duplicate keys. Assigning a value to an existing key will update/overwrite the previous value (`userDetails["city"] = "Mumbai"`), and the UI will display the updated value.

### Q4: How can you clear the input fields after adding new data?
**Answer:** Reset the `value` property of the input elements to empty strings:
```javascript
document.getElementById("key").value = "";
document.getElementById("value").value = "";
