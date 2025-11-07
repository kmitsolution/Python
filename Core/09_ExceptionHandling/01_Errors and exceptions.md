# 🧩 **Exception Handling — Errors and Exceptions in Python**

---

## 💡 **1️⃣ What Are Errors and Exceptions?**

When something goes wrong in your program, Python **raises an error** that stops execution.

There are two main categories:

| **Type**          | **Meaning**                                           |
| ----------------- | ----------------------------------------------------- |
| **Syntax Errors** | Mistakes in code structure (detected before running)  |
| **Exceptions**    | Errors that occur *during execution* (runtime errors) |

---

### ⚙️ **A. Syntax Error Example**

```python
print("Hello"
```

❌ **Output:**

```
SyntaxError: '(' was never closed
```

🧠 Python catches this before running the program — it can’t even start executing!

---

### ⚙️ **B. Exception Example (Runtime Error)**

```python
num = int(input("Enter a number: "))
print(10 / num)
```

If the user enters `0`, ❌ you get:

```
ZeroDivisionError: division by zero
```

If the user enters `"abc"`, ❌ you get:

```
ValueError: invalid literal for int() with base 10: 'abc'
```

These are **exceptions** — Python runs fine until an unexpected situation occurs.

---

## 🧠 **2️⃣ Common Types of Exceptions**

| **Exception Type**  | **Description**                             |
| ------------------- | ------------------------------------------- |
| `ZeroDivisionError` | Dividing by zero                            |
| `ValueError`        | Invalid value (e.g. converting text to int) |
| `TypeError`         | Wrong data type used                        |
| `IndexError`        | List index out of range                     |
| `KeyError`          | Dictionary key not found                    |
| `FileNotFoundError` | Trying to open a non-existent file          |
| `ImportError`       | Module not found                            |
| `NameError`         | Using variable before defining it           |
| `AttributeError`    | Calling undefined method or property        |
| `IOError`           | Input/output operation failure              |

---

## 🧱 **3️⃣ Handling Exceptions with `try` and `except`**

You can handle exceptions and prevent program crashes using:

### **Syntax**

```python
try:
    # risky code
except ExceptionType:
    # code to handle error
```

---

### **Example 1: Basic Exception Handling**

```python
try:
    a = int(input("Enter a number: "))
    result = 10 / a
    print("Result:", result)
except ZeroDivisionError:
    print("Error: You cannot divide by zero.")
except ValueError:
    print("Error: Invalid input. Please enter a number.")
```

✅ **Output (if user enters 0):**

```
Error: You cannot divide by zero.
```

✅ **Output (if user enters abc):**

```
Error: Invalid input. Please enter a number.
```

---

## 🔁 **4️⃣ Handling Multiple Exceptions**

You can handle multiple exceptions together:

```python
try:
    num = int(input("Enter a number: "))
    print(10 / num)
except (ZeroDivisionError, ValueError):
    print("Oops! Something went wrong. Enter a valid non-zero number.")
```

✅ Handles both division and value errors with one message.

---

## ⚙️ **5️⃣ Using a Generic Exception**

Catch any type of exception (not recommended for all cases, but useful for debugging):

```python
try:
    x = int("abc")
except Exception as e:
    print("An error occurred:", e)
```

✅ **Output:**

```
An error occurred: invalid literal for int() with base 10: 'abc'
```

---

## 🧩 **6️⃣ Using `else` and `finally` Blocks**

Python allows optional `else` and `finally` blocks for cleaner logic.

### **Syntax:**

```python
try:
    # code that may raise exception
except:
    # runs if an error occurs
else:
    # runs if no error occurs
finally:
    # runs no matter what
```

---

### **Example 1: Using `else`**

```python
try:
    num = int(input("Enter a number: "))
    print(10 / num)
except ZeroDivisionError:
    print("Division by zero is not allowed.")
else:
    print("No errors occurred. Well done!")
```

✅ **Output (if user enters 2):**

```
5.0
No errors occurred. Well done!
```

---

### **Example 2: Using `finally`**

```python
try:
    file = open("data.txt", "r")
    content = file.read()
except FileNotFoundError:
    print("File not found.")
finally:
    print("Closing the file or ending process.")
```

✅ **Output:**

```
File not found.
Closing the file or ending process.
```

🧠 The `finally` block **always runs**, even if an exception occurs or not.

---

## ⚡ **7️⃣ Raising Exceptions Manually**

You can raise (throw) your own exceptions using the `raise` keyword.

### **Example 1: Custom Raise**

```python
age = int(input("Enter your age: "))
if age < 0:
    raise ValueError("Age cannot be negative!")
else:
    print("Your age is", age)
```

✅ **Output:**

```
ValueError: Age cannot be negative!
```

---

### **Example 2: Raising Custom Error in Function**

```python
def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("Cannot divide by zero.")
    return a / b

try:
    print(divide(10, 0))
except ZeroDivisionError as e:
    print("Error:", e)
```

✅ **Output:**

```
Error: Cannot divide by zero.
```

---

## 🧠 **8️⃣ Creating Custom Exceptions (Advanced)**

You can define your own exception classes by inheriting from `Exception`.

```python
class NegativeNumberError(Exception):
    """Custom exception for negative numbers."""
    pass

try:
    num = int(input("Enter a positive number: "))
    if num < 0:
        raise NegativeNumberError("Number cannot be negative!")
except NegativeNumberError as e:
    print("Custom Error:", e)
```

✅ **Output:**

```
Custom Error: Number cannot be negative!
```

---

## 📘 **9️⃣ Nested try–except Example**

```python
try:
    with open("numbers.txt", "r") as file:
        for line in file:
            try:
                print(int(line.strip()))
            except ValueError:
                print("Invalid line:", line.strip())
except FileNotFoundError:
    print("File not found.")
```

✅ Handles both missing files and bad data lines inside.

---

## ✅ **🔟 Summary Table**

| **Block**        | **Purpose**                          |
| ---------------- | ------------------------------------ |
| `try`            | Code that may raise an exception     |
| `except`         | Handles the error                    |
| `else`           | Runs if no error occurs              |
| `finally`        | Runs always (cleanup code)           |
| `raise`          | Manually trigger an exception        |
| `Exception as e` | Capture error message for inspection |

---

## ⚙️ **Common Exceptions and Fixes**

| **Error**           | **Cause**                     | **Fix**                                 |
| ------------------- | ----------------------------- | --------------------------------------- |
| `ZeroDivisionError` | Divide by zero                | Check denominator                       |
| `ValueError`        | Invalid data type             | Validate input                          |
| `TypeError`         | Wrong operation between types | Cast types properly                     |
| `FileNotFoundError` | File missing                  | Check path or create file               |
| `KeyError`          | Missing dict key              | Use `dict.get()` or check key existence |
| `IndexError`        | List index too large          | Check index length                      |

---

## 🧠 **Practice Questions**

1. Write a program to divide two numbers and handle both `ZeroDivisionError` and `ValueError`.
2. Write a program to read a file, and handle `FileNotFoundError`.
3. Create a function that only accepts positive numbers and raises a `ValueError` if not.
4. Use `try...else...finally` to demonstrate file operations safely.
5. Define your own custom exception for invalid user input.

---

## ✅ **In Summary**

| **Concept**           | **Description**                         |
| --------------------- | --------------------------------------- |
| **Errors**            | Problems in code execution              |
| **Exceptions**        | Runtime errors that can be handled      |
| **try–except**        | Prevent program crashes                 |
| **else**              | Runs only if no exception occurs        |
| **finally**           | Runs always (for cleanup)               |
| **raise**             | Trigger custom exceptions               |
| **Custom Exceptions** | Define your own rules for special cases |

---


