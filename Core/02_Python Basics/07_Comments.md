**Comments and Documentation Strings (Docstrings)** in Python.

They make your code **readable**, **maintainable**, and **professional**. 💡

---

## 📝 **Comments and Documentation Strings in Python**

---

### **1️⃣ Comments in Python**

**Comments** are notes in your code that are **ignored by the Python interpreter**.
They help explain what your code does for **you** and **others** who read it later.

---

### **Types of Comments**

#### **a) Single-Line Comments**

Start with the `#` symbol.

```python
# This is a single-line comment
print("Hello, World!")  # This comment is after code
```

✅ Everything after `#` on the same line is ignored.

---

#### **b) Multi-Line Comments**

Python doesn’t have a dedicated multi-line comment syntax.
However, you can use **multiple `#` symbols** or **triple quotes** (`'''` or `"""`) for readability.

**Using multiple # symbols:**

```python
# This is a comment
# that spans multiple
# lines
print("Python is fun!")
```

**Using triple quotes (not recommended for real multi-line comments):**

```python
'''
This is a multi-line comment.
Python ignores it if it’s not assigned to a variable.
'''
print("Learning Python")
```

✅ Triple quotes can work as comments **only if not used as docstrings**.

---

### **When to Use Comments**

* To explain **complex code logic**
* To describe **purpose** of variables or functions
* To **temporarily disable** code for testing

Example:

```python
# calculate area of a circle
radius = 5
area = 3.14 * radius ** 2  # formula: πr²
print("Area:", area)
```

---

### **2️⃣ Documentation Strings (Docstrings)**

A **docstring** is a special kind of string used to **document modules, classes, functions, or methods**.
It tells **what** the function/class/module does — like a built-in help guide!

---

### **Syntax:**

```python
def function_name():
    """This is a documentation string."""
    # function body
```

✅ Must be the **first statement** inside a function, class, or module.
✅ Enclosed in **triple quotes** (`"""` or `'''`).
✅ Accessible using the **`.__doc__`** attribute or the `help()` function.

---

### **Example 1: Function Docstring**

```python
def greet(name):
    """This function greets the user by name."""
    print("Hello,", name)
```

Accessing the docstring:

```python
print(greet.__doc__)
```

**Output:**

```
This function greets the user by name.
```

Or use:

```python
help(greet)
```

Output:

```
Help on function greet in module __main__:

greet(name)
    This function greets the user by name.
```

---

### **Example 2: Multi-line Docstring**

```python
def add(a, b):
    """
    Returns the sum of two numbers.

    Parameters:
        a (int or float): First number
        b (int or float): Second number

    Returns:
        int or float: The sum of a and b
    """
    return a + b
```

Accessing it:

```python
print(add.__doc__)
```

---

### **Example 3: Module Docstring**

You can also write docstrings at the **top of a file** to describe the module.

```python
"""
math_utils.py

This module provides basic mathematical operations:
- add(a, b)
- subtract(a, b)
"""
```

✅ Good practice for **professional Python projects**.

---

### **Example 4: Class Docstring**

```python
class Person:
    """Represents a person with name and age."""
    
    def __init__(self, name, age):
        """Initializes the person's name and age."""
        self.name = name
        self.age = age
```

---

### **Best Practices**

✅ Use **comments** for logic explanations.
✅ Use **docstrings** for documentation (functions, classes, modules).
✅ Keep comments **short, clear, and relevant**.
✅ Don’t over-comment obvious code.

Example (❌ Bad):

```python
i = 0  # set i to zero
```

Better (✅):

```python
i = 0  # index counter for loop
```

---

### **Quick Comparison Table**

| Feature                | Comment            | Docstring                      |
| ---------------------- | ------------------ | ------------------------------ |
| Symbol                 | `#`                | `""" """`                      |
| Purpose                | Explain code logic | Document module/class/function |
| Ignored by Interpreter | ✅                  | ❌ (stored as `__doc__`)        |
| Accessed at runtime    | ❌                  | ✅ via `.__doc__` or `help()`   |
| Common use             | Inline explanation | Code documentation             |

---

### **Example Summary**

```python
# This program demonstrates comments and docstrings

def multiply(x, y):
    """Multiply two numbers and return the result."""
    # perform multiplication
    result = x * y
    return result

print(multiply(3, 4))
print(multiply.__doc__)
```

**Output:**

```
12
Multiply two numbers and return the result.
```

---

### ✅ **In Short**

* Use **`#`** for normal comments.
* Use **`""" """`** for docstrings.
* Always document your functions and classes — it’s great practice for clean, maintainable code.

---


