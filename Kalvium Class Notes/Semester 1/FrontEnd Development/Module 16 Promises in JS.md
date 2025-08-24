# 📘 Study Notes: **Promises in JavaScript**

### 🔑 Learning Objectives

- Understand **what a Promise is** and why it exists.
- Learn the **3 states of a Promise**.
- Use `.then()`, `.catch()`, `.finally()` to handle results.
- Rewrite **callback-based async code** using Promises.
- Simulate real-world async flows (e.g., data fetching, login).

---

## 📌 What is a Promise?

- A **Promise** represents a value that may be available:
    - **now**,
    - **later**,
    - or **never**.

👉 Think of it as an **online order**:

- **Pending:** Order placed.
- **Fulfilled:** Order delivered.
- **Rejected:** Delivery failed.

✔ Helps manage async operations with **cleaner syntax** compared to callbacks.

---

## 📌 Promise States

1. **Pending** – initial state.
2. **Fulfilled** – operation succeeded.
3. **Rejected** – operation failed.

➡️ Use `.then()` for success, `.catch()` for errors.

---

## 📌 Creating a Promise

```js
const myPromise = new Promise((resolve, reject) => {
   const success = true;
	setTimeout(() => {
	     if (success) {
	        resolve("Data fetched!");
		} else {
		    reject("Failed to fetch data.");     
		}   
	}, 2000);
});  
myPromise   
	.then(result => console.log(result))   // success   
	.catch(error => console.log(error));   // error

```
**Explanation:**

- `resolve()` → called on success.
- `reject()` → called on failure.
- `.then()` → runs if resolved.
- `.catch()` → runs if rejected.

---

## 📌 Real-World Example: Login

```js
function login(username, password) {   
	return new Promise((resolve, reject) => {
	     setTimeout(() => {
			if (username === "admin" && password === "1234") {
				resolve("Login successful!");
			}
			else {
				reject("Invalid credentials.");       
			}
		}, 1500);   
	}); 
}  
login("admin", "1234")   
	.then(message => console.log(message))   // "Login successful!"   
	.catch(err => console.log(err));
```

---

## 📌 Using `.finally()`

- Runs **always** (after resolve/reject).
- Good for cleanup (e.g., hiding loaders).

```js
myPromise   
	.then(result => console.log(result))   
	.catch(error => console.log(error))   
	.finally(() => console.log("Promise completed"));
```

---

## 📌 Chaining Promises

- Avoids "callback hell" (pyramid of doom).

```js
getUser()
	.then(user => getPosts(user.id))
	.then(posts => displayPosts(posts))
	.catch(error => console.error("Error:", error));
```
---

## 📝 Interactive Practice

1. Create a Promise that resolves with `"Loaded!"` after **1s**.
2. Write `fetchData()` → randomly resolves or rejects.
3. Chain 3 `.then()` calls:
    - simulate loading,
    - transform data,
    - log result.

---
```embed
title: "What are JavaScript PROMISES? 🤞"
image: "https://i.ytimg.com/vi/NOzi4wBHn0o/maxresdefault.jpg"
description: "#JavaScript #tutorial #courses // Promise = An Object that manages asynchronous operations.//                    Wrap a Promise Object around {asynchronous c..."
url: "https://youtu.be/NOzi4wBHn0o"
favicon: ""
aspectRatio: "56.25"
```

# ⚡ Cheat Sheet: Promises in JS

|Concept|Syntax / Usage|
|---|---|
|Create a Promise|`new Promise((resolve, reject) => {...})`|
|Resolve|`resolve(value)`|
|Reject|`reject(error)`|
|Handle success|`.then(result => {...})`|
|Handle error|`.catch(err => {...})`|
|Always run cleanup|`.finally(() => {...})`|
|States|`pending`, `fulfilled`, `rejected`|
|Chaining|`.then(...).then(...).catch(...)`|

---

✅ **Key Takeaway:**  
Promises = Cleaner async code → **no nesting, easier to read/debug, real-world ready**.