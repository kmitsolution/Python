# 🧩 **The `__name__ == "__main__"` Idiom in Python**

---

## 🧠 **1️⃣ What Does `__name__` Mean?**

Every Python file (module) has a **built-in variable** called `__name__`.

* When a Python file is **run directly**, `__name__` is automatically set to `"__main__"`.
* When the same file is **imported as a module**, `__name__` is set to the **module’s name** (i.e., the filename without `.py`).

---

### 💡 Example 1: Running Directly

Let’s create a file named **`example.py`**:

```python
print("The value of __name__ is:", __name__)
```

✅ **Output (when run directly):**

```
The value of __name__ is: __main__
```

---

### 💡 Example 2: Importing the File

Now create another file **`main.py`** in the same folder:

```python
import example
```

✅ **Output:**

```
The value of __name__ is: example
```

🧩 Explanation:
When `example.py` is imported, Python doesn’t treat it as the “main” program —
so its `__name__` becomes `"example"`, not `"__main__"`.

---

## ⚙️ **2️⃣ The Purpose of `if __name__ == "__main__":`**

This condition lets you **control which parts of code run automatically** when the file is executed directly — and **which parts stay inactive** when imported.

---

### 💡 Example 3: Without the Idiom

**`math_utils.py`**

```python
def add(a, b):
    return a + b

print("Sum:", add(3, 4))
```

Now run this:

```bash
python math_utils.py
```

✅ **Output:**

```
Sum: 7
```

But when you import it:

```python
import math_utils
```

❌ **Output (unwanted):**

```
Sum: 7
```

➡️ The print statement runs **even when imported**, which can be annoying in larger projects.

---

### 💡 Example 4: Using the Idiom (Correct Way)

**`math_utils.py`**

```python
def add(a, b):
    return a + b

if __name__ == "__main__":
    print("Sum:", add(3, 4))
```

Now:

* When you **run directly**:

  ```bash
  python math_utils.py
  ```

  ✅ **Output:**

  ```
  Sum: 7
  ```

* When you **import** it:

  ```python
  import math_utils
  ```

  ✅ **Output:**

  ```
  (No output)
  ```

Perfect! 🎯
Now the print statement only executes when the script runs directly, not when it’s imported.

---

## 🧩 **3️⃣ Why Use This Idiom?**

| **Reason**                        | **Explanation**                                                  |
| --------------------------------- | ---------------------------------------------------------------- |
| ✅ **Code reusability**            | Keeps reusable code (functions, classes) separate from test code |
| ✅ **Prevents unwanted execution** | Avoids running test or demo code during imports                  |
| ✅ **Best practice**               | Used by almost all professional Python developers                |
| ✅ **Organizes scripts cleanly**   | Separates “definition” part from “execution” part                |

---

## 🧠 **4️⃣ Typical Structure of a Python Script**

```python
# my_module.py

def greet(name):
    print(f"Hello, {name}!")

def main():
    greet("Python Learner")

if __name__ == "__main__":
    main()
```

✅ **Explanation:**

* `greet()` — function definition (reusable)
* `main()` — main logic of the program
* `if __name__ == "__main__": main()` — runs only when executed directly

---

## 📘 **5️⃣ Example: Using in Real Projects**

### File: `calculator.py`

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def main():
    print("Running calculator as main program...")
    print("2 + 3 =", add(2, 3))
    print("5 - 2 =", subtract(5, 2))

if __name__ == "__main__":
    main()
```

### File: `app.py`

```python
import calculator

print("Using calculator from another script:")
print("10 + 20 =", calculator.add(10, 20))
```

✅ **When you run `calculator.py`:**

```
Running calculator as main program...
2 + 3 = 5
5 - 2 = 3
```

✅ **When you run `app.py`:**

```
Using calculator from another script:
10 + 20 = 30
```

🔹 No extra output from `calculator.py` — exactly what we want.

---

## 🧩 **6️⃣ Summary Table**

| **Situation**        | **Value of `__name__`** | **Code under `if __name__ == "__main__":` runs?** |
| -------------------- | ----------------------- | ------------------------------------------------- |
| File is run directly | `"__main__"`            | ✅ Yes                                             |
| File is imported     | `"module_name"`         | ❌ No                                              |

---

## 🧠 **7️⃣ Practice Questions**

1. Create a module named `greet_module.py` with a function `say_hello(name)`.
   Add code under `if __name__ == "__main__":` to greet yourself.
2. Create another file and import `greet_module`.
   Does the greeting message print automatically? Why or why not?
3. Write a script with a `main()` function and call it using the idiom.
4. Modify your previous custom module to include this idiom for testing.
5. Explain in your own words why this practice is useful in large projects.

---

## ✅ **In Summary**

* Every Python file has a special variable: `__name__`.
* If a file is **run directly**, `__name__ == "__main__"`.
* If a file is **imported**, `__name__ == "module_name"`.
* Use this idiom to **control what code runs automatically**.
* It’s a **best practice** for all Python developers.

---


