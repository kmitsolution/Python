
## 🔤 **Python Keywords and Identifiers**

---

### **What Are Keywords?**

**Keywords** are special reserved words in Python that have predefined meanings and purposes.
They are part of the language syntax and **cannot** be used as variable names, function names, or identifiers.

Example:

```python
if = 5       # ❌ Error! "if" is a keyword
print(if)
```

Output:

```
SyntaxError: invalid syntax
```

---

### **How to View All Keywords in Python**

You can see all keywords available in your version of Python by running:

```python
import keyword
print(keyword.kwlist)
```

✅ **Example Output (Python 3.12):**

```
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await',
 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except',
 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is',
 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try',
 'while', 'with', 'yield']
```

> Note: The keyword list may differ slightly in other Python versions.

---

### **Common Python Keywords (with Examples)**

| **Keyword**                 | **Meaning / Use**                 | **Example**                   |
| --------------------------- | --------------------------------- | ----------------------------- |
| `False`, `True`             | Boolean values                    | `is_active = True`            |
| `None`                      | Represents “no value”             | `x = None`                    |
| `and`, `or`, `not`          | Logical operators                 | `if x > 0 and y > 0:`         |
| `if`, `elif`, `else`        | Conditional statements            | `if x > 5: ...`               |
| `for`, `while`              | Loops                             | `for i in range(5):`          |
| `break`, `continue`, `pass` | Loop control                      | `break` exits a loop          |
| `def`, `return`             | Define and return from a function | `def add(a, b): return a + b` |
| `class`                     | Define a class                    | `class Student:`              |
| `try`, `except`, `finally`  | Handle errors                     | `try: ... except: ...`        |
| `import`, `from`, `as`      | Module import                     | `import math as m`            |
| `with`                      | Context manager                   | `with open('file.txt') as f:` |
| `lambda`                    | Anonymous (inline) function       | `square = lambda x: x * x`    |
| `yield`                     | Create a generator                | `yield value`                 |
| `assert`                    | Debugging check                   | `assert x > 0`                |
| `global`, `nonlocal`        | Scope control                     | `global total`                |

---

### **What Are Identifiers?**

An **identifier** is a name used to identify a variable, function, class, or any other object in Python.

Example:

```python
name = "Alice"
age = 25

def greet():
    print("Hello!")
```

Here:

* `name` and `age` are variable identifiers.
* `greet` is a function identifier.

---

### **Rules for Naming Identifiers**

✅ Follow these basic rules:

| **Rule**                                                           | **Example**                     |
| ------------------------------------------------------------------ | ------------------------------- |
| Must begin with a **letter (A–Z or a–z)** or an **underscore (_)** |                                 |
| `name`, `_temp`                                                    |                                 |
| Can include **letters, digits, and underscores**                   | `user_name`, `age1`             |
| Cannot start with a number                                         | ❌ `1student`                    |
| Cannot be a keyword                                                | ❌ `class = "Math"`              |
| Are **case-sensitive**                                             | `Name` and `name` are different |
| No spaces or symbols allowed                                       | ❌ `user name`, `user-name`      |

---

### **Valid vs Invalid Identifiers**

| **Valid**     | **Invalid** | **Reason**                |
| ------------- | ----------- | ------------------------- |
| `name`        | `1name`     | Cannot start with a digit |
| `_value`      | `user-name` | Hyphen not allowed        |
| `student_age` | `import`    | Keyword                   |
| `user123`     | `my var`    | Spaces not allowed        |
| `totalMarks`  | `for`       | Keyword                   |

---

### **Naming Conventions (Best Practices)**

Follow **PEP 8**, Python’s official style guide:

| **Use Case**         | **Convention**             | **Example**             |
| -------------------- | -------------------------- | ----------------------- |
| Variable             | lowercase, use underscores | `student_name`          |
| Constant             | ALL UPPERCASE              | `PI = 3.14159`          |
| Function             | lowercase with underscores | `get_total()`           |
| Class                | PascalCase                 | `class StudentProfile:` |
| Private/Internal use | Starts with underscore     | `_internal_data`        |

💡 Use **meaningful names** — `student_age` is better than `x`.

---

### **Using Identifiers in Code**

Example:

```python
user_name = "Alice"
user_age = 21

def greet_user():
    print("Hello", user_name)

greet_user()
```

**Output:**

```
Hello Alice
```

---

### **Quick Practice**

Identify which of these are **valid identifiers**:

```
1. myVariable
2. _data
3. 2ndUser
4. user-name
5. lambda
6. MAX_VALUE
```

✅ **Answer:**

* Valid → `myVariable`, `_data`, `MAX_VALUE`
* Invalid → `2ndUser` (starts with number), `user-name` (hyphen), `lambda` (keyword)

---

### **Summary**

| **Concept**        | **Description**                                                      |
| ------------------ | -------------------------------------------------------------------- |
| **Keywords**       | Reserved words that can’t be used as identifiers                     |
| **Identifiers**    | Names given to variables, functions, or classes                      |
| **Rules**          | Start with letter or `_`, can include digits and underscores         |
| **Case-sensitive** | `Name` ≠ `name`                                                      |
| **Style Guide**    | Use lowercase_with_underscores for variables, PascalCase for classes |

---

✅ **Quick Exercise**
Create a Python script that:

1. Defines a variable `user_name`.
2. Defines a constant `PI`.
3. Prints both with descriptive messages.


