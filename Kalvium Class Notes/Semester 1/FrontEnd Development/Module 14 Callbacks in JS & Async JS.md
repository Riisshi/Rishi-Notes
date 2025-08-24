# 📘 Study Notes: Callbacks & Async JavaScript

## 🎯 Learning Objectives

- Understand **asynchronous JavaScript** and why it’s needed.
- Learn what a **callback function** is.
- Use **setTimeout()** to simulate async behavior.
- See **real-world async use cases** (network requests, events, etc.).
- Recognize how **callback-based async code works**.

---

## 🔹 1. What is Asynchronous JavaScript?

- **JavaScript is single-threaded** → executes one line at a time.
- Problem: Long tasks (e.g., downloading a file) block execution.
- **Async JS** → lets tasks run in the background → program stays responsive.
- ✅ Example: Like ordering food at a restaurant 🍽️ → you wait at your table, food comes later (callback).

---

## 🔹 2. What is a Callback Function?

- **Callback** → A function passed into another function to be executed later.
- Used when an operation takes time and you want code to run after it finishes.

✅ Example:

```js
function greetUser(name, callback) {
	console.log("Hi, " + name);
	callback(); 
}  
function showMessage() {
	console.log("Welcome to the dashboard!"); 
}  
greetUser("Ravi", showMessage); // Hi, Ravi // Welcome to the dashboard!
```

---

## 🔹 3. `setTimeout()` → Simulating Async Behavior

- Delays execution without blocking other code.

✅ Example:

```js
console.log("Start");  
setTimeout(() => {
   console.log("This runs after 2 seconds");
}, 2000);
console.log("End");
```

Output:

`Start End This runs after 2 seconds`

---

## 🔹 4. Real-World Example: Simulating Data Loading

```js
function fetchData(callback) {
	setTimeout(() => {
		console.log("Data loaded!");
		callback();   
}, 3000); 
}  
function showUI() {
	console.log("Displaying UI..."); 
}  
fetchData(showUI); // Data loaded! // Displaying UI...
```
✔️ Mimics network request → callback runs after data is ready.

---

## 🔹 5. When Are Callbacks Used?

- 🖱️ **User events** → clicks, inputs.
- ⏱️ **Timers** → `setTimeout`, `setInterval`.
- 🌐 **API requests** → fetch data from server.
- 📂 **File loading / images / animations**.

👉 Callbacks keep apps **non-blocking & responsive**.

---

## 🎮 Exercises

1. Log → `"Step 1"` immediately, `"Step 2"` after 1 sec, `"Step 3"` after 2 sec.
2. Create `downloadFile(filename, callback)` → logs `"Download complete"` after 2s, then callback runs.
3. Simulate user login → `setTimeout` → `"Login successful"` → then callback loads dashboard.

---

## ✨ Summary

- **Async JS** → Handles time-taking tasks without blocking.
- **Callback** → Function passed to another function, executed later.
- **setTimeout** → Simulates async delay.
- Common uses: **Events, Timers, API calls, File loading**.
- First step toward mastering async programming → next: **Promises & async/await**.

---

# ⚡ Quick Cheat Sheet: Callbacks & Async JS

📌 **Async JS** → Non-blocking, background tasks.  
📌 **Callback** → Function passed as argument, runs later.  
📌 **setTimeout** → Delay execution.

✅ Example:

```js
setTimeout(()=>console.log("Hello"), 1000);
```

📌 **Uses** → Events, Timers, API requests, File loading.  
📌 **Flow** → Task starts → main code continues → callback runs when task finishes.