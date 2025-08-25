# 🧠 Functional Programming – II (JavaScript)

## 🎯 Learning Objectives

- Understand **pure functions** and their importance.
- Use **anonymous functions** effectively.
- Implement **IIFE (Immediately Invoked Function Expressions)**.
- Pass **callbacks** into a calculator function.
- Validate using test cases (like Jasmine).

---

## 📌 Key Concepts

### 1️⃣ **Pure Functions**

- Output depends **only** on input.
- No side effects (doesn’t depend on `Math.random()`, `Date.now()`, external variables).

```js
// ❌ Impure function 
multiply(x) {
   return x * Math.random();
}  
// ✅ Pure function 
pureMultiply(x, y) {
   return x * y; 
}
```

---

### 2️⃣ **Anonymous Functions**

- Functions **without names**, assigned to variables.

```js
const squareroot = function(num) {
   return Math.sqrt(num);
};  
console.log(squareroot(25)); // 5
```

---

### 3️⃣ **IIFE (Immediately Invoked Function Expression)**

- Function runs **as soon as it’s defined**.

```js
const result = (function(x) {
   return Math.sqrt(x);
})(25);  
console.log(result); // 5
```

---

### 4️⃣ **Arithmetic Operations with Anonymous Functions**

```js
const addition = function(a, b){
	return a + b;
}; 
const multiplication = function(a, b){ 
	return a * b;
}; 
const division = function(a, b){
	return a / b;
};
const modulus = function(a, b){ 
	return a % b;
};
```

---

### 5️⃣ **Calculator Function with Callbacks**

- Functions can be passed as arguments (callbacks).

```js
function calculator(a, b, operation) {
   return operation(a, b); 
}
console.log(calculator(10, 5, addition)); // 15 
console.log(calculator(10, 5, multiplication)); // 50
```
---

## 📝 Summary / Key Takeaways

- **Pure functions** = predictable & testable, no side effects.
- **Anonymous functions** = unnamed, assigned to variables.
- **IIFE** = executes immediately after definition.
- **Callbacks** = functions passed as arguments to other functions.
- **Calculator example** shows modularity and flexibility.

---

# ⚡ Cheat Sheet (Quick-Glance)

👉 **Pure fn** → output only depends on inputs.  
👉 **Anonymous fn** → `const f = function(...) { ... }`.  
👉 **IIFE** → `(function(x){ return ... })(value)`.  
👉 **Ops** → `+`, `*`, `/`, `%` as anonymous functions.  
👉 **Callback fn** → pass function into another (`calculator(a,b,fn)`).