# 🧠 Functional Programming – I (JavaScript)

## 🎯 Learning Objectives

- Transform arrays using **map()**.
- Use **this** keyword in object methods.
- Control context with **call(), apply(), bind()**.
- Implement **recursion** (factorial example).

---

## 📌 Key Concepts

### 1️⃣ **map() – Transform Arrays**

- Creates a **new array** by applying a function to each element.

```js
let nums = [1, 2, 3, 4]; 
let squares = nums.map(n => n * n); 
console.log(squares); // [1, 4, 9, 16]
```

---

### 2️⃣ **this in Object Methods**

- Inside an object method, `this` refers to the object itself.

```js
let person = {
   firstName: "John",   
   lastName: "Doe",   
   getName: function() {
        return this.firstName + " " + this.lastName;
	} 
}; 
console.log(person.getName()); // John Doe
```

---

### 3️⃣ **Controlling Context: call(), apply(), bind()**

- **call()** – invokes function, allows passing arguments one by one.
- **apply()** – same as call, but arguments as an array.
- **bind()** – creates a new function permanently bound to given object.

```js
function greet(greeting, symbol) {
   console.log(greeting + ", " + this.name + symbol);
}  
let user = { name: "Alice" };
greet.call(user, "Hello", "!");   // Hello, Alice! 
greet.apply(user, ["Hi", "!!"]);  // Hi, Alice!! 
let boundFn = greet.bind(user); 
boundFn("Hey", "!!!");            // Hey, Alice!!!
```

---

### 4️⃣ **Recursion – Factorial Example**

- Function calls itself until base case is met.

```js
function factorial(n) {
   if (n === 0)
    return 1;      // base case   
    return n * factorial(n - 1); // recursive call 
} 
console.log(factorial(5)); // 120
```

---

## 📝 Summary / Key Takeaways

- **map()**: Transforms arrays element-wise.
- **this**: Refers to the current object in methods.
- **call/apply/bind**: Control function execution context.
- **Recursion**: Breaks problem into smaller self-calls; requires base case.

---

# ⚡ Cheat Sheet (Quick-Glance)

👉 **map()** → `arr.map(fn)` → returns new array.  
👉 **this** → inside object method = current object.  
👉 **call()** → `fn.call(obj, arg1, arg2)`  
👉 **apply()** → `fn.apply(obj, [args])`  
👉 **bind()** → `let f = fn.bind(obj)` (permanent binding).  
👉 **Recursion** → base case + recursive call. Example: factorial.