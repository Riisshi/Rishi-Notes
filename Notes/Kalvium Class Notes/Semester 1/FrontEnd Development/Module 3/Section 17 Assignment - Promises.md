# 📘 Study Notes: Assignment | Promises

### 🎯 Objective

- Strengthen understanding of **JavaScript Promises**.
- Practice handling **asynchronous operations** with success & failure cases.

---

### 📝 Task Breakdown

- Implement `fetchData(success, delay)` in **src/app.js**.
- Function requirements:
    - Returns a **Promise**.
    - Uses **setTimeout** to simulate async behavior.
    - If `success === true` → **resolve** with a success message (including `delay`).
    - If `success === false` → **reject** with an error message (including `delay`).
    - Must handle multiple calls consistently.

---

### ⚙️ Hints

- Use the **Promise constructor**:
    `return new Promise((resolve, reject) => { ... });`
- `resolve` → for success.
- `reject` → for failure.
- Use **template literals** for messages:
    `` `Success after ${delay}ms` ``

---

### ✅ Example Logic (Simplified)

```js
function fetchData(success, delay) {   
	return new Promise((resolve, reject) => {
		setTimeout(() => {
			if (success) {
				resolve(`Success: Data fetched after ${delay}ms`);
			} 
			else {
				reject(`Error: Failed after ${delay}ms`);       
			}     
		}, delay);
	}); 
}
```

---

### 🧩 Key Concepts Reinforced

- **Promises**: Cleaner async handling than callbacks.
- **setTimeout**: Simulates async operation.
- **resolve / reject**: Control flow for success vs. failure.
- **Template literals**: Easy string formatting.

---

### 📌 Summary / Key Takeaways

- `fetchData` demonstrates **async simulation with Promises**.
- Always return the **Promise object**.
- Use **resolve** for success, **reject** for failure.
- **Template strings** make messages dynamic.
- Helps practice writing **testable async code**.

---

# ⚡ Cheat Sheet: Promises Assignment

### Function Signature

```js
function fetchData(success, delay) { ... }
```

### Core Logic

- **Return Promise**:
```js
new Promise((resolve, reject) => { ... })
```
- **Async delay**:
```js
setTimeout(() => { ... }, delay)
```
- **Decision**:
```js
    ✅ success → resolve("... with delay")
    ❌ failure → reject("... with delay")
```
### Example Message

```js
"Success: Data fetched after 2000ms"
"Error: Failed after 2000ms"
```

👉 Think: _Promise = async wrapper → success/failure message after delay._