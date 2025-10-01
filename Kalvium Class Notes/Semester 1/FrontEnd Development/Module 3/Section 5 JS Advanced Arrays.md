# 📑 Study Notes — JS Advanced Arrays (map, filter, reduce)

### 🎯 Learning Objectives

- Understand **map** for transforming arrays
- Use **filter** for selecting specific elements
- Apply **reduce** for aggregating data
- Solve real-world problems with these methods

---
![[Pasted image 20250825002531.png]]
### 🔄 `map()` → Transforming Arrays

- **Definition:** Creates a **new array** by applying a function to each element.
- Does **not** modify the original array.
- 🛠️ Use when you want to **transform data** but keep the structure.
- **Analogy:** Transformation belt — items go in, get modified, come out new.

**Example:**

```js
const numbers = [1, 2, 3, 4, 5];
 const doubled = numbers.map(num => num * 2); 
 console.log(doubled); // [2, 4, 6, 8, 10]

```
---

### 🚪 `filter()` → Selecting Elements

- **Definition:** Creates a new array with elements that pass a condition.
- Returns only elements for which the function returns **true**.
- **Analogy:** Bouncer at the door — only valid elements get in.

**Example:**

```js
const numbers = [1, 2, 3, 4, 5, 6]; 
const evens = numbers.filter(num => num % 2 === 0); 
console.log(evens); // [2, 4, 6]
```

---

### 🍲 `reduce()` → Aggregating Data

- **Definition:** Reduces an array to a **single value**.
    
- Takes two arguments:
    
    1. **Reducer function** (accumulator, element)
    2. **Initial value**
- **Analogy:** Cooking pot — keep adding and mixing until one final dish.
    

**Example:**

```js
const numbers = [1, 2, 3, 4, 5]; 
const sum = numbers.reduce((acc, num) => acc + num, 0); 
console.log(sum); // 15
```

---

### 📊 Real-World Example: Average Grade

```js
const students = [
	{ name: "Alice", grade: 90 },
	{ name: "Bob", grade: 80 },   
	{ name: "Charlie", grade: 70 },   
	{ name: "David", grade: 60 }
];  
const total = students.reduce((acc, s) => acc + s.grade, 0);
const average = total / students.length; 
console.log(average); // 75
```

---

### 🎨 Interactive Practice

- `map`: `["hi", "hello"] → [2, 5]` (string lengths)
- `filter`: `[3, 7, 2, 9, 5] → [7, 9]` (numbers > 5)
- `reduce`: `[{price: 10}, {price: 20}] → 30` (total price)

---
```embed
title: "How to use map() filter() reduce() | JavaScript Array Methods Tutorial"
image: "https://i.ytimg.com/vi/PojpwEbOQJg/maxresdefault.jpg"
description: "Most important Array Methods Explained for Beginners | Learn Map, Filter, Reduce in JavaScript with Examples | Use array methods instead of foreach.Become a ..."
url: "https://youtu.be/PojpwEbOQJg"
favicon: ""
aspectRatio: "56.25"
```

### 🏆 Summary / Key Takeaways

- `map`: 🔄 Transform elements → returns new array
- `filter`: 🚪 Keep elements passing a condition → new array
- `reduce`: 🍲 Condense array → single value
- Together → cleaner, shorter, more powerful array code

---

# 📝 Cheat Sheet — JS Advanced Arrays

### 🔄 `map()`

- Transforms each element → new array

```js
arr.map(x => x * 2);
```

### 🚪 `filter()`

- Keeps elements passing condition → new array

```js
arr.filter(x => x > 5);
```

### 🍲 `reduce()`

- Combines all → single value

```js
arr.reduce((acc, x) => acc + x, 0);
```

### 💡 Quick Uses

- `map` → transform (double, string length, etc.)
- `filter` → select (evens, > 5, matches condition)
- `reduce` → aggregate (sum, average, total price)