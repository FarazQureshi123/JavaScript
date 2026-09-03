# JavaScript Notes & Code Snippets - Day 3: Data Types

Welcome to **Day 3** of the JavaScript Learning Series! Today's focus is understanding how JavaScript categorizes and handles different kinds of data using **Data Types**.

---

## 📌 Overview of JavaScript Data Types

In JavaScript, data types define the kind of value a variable can store. JavaScript is a **dynamically typed language**, meaning variables do not need to have a declared type; the engine automatically determines the type based on the value assigned.

Data types in JavaScript are broadly categorized into two types:
1. **Primitive Data Types** (7 types)
2. **Reference Data Types / Non-Primitive Data Types** (Objects, Arrays, Functions, etc.)

---

## 1. 🔹 Primitive Data Types

Primitive values are immutable (cannot be altered directly) and are passed/copied **by value**. There are **7 primitive data types** in JavaScript:

| Data Type | Description | Example Code |
| :--- | :--- | :--- |
| **String** | Textual data enclosed in quotes | `let name = "Faraz";` |
| **Number** | Represents both integer and floating-point numbers | `let age = 10;` |
| **Boolean** | Logical entity representing `true` or `false` | `let isActive = true;` |
| **Undefined** | Variable declared but not assigned a value | `let userName;` |
| **Null** | Represents an intentional absence of any value | `let empty = null;` |
| **Symbol** | Unique and immutable primitive value used for object keys | `let id = Symbol("id");` |
| **BigInt** | Represents integers larger than $2^{53} - 1$ | `let BigNumber = 123n;` |

---

## 2. 🔸 Reference Data Types (Non-Primitive)

Reference data types store references to memory locations rather than raw values. They are mutable and copied **by reference**.

Key Reference Types include:
- **Objects**: Key-value collections
- **Arrays**: Ordered lists of values
- **Functions**: Executable blocks of code
- **Date, Map, Set, etc.**

---

## 💡 Key Takeaways

1. **Primitive vs Reference**: Primitives hold values directly in memory; reference types hold pointers to memory addresses.
2. **`null` vs `undefined`**: `undefined` means a variable exists but hasn't been assigned a value; `null` is an explicit assignment representing "nothing".
3. **`typeof null` Bug**: In JavaScript, `typeof null` returns `"object"`. This is a historical bug in JS that remains for backward compatibility.