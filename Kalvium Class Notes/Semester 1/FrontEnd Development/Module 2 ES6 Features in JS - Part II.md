# 📑 Study Notes: ES6 Features in JavaScript (Part II)

### 🌟 Learning Goals

By the end of this lesson, you’ll know:  
✅ Default Parameters  
✅ Spread & Rest Operators  
✅ Classes  
✅ Maps & Sets  
✅ Modules

---

### 1️⃣ Default Parameters

- Allow you to assign default values to function arguments if none are provided.
    
- Helps avoid `undefined` values and makes functions more robust.
    

```js
function greet(name = "friend", greeting = "Hi") {   console.log(`${greeting}, ${name}!`); 
}  
greet();               // "Hi, friend!" 
greet("Alice");        // "Hi, Alice!" 
greet("Bob", "Hello"); // "Hello, Bob!"
```

**Why useful?**  
✔ Prevents missing argument errors  
✔ Cleaner, safer functions

---

### 2️⃣ Spread & Rest Operators (`...`)

- **Spread (`...`)** → expands elements of arrays/objects.
    
- **Rest (`...`)** → collects multiple values into an array.
    

**Spread Example:**

```js
let numbers = [1, 2, 3]; 
let moreNumbers = [4, 5, 6]; 
let allNumbers = [...numbers, ...moreNumbers]; 
console.log(allNumbers); // [1, 2, 3, 4, 5, 6]
```

**Rest Example:**

```js
function sum(...numbers) {
   return numbers.reduce((total, num) => total + num, 0); 
} 
console.log(sum(1, 2, 3));      // 6 console.log(sum(4, 5, 6, 7));   // 22
```

**Why useful?**  
✔ Spread → copy/combine arrays or objects  
✔ Rest → handle unlimited arguments easily

---

### 3️⃣ Classes

- A cleaner syntax for creating objects and handling inheritance.
    

```js
class Person {
   constructor(name, age) {     
	   this.name = name;     
	   this.age = age;
   }
    introduce() {
         console.log(`Hi, I’m ${this.name}, and I’m ${this.age} years old.`);   
	} 
}  
let alice = new Person("Alice", 25); 
alice.introduce(); // "Hi, I’m Alice, and I’m 25 years old."
```

**Why useful?**  
✔ More organized, object-oriented code  
✔ Easier to maintain and extend

---

### 4️⃣ Maps and Sets

- **Map** → key-value pairs (keys can be any type).
    
- **Set** → collection of unique values.
    

**Map Example:**

```js
let userMap = new Map(); 
userMap.set("name", "Alice"); 
userMap.set("age", 25);  
console.log(userMap.get("name")); // "Alice" 
console.log(userMap.size);        // 2
```

**Set Example:**

```js
let numbers = new Set([1, 2, 2, 3]); 
console.log(numbers.size); // 3 (duplicates removed) 
console.log(numbers.has(2)); // true
```

**Why useful?**  
✔ Map → better than objects for dynamic key-value storage  
✔ Set → ensures uniqueness in collections

---

### 5️⃣ Modules

- Split code into multiple files and reuse them.
    

**Export Example:**

```js
// math.js
export function add(a, b) {
   return a + b;
}
```

**Import Example:**

```js
// main.js
import { add } from './math.js';
console.log(add(2, 3)); // 5
```

**Why useful?**  
✔ Cleaner, modular code  
✔ Easier collaboration & maintainability

---

### 📌 Summary / Key Takeaways

- **Default Parameters** → safer functions with default values.
    
- **Spread & Rest** → versatile use of `...` for expansion & grouping.
    
- **Classes** → structured, object-oriented programming in JS.
    
- **Maps & Sets** → efficient data structures for unique values and key-value pairs.
    
- **Modules** → break code into reusable, manageable files.
    

---

# 📝 Cheat Sheet: ES6 Features (Part II)

- **Default Parameters**
    
```js
function greet(name = "friend") { ... }
```
    
- **Spread & Rest**
    
    - Spread → `[...arr1, ...arr2]`
        
    - Rest → `function sum(...nums) {}`
        
- **Classes**
    
```js
class Person { constructor(n,a){...} }
```
    
- **Map & Set**
    
    - Map → `map.set("key", value)` / `map.get("key")`
        
    - Set → `new Set([1,2,3])` (unique only)
        
- **Modules**
    
    `export function f(){}   import { f } from './file.js';`
    

✅ ES6 Part II gives you **powerful tools** for cleaner, modular, and efficient JS!