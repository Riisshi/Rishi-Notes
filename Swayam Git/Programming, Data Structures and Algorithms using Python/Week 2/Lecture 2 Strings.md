### 🔤 **Working with Strings in Python**

#### 1. **Concatenation (`+` operator)**

- `+` operator joins two strings **end-to-end**.
    - Example:
        
```python
s = "hello" t = "there" print(s + t)  # Output: "hellothere"
```
        
- **No spaces or punctuation** are added automatically.
    - To include a space:
        
```python
t = " there" print(s + t)  # Output: "hello there"
```

---

#### 2. **Getting Length of a String**

- Use `len(string)` to get the **number of characters**.
    - Example:
        
```python
len("hello")  # Output: 5
```

---

#### 3. **String Indexing and Slicing**

- Indexing starts from **0**.
- Use slicing `s[i:j]` to extract a **substring** from index `i` to `j-1`.
    - Example:
        
```python
s = "hello" s[1:4]  # Output: "ell"
```

##### 🪄 **Slicing Shortcuts**

- `s[:j]` → from **start** to `j-1`
- `s[i:]` → from `i` to **end**
- Invalid ranges return `""` (empty string), not error.
    - Example:
        
```python
s[3:2]  # Output: ""
```

---

#### 4. **Strings are Immutable**

- Cannot update part of a string directly.
    
    - ❌ `s[3] = "p"` → Error!
- Must **create a new string** using slices and concatenation:
    - Example:
        
```python
s = "hello" s = s[:3] + "p!" print(s)  # Output: "help!"
```

---

#### 5. **Key Takeaways**

- Strings are sequences of characters with no special type for single characters.
- Use:
    - **Indexing** for individual characters,
    - **Slicing** for substrings,
    - **`+` operator** for joining,
    - **`len()`** for length,
- Strings are **immutable** – you must build a new one for any change.