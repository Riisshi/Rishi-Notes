# 📘 Study Notes: Closures & Scoping in JavaScript

## 🔹 1. Scope in JavaScript

- **Scope** → Region where variables are accessible.
- **Types of Scope:**
    - 🌍 **Global Scope** → Variables declared outside any function. Accessible everywhere.
    - 🏠 **Function Scope** → Variables declared inside a function. Accessible only in that function.
    - 📦 **Block Scope** (`let`, `const`) → Accessible only inside `{}` (loops, if-blocks, etc.).

✅ Example:

```js
let x = 'global';
function test() {
	let y = 'local';
	console.log(x); // ✅ global   
	console.log(y); // ✅ local 
}  
console.log(x); // ✅ global 
console.log(y); // ❌ ReferenceError
```

---

## 🔹 2. Closures

- **Closure** → A function that **remembers variables from its outer scope** even after the outer function is finished.
- The inner function “closes over” the outer function’s variables.

✅ Example:

```js
function makeCounter() {   
	let count = 0;   
	return function() {     
		return count++;   
	}; 
}  
let counter = makeCounter();
console.log(counter()); // 0 
console.log(counter()); // 1
```

---

## 🔹 3. Lexical Scoping

- **Definition**: Scope is determined by **where a function is defined**, not where it is executed.
- Inner functions can access outer variables.

✅ Example:

```js
function outer() {   
	let outerVar = "I am outside!";   
	function inner() {     
		console.log(outerVar);
	}
	inner();
} 
outer(); // "I am outside!"
```

---

## 🔹 4. Closures & Memory

- Closures **preserve variables in memory**.
- ⚠️ Risk: If closures reference large objects unnecessarily → **Memory leaks**.
- 💡 Tip: Avoid retaining unused variables/objects.

---

## 🔹 5. Closures in Asynchronous Programming

- Used in **callbacks, promises, setTimeout**, etc.
- Helps maintain state across async operations.

✅ Example:

```js
function delayedMessage(msg, delay) {
	setTimeout(function() {
		console.log(msg);   
	}, delay);
}  delayedMessage("Hello!", 2000); // Logs after 2s
```
---

## 🔹 6. Exercise (Lexical Scope Challenge)

```js
function outer() {
	let outerVar = 'I am outside!';
	function inner() {
	let innerVar = 'I am inside!';
	console.log(outerVar); // "I am outside!"     
	console.log(innerVar); // "I am inside!"   
	}   
	inner();
} 
outer();
```

- **outerVar** → Defined in outer function, accessible inside `outer` & `inner`.
- **innerVar** → Defined in inner function, accessible **only in inner**.
- Logs:
    `I am outside! I am inside!`

---

## ✨ Summary / Key Takeaways

- **Scope** defines variable accessibility (Global, Function, Block).
- **Closures** let inner functions access outer variables even after execution ends.
- **Lexical Scope** → Based on where function is written, not called.
- ⚠️ Closures can cause **memory leaks** if misused.
- Widely used in **async programming, callbacks, data privacy, modular code**.

---

# ⚡ Cheat Sheet: Closures & Scope

📌 **Scope**

- Global → Everywhere
- Function → Inside function
- Block → `{}` with `let`, `const`

📌 **Closure**

- Function + Environment (outer vars)
- Example:

```js
function outer(){
	let x = 10;   
	return ()=>x; 
}
```
📌 **Lexical Scope**

- Based on **definition place** (not execution).

📌 **Async Use**

```js
setTimeout(()=>console.log("Hi"), 1000);
```

📌 **Memory Tip**

- Don’t let closures hold unnecessary large data.