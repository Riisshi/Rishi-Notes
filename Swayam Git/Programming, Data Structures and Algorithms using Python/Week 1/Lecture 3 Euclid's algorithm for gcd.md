# 🧮 Refining the GCD Algorithm – Lecture Summary

## ✅ Recap: The Naive Approach

- We start by computing the **list of factors** of both numbers `m` and `n`.
    - `fm =` factors of `m`
    - `fn =` factors of `n`
    - `cf =` common factors of `fm` and `fn`
- The GCD is the **largest number in `cf`**, i.e., the last one (since lists are sorted in ascending order).
    

---

## 🚀 Optimization 1: Single Scan for Both Lists

- Instead of two separate loops:
```python
for i in range(1, m+1): # for m
for j in range(1, n+1): # for n
```
    
- Use **one loop** from `1` to `max(m, n)` to simultaneously check factors:
    
```python
for i in range(1, max(m, n) + 1):
    if m % i == 0:
        #add i to fm
    if n % i == 0:
        #add i to fn
```
    


## 🚀 Optimization 2: Directly Check Common Factors

- Instead of building `fm` and `fn`, check directly if `i` divides **both `m` and `n`**:
    
```python
for i in range(1, min(m, n) + 1):
    if m % i == 0 and n % i == 0:
        #add i to cf
```
    
- We only go up to `min(m, n)` since no number greater than `min(m, n)` can divide both.
    

---

## 🚀 Optimization 3: Avoid Storing All Common Factors

- We **don’t need a list** of all common factors, only the **largest**.
    
- Keep track of the **Most Recent Common Factor (mrcf)**:
    
```python
mrcf = 1
for i in range(1, min(m, n) + 1):
    if m % i == 0 and n % i == 0:
        mrcf = i
return mrcf

```
    



## 🚀 Optimization 4: Reverse the Scan

- Why start from `1`? Start from the **largest** possible factor:
    
- As soon as we find a common factor, it's the GCD!
    
```python
for i in range(min(m, n), 0, -1):  # Start from min(m, n) and go down to 1
    if m % i == 0 and n % i == 0:
        return i  # First such i is the GCD

```
    

---

## 🌀 Introducing the `while` Loop

- Alternate way to loop backward:
```python
i = min(m, n)
while i > 0:
    if m % i == 0 and n % i == 0:
        return i
    i = i - 1

```
    
- `while` is useful when we **don’t know** in advance how many iterations are needed.
    

> ⚠️ Be careful: Make sure `i` decreases so that the loop eventually stops. Otherwise, you'll get an **infinite loop**!

---

## 🧠 Summary: What We Learned

- Start with a direct implementation of a definition.
    
- Refine the approach step by step:
    
    1. Avoid repeated scans.
        
    2. Skip unnecessary lists.
        
    3. Check only relevant values (down to `min(m, n)`).
        
    4. Stop early using reverse order or `while`.
        
- Though logically better, all these methods still take **time proportional to `min(m, n)`**.
    

📌 **Next Lecture Teaser**: We’ll see a drastically more efficient algorithm—**the Euclidean Algorithm**.