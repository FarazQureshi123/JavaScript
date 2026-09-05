# JavaScript Notes - Day 8: Logical Operators

Welcome to **Day 8** of the JavaScript Learning Series! Today's session covers **Logical Operators** in JavaScript—how to combine multiple boolean conditions and control decision-making logic using `&&` (AND), `||` (OR), and `!` (NOT).

---

## 📌 What are Logical Operators?

**Logical operators** are used to evaluate and combine boolean values (`true` or `false`). They allow JavaScript programs to test multiple conditions inside conditional statements like `if` blocks.

---

## 📚 The 3 Main Logical Operators

### 1. Logical AND (`&&`)
* **Rule**: Returns `true` **only if both conditions** are true.
* **Example**:
  ```javascript
  let name = "anil";
  let age = 29;

  if (name == "anil" && age == 30) {
      // Evaluates to: true && false -> false
      console.log("This will NOT run");
  }

  2. Logical OR (||)
Rule: Returns true if at least one condition is true.

Example:

JavaScript
if (name == "anil" || age == 30) {
    // Evaluates to: true || false -> true
    console.log("Write your code here"); // This WILL run
}


3. Logical NOT (!)
Rule: Inverts (reverses) the boolean value—converts true to false and false to true.

Example:

JavaScript
let login = false;

if (!login) {
    // Evaluates to: !false -> true
    console.log("User is not loggedIn"); // This WILL run
}


