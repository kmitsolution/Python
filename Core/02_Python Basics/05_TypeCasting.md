
## 🔁 **Type Conversion and Casting in Python**

---

### **What Is Type Conversion?**

**Type Conversion** means changing a value from one data type to another.
In Python, this can happen **automatically** or **manually**.

There are **two types** of conversions:

1. **Implicit Type Conversion (Type Coercion)** – Done automatically by Python.
2. **Explicit Type Conversion (Type Casting)** – Done manually by the programmer.

---

### **1️⃣ Implicit Type Conversion**

Python automatically converts one data type to another **compatible type** to avoid data loss.

**Example 1: int → float**

```python
x = 10       # int
y = 2.5      # float

result = x + y
print(result)
print(type(result))
```

**Output:**

```
12.5
<class 'float'>
```

✅ Here, Python automatically converted `x` (int) into a float before addition.

---

**Example 2: bool → int**

```python
a = True
b = 5

print(a + b)
print(type(a + b))
```

**Output:**

```
6
<class 'int'>
```

✅ `True` is treated as `1`, so `1 + 5 = 6`.

---

**⚠️ Note:**
Python does **not** automatically convert between **string** and **numeric** types — you must do that manually.

Example:

```python
x = "10"
y = 5
print(x + y)   # ❌ Error
```

Output:

```
TypeError: can only concatenate str (not "int") to str
```

---

### **2️⃣ Explicit Type Conversion (Type Casting)**

When you manually convert a data type using **built-in functions** like:

* `int()`
* `float()`
* `str()`
* `bool()`
* `complex()`

---

#### **a) Converting to int**

```python
x = 10.9
y = "15"
print(int(x))   # 10
print(int(y))   # 15
```

✅ Converts floats and numeric strings to integers
⚠️ Decimal part is **truncated** (not rounded)

❌ Invalid example:

```python
z = "abc"
print(int(z))   # ValueError
```

---

#### **b) Converting to float**

```python
x = 10
y = "3.14"

print(float(x))  # 10.0
print(float(y))  # 3.14
```

✅ Works for integers and numeric strings.

---

#### **c) Converting to str**

```python
x = 100
y = 3.14
z = True

print(str(x))   # '100'
print(str(y))   # '3.14'
print(str(z))   # 'True'
```

✅ Converts numbers and booleans to strings (useful for display or concatenation).

---

#### **d) Converting to bool**

```python
print(bool(0))        # False
print(bool(1))        # True
print(bool(""))       # False
print(bool("Hello"))  # True
```

✅ Rules:

* `0`, `0.0`, `None`, `''`, `[]`, `{}` → `False`
* Everything else → `True`

---

#### **e) Converting to complex**

```python
x = 5
y = 3.2
print(complex(x))      # (5+0j)
print(complex(x, y))   # (5+3.2j)
```

✅ Creates complex numbers from real and imaginary parts.

---

### **Examples of Common Conversions**

| **From → To** | **Function**    | **Example** | **Result** |
| ------------- | --------------- | ----------- | ---------- |
| int → float   | `float(x)`      | `float(5)`  | `5.0`      |
| float → int   | `int(x)`        | `int(5.8)`  | `5`        |
| str → int     | `int("10")`     | `"10"`      | `10`       |
| str → float   | `float("3.14")` | `"3.14"`    | `3.14`     |
| int → str     | `str(25)`       | `25`        | `'25'`     |
| bool → int    | `int(True)`     | `True`      | `1`        |
| int → bool    | `bool(0)`       | `0`         | `False`    |

---

### **Example Program: Type Casting**

```python
# Original values
x = 5
y = 2.5
z = "100"

# Conversions
a = float(x)       # int → float
b = int(y)         # float → int
c = int(z)         # str → int
d = str(x)         # int → str

print(a, type(a))
print(b, type(b))
print(c, type(c))
print(d, type(d))
```

**Output:**

```
5.0 <class 'float'>
2 <class 'int'>
100 <class 'int'>
5 <class 'str'>
```

---

### **Summary Table**

| **Conversion Type** | **Function**     | **Example** | **Output** |
| ------------------- | ---------------- | ----------- | ---------- |
| Implicit            | Auto (by Python) | `5 + 2.5`   | `7.5`      |
| int → float         | `float(10)`      | `10.0`      |            |
| float → int         | `int(10.9)`      | `10`        |            |
| str → int           | `int("5")`       | `5`         |            |
| str → float         | `float("2.5")`   | `2.5`       |            |
| int → str           | `str(25)`        | `'25'`      |            |
| bool → int          | `int(True)`      | `1`         |            |
| int → bool          | `bool(0)`        | `False`     |            |

---

### **Quick Practice**

Write a Python script that:

1. Defines a string variable `num_str = "25"`.
2. Converts it into an integer and a float.
3. Adds 10 to both converted values.
4. Prints the results with their data types.


