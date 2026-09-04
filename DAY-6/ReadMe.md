# JavaScript Notes - Day 5: Arithmetic Operators & Type Coercion

Welcome to Day 5 of the JavaScript Learning Series! This module covers standard **Arithmetic Operators** in JavaScript, how basic mathematical operations work inside functions, and how JavaScript handles **Type Coercion** during arithmetic tasks.

---

## 📌 1. JavaScript Arithmetic Operators

Arithmetic operators perform basic mathematical calculations on numerical values (operands).

| Operator | Name | Description | Code Example | Output |
| :--- | :--- | :--- | :--- | :--- |
| `+` | **Addition** | Adds two numbers together | `10 + 2` | `12` |
| `-` | **Subtraction** | Subtracts the right operand from the left | `10 - 2` | `8` |
| `*` | **Multiplication** | Multiplies two numbers | `10 * 2` | `20` |
| `/` | **Division** | Divides the left operand by the right | `10 / 2` | `5` |
| `%` | **Modulus** | Returns the remainder of division | `10 % 2` | `0` |
| `**` | **Exponentiation** | Raises the base to the power of the exponent | `10 ** 2` | `100` |

---

## 🔄 2. Implicit Type Coercion in Arithmetic Operations

JavaScript is dynamically typed and performs **implicit type conversion (coercion)** when arithmetic operations involve mixed data types (e.g., Strings, Booleans, Numbers).

### Key Rules Learned:

* **Addition (`+`) with Strings (Concatenation):**
  When using `+` between a String and a Number, JavaScript converts the Number to a String and joins them together.
  * `"5" + 1` ➔ `"51"`
  * `5 + "1"` ➔ `"51"`

* **Numeric Operators (`-`, `*`, `/`) with Numeric Strings:**
  Operators like `-` and `*` automatically convert numeric strings into actual numbers before evaluating.
  * `"5" - 1` ➔ `4`
  * `"5" * 4` ➔ `20`

* **Invalid String Operations (`NaN`):**
  If a string contains non-numeric characters and cannot be converted into a valid number, arithmetic operations return **`NaN`** (Not a Number).
  * `"abc" * 3` ➔ `NaN`

* **Boolean Arithmetic:**
  When booleans are used in arithmetic expressions, JavaScript treats `true` as `1` and `false` as `0`.
  * `true + true` ➔ `1 + 1` = `2`

---

