## 🐍 **Getting Started with Python**

### 🧭 Platforms

- Python is available on **Linux**, **macOS**, and **Windows**.
- Most Linux systems come with Python pre-installed (often **Python 2.7**).
- Windows/macOS may require a manual install, especially for **Python 3**.

---

## 🔢 **Python Versions: Python 2.7 vs Python 3**

|Feature|Python 2.7|Python 3 (e.g., 3.5.2)|
|---|---|---|
|Status|Legacy version|Actively developed|
|Compatibility|Some scientific libraries still use it|Modern syntax and features|
|Recommendation|Avoid unless necessary|Use Python 3 for new projects|
|Syntax Differences|Some major (e.g., `print`, division)|Cleaner and more consistent|

- This course uses **Python 3**.
- Minor version differences (like 3.4 vs 3.5) don’t matter for this course.

---

## 🔧 **Installing Python 3**

- Official download: https://www.python.org/downloads/
- Look for the version that matches your operating system.

> **Linux users**: Use your package manager (`sudo apt install python3`)  
> **Windows/macOS users**: Download installer from the website

---

## ⚙️ **Python Execution Model: Interpreter vs Compiler**

|Term|What it Does|Python Behavior|
|---|---|---|
|Compiler|Converts code to machine instructions|Used in C, Java|
|Interpreter|Executes code line-by-line|Python uses this|

- Python is **interpreted**: it lets you run code interactively (like a calculator).
- Use a command like `python3.5` or `python3` in your terminal to start it.

---

## 🖥️ **Using Python Interactively**

- Launch Python:
    
```bash
python3
```
    
- Prompt: `>>>`  
    Example session:
```python   
>>> i = 5
>>> i + 1
6
```
    

### Defining Functions:

```python
>>> def twice(x):
...   y = 2 * x
...   return y
...
>>> twice(7)
14

```

---

## 📄 **Working with Python Files**

- Write code in a `.py` file using a plain **text editor** (Not Word or Google Docs).
    
- Example file: `gcd1.py`
    

### Loading a File in Python:

```python
>>> from gcd1 import *
>>> gcd(14, 63)
7
```

### Tip:

- If you change the file, **restart the interpreter** to reload changes (or use `importlib.reload()`).
    

---

## 🧮 **Speed Comparison – Naive vs Efficient Algorithm**

Example:

```python

>>> gcd(9999999, 1000000)
```

- Naive version: **slow**
    
- Euclid’s algorithm: **very fast**
    
- Demonstrates how **good algorithms matter** more than just the programming language.
    

---

## ❌ **Common Errors in Python**

|Mistake|Example|What Happens|
|---|---|---|
|Undefined function|`loop()`|`NameError: name 'loop' is not defined`|
|Syntax error|`7 <> 5` or wrong indenting|`SyntaxError`|

### Tip:

- **Use consistent indentation** (spaces or tabs, not both).
    
- Python is **sensitive** to indentation!
    

---

## 📚 **Helpful Resources**

- **Python official docs**:  
    [https://docs.python.org/3/](https://docs.python.org/3/)
    
- **Beginner-friendly books** (free online):
    
    - _Dive Into Python_
        
    - _Think Python_
        

---

## 🧠 **Final Advice**

> **You can’t learn programming just by watching.**

- Practice actively by:
    
    - Typing code
        
    - Making mistakes
        
    - Experimenting with functions and files
        
- Learning one language well (like Python) makes others easier to pick up later.
    

---

### ✅ Your Next Steps

1. Install Python 3 on your system.
    
2. Try the Python interpreter: `python3`
    
3. Create and run `.py` files with simple functions like `gcd`.
    
4. Explore Python syntax with the official tutorial.
    
5. Practice, make mistakes, and debug them.
