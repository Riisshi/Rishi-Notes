# ✅ Python Control Flow – Summary Notes

---

## 🔁 1. **Top-Down Execution (Default Behavior)**

- Python executes statements **line by line**, from **top to bottom**.
- Function definitions are **parsed** but only **executed when called**.

---

## 🔀 2. **Conditional Execution**

### 🔸 `if`, `elif`, `else`

Used to **choose between alternate paths** based on conditions.

```python
if condition1:     
# block1 
elif condition2:     
# block2 
else:     
# fallback block
```

- `if`: Checks the first condition.
- `elif`: Checks other conditions **only if previous ones failed**.
- `else`: Optional. Executes when **no conditions match**.
- Avoids deep nesting of `if-else` statements → keeps code readable.

### ✅ Boolean Values in Conditions:

Python treats values like:

- `0`, `''`, `[]`, `None` → `False`
- Non-zero / Non-empty → `True`

```python
if m % n:  # True if remainder ≠ 0    
m, n = n, m % n
```

---

## 🔁 3. **Loops: Repetition Structures**

### 🔸 `for` Loop – Fixed Repetition

Used when you know **how many times** to repeat.

```python
for i in [1, 2, 3]:     do_something(i)
```

#### ✅ `range()` Function

Generates a sequence of numbers:

- `range(n)` → 0 to n-1
- `range(a, b)` → a to b-1
- Can include step: `range(a, b, step)`

```python
for i in range(1, n+1):  # to include n     
	if n % i == 0:         
		flist += [i]
```

#### 📌 Example: Finding Factors

```python
def factors(n):     
	flist = []     
	for i in range(1, n + 1):        
		 if n % i == 0:            
			  flist += [i]    
	return flist
```

---

### 🔸 `while` Loop – Conditional Repetition

Used when you **don’t know how many times** to repeat.

```python
while condition:     # keep repeating while condition is True
```

- Body is executed **only while** the condition is true.
- You must ensure the loop **eventually ends**, or it becomes **infinite**.

#### 📌 Example: GCD with `while`

```python
def gcd(m, n):     
	if m < n:        
		m, n = n, m    
	while m % n != 0:         
		m, n = n, m % n     
	return n

```
Or shorter:
```python
while m % n:     m, n = n, m % n
```

---
## 🔚 Summary of Python Control Flow

|Type|Purpose|Example|
|---|---|---|
|`if`|Condition-based execution|`if x > 0:`|
|`elif`|Multiple conditions|`elif x == 0:`|
|`else`|Fallback when no conditions match|`else:`|
|`for`|Fixed number of repetitions|`for i in range(n)`|
|`while`|Repeat while a condition is true|`while x != 0:`|