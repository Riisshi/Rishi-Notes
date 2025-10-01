### 🔢 **Integers and Floating Point Numbers in Python**

- **Integers (int)** are whole numbers and are stored in binary format.
- **Floating point numbers (float)** are real numbers with a decimal point.
    - Represented using two parts:
        - **Mantissa**: the digits of the number.
        - **Exponent**: how much to shift the decimal point (like in scientific notation).
    - Called “floating point” because the decimal point can "float" or move.

---

### ⚙️ **Operations in Python**

- **Basic operations**: `+`, `-`, `*`, `/`
    - Mixing `int` and `float` results in a `float`.
    - Example: `7 / 2` → `3.5` (float even though both are ints).
- **Integer-specific operations**:
    - `//`: Integer division (quotient).
        
        - `9 // 5` → `1`
            
    - `%`: Modulo (remainder).
        
        - `9 % 5` → `4`
            
- **Power operation**: `**`
    
    - `3 ** 4` → `81` (3 to the power 4)
        
- **Advanced math** functions like `log`, `sqrt`, `sin`:
    
    - Must use: `from math import *`
        

---

### 🧠 **Variables and Types**

- In Python:
    - Variable **names don’t have fixed types**.
    - Type depends on the **value currently assigned**.
    - You can assign an `int` to `i`, then later assign a `float` to the same `i`.
- Use `type(variable)` to check the current type.

Example:


```python
i = 5             # int 
type(i)           # <class 'int'>  
j = 7.5           # float 
type(j)           # <class 'float'>  
i = 2 * j         # i becomes float 
type(i)           # <class 'float'>
```

> ⚠️ It's not good practice to change a variable’s type often – it makes the code hard to understand.

---

### ✅ **Boolean Values (`bool`)**

- Represent **truth values**: `True` and `False`
- Produced by **comparisons**:
    - `==`: equal
    - `!=`: not equal
    - `<`, `>`, `<=`, `>=`: comparison
- **Logical operations**:
    - `not`: negation
    - `and`: both must be true
    - `or`: at least one must be true

> Note: In Python, `or` is **inclusive**, meaning it is true if **one or both** conditions are true.

---

### 💡 **Using Boolean Logic in Code**

- You can assign Boolean expressions to variables:
    

Example:

```python
divisor = (m % n == 0)  # True if n divides m
```

- You can use one Boolean function to define another:

Example:

```python
def divides(m, n):     
	return n % m == 0  
def is_even(n):     
	return divides(2, n)  
def is_odd(n):     
	return not divides(2, n)
```

---

### 🔁 **Key Takeaways**

- Python uses **dynamic typing**: variable types are determined at runtime.
- Core types covered:
    - `int`: whole numbers
    - `float`: real numbers
    - `bool`: truth values
- Be cautious with type mixing and variable reuse.
- Understand how arithmetic and logical operations behave.