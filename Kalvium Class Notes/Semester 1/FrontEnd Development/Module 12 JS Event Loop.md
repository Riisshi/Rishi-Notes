# 🧠 JavaScript Event Loop — Study Notes

## 🎯 Learning Goals

- Recall how JavaScript code executes.
- Understand and explain the **Event Loop**.
- Explore **asynchronous behavior** in JS.

---

## ⚡ JavaScript Execution Recap

### 🥞 Call Stack

- Stores function calls (like a stack of plates).
- Operates on **LIFO** (Last In, First Out).
- Example:
```js
function greet() {
	console.log("Hello!"); 
} 
function sayGoodbye() {
	console.log("Goodbye!"); 
}
greet(); 
sayGoodbye();
```
    - `greet()` → pushed, executed, removed.
        
    - `sayGoodbye()` → pushed, executed, removed.

---

## 🔄 The Event Loop

- JS is **single-threaded**, but can still handle async tasks.
- Works with:
    - **Call Stack** → runs synchronous code.
    - **Message Queue (Macrotask Queue)** → tasks from `setTimeout`, events.
    - **Microtask Queue** → tasks from `Promises`, `MutationObserver`.
- **Order of execution**:
    1. Call stack (sync code).
    2. Microtask queue (Promises).
    3. Message queue (Timers, events).

---

## 👨‍🍳 Analogy (Chef & Kitchen)

- **Call Stack** → Orders being cooked.
- **Message Queue** → Normal pending orders.
- **Microtask Queue** → Urgent orders (priority).
- **Event Loop** → Assistant ensuring smooth workflow.

---

## 💻 Code Examples

### Example 1: Basic Event Loop

```js
console.log("Start");
setTimeout(() => console.log("Timeout"), 2000); 
console.log("End");
```

➡ Output:

`Start   End   Timeout (after 2s)`  

---

### Example 2: Microtasks vs. Macrotasks

```js
console.log("Start"); 
Promise.resolve().then(() => console.log("Microtask")); 
setTimeout(() => console.log("Macrotask"), 0); 
console.log("End");
```

➡ Execution Order:

`Start   End   Microtask   Macrotask`  

---

### Example 3: Analogy Code

```js
console.log("Order Placed"); 
setTimeout(() => console.log("Preparing Order"), 0); Promise.resolve().then(() => console.log("Order Confirmed")); console.log("Order Completed");
```

➡ Output:

`Order Placed   Order Completed   Order Confirmed   Preparing Order`  

---

### Example 4: Predict Output

```js
console.log("A"); 
setTimeout(() => console.log("B"), 1000); 
setTimeout(() => console.log("C"), 0); 
console.log("D");
```

➡ Output:

`A   D   C   B`  

---

### Example 5: Debug Sequence (Ensure Task 3 is last)

```js
console.log("Task 1"); 
setTimeout(() => console.log("Task 2"), 0); 
Promise.resolve().then(() => console.log("Task 3"));
```

➡ Output:

`Task 1   Task 3   Task 2`  

---

## 📌 Summary / Key Takeaways

- JS is **single-threaded** but async via Event Loop.
- **Call Stack** → executes sync code.
- **Microtask Queue** (Promises) runs **before** Macrotask Queue (`setTimeout`).
- **Execution order rule**:
    - Sync → Microtasks → Macrotasks.

---

# ⚡ Quick Cheat Sheet — JS Event Loop

✅ **Call Stack** = function execution (LIFO).  
✅ **Event Loop** = checks stack, microtasks, then macrotasks.  
✅ **Microtasks** (Promises) always before Macrotasks (setTimeout).

### Code Output Templates

`console.log("Start"); setTimeout(() => console.log("Macrotask"), 0); Promise.resolve().then(() => console.log("Microtask")); console.log("End");`

➡ Order: Start → End → Microtask → Macrotask