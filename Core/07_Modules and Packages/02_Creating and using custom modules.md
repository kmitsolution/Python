
# 🧠 **Creating and Using Custom Modules in Python**

---

## 🧩 **1️⃣ What is a Custom Module?**

A **custom module** is simply a **Python file** (`.py`) that contains **functions, variables, or classes** you’ve defined — so you can reuse them in other programs.

✅ Think of it like your **own personal toolbox** that can be imported whenever you need it.

---

## 🧮 **2️⃣ Why Use Modules?**

* To **organize** large programs into smaller, manageable files.
* To **reuse** code without rewriting it.
* To **share** functionality between multiple projects.

---

## 📁 **3️⃣ Creating a Custom Module**

Let’s create a file called **`mymath.py`**

### 📄 **mymath.py**

```python
# This is my custom math module

def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    if b == 0:
        return "Division by zero not allowed"
    return a / b

pi = 3.14159
```

✅ This file defines **4 functions** and **1 variable**.

---

## 🧩 **4️⃣ Importing and Using Your Module**

Now, create another Python file in the same folder called **`main.py`**.

### 📄 **main.py**

```python
import mymath

print("Addition:", mymath.add(10, 5))
print("Subtraction:", mymath.subtract(10, 5))
print("Multiplication:", mymath.multiply(10, 5))
print("Division:", mymath.divide(10, 5))
print("Pi value:", mymath.pi)
```

✅ **Output:**

```
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2.0
Pi value: 3.14159
```

---

## ⚙️ **5️⃣ Importing Specific Functions from a Module**

If you only need certain functions, import them directly:

```python
from mymath import add, divide

print(add(2, 3))
print(divide(10, 2))
```

✅ **Output:**

```
5
5.0
```

---

## 🧩 **6️⃣ Giving Your Module an Alias**

To shorten the name, use `as`:

```python
import mymath as m

print(m.multiply(4, 6))
```

✅ **Output:**

```
24
```

---

## 🧠 **7️⃣ Module Search Path**

When you import a module, Python looks for it in these locations (in order):

1. The **current directory** (where your script is located)
2. The directories listed in **`PYTHONPATH`**
3. The **default Python library** directory

You can check where Python looks for modules using:

```python
import sys
print(sys.path)
```

✅ It prints a list of directories Python searches for modules.

---

## 🔁 **8️⃣ Reloading a Module**

If you modify your module while the program is running, Python doesn’t automatically reload it.
Use `importlib` to reload:

```python
import importlib
import mymath

# After editing mymath.py
importlib.reload(mymath)
```

---

## 🧮 **9️⃣ Using `__name__ == "__main__"` in Modules**

If you want code in your module to **run only when executed directly**, not when imported, use this:

### 📄 **mymath.py**

```python
def add(a, b):
    return a + b

def multiply(a, b):
    return a * b

if __name__ == "__main__":
    print("Running mymath module directly!")
    print("5 + 3 =", add(5, 3))
```

### 📄 **main.py**

```python
import mymath
```

✅ When you run `main.py`, it **won’t print** the message.
✅ When you run `mymath.py` directly, it **will print**:

```
Running mymath module directly!
5 + 3 = 8
```

---

## 🧰 **10️⃣ Organizing Modules into Packages**

A **package** is a collection of modules in a **folder** that includes a special file called `__init__.py`.

**Example folder structure:**

```
myproject/
│
├── mathutils/
│   ├── __init__.py
│   ├── basic.py
│   └── advanced.py
└── main.py
```

### **basic.py**

```python
def add(a, b):
    return a + b
```

### **advanced.py**

```python
def power(a, b):
    return a ** b
```

### **main.py**

```python
from mathutils.basic import add
from mathutils.advanced import power

print(add(3, 4))
print(power(2, 3))
```

✅ **Output:**

```
7
8
```

---

## 🧠 **11️⃣ Useful Built-in Attributes**

| **Attribute** | **Description**               |
| ------------- | ----------------------------- |
| `__name__`    | Name of the module            |
| `__file__`    | Path of the module file       |
| `__doc__`     | Module’s documentation string |
| `__package__` | Package name of the module    |

### Example:

```python
import mymath
print(mymath.__name__)
print(mymath.__file__)
print(mymath.__doc__)
```

---

## 💡 **12️⃣ Practice Questions**

1. Create a module called `converter.py` with functions to:

   * Convert kilometers to miles
   * Convert Celsius to Fahrenheit
   * Convert seconds to minutes
2. Import the module into another file and call all functions.
3. Use `import as` to give your module an alias.
4. Try reloading your module after editing it.
5. Use `if __name__ == "__main__"` in your module to add a test section.
6. Create a package with two modules and import them into a main script.

---

## ✅ **Summary**

| **Concept**               | **Description**              | **Example**                       |
| ------------------------- | ---------------------------- | --------------------------------- |
| Create module             | Save functions in `.py` file | `mymath.py`                       |
| Import module             | `import module_name`         | `import mymath`                   |
| Import specific functions | `from module import func`    | `from mymath import add`          |
| Alias name                | `import module as alias`     | `import mymath as m`              |
| Check attributes          | `dir(module)`                | `dir(mymath)`                     |
| Protect main code         | `if __name__ == "__main__":` | Run-only block                    |
| Organize modules          | Use packages                 | `from package.module import func` |

---


