
## 💻 **1.4 Writing and Running Your First Python Program**

---

### **1.4.1 Python Program Basics**

Every Python program is just a **plain text file** that ends with the extension:

```
.py
```

Inside this file, you’ll write Python **statements** — instructions that the Python interpreter will execute **line by line**.

---

### **1.4.2 Your First Program: “Hello, World!”**

The traditional first step in any programming language is to print “Hello, World!” on the screen.

#### 🧩 Code:

```python
# This is my first Python program
print("Hello, World!")
```

#### 🖥️ Output:

```
Hello, World!
```

---

### **1.4.3 Understanding the Code**

| **Part**                            | **Explanation**                                                     |
| ----------------------------------- | ------------------------------------------------------------------- |
| `# This is my first Python program` | A **comment** — ignored by Python, used to describe your code.      |
| `print()`                           | A **built-in function** that displays text or values on the screen. |
| `"Hello, World!"`                   | A **string** — text enclosed in quotes.                             |

✅ When you run this file, Python executes the `print()` function and outputs the message to your console.

---

### **1.4.4 How to Run the Program**

You can run Python programs in **three main ways**:

---

#### **Option 1: Using the Command Line / Terminal**

1. Open your terminal or command prompt.
2. Navigate to the folder where your Python file is saved.
   Example:

   ```bash
   cd Desktop
   ```
3. Run the program:

   ```bash
   python hello.py
   ```

   or on macOS/Linux:

   ```bash
   python3 hello.py
   ```

✅ Output:

```
Hello, World!
```

---

#### **Option 2: Using an IDE (like VS Code, PyCharm, or Thonny)**

1. Open your `.py` file in the IDE.
2. Look for the **Run ▶️** button and click it, or use:

   * **VS Code:** `Ctrl + F5` (Windows) / `Cmd + F5` (Mac)
   * **Thonny:** Press **F5**
3. See the output in the built-in terminal or console.

---

#### **Option 3: Using the Interactive Shell (REPL)**

If you just want to test a few lines of code:

1. Open a terminal.
2. Type:

   ```bash
   python
   ```
3. You’ll see:

   ```
   >>>
   ```
4. Now type:

   ```python
   print("Hello, World!")
   ```

   Output:

   ```
   Hello, World!
   ```
5. Type `exit()` or press `Ctrl + Z` (Windows) / `Ctrl + D` (Mac/Linux) to quit.

---

### **1.4.5 Adding More Lines**

You can add more `print()` statements to display multiple lines:

```python
print("Hello, World!")
print("Welcome to Python programming.")
print("Let’s learn something awesome!")
```

**Output:**

```
Hello, World!
Welcome to Python programming.
Let’s learn something awesome!
```

---

### **1.4.6 Common Errors for Beginners**

| **Error**                                        | **Cause**                                        | **Example**                        |
| ------------------------------------------------ | ------------------------------------------------ | ---------------------------------- |
| `SyntaxError: EOL while scanning string literal` | Missing closing quotation mark.                  | `print("Hello)`                    |
| `IndentationError`                               | Wrong or missing indentation (spacing).          | Misaligned code block              |
| `NameError`                                      | Using a variable or function that doesn’t exist. | `pritn("Hi")` instead of `print()` |

💡 **Tip:** Python cares about indentation (spaces). Always keep your code neatly aligned.

---

### **1.4.7 Quick Experiment**

Try this program to see Python in action:

```python
name = input("Enter your name: ")
print("Hello, " + name + "! Welcome to Python!")
```

**Example Output:**

```
Enter your name: Alice
Hello, Alice! Welcome to Python!
```

✅ You’ve now used:

* `input()` → takes user input.
* `print()` → displays output.
* `+` → joins (concatenates) strings.

---

### **1.4.8 Summary**

| **Concept**           | **Example / Description** |
| --------------------- | ------------------------- |
| Python file extension | `.py`                     |
| Print output          | `print("Hello, World!")`  |
| Run program           | `python filename.py`      |
| Comment syntax        | `# comment text`          |
| Take user input       | `input("Message")`        |

---

🎯 **You’ve just written and executed your first Python program!**

---


