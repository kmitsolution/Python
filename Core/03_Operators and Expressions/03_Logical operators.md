
## 🧠 **Logical Operators in Python**

Logical operators are used to **combine multiple conditions** (expressions) and return a **Boolean value** (`True` or `False`).

---

### **List of Logical Operators**

| **Operator** | **Description**                                      | **Example**            | **Result** |
| ------------ | ---------------------------------------------------- | ---------------------- | ---------- |
| `and`        | Returns `True` if **both** conditions are True       | `(5 > 2) and (10 > 5)` | `True`     |
| `or`         | Returns `True` if **at least one** condition is True | `(5 > 10) or (10 > 5)` | `True`     |
| `not`        | **Reverses** the result (True → False, False → True) | `not(5 > 3)`           | `False`    |

---

### **1️⃣ The `and` Operator**

✅ **True** only if **both conditions** are True.
If either condition is False → the result is **False**.

```python
a = 10
b = 5

print(a > 5 and b < 10)   # True (both conditions are True)
print(a > 5 and b > 10)   # False (second condition is False)
```

**Truth Table for `and`:**

| A     | B     | A and B |
| ----- | ----- | ------- |
| True  | True  | True    |
| True  | False | False   |
| False | True  | False   |
| False | False | False   |

---

### **2️⃣ The `or` Operator**

✅ **True** if **at least one** condition is True.
Only returns **False** if both are False.

```python
a = 10
b = 20

print(a > 5 or b < 15)   # True (first condition True)
print(a < 5 or b < 15)   # False (both False)
```

**Truth Table for `or`:**

| A     | B     | A or B |
| ----- | ----- | ------ |
| True  | True  | True   |
| True  | False | True   |
| False | True  | True   |
| False | False | False  |

---

### **3️⃣ The `not` Operator**

✅ **Reverses** the Boolean value.

* `not True` → `False`
* `not False` → `True`

```python
x = True
y = False

print(not x)   # False
print(not y)   # True
```

**Example in condition:**

```python
is_logged_in = False

if not is_logged_in:
    print("Please log in first.")
```

Output:

```
Please log in first.
```

---

### **Combining Logical Operators**

You can combine multiple operators to form complex conditions:

```python
age = 25
has_id = True

if age >= 18 and has_id:
    print("Access granted!")
else:
    print("Access denied!")
```

Output:

```
Access granted!
```

---

### **Example: Using `and`, `or`, `not` Together**

```python
a = 10
b = 20
c = 30

print((a < b) and (b < c))      # True
print((a > b) or (b < c))       # True
print(not(a == 10))             # False
```

---

### **Short-Circuit Behavior**

Python uses **short-circuit evaluation** —
It **stops evaluating** as soon as the result is determined.

Example:

```python
a = 10
b = 0

# Here, (b != 0) is False, so the second condition is not checked
if b != 0 and (a / b > 2):
    print("Valid")
else:
    print("Invalid")
```

✅ Output:

```
Invalid
```

No error occurs even though `a / b` would cause a ZeroDivisionError — because Python **skipped** that part due to `and`.

---

### **Using Logical Operators with Non-Boolean Values**

Python treats **non-zero / non-empty** values as `True`,
and `0`, `None`, `''`, `[]`, `{}` as `False`.

```python
print(10 and 20)   # 20
print(0 and 20)    # 0
print(10 or 0)     # 10
print(not 0)       # True
```

✅ This is because `and` returns the **last evaluated value**,
and `or` returns the **first truthy value**.

---

### **Example Program: Logical Operators**

```python
x = 15
y = 10
z = 5

print("x > y and y > z:", x > y and y > z)
print("x > y or y < z:", x > y or y < z)
print("not(x > y):", not(x > y))
```

**Output:**

```
x > y and y > z: True
x > y or y < z: True
not(x > y): False
```

---

### **Summary Table**

| **Operator** | **Description**              | **Example**        | **Result** |
| ------------ | ---------------------------- | ------------------ | ---------- |
| `and`        | True if both are True        | `5 > 2 and 10 > 5` | `True`     |
| `or`         | True if at least one is True | `5 > 10 or 10 > 5` | `True`     |
| `not`        | Reverses the result          | `not(5 > 3)`       | `False`    |

---

### **Quick Practice**

Write a Python program that:

1. Takes your age and whether you have an ID (`True/False`) as input.
2. Uses logical operators to check if you’re allowed entry:

   * Age ≥ 18 **and** has ID → “Access Granted”
   * Otherwise → “Access Denied”


