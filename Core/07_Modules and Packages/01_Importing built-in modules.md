
## 🧠 **1️⃣ What is a Module?**

A **module** in Python is simply a **file that contains Python code** — functions, variables, or classes — that you can **reuse** in other programs.

✅ Think of it as a *toolbox* full of ready-to-use tools.

---

## 🧩 **2️⃣ Types of Modules**

| **Type**                 | **Description**           | **Examples**                              |
| ------------------------ | ------------------------- | ----------------------------------------- |
| **Built-in Modules**     | Pre-installed with Python | `math`, `os`, `sys`, `random`, `datetime` |
| **User-defined Modules** | Created by the programmer | Your own `.py` files                      |
| **External Modules**     | Installed via `pip`       | `numpy`, `pandas`, `requests`             |

---

## ⚙️ **3️⃣ Importing a Module**

### **Syntax:**

```python
import module_name
```

Once imported, you can access its functions and variables using **dot notation** (`module_name.function_name`).

---

### **Example:**

```python
import math

print(math.sqrt(16))
print(math.pi)
```

✅ **Output:**

```
4.0
3.141592653589793
```

---

## 🧩 **4️⃣ Importing Specific Functions from a Module**

If you only need certain items, you can import them directly.

### **Syntax:**

```python
from module_name import function_name
```

### **Example:**

```python
from math import sqrt, pi

print(sqrt(25))
print(pi)
```

✅ **Output:**

```
5.0
3.141592653589793
```

---

## 💡 **5️⃣ Giving an Alias (Rename a Module)**

To make names shorter or avoid conflicts, use `as`.

### **Example:**

```python
import math as m

print(m.pow(2, 3))
print(m.factorial(5))
```

✅ **Output:**

```
8.0
120
```

---

## 🔍 **6️⃣ Importing Everything from a Module**

You can import all definitions using the `*` symbol.
⚠️ **Not recommended** — it can cause name conflicts.

### **Example:**

```python
from math import *

print(sin(90))
print(sqrt(49))
```

✅ **Output:**

```
0.8939966636005579
7.0
```

---

## 📘 **7️⃣ Commonly Used Built-in Modules**

Let’s explore a few of the most useful ones.

---

### 🔹 **(a) `math` Module**

Provides mathematical functions.

```python
import math

print(math.sqrt(25))
print(math.ceil(4.2))
print(math.floor(4.9))
print(math.factorial(5))
```

✅ **Output:**

```
5.0
5
4
120
```

---

### 🔹 **(b) `random` Module**

Used to generate random numbers.

```python
import random

print(random.randint(1, 10))     # Random integer between 1–10
print(random.random())           # Random float between 0–1
print(random.choice(['apple', 'banana', 'cherry']))  # Random element from list
```

✅ **Output (varies):**

```
3
0.4835
banana
```

---

### 🔹 **(c) `datetime` Module**

Works with dates and times.

```python
import datetime

today = datetime.date.today()
print("Today:", today)

now = datetime.datetime.now()
print("Current Time:", now)
```

✅ **Output:**

```
Today: 2025-11-06
Current Time: 2025-11-06 13:42:10.123456
```

---

### 🔹 **(d) `os` Module**

Interacts with the operating system.

```python
import os

print(os.getcwd())       # Get current working directory
print(os.name)           # Get OS name
```

✅ **Output (example):**

```
/Users/admin/Desktop
posix
```

---

### 🔹 **(e) `sys` Module**

Provides system-related information and functions.

```python
import sys

print("Python version:", sys.version)
print("Path to search modules:", sys.path)
```

✅ **Output (example):**

```
Python version: 3.12.2 ...
['/usr/lib/python3.12', '/usr/local/lib/python3.12/site-packages', ...]
```

---

### 🔹 **(f) `time` Module**

Handles time-related operations.

```python
import time

print("Current time:", time.ctime())
print("Sleeping for 2 seconds...")
time.sleep(2)
print("Awake now!")
```

✅ **Output:**

```
Current time: Thu Nov  6 14:20:15 2025
Sleeping for 2 seconds...
Awake now!
```

---

## 🧠 **8️⃣ Checking All Functions in a Module**

Use the built-in `dir()` function to see what’s inside a module.

```python
import math
print(dir(math))
```

✅ **Output (partial):**

```
['acos', 'asin', 'atan', 'ceil', 'cos', 'degrees', 'factorial', 'pi', 'sqrt', ...]
```

---

## 🧩 **9️⃣ Reloading a Module**

If a module changes during runtime, you can reload it:

```python
import importlib
import my_module

importlib.reload(my_module)
```

> Useful for debugging custom modules.

---

## 🧮 **🔟 Using `help()` on Modules**

```python
import math
help(math)
```

✅ Displays detailed documentation about the module’s contents.

---

## 🧠 **11️⃣ Practice Questions**

1. Import the `math` module and find the square root of 144.
2. Import only the `sqrt` and `pow` functions from the `math` module.
3. Generate a random number between 50 and 100 using `random.randint()`.
4. Use `datetime` to print the current date and time.
5. Print the Python version using the `sys` module.
6. Get the current working directory using the `os` module.
7. Pause the program for 3 seconds using the `time.sleep()` function.
8. Print all available functions in the `random` module.
9. Rename the `math` module as `m` and print `m.pi`.
10. Explore what happens when you use `from math import *`.

---

## ✅ **Summary**

| **Method**                    | **Usage**                             | **Example**             |
| ----------------------------- | ------------------------------------- | ----------------------- |
| `import module`               | Import entire module                  | `import math`           |
| `from module import function` | Import specific functions             | `from math import sqrt` |
| `import module as alias`      | Give short name                       | `import math as m`      |
| `from module import *`        | Import all contents (not recommended) | `from math import *`    |
| `dir(module)`                 | List all attributes                   | `dir(math)`             |
| `help(module)`                | Show documentation                    | `help(math)`            |

---


