### ✅ Key Concepts:

**1. Function Definitions & Calling Order**
- Functions must be **defined before they are used**.
- A function (`f`) can call another function (`g`) that appears later in the code as long as `f` is not **executed** before `g` is defined.

**2. Function Scope**
- Variables inside functions are **local**.
- Modifying a variable inside a function **doesn’t affect** the outside unless it's mutable (like lists).

**3. Recursion (e.g., Factorial)**
- Recursive functions call themselves with a **smaller problem**.
- Always include a **base case** to avoid infinite recursion.

**4. Code Reuse**
- Break problems into **smaller functions** (like `factors()`, `isprime()`, `primesupto()`) to:
    - Improve readability
    - Make code reusable
    - Help with debugging and optimization

**5. `for` vs `while`**
- Use `for` when the **number of iterations is known** (like from 1 to n).
- Use `while` when the **condition depends on runtime logic** (like finding the first `n` primes).

**6. Readability Matters**
- Prefer clarity over cleverness.
- Others (or future you) should be able to understand and maintain your code.