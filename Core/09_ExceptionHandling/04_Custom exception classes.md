# 🧩 **Custom Exception Classes in Python**

---

## 🧠 **1️⃣ Why Create Custom Exceptions?**

Built-in exceptions like `ValueError`, `TypeError`, and `FileNotFoundError` are great for general problems.

But in **larger projects**, you might need **application-specific errors** such as:

* `InsufficientFundsError`
* `InvalidAgeError`
* `NegativeBalanceError`
* `AuthenticationError`

Custom exceptions make your code more:
✅ **Readable**
✅ **Structured**
✅ **Easy to debug**

---

## ⚙️ **2️⃣ How to Create a Custom Exception**

You create a custom exception by **defining a new class** that inherits from the built-in `Exception` class.

### **Syntax:**

```python
class MyCustomError(Exception):
    """Description of the custom exception."""
    pass
```

---

### **Example 1: A Simple Custom Exception**

```python
class NegativeNumberError(Exception):
    """Raised when a negative number is entered."""
    pass

num = int(input("Enter a positive number: "))
if num < 0:
    raise NegativeNumberError("Negative numbers are not allowed.")
else:
    print("You entered:", num)
```

✅ **Output (if input = -5):**

```
NegativeNumberError: Negative numbers are not allowed.
```

---

## 🧩 **3️⃣ Adding Custom Attributes**

You can make your custom exception class **store extra information**, such as values or error codes.

### **Example 2: Custom Exception with Attributes**

```python
class AgeError(Exception):
    """Raised when the age is invalid."""
    def __init__(self, age, message="Age must be between 1 and 120"):
        self.age = age
        self.message = message
        super().__init__(self.message)

try:
    age = int(input("Enter your age: "))
    if age < 1 or age > 120:
        raise AgeError(age)
    print("Valid age:", age)
except AgeError as e:
    print(f"Error: {e.message} (Invalid age: {e.age})")
```

✅ **Output (if input = 150):**

```
Error: Age must be between 1 and 120 (Invalid age: 150)
```

---

## 💡 **4️⃣ Using Custom Exceptions in Functions**

Custom exceptions are most useful when used inside **functions** or **classes**.

### **Example 3: Function with Custom Exception**

```python
class InsufficientFundsError(Exception):
    """Raised when a withdrawal amount exceeds available balance."""
    def __init__(self, balance, amount):
        super().__init__(f"Insufficient funds! Available: {balance}, Requested: {amount}")

def withdraw(balance, amount):
    if amount > balance:
        raise InsufficientFundsError(balance, amount)
    return balance - amount

try:
    remaining = withdraw(500, 1000)
    print("Remaining balance:", remaining)
except InsufficientFundsError as e:
    print("Transaction failed:", e)
```

✅ **Output:**

```
Transaction failed: Insufficient funds! Available: 500, Requested: 1000
```

---

## 🧱 **5️⃣ Creating a Hierarchy of Custom Exceptions**

In larger projects, it’s common to define a **base exception** and then inherit specific exceptions from it.

### **Example 4: Exception Hierarchy**

```python
# Base exception
class BankError(Exception):
    """Base class for all bank-related exceptions."""
    pass

# Derived exceptions
class InsufficientFundsError(BankError):
    pass

class InvalidAccountError(BankError):
    pass

class TransactionLimitError(BankError):
    pass

# Usage example
try:
    raise InvalidAccountError("Account not found!")
except BankError as e:
    print("Bank error occurred:", e)
```

✅ **Output:**

```
Bank error occurred: Account not found!
```

🧠 Benefit: You can catch **all bank-related errors** with `except BankError:`
or catch specific ones like `InvalidAccountError`.

---

## ⚙️ **6️⃣ Combining Custom and Built-in Exceptions**

You can raise custom exceptions alongside built-ins for more complete validation.

### **Example 5: Input Validation System**

```python
class InputTooShortError(Exception):
    """Raised when the input string is too short."""
    pass

class InputTooLongError(Exception):
    """Raised when the input string is too long."""
    pass

def validate_name(name):
    if len(name) < 3:
        raise InputTooShortError("Name must have at least 3 characters.")
    elif len(name) > 20:
        raise InputTooLongError("Name cannot exceed 20 characters.")
    else:
        print("Valid name:", name)

try:
    validate_name("Al")   # too short
except InputTooShortError as e:
    print("Error:", e)
except InputTooLongError as e:
    print("Error:", e)
```

✅ **Output:**

```
Error: Name must have at least 3 characters.
```

---

## 🧠 **7️⃣ Raising Multiple Custom Exceptions**

```python
class InvalidInputError(Exception): pass
class TooLargeError(Exception): pass
class TooSmallError(Exception): pass

def check_number(n):
    if not isinstance(n, int):
        raise InvalidInputError("Input must be an integer.")
    if n > 100:
        raise TooLargeError("Number is too large!")
    if n < 1:
        raise TooSmallError("Number is too small!")
    print("Valid number:", n)

try:
    check_number(150)
except (InvalidInputError, TooLargeError, TooSmallError) as e:
    print("Error:", e)
```

✅ **Output:**

```
Error: Number is too large!
```

---

## 💡 **8️⃣ Best Practices for Custom Exceptions**

✅ Always inherit from the **`Exception`** class (not `BaseException`).
✅ Use clear, descriptive names (e.g., `FileUploadError`, `InvalidAgeError`).
✅ Add **docstrings** to describe the purpose of the exception.
✅ Include useful **contextual information** in the message.
✅ Create a **base exception class** for large applications.

---

## 🧾 **9️⃣ Summary Table**

| **Concept**            | **Purpose**                       | **Example**                         |
| ---------------------- | --------------------------------- | ----------------------------------- |
| Define exception class | Create new exception type         | `class MyError(Exception): pass`    |
| Raise it               | Manually trigger the custom error | `raise MyError("Something wrong")`  |
| Inherit from Exception | Keep behavior consistent          | `class CustomError(Exception)`      |
| Add attributes         | Store custom data                 | `def __init__(self, msg, code)`     |
| Use hierarchy          | Group related errors              | `class ValidationError(MyAppError)` |

---

## 🧠 **🔟 Practice Questions**

1. Define a custom exception `NegativeNumberError` that is raised when a negative number is entered.
2. Create a function `validate_age(age)` that raises `AgeError` if the age is not between 1 and 120.
3. Create a base class `EcommerceError` and subclasses:

   * `PaymentError`
   * `OutOfStockError`
   * `InvalidCouponError`
     Then raise and handle one of them.
4. Modify the `BankError` hierarchy to handle different transaction scenarios.
5. Write a program that uses **custom exceptions with attributes** to print detailed error info.

---

## ✅ **Summary**

| **Concept**             | **Description**                                       |
| ----------------------- | ----------------------------------------------------- |
| **Custom Exceptions**   | User-defined exception classes for specific scenarios |
| **Inheritance**         | Always subclass from `Exception`                      |
| **Raise Keyword**       | Triggers the exception                                |
| **Attributes**          | Store details like error codes or values              |
| **Exception Hierarchy** | Organize related errors                               |
| **Best Practice**       | Clear, meaningful class names & messages              |

---

### 🔎 Example Summary Program

```python
class InvalidAgeError(Exception):
    """Raised when the provided age is invalid."""
    def __init__(self, age, message="Age must be between 0 and 120"):
        self.age = age
        self.message = message
        super().__init__(self.message)

try:
    age = int(input("Enter your age: "))
    if age < 0 or age > 120:
        raise InvalidAgeError(age)
    print("Valid age:", age)
except InvalidAgeError as e:
    print(f"Error: {e.message} (Invalid age: {e.age})")
finally:
    print("Program finished.")
```

✅ **Output (if input = 130):**

```
Error: Age must be between 0 and 120 (Invalid age: 130)
Program finished.
```

---


