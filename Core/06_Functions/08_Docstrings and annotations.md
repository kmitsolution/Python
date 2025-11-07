
# 🧾 **Docstrings and Annotations in Python**

---

## 🧠 **1️⃣ What is a Docstring?**

A **docstring** (documentation string) is a **special multi-line string** used to **document** a module, class, function, or method.

It tells **what the code does**, **how it works**, and sometimes **examples of usage**.

📘 **Syntax:**

```python
def function_name(parameters):
    """This is a docstring — describes the purpose of the function."""
    statement(s)
```

You can use **triple quotes (`'''` or `"""`)** to write multi-line docstrings.

---

## 🧩 **2️⃣ Example: Function Docstring**

```python
def add(a, b):
    """Return the sum of two numbers."""
    return a + b

print(add(10, 20))
```

✅ **Output:**

```
30
```

You can view the docstring using:

```python
print(add.__doc__)
```

✅ **Output:**

```
Return the sum of two numbers.
```

---

## 💬 **3️⃣ Multi-line Docstring Example**

```python
def factorial(n):
    """
    Calculate the factorial of a number.

    Parameters:
        n (int): Non-negative integer

    Returns:
        int: Factorial of the number n
    """
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)
```

✅ **Output:**

```python
print(factorial.__doc__)
```

```
Calculate the factorial of a number.

Parameters:
    n (int): Non-negative integer

Returns:
    int: Factorial of the number n
```

---

## 🧱 **4️⃣ Types of Docstrings**

| **Where Used**                | **Purpose**                              |
| ----------------------------- | ---------------------------------------- |
| **Module docstring**          | Describes the purpose of the file/module |
| **Class docstring**           | Describes what the class represents      |
| **Method/Function docstring** | Describes what the function does         |

---

### 📘 Example: Module, Class, and Function Docstrings

```python
"""This module performs basic math operations."""

class Calculator:
    """A simple calculator class."""

    def add(self, a, b):
        """Return the sum of two numbers."""
        return a + b
```

✅ Accessing Docstrings:

```python
print(Calculator.__doc__)
print(Calculator.add.__doc__)
```

✅ **Output:**

```
A simple calculator class.
Return the sum of two numbers.
```

---

## ⚙️ **5️⃣ Docstring vs Comments**

| **Feature**   | **Comment (`#`)**            | **Docstring (`"""`)**                           |
| ------------- | ---------------------------- | ----------------------------------------------- |
| **Purpose**   | Explain code for programmers | Describe usage for users/developers             |
| **Executed?** | Ignored by interpreter       | Stored as attribute (`__doc__`)                 |
| **Tools**     | Not accessible               | Used by `help()`, IDEs, and documentation tools |
| **Placement** | Anywhere                     | Inside a function, class, or module             |

---

## 💡 **6️⃣ Viewing Docstrings with `help()`**

```python
def greet(name):
    """Greet the user with their name."""
    print("Hello,", name)

help(greet)
```

✅ **Output:**

```
Help on function greet in module __main__:

greet(name)
    Greet the user with their name.
```

---

# ✨ **Function Annotations**

---

## 🧩 **7️⃣ What Are Function Annotations?**

**Function Annotations** provide **metadata** about the types of parameters and the return value.

They **don’t affect program behavior** — they are **hints** for developers or tools (like IDEs and linters).

📘 **Syntax:**

```python
def function_name(param1: type, param2: type) -> return_type:
    statement(s)
```

---

## 💡 **8️⃣ Example: Basic Annotations**

```python
def add(a: int, b: int) -> int:
    """Add two integers and return the result."""
    return a + b

print(add(5, 10))
```

✅ **Output:**

```
15
```

Annotations can be accessed using:

```python
print(add.__annotations__)
```

✅ **Output:**

```
{'a': <class 'int'>, 'b': <class 'int'>, 'return': <class 'int'>}
```

---

## 🔍 **9️⃣ Example: Annotations with Different Types**

```python
def greet(name: str, age: int) -> str:
    """Return a greeting message."""
    return f"Hello {name}, you are {age} years old!"
```

✅ Access annotations:

```python
print(greet.__annotations__)
```

✅ **Output:**

```
{'name': <class 'str'>, 'age': <class 'int'>, 'return': <class 'str'>}
```

---

## ⚙️ **🔟 Complex Example with Lists and Optional Types**

```python
from typing import List, Optional

def find_max(numbers: List[int]) -> Optional[int]:
    """Return the maximum number in a list, or None if empty."""
    if not numbers:
        return None
    return max(numbers)
```

✅ **Output:**

```python
print(find_max.__annotations__)
```

```
{'numbers': typing.List[int], 'return': typing.Optional[int]}
```

---

## 🧠 **11️⃣ Using Annotations with Default Arguments**

```python
def power(base: int, exp: int = 2) -> int:
    """Return the base raised to the power of exp."""
    return base ** exp

print(power(3))
print(power(2, 5))
```

✅ **Output:**

```
9
32
```

---

## 🧩 **12️⃣ Combining Docstrings and Annotations**

```python
def area(radius: float) -> float:
    """
    Calculate the area of a circle.

    Parameters:
        radius (float): Radius of the circle

    Returns:
        float: Area of the circle
    """
    return 3.1416 * radius * radius
```

✅ **Annotations:**

```python
print(area.__annotations__)
```

✅ **Output:**

```
{'radius': <class 'float'>, 'return': <class 'float'>}
```

✅ **Docstring:**

```python
print(area.__doc__)
```

✅ **Output:**

```
Calculate the area of a circle.

Parameters:
    radius (float): Radius of the circle

Returns:
    float: Area of the circle
```

---

## 💬 **13️⃣ Benefits of Docstrings and Annotations**

| **Feature**   | **Docstrings**                      | **Annotations**                       |
| ------------- | ----------------------------------- | ------------------------------------- |
| Purpose       | Describe what code does             | Describe data types                   |
| Used by       | `help()`, IDEs, documentation tools | Type checkers, IDEs, static analyzers |
| Stored as     | `__doc__`                           | `__annotations__`                     |
| Affects code? | No                                  | No                                    |
| Example       | `"""Return sum of numbers"""`       | `a: int, b: int -> int`               |

---

## 🧠 **14️⃣ Practice Questions**

1. Write a function with a docstring that describes what it does.
2. Create a function `multiply(a, b)` with annotations showing both are `float`.
3. Add a docstring and annotations to a function that returns a greeting.
4. Write a function `circle_area(radius)` with annotations and a docstring.
5. Create a function `is_even(num: int) -> bool` and access its annotations.
6. Demonstrate how to access `__doc__` and `__annotations__`.
7. Create a class with a class-level docstring and method-level docstrings.
8. Use the `help()` function to display documentation for a user-defined function.
9. Write a function that accepts a list of integers and returns the sum (use `List[int]`).
10. Combine docstrings and annotations to describe a `find_average()` function.

---

## ✅ **Summary**

| **Concept**             | **Purpose**                                | **Access Attribute**      |
| ----------------------- | ------------------------------------------ | ------------------------- |
| **Docstring**           | Describe what a function/class/module does | `__doc__`                 |
| **Annotation**          | Describe parameter and return types        | `__annotations__`         |
| **Tools Using Them**    | `help()`, IDEs, linters, `pydoc`           | Type checkers like `mypy` |
| **Effect on Execution** | None                                       | None (informational only) |

---


