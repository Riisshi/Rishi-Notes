# 📘 Study Notes: Fetching Data II (Crypto Price Tracker)

## 🎯 Learning Objectives

- Use **fetch() API** to get data from external sources.
- Handle **async/await** for asynchronous operations.
- Work with **JSON** responses.
- Dynamically **update the DOM** with fetched data.
- Use **Axios** for API calls.
- Implement **error handling**.
- Validate code using **Jasmine test cases**.

---

## 🏗️ Assignment Overview

- Build a **Crypto Price Tracker**.
- HTML & CSS provided, only **JavaScript logic** required.
- Fetch **real-time Bitcoin & Ethereum prices** using the **CoinGecko API**.
- Update prices in the UI dynamically.

API Endpoint:

```http
https://api.coingecko.com/api/v3/simple/price?ids=bitcoin,ethereum&vs_currencies=usd
```

---

## ⚡ Steps to Implement

### 1. Fetch with `fetch()`

```js
async function fetchWithFetch() {
	try {     
		const response = await fetch
		("https://api.coingecko.com/api/v3/simple/price?ids=bitcoin,ethereum&vs_currencies=usd");
	if (!response.ok) throw new Error("API Error: " + response.status);
		const data = await response.json();
		const bitcoinPrice = data.bitcoin.usd;           
		const ethereumPrice = data.ethereum.usd;      // update UI     
		document.getElementById("btc-price").textContent = `$${bitcoinPrice}`;     
		document.getElementById("eth-price").textContent = `$${ethereumPrice}`;
} 
catch (error) {
	console.error("Error fetching with fetch:", error);   
	} 
}
```

---

### 2. Fetch with `Axios`

```js
async function fetchWithAxios() {
	try {     
		const response = awaitaxios.get
		("https://api.coingecko.com/api/v3/simple/price?ids=bitcoin,ethereum&vs_currencies=usd"
		);
		const bitcoinPrice = response.data.bitcoin.usd;     
		const ethereumPrice = response.data.ethereum.usd;      // update UI
		document.getElementById("btc-price").textContent = `$${bitcoinPrice}`;     
		document.getElementById("eth-price").textContent = `$${ethereumPrice}`;   
	} 
	catch (error) {
		console.error("Error fetching with Axios:", error);   
	} 
}
```

---

## 🚨 Error Handling

- Always check if response is **ok** (`response.ok`).
- Use `try...catch` for both Fetch & Axios.
- Show fallback/error messages in UI if API fails.

---

## ✅ Testing

- Jasmine tests will verify:
    - API call success.
    - Correct JSON handling.
    - UI updates with actual prices.
    - Error handling.

---

# 📌 Cheat Sheet

- **Fetch Syntax**
    
```js
fetch(url)   
	.then(res => res.json())   
	.then(data => console.log(data))   
	.catch(err => console.error(err));
```
    
- **Fetch with async/await**
    
```js
const res = await fetch(url); 
const data = await res.json();
```
    
- **Axios Syntax**
    
```js
axios.get(url)   
	.then(res => console.log(res.data))   
	.catch(err => console.error(err));
```
    
- **Axios with async/await**
    
```js
const res = await axios.get(url); 
console.log(res.data);
```
    
- **Key Differences**
    - Fetch → must convert `.json()`.
    - Axios → auto-parses JSON.
    - Axios supports **older browsers** + easier config.