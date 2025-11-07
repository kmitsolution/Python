# ⚙️ **try, except, else, finally Blocks in Python**

---

## 🧩 **1️⃣ Purpose**

When Python detects an error during program execution, it raises an **exception** and **stops the program** — unless you handle it.

To prevent your program from crashing, wrap risky code in a `try` block and handle errors using `except`.

---

## 📘 **2️⃣ The Basic Structure**

```python
try:
    # Code that might cause an exception
except:
    # Code to handle the exception
```

✅ If an error occurs → the `except` block runs.
✅ If no error occurs → `except` block is skipped.

---

## 🧠 **3️⃣ The Full Form (4 Blocks)**

Python’s complete exception handling syntax allows **four** optional blocks:

```python
try:
    # Code that might raise an exception
except ExceptionType:
    # Code to handle the specific exception
else:
    # Runs if no exception occurs
finally:
    # Runs no matter what (for cleanup)
```

---

## 💥 **4️⃣ The `try` Block**

The `try` block contains code that might produce an error.

### Example:

```python
try:
    num = int(input("Enter a number: "))
    print(10 / num)
```

If you enter `0` → causes `ZeroDivisionError`
If you enter `"abc"` → causes `ValueError`

---

## 🧰 **5️⃣ The `except` Block**

The `except` block handles the error gracefully.

### Example 1: Specific Exception

```python
try:
    num = int(input("Enter a number: "))
    print(10 / num)
except ZeroDivisionError:
    print("Error: Division by zero is not allowed.")
```

✅ **Output:**

```
Error: Division by zero is not allowed.
```

---

### Example 2: Multiple Exception Types

```python
try:
    num = int(input("Enter a number: "))
    print(10 / num)
except (ZeroDivisionError, ValueError):
    print("Error: Invalid number or division by zero.")
```

✅ **Output:**

```
Error: Invalid number or division by zero.
```

---

### Example 3: Generic Exception

If you don’t know the exact error type:

```python
try:
    result = 10 / 0
except Exception as e:
    print("An error occurred:", e)
```

✅ **Output:**

```
An error occurred: division by zero
```

---

## 💡 **6️⃣ The `else` Block**

The `else` block runs **only if the `try` block succeeds** (no errors occur).

### Example:

```python
try:
    num = int(input("Enter a number: "))
    print("Result:", 10 / num)
except ZeroDivisionError:
    print("You cannot divide by zero.")
else:
    print("Division completed successfully!")
```

✅ **Output (if input = 2):**

```
Result: 5.0
Division completed successfully!
```

✅ **Output (if input = 0):**

```
You cannot divide by zero.
```

🧠 **Tip:**
Use `else` for code that should run **only when no exception happens** — instead of placing it inside the `try` block.

---

## 🧹 **7️⃣ The `finally` Block**

The `finally` block **always runs**, whether an error occurred or not.
It’s perfect for **cleanup actions**, such as closing files or network connections.

### Example:

```python
try:
    file = open("test.txt", "r")
    data = file.read()
    print(data)
except FileNotFoundError:
    print("File not found.")
finally:
    print("This always runs — closing resources.")
```

✅ **Output:**

```
File not found.
This always runs — closing resources.
```

✅ Even if no error occurs:

```
File content...
This always runs — closing resources.
```

---

## 🧩 **8️⃣ Using All Four Blocks Together**

```python
try:
    x = int(input("Enter a number: "))
    y = 10 / x
except ZeroDivisionError:
    print("Error: Division by zero.")
except ValueError:
    print("Error: Invalid number.")
else:
    print("Division successful! Result =", y)
finally:
    print("End of program (always executes).")
```

✅ **If user enters 2:**

```
Division successful! Result = 5.0
End of program (always executes).
```

✅ **If user enters 0:**

```
Error: Division by zero.
End of program (always executes).
```

✅ **If user enters "abc":**

```
Error: Invalid number.
End of program (always executes).
```

---

## 🔁 **9️⃣ Nested try–except Example**

You can even **nest** exception handlers for more granular control.

```python
try:
    with open("numbers.txt", "r") as file:
        for line in file:
            try:
                print(int(line.strip()))
            except ValueError:
                print("Skipping invalid line:", line.strip())
except FileNotFoundError:
    print("The file 'numbers.txt' does not exist.")
finally:
    print("Done processing file.")
```

✅ Handles:

* Missing file (`FileNotFoundError`)
* Bad data (`ValueError`)

---

## ⚙️ **🔟 Best Practices**

✅ Always handle **specific exceptions** instead of using `except:`
✅ Use `finally` for cleanup (e.g., closing files or connections)
✅ Use `else` only when code should run **if no exception** occurs
✅ Don’t ignore errors — at least print them or log them
✅ Don’t nest too many `try` blocks unless necessary

---

## 🧠 **Practice Questions**

1. Write a program that takes two numbers and divides them using `try`, `except`, and `else`.
2. Add a `finally` block to print `"Execution complete"` no matter what happens.
3. Create a program to read a file. If it doesn’t exist, print an error message.
4. Demonstrate how `finally` runs even if an exception occurs.
5. Combine all four blocks in a small program of your choice (e.g., reading input and dividing numbers).

---

## ✅ **Summary Table**

| **Block** | **When It Runs**       | **Purpose**                             |
| --------- | ---------------------- | --------------------------------------- |
| `try`     | Always first           | Contains code that might raise an error |
| `except`  | If an exception occurs | Handles errors gracefully               |
| `else`    | If no exception occurs | Executes code when everything is fine   |
| `finally` | Always                 | Cleanup code that runs no matter what   |

---

## 🔎 Example Summary Program

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ZeroDivisionError:
    print("You cannot divide by zero.")
except ValueError:
    print("Please enter a valid integer.")
else:
    print("Result:", result)
finally:
    print("Program finished. Cleaning up resources...")
```

✅ **Output 1 (Input = 2):**

```
Result: 5.0
Program finished. Cleaning up resources...
```

✅ **Output 2 (Input = 0):**

```
You cannot divide by zero.
Program finished. Cleaning up resources...
```

✅ **Output 3 (Input = abc):**

```
Please enter a valid integer.
Program finished. Cleaning up resources...
```

---


