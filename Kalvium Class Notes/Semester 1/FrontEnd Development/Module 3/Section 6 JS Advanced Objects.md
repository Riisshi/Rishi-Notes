# 📑 Study Notes — JS Advanced Objects

### 🎯 Learning Objectives

- Understand **prototypes** and how objects inherit
- Learn **prototypal inheritance** in JS
- Use **Object methods** (`keys`, `values`, `entries`, `assign`)
- Apply inheritance for cleaner, reusable code

---

### 🔗 The Prototype Chain: How Objects Inherit

- Every JS object has a hidden link to a **prototype**.
- If a property/method is missing → JS looks **up the chain**.
- **Analogy:** Backup plan → if I don’t know it, I’ll ask my parent.

**Example:**

```js
const animal = {
   speak: function() {
        return "I can make a sound";
    }
};
const dog = Object.create(animal);
dog.bark = function() {
   return "Woof!";
};
console.log(dog.bark());  // "Woof!" console.log(dog.speak()); // "I can make a sound"
```

✔️ `dog` inherits `speak` from `animal` via prototype chain.

---

### 👨‍👩‍👧 Prototypal Inheritance: Sharing Behavior

- Create objects that inherit from others using:
    - `Object.create()`
    - Constructor functions + `prototype`

**Constructor Example:**

```js
function Person(name) {
   this.name = name;
}  
Person.prototype.sayHello = function() {
   return `Hello, I'm ${this.name}`; 
};
const alice = new Person("Alice"); 
console.log(alice.sayHello()); // "Hello, I'm Alice"
```

✔️ All `Person` objects share **one copy** of `sayHello` → efficient memory use.

---

### ⚡ Useful Object Methods

- **`Object.keys(obj)`** → returns keys

```js
Object.keys({ name: "Leo", age: 21 }); // ["name", "age"]
```

- **`Object.values(obj)`** → returns values

```js
Object.values({ name: "Leo", age: 21 }); // ["Leo", 21]
```

- **`Object.entries(obj)`** → key-value pairs

```js
Object.entries({ name: "Leo", age: 21 }); // [["name","Leo"],["age",21]]
```

- **`Object.assign(target, source)`** → copy/merge objects

```js
Object.assign({}, { name: "Leo" }, { city: "Delhi" }); 
// { name: "Leo", city: "Delhi" }
```

---

### 🌍 Real-World Example: User Profiles

```js
const user = {
   login: function() {
        return `${this.name} has logged in`;
	} 
};  
const admin = Object.create(user); 
admin.name = "Admin"; 
admin.accessLevel = "super";  console.log(admin.login()); 
// "Admin has logged in"
```

✔️ Code reuse via **prototypal inheritance**.

---

### 🏋️ Interactive Exercises

1. Create a `car` object with `drive()`. Create `electricCar` inheriting `car` + `charge()`.
2. Use `Object.keys()` on `{ name: "Sara", role: "Student" }`.
3. Make `Book(title)` constructor + `describe()` method in its prototype → `"Title: <title>"`.

---

```embed
title: "Learn JavaScript OBJECTS in 7 minutes! 🧍"
image: "https://i.ytimg.com/vi/lo7o91qLzxc/maxresdefault.jpg"
description: "#JavaScript #tutorial #course // object = A collection of related properties and/or methods//                Can represent real world objects (people, produc..."
url: "https://youtu.be/lo7o91qLzxc"
favicon: ""
aspectRatio: "56.25"
```

### 🏆 Summary / Key Takeaways

- Prototypes = hidden link to parent object.
- Prototype chain = lookup path for missing properties.
- Inheritance → share methods without duplication.
- Object methods (`keys`, `values`, `entries`, `assign`) = quick inspection/manipulation.

---

# 📝 Cheat Sheet — JS Advanced Objects

### 🔗 Prototype

- Every object has a hidden `[[Prototype]]`.
- Lookup missing properties in parent.

`const child = Object.create(parent);`

---

### 👨‍👩‍👧 Inheritance

- **Constructor + prototype** = shared methods.

`function Person(name) { this.name = name; } Person.prototype.say = function() { return "Hi " + this.name; };`

---

### ⚡ Object Methods

- `Object.keys(obj)` → keys array
- `Object.values(obj)` → values array
- `Object.entries(obj)` → key-value pairs
- `Object.assign(t, s)` → merge objects

---

### 💡 Quick Uses

- Reuse methods via prototypes
- Extend objects without duplication
- Inspect/manipulate objects easily