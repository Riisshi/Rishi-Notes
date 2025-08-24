## ✅ Python Lists, Assignment & Mutability – Key Concepts

### 🔹 Immutable vs Mutable Types

- **Immutable types**: `int`, `float`, `bool`, `str`
    - Assignment creates a **fresh copy** of the value.
    - Updating one variable **does not affect** the other.
- **Mutable types**: `list`
    - Assignment does **not** create a copy — it creates a new **reference**.
    - Updating one variable **affects** the other, since both point to the **same list**.

---

### 🔹 Example: Mutable List Behavior

```python
list1 = [1, 3, 5, 7] 
list2 = list1
list1[2] = 4
```

- Both `list1` and `list2` now show: `[1, 3, 4, 7]`
- Why? Because `list2` points to the **same** list as `list1`.

---

### 🔹 Making a Real (Independent) Copy of a List

Use **full slice**:

```python
list2 = list1[:]  # This creates a new copy of list1
```

- Now `list1` and `list2` are **independent**.
- Changing `list1` won’t affect `list2`.

---

### 🔹 Equality vs Identity

- `==` checks if **values** are the same.
- `is` checks if both variables refer to the **same object** (same memory).

```python
list1 = [1, 3, 5, 7] 
list2 = [1, 3, 5, 7]
list3 = list2  
list1 == list2     # True (same values) 
list1 is list2     # False (different objects) 
list2 is list3     # True (same object)
```

---
### 🔹 List Concatenation Always Creates a New List

```python
list1 = [1, 3, 5, 7]
list2 = list1 
list1 = list1 + [9]  # creates a new list, doesn't affect list2
```

- After this, `list1` and `list2` are **different lists**.

---

### 🔹 Summary

- **Assignment with immutable types** = copy of value
- **Assignment with mutable types (like lists)** = shared reference
- To copy a list: `list2 = list1[:]`
- Use `==` to compare values, use `is` to check if two variables point to the same object
- Using `+` with lists creates a **new list**, breaking shared reference