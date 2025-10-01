# 📘 Study Notes: Recursive Functions

### 🌱 What is Recursion?

- **Recursion** = a function calling itself to solve a problem.
- Problem is broken into **smaller versions** until a **base case** is reached.
- Think of it like **Russian nesting dolls** → each smaller one inside until the smallest (base case).

---

### 🧩 Parts of a Recursive Function

1. **Base Case** → stopping condition (prevents infinite loop).
2. **Recursive Case** → function calls itself with a smaller input.

---

### 🖥 Example 1: Factorial

```js
function factorial(n) {
	if (n === 0) return 1;      // Base case   
	return n * factorial(n - 1); // Recursive case 
} 
console.log(factorial(5)); // 120
```

- Keeps reducing `n` until it hits `0`.
- Then resolves in reverse order.

---

### 🖥 Example 2: Countdown

```js
function countdown(n) {
   if (n === 0) {
        console.log("Liftoff!");
	} else {
		console.log(n);
		countdown(n - 1);
	}
}
countdown(5);
```

**Output:**  
5 → 4 → 3 → 2 → 1 → Liftoff!

---

### 🔑 When to Use Recursion

- Problems naturally broken into **smaller, similar problems**:
    - Factorial, Fibonacci
    - Traversing trees (DOM, file system)
    - Searching nested structures
- Makes code **clean** and mirrors the problem structure.

---

### ⚠️ Be Careful → Infinite Recursion

- Missing **base case** → stack overflow.

```js
function endless() {   return endless(); // 🚨 No base case }
```

---

### 🔄 Recursion vs Iteration

- **Iteration** = loops (for/while).
- **Recursion** = repeated function calls.
- Both can solve similar problems, but recursion is **more elegant** for nested/branching data.

---

### 🌍 Real-World Example → Sum of Nested Array

```js
function sumNestedArray(arr) {
	let sum = 0;
	arr.forEach(element => {     
		if (Array.isArray(element)) {
			sum += sumNestedArray(element); // Recursive call     
		} else {
		    sum += element;     
		}   
	});   
	return sum;
} 
console.log(sumNestedArray([1, [2, [3, 4]], 5])); // 15
```
- Recursively digs deeper until all numbers are added.
    

---

### 🏋️ Practice Exercises

- Write a recursive function to:  
    ✅ Sum numbers from 1 → n.  
    ✅ Reverse a string.  
    ✅ Print elements of a nested object.

---

```embed
title: "Best Javascript Recursion Explanation on YouTube"
image: "https://i.ytimg.com/vi/LteNqj4DFD8/maxresdefault.jpg"
description: "What is recursion?The process in which a function calls itself is called recursion. The corresponding function is called a recursive function. A recursive fu..."
url: "https://youtu.be/LteNqj4DFD8"
favicon: ""
aspectRatio: "56.25"
```

### 📌 Summary / Key Takeaways

- Recursion = function calling itself.
- Needs **base case** + **recursive case**.
- Best for nested, repeating, or tree-like problems.
- Beware of **stack overflow** if no base case.
- Powerful tool, but use wisely (iteration may be more efficient sometimes).

---

# ⚡ Cheat Sheet: Recursion in JS

🔹 **Definition** → Function calls itself until base case.  
🔹 **Parts** → Base Case (stop) + Recursive Case (call self).

```js
function recurse(x) {
   if (x <= 0) return;   // base case   
   recurse(x - 1);       // recursive case 
}
```

✅ **Uses** → Factorial, Fibonacci, Tree Traversal, Nested structures.  
⚠️ **Watch Out** → No base case → infinite recursion → stack overflow.

**Examples:**

- Factorial → `n! = n * factorial(n-1)`
- Countdown → print `n` then recurse `(n-1)`
- Nested Array Sum → recursive traversal