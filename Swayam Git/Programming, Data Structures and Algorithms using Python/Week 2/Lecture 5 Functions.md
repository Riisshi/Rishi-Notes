## 📘 Python Functions – Complete Notes

### 🧠 **What is a Function?**

- A **function** is a named block of code designed to perform a specific task.
- Helps organize code into reusable and logical sections.
- Functions are useful when a task is performed repeatedly with different inputs.

---
### 🛠️ **Defining a Function**

```python
def function_name(param1, param2, ...):     # Function body (indented)
return result  # (optional)
```

- Use `def` keyword.
- Parameters are input values passed to the function.
- `return` ends the function and optionally returns a result.

---

### 🧪 **Calling a Function**

```python
function_name(arg1, arg2, ...)
```
- Values passed become local names inside the function.
- Calling a function is like assigning values to parameters:

```python
    def power(x, n):     
	    ans = 1     
	    for i in range(n):         
		    ans *= x     
		return ans  
	power(3, 5)  # returns 243
```

---

### ♻️ **Mutability & Side Effects**

- **Immutable values** (e.g., int, str, float):
    - Changes inside the function **do not affect** the original value.
- **Mutable values** (e.g., list, dict):
    - Changes inside the function **can affect** the original value.

✅ _Example:_

```python
def update(l, i, v):     
if 0 <= i < len(l):        
	l[i] = v  # modifies original list         
	v += 1    # only affects local copy if v is immutable         
	return True     
return False
```

---
### 🔒 **Scope of Names**

- Variables defined **inside a function** are **local** to that function.
- Same name inside and outside are completely **independent**.

✅ _Example:_

```python
n = 7 def sample():     
	n = 17  # different 'n'     
	return n  
sample()  # returns 17 
print(n)  # still 7
```

---

### 🕰️ **Function Definitions Must Come Before Use**

- Python reads top to bottom.
- A function can call another defined **later** only if it is called **after that definition is encountered**.

✅ Valid:

```python
def f(x):     
	return g(x + 1) 
	 
def g(y):     
	return y + 3  
	
print(f(77))  # OK, g is defined before this call
```

❌ Invalid:

```python
def f(x):     
	return g(x + 1)  
	
print(f(77))  # Error: g not yet defined  

def g(y):     
	return y + 3
```

✅ **Tip**: Define all your functions first, then write your main logic.

---
### 🔁 **Recursive Functions**

- A function can call **itself** – this is called **recursion**.
- Needs a **base case** to stop infinite calls.

✅ _Example: Factorial_

```python
def fact(n):     
	if n <= 0:         
		return 1  # base case     
	return n * fact(n - 1)  # recursive call
	  
print(fact(3))  # returns 6
```

---
### 📌 **Summary**

|Concept|Key Point|
|---|---|
|Function purpose|Reusable computation block|
|`def` keyword|Used to define functions|
|`return` keyword|Ends function and returns value|
|Mutable vs Immutable|Mutable values can be changed inside functions|
|Variable scope|Function variables are local by default|
|Call before define|Ensure function is defined before being called|
|Recursion|Function calls itself, needs base case|
|Function with no `return`|Used for side-effects (e.g., printing messages)|