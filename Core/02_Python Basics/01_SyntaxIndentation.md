## 🧱 **1.5 Python Syntax and Indentation**

---

### **1.5.1 What is Syntax?**

**Syntax** refers to the **rules** that define how Python code must be written and structured so the interpreter can understand it.

Just like grammar rules in English, **Python syntax** ensures your program makes sense to the computer.

Example:

```python
print("Hello, World!")   # ✅ Correct syntax
print "Hello, World!"    # ❌ Incorrect syntax
```

Python requires parentheses `()` after the `print` function — otherwise, you’ll get a `SyntaxError`.

---

### **1.5.2 Case Sensitivity**

Python is **case-sensitive** — meaning uppercase and lowercase letters are treated differently.

```python
name = "Alice"
print(name)   # ✅ Works fine
print(Name)   # ❌ Error: NameError: name 'Name' is not defined
```

So always be careful with capitalization.

---

### **1.5.3 Statements in Python**

A **statement** is a single line of code that performs an action.

Example statements:

```python
x = 5
y = 10
print(x + y)
```

Each line here is a **separate statement**.
Python executes statements **one after another**, from top to bottom.

---

### **1.5.4 Multiple Statements on One Line**

Although not recommended for readability, you *can* write multiple statements on one line using semicolons `;`:

```python
x = 5; y = 10; print(x + y)
```

✅ Works fine, but ❌ not considered good style in Python.

---

### **1.5.5 Line Continuation**

If your statement is too long, you can break it into multiple lines using a **backslash (`\`)**:

```python
total = 10 + 20 + 30 + \
        40 + 50
print(total)
```

Or better yet, use **parentheses**, **brackets**, or **braces** for multi-line statements (preferred style):

```python
numbers = [
    10, 20, 30,
    40, 50
]
```

---

### **1.5.6 Indentation in Python**

Unlike most languages that use `{}` or `begin/end` blocks,
**Python uses indentation (spaces or tabs)** to define **code blocks**.

For example:

```python
if 5 > 2:
    print("Five is greater than two!")
```

✅ The **indentation (space)** after the `if` statement defines what code belongs to that block.

If you forget or misalign indentation, Python will throw an **IndentationError**.

```python
if 5 > 2:
print("Five is greater than two!")   # ❌ Error
```

Output:

```
IndentationError: expected an indented block
```

---

### **1.5.7 How Much Indentation?**

There’s no strict rule on how many spaces, but **4 spaces per indentation level** is the Python standard (PEP 8 style guide).

Example:

```python
if True:
    print("This is indented 4 spaces")
    print("Still inside the block")
print("Now outside the block")
```

---

### **1.5.8 Nested Indentation**

Blocks can be nested — meaning one block inside another.

Example:

```python
if True:
    print("Outer block")
    if 3 > 2:
        print("Inner block")
```

**Output:**

```
Outer block
Inner block
```

Here:

* The first `print()` is indented **4 spaces** → inside the outer `if`.
* The second `print()` is indented **8 spaces** → inside the inner `if`.

---

### **1.5.9 Using Tabs vs Spaces**

Python allows both **tabs** and **spaces**, but **you must not mix them**.
Mixing tabs and spaces can cause invisible indentation errors.

✅ **Best practice:**

* Use **spaces only**.
* Most IDEs (like VS Code or PyCharm) automatically insert **4 spaces** when you press the **Tab** key.

---

### **1.5.10 Example: Proper Syntax and Indentation**

```python
age = 18

if age >= 18:
    print("You are an adult.")
    print("You can vote.")
else:
    print("You are underage.")
```

✅ **Explanation:**

* The lines under `if` and `else` are **indented** to show they belong to that block.
* The outermost lines (`age = 18`, `if`, `else`) start at the left margin.

---

### **1.5.11 Common Syntax & Indentation Errors**

| **Error Type**     | **Example**                                 | **Explanation**                                     |
| ------------------ | ------------------------------------------- | --------------------------------------------------- |
| `IndentationError` | Missing indentation after a block statement | `if x > 0: print(x)` ✅ or `if x > 0:\n    print(x)` |
| `SyntaxError`      | Missing colon or parentheses                | `if x > 0 print(x)` ❌                               |
| `TabError`         | Mixing tabs and spaces                      | Avoid using both together                           |

---

### **1.5.12 Summary**

| **Concept**          | **Description / Example**                |
| -------------------- | ---------------------------------------- |
| Syntax               | Rules defining valid Python code         |
| Case sensitivity     | `Name` ≠ `name`                          |
| Statement            | Each line of executable code             |
| Indentation          | Defines code blocks using spaces         |
| Standard indentation | 4 spaces per block                       |
| Common error         | `IndentationError` if alignment is wrong |

---

✅ **Quick Practice:**

Try to spot the error in this code:

```python
x = 10
if x > 5:
print("Big number")
```

**Answer:** The `print` line needs indentation!
Correct version:

```python
x = 10
if x > 5:
    print("Big number")
```

---

