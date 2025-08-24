# 📘 Study Notes + Cheat Sheet

### JavaScript – Arrays & Higher-Order Functions

---

## 🔹 What are Higher-Order Functions?

- A **higher-order function (HOF)** is any function that:
    - **Takes another function as input** (callback).
    - **Returns a function as output**.
- Examples: `map`, `filter`, `reduce`

👉 Think of them as "functions that manage functions."

---

## 🔹 map, filter, reduce – Core HOFs

### 1. `map()` → **Transform each element**

- Returns a **new array** with modified elements.
- Does **not change** the original array.

```js
const numbers = [1, 2, 3]; 
const doubled = numbers.map(n => n * 2); 
console.log(doubled); // [2, 4, 6]
```

💡 Use when: you want to **change every element**.

---

### 2. `filter()` → **Select some elements**

- Returns a **new array** with elements that pass a test (condition).

```js
const numbers = [1, 2, 3, 4, 5]; 
const evens = numbers.filter(n => n % 2 === 0); 
console.log(evens); // [2, 4]
```

💡 Use when: you want to **remove unwanted items**.

---

### 3. `reduce()` → **Condense to one value**

- Applies a function to each element + accumulator → single result.

```js
const numbers = [1, 2, 3, 4]; 
const sum = numbers.reduce((acc, n) => acc + n, 0); 
console.log(sum); // 10
```

💡 Use when: you want a **summary/aggregate** (sum, product, avg, max, etc).

---

## 🔹 Writing Your Own Higher-Order Functions

### 1. Passing Functions as Arguments

```js
function greet(name) {
   return "Hello, " + name;
}  
function processUserInput(callback) {
	const user = "Aditi";
	return callback(user);
}  
console.log(processUserInput(greet));  // Hello, Aditi
```

---

### 2. Returning Functions

```js
function multiplier(factor){
	return function(num) {
	return num * factor;
	};
}  
const double = multiplier(2); 
console.log(double(5)); // 10
```

---

### 3. Decorating/Enhancing Functions

```js
function withLogging(fn) {
   return function(...args) {
        console.log("Calling...");     
        const result = fn(...args);     
        console.log("Result:", result);     
        return result;   
    }; 
}  
const add = (a, b) => a + b;
const loggedAdd = withLogging(add);
loggedAdd(3, 4); // Logs calls + result
```

---

## 🔹 Real-World Example

### Average grade (using reduce):

```js
const students = [
	{ name: "Alice", grade: 90 },
	{ name: "Bob", grade: 80 },
	{ name: "Charlie", grade: 70 },
];  
const total = students.reduce((acc, s) => acc + s.grade, 0); 
const avg = total / students.length; console.log(avg); // 80
```

---

## 🔹 Quick Exercises

✅ `map` → String lengths

```js
["hi", "hello"].map(str => str.length); // [2, 5]
```

✅ `filter` → Numbers > 5

```js
[3, 7, 2, 9, 5].filter(n => n > 5); // [7, 9]
```

✅ `reduce` → Total price

```js
[{price: 10}, {price: 20}].reduce((acc, obj) => acc + obj.price, 0); // 30
```

✅ Custom HOFs

- `repeat(fn, n)` → run fn n times.
- `makeGreeting(msg)` → returns a greeter function.
- `applyTwice(fn, val)` → applies function 2 times.

---

```embed
title: "Higher Order Function | javascript interview series"
image: "https://i.ytimg.com/vi/E7WIis2NjZU/maxresdefault.jpg"
description: "Welcome to a youtube channel dedicated to programming and coding related tutorials. We talk about tech, write code, discuss about cloud and devops. That’s wh..."
url: "https://youtu.be/E7WIis2NjZU"
favicon: ""
aspectRatio: "56.25"
```

# 🎯 Summary Cheat Sheet

|Method / Concept|What it Does|Example|
|---|---|---|
|`map()`|Transform each element → new array|`[1,2,3].map(n=>n*2) → [2,4,6]`|
|`filter()`|Select elements that pass condition|`[1,2,3,4].filter(n=>n%2===0) → [2,4]`|
|`reduce()`|Condense into one value|`[1,2,3].reduce((a,n)=>a+n,0) → 6`|
|HOF (pass fn)|Accepts function as argument|`arr.map(fn)`|
|HOF (return fn)|Returns new function|`multiplier(2)(5) → 10`|
|Decorator|Wraps fn with extra behavior|`withLogging(fn)`|

---

⚡ With **map, filter, reduce** + HOF basics, you can write **clean, powerful, reusable JS code** like a pro.