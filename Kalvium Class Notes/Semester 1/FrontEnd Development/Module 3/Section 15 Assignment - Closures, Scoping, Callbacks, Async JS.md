# 📘 Study Notes – Closures, Scoping, Callbacks & Async JS (Task Scheduler Assignment)

## 🔑 Concepts Applied

- **Closures** → Used to create isolated task counters without global variables.
- **Scoping** → Keeps task-related variables private and prevents pollution of the global scope.
- **Callbacks** → Functions executed when a task finishes (e.g., notify user).
- **Async JS (setTimeout)** → Simulates task execution delay.

---

## 🛠 Features of the Task Scheduler

- User inputs **task name** + **delay (ms)**.
- Task is added to the list and runs after the delay.
- Uses closure to **keep track of tasks** (no global task count).
- When completed → triggers a **callback** + updates DOM log.
- DOM updates in real-time (Task added ✅ → Task completed 🎉).

---

## ⚙️ How It Works

1. **Closure for Task Counter**
    
```js
function taskManager() {   
	let count = 0;
	return function () {
	     count++;
		return count;
	}; 
} 
let getTaskId = taskManager();
console.log(getTaskId()); // 1 
console.log(getTaskId()); // 2
```
    
    - Keeps `count` private.
    - Each new task gets its own ID.
        
2. **Adding a Task**
    
```js
function addTask(name, delay, callback) {
   console.log(`Task added: ${name} (Delay: ${delay}ms)`);   
   setTimeout(() => {
        console.log(`Task completed: ${name}`);
		callback();
}, delay); }
```
    
3. **Callback Example**
    
```js
function notify() {
   console.log("✅ Callback: Task finished!"); 
}  
addTask("Drink Water", 2000, notify);
```

---

## 💡 Real-World Application

- Task scheduling in productivity apps.
- Background jobs (e.g., reminders, notifications).
- Delayed UI updates.

---

## 📝 Summary / Key Takeaways

- **Closures** → Private state management.
- **Scoping** → Protects variables from leaking globally.
- **Callbacks** → Run after async operation is finished.
- **Async JS (setTimeout)** → Enables non-blocking task scheduling.
- **DOM Updates** → Essential for showing real-time logs.

---

# ⚡ Cheat Sheet – Closures, Callbacks & Async (Task Scheduler)

- **Closure:**
```js
function counter() { let c=0; return ()=> ++c; }   
```
- **Callback:** Function passed to another → runs after task finishes.
    
- **setTimeout:**
    
```js
setTimeout(()=>console.log("done"),2000);
```
    
- **Task Example:**
    
```js
function addTask(task, delay, cb){
   setTimeout(()=>{ console.log(task); cb(); }, delay); }
```
    
- **Key Uses:** Timers ⏳, Events 🎯, API calls 🌐.