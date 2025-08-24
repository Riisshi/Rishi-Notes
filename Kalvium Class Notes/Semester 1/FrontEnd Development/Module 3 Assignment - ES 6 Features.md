# 📑 ES6 Features – Assignment Recap

### ✅ Learning Outcomes Practiced

1. **Destructuring** (objects & arrays)
    
```js
const person = { name: "Alice", age: 25 }; 
const { name, age } = person;   // name = "Alice", age = 25
```
    
```js
const colors = ["red", "blue", "green", "yellow"]; 
const [firstColor, secondColor, ...otherColors] = colors;
// firstColor = "red", secondColor = "blue", otherColors = ["green", "yellow"]
```

---

2. **Template Literals**
    
```js
console.log(`Hi, I’m ${name} and I’m ${age} years old.`);
```

---

3. **Spread Operator**
    
```js
const arr1 = [1, 2, 3]; 
const arr2 = [4, 5, 6]; 
const combined = [...arr1, ...arr2];   // [1,2,3,4,5,6]
```

---

4. **Rest Parameter**
    
```js
function countArgs(...args) {
   return args.length;
} 
console.log(countArgs(1,2,3,4)); // 4
```

---

5. **Classes & Inheritance**
    
```js
class Book {
   constructor(title) {
        this.title = title;
   } 
}
class Manual extends Book {
   constructor(title, subject) {
        super(title);
		this.subject = subject;
	}
}  
class Novel extends Book {
   constructor(title, genre) {
        super(title);     
        this.genre = genre;
    }
}
```

---

### 📌 Key Takeaways

- **Destructuring** simplifies extraction from arrays/objects.
- **Template literals** make string formatting clean & readable.
- **Spread & Rest** use the same syntax (`...`) but opposite purposes (expand vs. collect).
- **Classes & subclasses** allow object-oriented programming in JS.
- **Always prefer `let` & `const`** with ES6 code.

---

# 📝 Cheat Sheet (Assignment-Focused)

- Object Destructuring:
    
```js
const {a, b} = obj;
```
    
- Array Destructuring:
    
```js
const [x, y, ...rest] = arr;
```
    
- Template Literals:
    
```js
`Hello, ${name}` 
```
    
- Spread:
    
    `[...arr1, ...arr2]`
    
- Rest:
    
    `function f(...args){}`
    
- Classes:
    
```js
class A { constructor(x) {this.x = x;} } 
class B extends A { constructor(x,y){ super(x); this.y = y; } }
```