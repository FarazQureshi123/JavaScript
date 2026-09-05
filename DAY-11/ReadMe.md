# JavaScript Notes - Day 11: Type & Special Operators

Welcome to **Day 11** of the JavaScript Learning Series! Today's session covers **Type & Special Operators** in JavaScript (`typeof`, `in`, and `instanceof`)—used for evaluating data types, verifying object properties, and inspecting instance relationships.

---

## 📌 What are Type & Special Operators?

JavaScript provides dedicated operators to inspect the type of variables, check property existence inside objects, and verify object instances down the prototype chain.

---

## 📚 Core Operators Learned

### 1. The `typeof` Operator
The `typeof` operator returns a string indicating the primitive or object data type of an unevaluated operand.

```javascript
let data;

typeof data;             // "undefined"
typeof "Anil";           // "string"
typeof 123;              // "number"
typeof true;             // "boolean"
typeof NaN;              // "number" (Special numeric value)
typeof [];               // "object" (Arrays are special objects in JS)
typeof function(){};     // "function"
typeof null;             // "object" (Historical JS quirk)

⚠️ Key Note: typeof null returns "object" due to a legacy design decision in JavaScript.

2. The in Operator
The in operator checks whether a specified property exists within an object or its prototype chain, returning true or false.

JavaScript
let user = { name: "anil", age: 29, email: "anil@test.com" };

console.log("email" in user);    // true
console.log("address" in user);  // false


3. The instanceof Operator
The instanceof operator checks if an object's prototype chain contains the prototype property of a given constructor function or class.

JavaScript
let info = [];

console.log(info instanceof Array);   // true (info is created from Array)
console.log(info instanceof Object);  // true (Array inherits from Object)
console.log(info instanceof Date);    // false

let currentDate = new Date();
console.log(currentDate instanceof Date); // true


