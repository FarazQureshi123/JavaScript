# JavaScript Learning Journey: Day 2

Welcome to Day 2! Today’s focus is understanding variables, variable declarations (`var`, `let`, `const`), variable scope, hoisting, and naming conventions in JavaScript.

---

## 📌 Day 2: Variables, Scope & Declaration Keywords

### 💡 Core Key Concepts

1. **What is a Variable?**
   - A variable is a named container used to store data values in memory so they can be referenced and manipulated throughout a program.

2. **Ways to Declare Variables:**
   - `var` *(Legacy / Avoid)*
   - `let` *(Modern / Re-assignable)*
   - `const` *(Modern / Fixed Value)*

---

## 🛑 Why Should We Avoid `var`?

`var` was the original way to declare variables in JavaScript, but it introduces several issues in modern development:

1. **Allows Redeclaration:** You can accidentally redeclare the same variable name, overwriting existing data without throwing an error.
2. **Function-Scoped (No Block Scope):** Variables declared with `var` leak outside of block statements (`{ ... }`), making them accessible where they shouldn't be.
3. **Attaches to the Global Object:** Global `var` declarations attach directly to the `window` object in browsers, which can lead to global namespace pollution.
4. **Hoisting Quirks:** Calling a `var` variable before its declaration returns `undefined` instead of throwing a reference error.

---

## ⚔️ `var` vs `let` vs `const` Comparison

| Feature | `var` | `let` | `const` |
| :--- | :--- | :--- | :--- |
| **Scope** | Function Scope | Block Scope (`{}`) | Block Scope (`{}`) |
| **Redeclaration** | ✅ Allowed | ❌ Not Allowed | ❌ Not Allowed |
| **Re-assignment** | ✅ Allowed | ✅ Allowed | ❌ Not Allowed |
| **Hoisting** | Hoisted (`undefined`) | Hoisted (Temporal Dead Zone) | Hoisted (Temporal Dead Zone) |
| **Global Object Attachment** | Attaches to `window` | Does NOT attach to `window` | Does NOT attach to `window` |

---

## 🏷️ Naming Rules & Best Practices

### **Allowed Rules:**
- Can contain **letters**, **numbers**, **underscores (`_`)**, or **dollar signs (`$`)**.
- **Cannot** start with a number.
- **Cannot** contain spaces.
- **Cannot** use reserved JavaScript keywords (e.g., `let`, `function`, `class`).

### **Best Practices:**
- 🚫 **Avoid `var`** completely in modern code.
- 🔄 **Use `let`** when you know the value will change later.
- 🔒 **Use `const`** by default for fixed values.
- 🐫 **Use camelCase** naming conventions (e.g., `userName`, `adminName`, `isLoggedIn`).
- 📝 **Use meaningful names** that describe what data the variable holds.

---

❓ Frequently Asked Questions

-> What is a variable in JS?

A container for storing data values.

-> What are the ways to declare a variable in JS?

Using var, let, or const.

-> Why should we avoid using var?

Because it lacks block scope, permits accidental redeclaration, attaches to window, and causes confusing hoisting behavior.

-> Can you reassign a const variable?

No, reassigning a const variable throws a TypeError.

-> Can we call var before declaration?

Yes, but its value will be undefined due to hoisting.

-> Can we redeclare variables?

var allows redeclaration within the same scope; let and const do not.