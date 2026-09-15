# Day 30: Array of Objects and Iteration Methods in JavaScript

Welcome to Day 30 of the JavaScript Learning Series! Today's session explores how to work with an **Array of Objects**, access object properties within an array, and iterate through them using various JavaScript loop mechanisms (`for...of`, `Array.prototype.map`, and `Array.prototype.forEach`) to render content onto the DOM.

---

## 📌 Key Concepts Covered

### 1. What is an Array of Objects?
An **Array of Objects** is a collection where each element inside the array is a JavaScript object containing key-value pairs. This is one of the most common data structures used in real-world applications when fetching structured records (like users, products, or posts) from APIs.

```javascript
let users = [
    { name: "anil", age: 29, email: "anil@test.com" },
    { name: "sam", age: 30, email: "sam@test.com" },
    { name: "peter", age: 31, email: "peter@test.com" }
];
```

---

### 2. Iteration Methods Compared

#### Approach A: `for...of` Loop
The standard block-scoped loop used to iterate directly over iterable objects (including arrays).

```javascript
for (let user of users) {
    list.innerHTML += "<li>Hello User name is " + user.name + " and User age is " + user.age + "</li>";
}
```

#### Approach B: `Array.prototype.map()`
`map()` iterates through the array and returns a new transformed array. While frequently used in UI frameworks like React to return elements, using it solely for side effects (like directly mutating DOM elements) without returning anything is generally discouraged in pure JavaScript.

```javascript
users.map((user) => {
    list.innerHTML += "<li>Hello User name is " + user.name + " and User age is " + user.age + "</li>";
});
```

#### Approach C: `Array.prototype.forEach()` (Recommended for Side Effects)
`forEach()` executes a provided callback function once for each array element. It is specifically intended for running side effects (such as updating DOM nodes or logging data) without creating a new array.

```javascript
users.forEach((user) => {
    list.innerHTML += "<li>Hello User name is " + user.name + " and User age is " + user.age + "</li>";
});
```

---

## 💡 Best Practice Tip: Refactoring DOM Manipulation

In large datasets, appending to `innerHTML` inside a loop (`list.innerHTML += ...`) causes multiple DOM re-paints, which negatively impacts performance. Instead, build a complete string or use `.map().join('')`:

```javascript
// Efficient single-pass DOM insertion
list.innerHTML = users.map(user => 
    `<li>Hello User name is ${user.name} and User age is ${user.age}</li>`
).join('');
```

---

## 💻 Complete HTML & JavaScript Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Array of Objects</title>
</head>
<body>
    <h1>Array of Objects in Javascript</h1>
    <ul id="user-list"></ul>

    <script>
        let users = [
            { name: "anil", age: 29, email: "anil@test.com" },
            { name: "sam", age: 30, email: "sam@test.com" },
            { name: "peter", age: 31, email: "peter@test.com" }
        ];

        let list = document.getElementById("user-list");
        list.innerHTML = "";

        // Rendering using forEach
        users.forEach((user) => {
            list.innerHTML += `<li>Hello User name is ${user.name} and User age is ${user.age}</li>`;
        });
    </script>
</body>
</html>
```

---

## 📝 Practice Questions & Answers

### Q1: How do you access the email address of the second user in the `users` array?
**Answer:** Use array indexing followed by dot notation: `users[1].email` (returns `"sam@test.com"`).

### Q2: What is the key functional difference between `forEach()` and `map()`?
**Answer:** `forEach()` returns `undefined` and is used strictly to execute side effects on array elements. `map()` transforms the array elements and returns a **new array** containing the transformed results.

### Q3: Why is `forEach()` preferred over `map()` when directly appending elements to the DOM in vanilla JS?
**Answer:** Because `map()` creates an unused array in memory when you don't return a value, leading to unnecessary memory overhead. `forEach()` is purpose-built for executing side-effects like DOM modifications.

### Q4: How can you write the template string inside the loop using ES6 Template Literals?
**Answer:** Use backticks (`` ` ``) and string interpolation (`${}`):
```javascript
`<li>Hello User name is ${user.name} and User age is ${user.age}</li>`