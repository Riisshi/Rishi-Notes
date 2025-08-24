# 📘 Study Notes: JS API – Fetch & Axios

### 🎯 Learning Objectives

- Understand what an **API** is.
- Use **Fetch API** for GET requests.
- Handle **JSON responses** & errors.
- Use **Axios** for simpler requests.
- Practice fetching & displaying real data.

---

### 🔑 What is an API?

- **API = Application Programming Interface**.
- Acts like a _messenger_ between apps & servers.
- Analogy: Ordering food online → request (order) → server → response (food).

---

### 🚀 Fetch API (Built-in)

- Returns a **Promise**.

```embed
title: "API Tutorial - Fetch Data with Axios - (Example in React)"
image: "https://i.ytimg.com/vi/bMRrSqWFKqM/maxresdefault.jpg"
description: "Tutorial on how to make API calls to fetch data using axios. I'm using React in this example, but you'll know how to use axios anywhere 👍.Hope it helps! Fee..."
url: "https://youtu.be/bMRrSqWFKqM"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "Learn Fetch API In 6 Minutes"
image: "https://i.ytimg.com/vi/cuEtnrL9-H0/maxresdefault.jpg"
description: "Accessing data from an API is one of the most common things you will do in web development, and the way to access APIs is with fetch. Fetch is function built..."
url: "https://youtu.be/cuEtnrL9-H0"
favicon: ""
aspectRatio: "56.25"
```


#### Example: Single Item

```js
fetch("https://jsonplaceholder.typicode.com/posts/1")
	.then(response => response.json())   
	.then(data => {
		console.log("Post Title:", data.title);
	})   
	.catch(error => {     
		console.error("Error fetching data:", error);   
	});
```

👉 Steps:

1. `fetch(url)` → sends request.
2. `.json()` → convert response → JS object.
3. `.then(data)` → use data.
4. `.catch(error)` → handle error.

#### Example: Multiple Items

```js
fetch("https://jsonplaceholder.typicode.com/posts")
	.then(res => res.json())
	.then(posts => {
	posts.forEach(post => console.log(post.title));
	});
```

👉 Great for blogs, products, lists.

---

### ⚡ Axios (Library)

- Must include via CDN or npm.
- Simpler, works in old browsers, auto-parses JSON.

#### Example:

```js
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>

axios.get("https://jsonplaceholder.typicode.com/posts/1")   
	.then(response => {
		console.log("Post Title:", response.data.title);
	})   
	.catch(error => {
		console.error("Error fetching with Axios:", error);
	});
```

👉 Differences:

- Data inside `response.data`.
- Easier for **headers, POST, error handling**.

---

### 🌍 Real-world Example

```js
fetch("https://jsonplaceholder.typicode.com/users")   
	.then(res => res.json())   
	.then(users => {
		users.forEach(user => {
			console.log(`${user.name} - ${user.email}`);
		});
	});
```

Use case: Team members, students, customers.

---

### 📦 Common API Request Types

- **GET** → Fetch data.
- **POST** → Send new data.
- **PUT / PATCH** → Update data.
- **DELETE** → Remove data.

Both Fetch & Axios support these.

---

### 🧩 Interactive Exercise Ideas

1. Fetch all users → log usernames.
2. Axios → fetch post by ID → print title.
3. Fetch with wrong URL → custom error message.
4. Bonus: Create **search bar** → fetch posts by keyword.

---

### 📌 Summary

- APIs let JS talk to servers.
- **Fetch API**: built-in, Promise-based.
- **Axios**: simpler, more powerful, older browser support.
- Both support GET, POST, PUT, DELETE.
- Essential for **real-world, dynamic apps**.

---

# ⚡ Cheat Sheet: Fetch vs Axios

### Fetch (built-in)

```js
fetch(url)   
	.then(res => res.json())   
	.then(data => console.log(data))   
	.catch(err => console.error(err));
```

### Axios (library)

```js
axios.get(url)   
	.then(res => console.log(res.data))   
	.catch(err => console.error(err));
```

### Quick Differences

|Feature|Fetch|Axios|
|---|---|---|
|Built-in?|✅ Yes|❌ Needs install|
|Response data|`res.json()` needed|`res.data` ready|
|Browser support|Modern only|Works everywhere|
|Extras|Basic only|Easy headers, POST, interceptors|

👉 Rule of thumb: Use **Fetch** for simple tasks, **Axios** for bigger apps.