## 🔢 **Improving the GCD Algorithm – Lecture Summary**

### ✅ **Initial Naive Algorithm**

- **Idea:** Compute all factors of `m` and `n`, then find the common factors, and finally return the largest one.
- **Steps:**
    
    1. Construct list `fm` = factors of `m`
    2. Construct list `fn` = factors of `n`
    3. Find `cf` = common elements in `fm` and `fn`
    4. Return the last (largest) element in `cf`

### 🔁 **First Optimization – Single Loop for Both Lists**

- Instead of two separate loops (1 to `m` and 1 to `n`), loop from 1 to `max(m, n)` once.
    
- In each iteration:
    
    - If `i` divides `m`, add to `fm`
    - If `i` divides `n`, add to `fn`

### ⚡ **Second Optimization – Directly Check for Common Factors**

- Skip creating `fm` and `fn`.
- For each `i` from 1 to `min(m, n)`:
    - If `i` divides both `m` and `n`, add `i` to `cf`
- This avoids computing two full lists.

### 🎯 **Third Optimization – Only Track the Largest Common Factor**

- We don’t need the full list of common factors—just the largest one.
- Initialize `mrcf = 1` (most recent common factor)
- For each `i` in 1 to `min(m, n)`:
    - If `i` divides both `m` and `n`, update `mrcf = i`
- At the end, return `mrcf`
    

### 🔁 **Fourth Optimization – Loop in Reverse**

- Start from `min(m, n)` and go down to 1.
- This way, the **first** common factor found is the **largest**.
- Use a `while` loop:
    
```python
i = min(m, n)
while i > 0:
    if m % i == 0 and n % i == 0:
        return i
    i = i - 1
```
    
- This method exits early, making it potentially faster.
    


## 🧠 Key Learnings

### 🔄 For Loop vs While Loop

- **For loop**: Use when the number of iterations is known.
- **While loop**: Use when you loop until a condition is met.

### ⚠️ Infinite Loops

- In a `while` loop, ensure the loop variable (like `i`) is **updated**.
- Otherwise, you might end up in an **infinite loop**.

---

## ⏱️ Computational Insight

- Despite these optimizations, all versions still take time proportional to `min(m, n)` in the worst case (e.g., when `GCD(m, n) = 1`)
 
- The real improvement in **efficiency** comes in the **next lecture**, likely referring to **Euclid's algorithm**.