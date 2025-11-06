
## 🧠 **Python Data Types: `int`, `float`, `str`, `bool`, `complex`**

---

### **What Are Data Types?**

A **data type** defines the kind of value a variable can hold and the operations that can be performed on it.
Python automatically assigns a data type to a variable when a value is assigned — this is called **dynamic typing**.

Example:

```python
x = 10         # int
y = 10.5       # float
name = "Alice" # str
is_valid = True # bool
z = 2 + 3j     # complex
```

---

### **1️⃣ Integer (`int`)**

Integers are **whole numbers** (positive, negative, or zero) without decimals.

**Examples:**

```python
a = 5
b = -20
c = 0
```

**Type check:**

```python
print(type(a))
```

**Output:**

```
<class 'int'>
```

✅ **Features of `int`:**

* Can be any length (Python automatically handles large integers)
* Supports arithmetic operations (`+`, `-`, `*`, `//`, `%`, `**`)

**Example:**

```python
x = 10
y = 3
print(x + y)   # 13
print(x ** y)  # 1000 (exponentiation)
```

---

### **2️⃣ Float (`float`)**

Floats represent **numbers with decimal points** or **in exponential form**.

**Examples:**

```python
pi = 3.14159
temp = -4.5
exp_num = 2.5e3   # 2.5 × 10³ = 2500.0
```

**Type check:**

```python
print(type(pi))
```

**Output:**

```
<class 'float'>
```

✅ **Common operations:**

```python
a = 10.5
b = 2.0
print(a / b)   # 5.25
print(round(a))  # 10
```

> 💡 Floating-point numbers may not always be exact due to memory representation.

---

### **3️⃣ String (`str`)**

A **string** is a sequence of characters enclosed in **single**, **double**, or **triple quotes**.

**Examples:**

```python
name = "Alice"
greeting = 'Hello'
message = """Welcome to Python!"""
```

**Type check:**

```python
print(type(name))
```

**Output:**

```
<class 'str'>
```

✅ **Common string operations:**

```python
text = "Python"
print(text.upper())      # PYTHON
print(text.lower())      # python
print(len(text))         # 6
print(text[0])           # P
print(text[0:3])         # Pyt
```

✅ **String concatenation and repetition:**

```python
a = "Hello"
b = "World"
print(a + " " + b)  # Hello World
print(a * 3)        # HelloHelloHello
```

---

### **4️⃣ Boolean (`bool`)**

Booleans represent **truth values** — `True` or `False`.

**Examples:**

```python
is_valid = True
is_admin = False
```

**Type check:**

```python
print(type(is_valid))
```

**Output:**

```
<class 'bool'>
```

✅ **Boolean expressions:**

```python
x = 10
y = 5
print(x > y)   # True
print(x == y)  # False
```

✅ **Booleans in arithmetic:**

* `True` → `1`
* `False` → `0`

Example:

```python
print(True + True)   # 2
print(False + 5)     # 5
```

---

### **5️⃣ Complex (`complex`)**

A complex number consists of a **real** and an **imaginary** part, represented as `a + bj`.

**Examples:**

```python
z1 = 2 + 3j
z2 = 5 - 2j
```

**Type check:**

```python
print(type(z1))
```

**Output:**

```
<class 'complex'>
```

✅ **Complex number operations:**

```python
print(z1 + z2)      # (7+1j)
print(z1 * z2)      # (16+11j)
print(z1.real)      # 2.0
print(z1.imag)      # 3.0
```

---

### **Checking Data Types**

Use the built-in `type()` function:

```python
x = 100
print(type(x))   # <class 'int'>
```

---

### **Type Conversion (Casting)**

You can convert between compatible data types using **type casting** functions.

**Examples:**

```python
x = 10
print(float(x))    # 10.0

y = 3.14
print(int(y))      # 3

z = "100"
print(int(z))      # 100

a = True
print(int(a))      # 1
print(float(a))    # 1.0
```

> ⚠️ Conversion fails if data isn’t compatible:

```python
num = "abc"
print(int(num))   # ❌ ValueError
```

---

### **Summary Table**

| **Type**  | **Description**                       | **Example**       |
| --------- | ------------------------------------- | ----------------- |
| `int`     | Whole numbers                         | `x = 10`          |
| `float`   | Decimal numbers                       | `y = 10.5`        |
| `str`     | Sequence of characters                | `name = "Alice"`  |
| `bool`    | Boolean values (True/False)           | `is_valid = True` |
| `complex` | Numbers with real and imaginary parts | `z = 2 + 3j`      |

---

### **Quick Practice**

Write a Python script that:

1. Creates five variables — one of each data type (`int`, `float`, `str`, `bool`, `complex`)
2. Prints each variable’s value and its data type using `type()`


