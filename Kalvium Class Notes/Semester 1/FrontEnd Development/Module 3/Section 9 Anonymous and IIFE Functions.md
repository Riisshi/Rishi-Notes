# 📘 Study Notes: Anonymous & IIFE Functions

### 🌱 Anonymous Functions → _“More than just a name”_

- A **function without a name**.
- Useful for **short, specific tasks** → like a tool you use once and put back.
- Often passed as arguments to other functions.

**Example:**

```js
let numbers = [1, 2, 3, 4, 5]; 
numbers.forEach(function(number) {
	console.log(number);
}); // Output: 1 2 3 4 5
```

- Temporary, one-time use.

---

### ⚡ Arrow Functions → _“A streamlined tool”_

- **Shorter syntax** for anonymous functions.
- More concise, efficient, often used for small tasks.

**Example:**

```js
let multiply = (a, b) => a * b; 
console.log(multiply(2, 3)); // Output: 6
```

- Equivalent to writing a longer function.

---

### 🚀 IIFE (Immediately Invoked Function Expression) → _“The function that doesn’t wait”_

- Function that **executes immediately** after creation.
- No need to call it separately.
- Good for one-time operations or creating isolated scope.

**Example:**

```js
(function() {   console.log("Hello, IIFE!"); })(); // Output: Hello, IIFE!
```

---

### 🥗 IIFE with Parameters → _“Feed the machine”_

- You can pass arguments into an IIFE.

```js
(function(name) {
	console.log("Hello, " + name + "!");
})("John"); // Output: Hello, John!
```

---

### 🔒 Private Scope with IIFE → _“Keep things organized”_

- Variables inside an IIFE don’t interfere with outside variables.
- Helps prevent naming conflicts.

```js
var global = "I am global";
(function(){
	var global = "I am private";
	console.log(global); // Output: I am private 
})(); 
console.log(global); // Output: I am global
```

---

### 🏋️ Practice Ideas

- Create an IIFE that calculates the sum of two numbers.
- Pass different parameters into an IIFE (like names, ages).
- Use anonymous + arrow functions with `map`, `filter`, `reduce`.

---

### 📌 Summary / Key Takeaways

- **Anonymous Functions** → unnamed, temporary functions.
- **Arrow Functions** → shorter, cleaner syntax for anonymous functions.
- **IIFE** → runs immediately when defined, great for one-time tasks.
- **IIFE with Parameters** → allows arguments at execution.
- **Private Scope with IIFE** → avoids variable conflicts.

---

# ⚡ Cheat Sheet: Anonymous & IIFE Functions

🔹 **Anonymous Function** → no name, used for short tasks.

```js
function(a, b) { return a + b; }
```

🔹 **Arrow Function** → shorter version.

```js
`(a, b) => a + b`
```

🔹 **IIFE** → runs immediately.

```js
(function() { console.log("Hi"); 
})();
```
🔹 **IIFE with Parameters**

```js
(function(x){ 
	console.log(x*x);
})(5);
```

🔹 **Private Scope**

```js
(function(){
	let secret = "hidden";
	console.log(secret); 
})();
```

✅ Use when you need **one-time execution, isolation, or small helper functions**.