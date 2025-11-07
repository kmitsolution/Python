
# ⚡ **Raising Exceptions in Python**

---

## 🧠 **1️⃣ What Does "Raising an Exception" Mean?**

When something goes wrong in your program — like dividing by zero — Python automatically **raises an exception** such as:

```python
ZeroDivisionError: division by zero
```

But sometimes, *you* want to stop the program or flag a problem **manually** when certain conditions are not met.

That’s when you **raise** an exception yourself using the `raise` keyword.

---

## ⚙️ **2️⃣ Basic Syntax**

```python
raise ExceptionType("Custom error message")
```

✅ Example:

```python
raise ValueError("Invalid input value!")
```

When Python executes this line, it **stops immediately** and raises the specified error.

---

## 💡 **3️⃣ Simple Example: Raising a Built-in Exception**

```python
age = int(input("Enter your age: "))

if age < 0:
    raise ValueError("Age cannot be negative!")
else:
    print("Your age is:", age)
```

✅ **Output (if input = -5):**

```
ValueError: Age cannot be negative!
```

✅ **Output (if input = 25):**

```
Your age is: 25
```

🧠 You can use `raise` anywhere — inside functions, loops, or conditionals.

---

## 🧩 **4️⃣ Raising Exceptions Inside a Function**

```python
def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("Cannot divide by zero!")
    return a / b

try:
    print(divide(10, 0))
except ZeroDivisionError as e:
    print("Error:", e)
```

✅ **Output:**

```
Error: Cannot divide by zero!
```

---

## 🔍 **5️⃣ Raising Different Built-in Exceptions**

| **Exception**       | **Use Case Example**    |
| ------------------- | ----------------------- |
| `ValueError`        | Invalid numeric value   |
| `TypeError`         | Wrong data type         |
| `ZeroDivisionError` | Division by zero        |
| `FileNotFoundError` | File not found          |
| `PermissionError`   | Restricted access       |
| `AssertionError`    | When an assertion fails |

---

### Example — `TypeError`:

```python
def greet(name):
    if not isinstance(name, str):
        raise TypeError("Name must be a string.")
    print("Hello,", name)

greet(123)  # ❌
```

✅ **Output:**

```
TypeError: Name must be a string.
```

---

## 🧠 **6️⃣ Raising Exceptions with `try...except`**

You can handle the exception you raise using `try` and `except`.

```python
try:
    x = -10
    if x < 0:
        raise ValueError("Number cannot be negative!")
except ValueError as e:
    print("Handled Exception:", e)
```

✅ **Output:**

```
Handled Exception: Number cannot be negative!
```

---

## 🔁 **7️⃣ Raising Exceptions Conditionally**

Sometimes you may raise an exception **based on user input or business rules**.

```python
def check_password(password):
    if len(password) < 6:
        raise ValueError("Password too short! Must be at least 6 characters.")
    if password.isdigit():
        raise ValueError("Password cannot be all numbers.")
    print("Password accepted!")

try:
    check_password("12345")
except ValueError as e:
    print("Error:", e)
```

✅ **Output:**

```
Error: Password too short! Must be at least 6 characters.
```

---

## 🧱 **8️⃣ Re-raising Exceptions**

You can **catch an exception** and then **raise it again** to pass it up to another handler.

```python
try:
    x = int("abc")
except ValueError as e:
    print("Caught an error:", e)
    raise   # Re-raises the same exception
```

✅ Output:

```
Caught an error: invalid literal for int() with base 10: 'abc'
Traceback (most recent call last):
  ...
ValueError: invalid literal for int() with base 10: 'abc'
```

🧠 Re-raising is useful when you want to **log the error first**, then let it propagate.

---

## 🧩 **9️⃣ Raising Custom Error Messages**

You can give specific feedback by raising **built-in exceptions with descriptive messages**.

```python
def withdraw(balance, amount):
    if amount > balance:
        raise ValueError(f"Insufficient funds! Available: {balance}, Requested: {amount}")
    print(f"Withdrawal successful. Remaining balance: {balance - amount}")

try:
    withdraw(500, 800)
except ValueError as e:
    print("Transaction Error:", e)
```

✅ **Output:**

```
Transaction Error: Insufficient funds! Available: 500, Requested: 800
```

---

## ⚙️ **🔟 Using `assert` to Raise Exceptions Automatically**

The `assert` keyword automatically raises an `AssertionError` if a condition is false.

```python
x = -1
assert x >= 0, "x must be non-negative"
```

✅ Output:

```
AssertionError: x must be non-negative
```

🧠 `assert` is a shortcut for:

```python
if not condition:
    raise AssertionError("message")
```

---

## 💡 **11️⃣ Combining `raise` with `try...finally`**

```python
try:
    raise ValueError("Something went wrong!")
finally:
    print("Cleaning up before exit...")
```

✅ Output:

```
Cleaning up before exit...
Traceback (most recent call last):
  ...
ValueError: Something went wrong!
```

✅ The `finally` block executes even when you raise an exception.

---

## 🧠 **12️⃣ Best Practices**

✅ Raise exceptions **only when necessary**.
✅ Use **meaningful error messages** — they help debugging.
✅ Always raise **specific exceptions** instead of generic ones.
✅ Avoid using `raise Exception` (too broad).
✅ Use `assert` only for **debugging**, not for user-facing checks.

---

## 🧩 **13️⃣ Summary Table**

| **Keyword / Concept** | **Purpose**                    | **Example**                          |
| --------------------- | ------------------------------ | ------------------------------------ |
| `raise`               | Manually trigger an exception  | `raise ValueError("Invalid value")`  |
| `raise e`             | Re-raise existing exception    | `raise`                              |
| `try...except`        | Handle exceptions              | `try: ... except ValueError:`        |
| `assert`              | Raise error if condition fails | `assert x > 0, "x must be positive"` |
| `Exception as e`      | Get error message              | `print(e)`                           |

---

## 🧠 **14️⃣ Practice Questions**

1. Write a function that raises a `ValueError` if the user’s input number is negative.
2. Create a function that raises a `TypeError` if the argument is not a string.
3. Write a function `divide(a, b)` that raises `ZeroDivisionError` if `b = 0`.
4. Modify your password validation function to raise custom error messages for different cases.
5. Use `assert` to check if a variable `age` is positive.

---

## ✅ **15️⃣ Summary**

| **Concept**            | **Description**                                         |
| ---------------------- | ------------------------------------------------------- |
| **Raising Exceptions** | Manually trigger an error when something’s wrong        |
| **raise keyword**      | Used to raise built-in or custom exceptions             |
| **Custom messages**    | Helps describe what went wrong                          |
| **Re-raising**         | Lets error continue after partial handling              |
| **assert**             | Debugging tool that raises AssertionError automatically |

---


