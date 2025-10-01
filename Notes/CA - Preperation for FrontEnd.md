# 📘 JavaScript Master Revision Chart

---

## 1. **ES6 Features (Part I)**

|**Concept**|**Explanation**|**Code Example**|**MCQs / Practice**|
|---|---|---|---|
|`let` & `const`|`let`: block scoped, can be reassigned  <br>`const`: block scoped, cannot be reassigned|`js let x = 10; const y = 20;`|Q: Which is block-scoped?  <br>a) var b) let c) const  <br>✅ Ans: b & c|
|Template Literals|Use backticks `` and `${}` for variables|``js let name = "Rishi"; console.log(`Hello ${name}`);``|Q: What will `` `2+2=${2+2}` `` print? ✅ Ans: 2+2=4|
|Arrow Functions|Shorter syntax for functions|`js let add = (a,b) => a+b; console.log(add(2,3));`|Q: Arrow functions automatically bind `this`? ✅ Ans: Yes|
|Default Parameters|Give default values to function args|`js function greet(name="User"){ console.log("Hi "+name); } greet();`|Q: Output of `greet("Rishi")`? ✅ Ans: Hi Rishi|

---

## 2. **ES6 Features (Part II)**

|**Concept**|**Explanation**|**Code Example**|**MCQs / Practice**|
|---|---|---|---|
|Destructuring|Extract values from arrays/objects|`js let [a,b] = [1,2]; let {name} = {name:"Rishi"};`|Q: Output of `let [x,,y]=[1,2,3]`? ✅ Ans: x=1, y=3|
|Spread `...`|Expands arrays/objects|`js let arr=[1,2]; let arr2=[...arr,3];`|Q: `Math.max(...[2,5,1])` = ? ✅ Ans: 5|
|Rest `...`|Collects remaining args|`js function sum(...nums){ return nums.reduce((a,b)=>a+b); }`|Q: `sum(1,2,3)` = ? ✅ Ans: 6|
|Classes|OOP in JS|`js class Car{ constructor(name){ this.name=name; } } let c=new Car("BMW");`|Q: What keyword is used to create objects from classes? ✅ Ans: `new`|

---

## 3. **Pure vs Impure Functions**

|**Concept**|**Explanation**|**Code Example**|**MCQs / Practice**|
|---|---|---|---|
|Pure Function|Same input → same output, no side effects|`js function add(a,b){ return a+b; }`|Q: Is `Math.random()` pure? ✅ Ans: No|
|Impure Function|Depends on external state, has side effects|`js let x=10; function impure(y){ return x+y; }`|Q: Why impure? ✅ Ans: Uses external `x`|

---

## 4. **Advanced Arrays**

|**Method**|**Explanation**|**Code Example**|**Practice**|
|---|---|---|---|
|`map()`|Transforms each element|`[1,2,3].map(x=>x*2)` → `[2,4,6]`|Q: What does `[1,2,3].map(x=>x+1)` return? ✅ `[2,3,4]`|
|`filter()`|Keeps elements that match condition|`[1,2,3,4].filter(x=>x%2==0)` → `[2,4]`|Q: Keep odd nums from `[5,6,7]`? ✅ `[5,7]`|
|`reduce()`|Reduces array to single value|`[1,2,3].reduce((a,b)=>a+b,0)` → `6`|Q: Sum of `[4,5,6]`? ✅ `15`|

---

## 5. **Advanced Objects & Prototypes**

|**Concept**|**Explanation**|**Code Example**|**Practice**|
|---|---|---|---|
|Object.keys / values|Get keys / values of object|`js let obj={a:1,b:2}; console.log(Object.keys(obj));`|Q: Keys of `{x:10,y:20}`? ✅ `[ "x","y" ]`|
|Prototype|Objects inherit from prototype|`js function Person(name){ this.name=name; } Person.prototype.greet=function(){ return "Hi "+this.name; }`|Q: Prototype used for? ✅ Reuse methods|

---

## 6. **Higher Order Functions (HOFs)**

|**Concept**|**Explanation**|**Code Example**|**Practice**|
|---|---|---|---|
|HOF|Function that takes/returns another function|`js function hof(fn){ return fn(5); } hof(x=>x*2);`|Q: Is `map()` HOF? ✅ Yes|

---

## 7. **Recursion**

|**Concept**|**Explanation**|**Code Example**|**Practice**|
|---|---|---|---|
|Recursion|Function calls itself|`js function fact(n){ return n<=1?1:n*fact(n-1); }`|Q: `fact(3)` = ? ✅ 6|

---

## 8. **Anonymous Functions & IIFEs**

|**Concept**|**Explanation**|**Code Example**|**Practice**|
|---|---|---|---|
|Anonymous|Function without name|`js setTimeout(function(){console.log("Hi")},1000);`|Q: Is `()=>{}` anonymous? ✅ Yes|
|IIFE|Runs immediately|`js (function(){console.log("Run now!")})();`|Q: Purpose of IIFE? ✅ Avoid polluting scope|

---

## 9. **Event Loop**

|**Concept**|**Explanation**|**Code Example**|**Practice**|
|---|---|---|---|
|Event Loop|Handles async tasks by queue|`js console.log("A"); setTimeout(()=>console.log("B"),0); console.log("C");` → A C B|Q: Output order? ✅ A C B|

---

## 10. **Closures & Scope**

|**Concept**|**Explanation**|**Code Example**|**Practice**|
|---|---|---|---|
|Closure|Function remembers outer vars|`js function outer(){ let x=10; return function(){ return x; } } let f=outer(); console.log(f());`|Q: Output? ✅ 10|

---

## 11. **Callbacks & Async JS**

|**Concept**|**Explanation**|**Code Example**|**Practice**|
|---|---|---|---|
|Callback|Function passed as arg|`js function greet(cb){ cb("Hi"); } greet(msg=>console.log(msg));`|Q: What is callback hell? ✅ Nested callbacks|

---

## 12. **Promises**

|**Concept**|**Explanation**|**Code Example**|**Practice**|
|---|---|---|---|
|Promise|Handles async tasks, has `resolve` & `reject`|`js let p=new Promise((res,rej)=>res("Done")); p.then(msg=>console.log(msg));`|Q: States of Promise? ✅ Pending, Fulfilled, Rejected|

---

## 13. **Fetch & Axios**

| **Concept** | **Explanation**                | **Code Example**                                                       | **Practice**                                  |
| ----------- | ------------------------------ | ---------------------------------------------------------------------- | --------------------------------------------- |
| Fetch       | Built-in API for HTTP requests | `js fetch("url").then(res=>res.json()).then(data=>console.log(data));` | Q: Fetch returns what? ✅ A Promise            |
| Axios       | External library for HTTP      | `js axios.get("url").then(res=>console.log(res.data));`                | Q: Axios vs Fetch? ✅ Axios simpler, auto JSON |