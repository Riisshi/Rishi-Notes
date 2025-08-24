# 📑 Study Notes — Pure & Impure Functions in JS

### 🎯 Learning Goals

- Define **Pure Function**
- Identify **Impure Function**
- Checklist for purity:
    - Same inputs → same outputs
    - No side effects
- Benefits of Pure Functions
- When & why to use Impure Functions

---

### 🧼 What is a Pure Function?

- **Definition:**  
    A function that always returns the same output for the same input and has **no side effects**.
    
- ✅ Properties:
    - Same inputs = same outputs
    - Doesn’t modify external state (no global variables, no DOM updates, no console logs)
    - Independent, predictable
- **Example:**
    
```js
function add(x, y) {
   return x + y;
} 
add(2, 3); // 5 add(2, 3); // 5 again ✅
```

---

### 😈 What’s NOT a Pure Function? (Impure)

- A function that **depends on external state** or **causes side effects**.
    
- 🔴 Examples:
    
    1. **Modifies global state**
        
```js
let counter = 0; 
function incrementCounter() {
   counter++; // touches global 
}
```
        
    2. **Randomness / logging**
        
```js
function rollDice() {
   return Math.ceil(Math.random() * 6); // unpredictable 
} 
function logMessage(msg) {
   console.log(msg); // side effect 
}
```

---

### 🌟 Why Pure Functions are Awesome

- **Predictable** → Same input, same output
- **Easy to test**
- **Debug-friendly** → No hidden bugs
- **Reusable**
- **Functional programming friendly**

---

### 💥 Are Impure Functions Always Bad?

- ❌ Not always. Sometimes they’re **necessary**:
    - Saving to a database
    - Logging errors
    - Updating UI
- ✅ Rule of thumb:
    - Use **pure functions** for business logic
    - Use **impure functions** for external interactions (API, DOM, DB)

---

### ✅ Quick Checklist

|Criteria|Pure Function|Impure Function|
|---|---|---|
|Same input → Same output|✅ Yes|❌ No|
|Modifies global variables|❌ No|✅ Yes|
|Side effects (logging, DOM, randomness)|❌ No|✅ Often|
|Easy to test|✅ Yes|⚠️ Sometimes|

---

### 🧽 Dishwasher Analogy

- Pure function = dishwasher → dirty dishes in, clean dishes out.
- You don’t want a dishwasher that sometimes throws forks at you 🥲

---

### 🎉 Key Takeaways

- Pure functions → predictable, reusable, easy to test.
- Impure functions → necessary for real-world interactions.
- Best practice → **keep core logic pure**; isolate impurity.

---

# 📝 Cheat Sheet — Pure vs Impure Functions

### ✅ Pure Function

- Same input → same output
- No side effects (no global state, DOM, logs)
- Easy to test

```js
const add = (x, y) => x + y;
```

### ❌ Impure Function

- Output may vary for same input
- Has side effects (global state, randomness, logs, DB)

```js
let c = 0; function inc() { c++; } // impure
```

### 🌟 Benefits of Pure Functions

- Predictable
- Testable
- Debug-friendly
- Reusable

### 💡 Rule

- Use **pure** for logic.
- Use **impure** for I/O (DB, API, UI).