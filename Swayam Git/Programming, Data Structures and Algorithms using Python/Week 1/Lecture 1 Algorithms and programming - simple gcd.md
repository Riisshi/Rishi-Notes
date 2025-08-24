## 📘 **Lecture 1: Introduction to Programming, Algorithms, and GCD Example**

### 🔹 **What is an Algorithm?**

- A **step-by-step** procedure to solve a problem (like a recipe).
- Must be:
    - **Unambiguous**
    - **Finite** (ends after some steps)
    - **Effective** (produces result)
- Can be executed by:
    - **Humans** (e.g., arranging a hall)
    - **Machines** (e.g., computer programs)

### 🔹 **What is Programming?**

- Writing algorithms in a **programming language**.
- A **program** is an implementation of an algorithm.
- Programming languages help:
    - Express conditional & repetitive steps.
    - Handle **data** (inputs, outputs, collections).

---

### 🔹 **Real-life Examples of Algorithms**

- Computing `x^y`, square root of `x`, or long division.
- Sorting data in spreadsheets.
- Finding shortest/cheapest flights on booking sites (optimization).
- Spell checking in word processors.
- Playing games like Sudoku, chess.

✅ These all involve **data manipulation** → require both **algorithms** and **data structures**.

---

## 🔸 **GCD (Greatest Common Divisor) - Problem Overview**

- **Definition**: Largest number that divides both `m` and `n`.
- Example:
    - `gcd(8, 12)` = 4
    - `gcd(18, 25)` = 1

💡 **Observation**: GCD always exists because **1 divides every number**.

---

### 🔹 **Naive GCD Algorithm (Conceptual Steps)**

1. List all **factors of `m`**.
2. List all **factors of `n`**.
3. Find the **largest common factor**.

📌 This is **correct but not efficient** (we will improve it in future).

---

### 🔹 **Example: GCD of 14 and 63**

- Factors of 14: `1, 2, 7, 14`
- Factors of 63: `1, 3, 7, 9, 21, 63`
- Common: `1, 7`
- **GCD = 7**

---

## 🔸 **Python Program for GCD (Naive Way)**


```python
def gcd(m, n):
    fm = []  # Factors of m
    for i in range(1, m + 1):
        if m % i == 0:
            fm.append(i)

    fn = []  # Factors of n
    for j in range(1, n + 1):
        if n % j == 0:
            fn.append(j)

    cf = []  # Common factors
    for f in fm:
        if f in fn:
            cf.append(f)

    return cf[-1]  # Last element = GCD

```

---

### 🔹 **Python Concepts Used**

- **`def`**: Define a function.

- **`range(a, b)`**: From `a` to `b-1`.

- **`%` operator**: Returns remainder (used to check divisibility).

- **Lists**:
    
    - Empty list: `[]`
        
    - Add element: `.append()`
        
- **Negative index**:
    
    - `cf[-1]` returns **last element** of list `cf`.
        

---

### 🧠 Key Takeaways / Concepts Introduced

|Concept|Meaning / Use|
|---|---|
|**Algorithm**|Step-by-step method to solve problems|
|**Program**|Implementation of an algorithm using a programming language|
|**Data structure**|Way to organize and store data (e.g., lists in this example)|
|**List**|Collection of values|
|**Assignment (`=`)**|Stores a value in a variable|
|**Control Flow**|Conditional (`if`) and repetitive (`for`) steps|
|**Function**|Reusable block of code (`def gcd(m, n)`)|
|**Efficiency**|The naive approach works but is not efficient|

---

### ✍️ Summary Points for Revision

- **Algorithm**: A recipe with clear, finite steps.
    
- **Programming**: Writing these steps for execution (typically by a computer).
    
- **GCD Example**: Good illustration of breaking down a problem algorithmically.
    
- Python helps **represent algorithms** precisely using variables, loops, and conditionals.
    
- Lists are a **basic data structure** used to store intermediate data.
    
- A program must:
    
    1. Store intermediate results,
        
    2. Use loops and conditions,
        
    3. Be readable and finite.