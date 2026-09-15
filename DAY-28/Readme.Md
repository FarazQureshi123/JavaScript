 Day 28: Object Methods and the `this` Keyword in JavaScript

Welcome to Day 28 of the JavaScript Learning Series! Today's focus is on adding methods (functions) inside objects and understanding how the `this` keyword works to reference object properties and re-use methods within the same context.

---

## 📌 Key Concepts Covered

### 1. What is an Object Method?
In JavaScript, an **object method** is simply a function stored as a property value inside an object. It allows objects to perform actions or computations using their internal data.

```javascript
let userDetails = {
    name: "anil",
    greet: function() {
        return "Hello!";
    }
};
```

---

### 2. The `this` Keyword
The `this` keyword in JavaScript refers to the **current execution context** (the object executing the code). Inside an object method, `this` allows you to access other properties and methods belonging to that same object.

```javascript
greet: function() {
    // 'this.name' points to the 'name' property of the current object ('anil')
    return "Hello, " + this.name + " How are you ?";
}
```

> ⚠️ **Note:** Without using `this.name`, JavaScript would search for a global variable named `name` rather than the object's own property.

### 3. Calling Methods within Methods
Methods inside an object can invoke other methods of the same object by using `this.methodName()`.

```javascript
hello: function(from) {
    // Calls the existing greet() method and concatenates additional text
    return this.greet() + " this is " + from;
}
```

---

## 💻 Code Example & Output

```javascript
let userDetails = {
    name: "anil",
    age: 20,
    city: "gurgaon",
    greet: function() {
        return "Hello, " + this.name + " How are you ?";
    },
    hello: function(from) {
        return this.greet() + " this is " + from;
    }
};

console.log(userDetails.hello("peter"));
```

### Expected Output:
```text
Hello, anil How are you ? this is peter
```

---

## 📝 Practice Questions & Answers

### Q1: What does the `this` keyword refer to inside an object method?
**Answer:** Inside an object method, `this` refers to the object itself (the object that owns or is calling the method).

### Q2: What happens if you use `name` instead of `this.name` inside `greet()`?
**Answer:** JavaScript will try to find a variable named `name` in the local or global scope. If it doesn't exist, it will throw a `ReferenceError`. Using `this.name` ensures it looks up the `name` property on the target object.

### Q3: How can a method take external arguments alongside internal properties?
**Answer:** You can pass arguments to an object method just like a regular function. Inside the function body, combine parameters with `this.propertyName`:
```javascript
hello: function(from) {
    return this.greet() + " this is " + from;
}
```

### Q4: What is the difference between an Arrow Function and a Regular Function when used as an object method?
**Answer:** Regular functions bind `this` to the object calling the method. Arrow functions do **not** have their own `this`; they inherit `this` from the surrounding lexical scope (e.g., the `window` or global object in non-strict mode), which often leads to `undefined` property values.