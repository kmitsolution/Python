
## ⚖️ **Comparison Operators in Python**

---

### **What Are Comparison Operators?**

**Comparison operators** are used to **compare two values**.
They return a **Boolean value** — either `True` or `False`.

---

### **List of Comparison Operators**

| **Operator** | **Name**                 | **Example** | **Result** |
| ------------ | ------------------------ | ----------- | ---------- |
| `==`         | Equal to                 | `5 == 5`    | `True`     |
| `!=`         | Not equal to             | `5 != 3`    | `True`     |
| `>`          | Greater than             | `7 > 3`     | `True`     |
| `<`          | Less than                | `4 < 2`     | `False`    |
| `>=`         | Greater than or equal to | `5 >= 5`    | `True`     |
| `<=`         | Less than or equal to    | `6 <= 7`    | `True`     |

---

### **1️⃣ Equal To (`==`)**

Checks if two values are **equal**.

```python
a = 10
b = 10
print(a == b)   # True
```

✅ Works with both numbers and strings:

```python
print("apple" == "apple")  # True
print("Apple" == "apple")  # False (case-sensitive)
```

---

### **2️⃣ Not Equal To (`!=`)**

Checks if two values are **not equal**.

```python
a = 5
b = 3
print(a != b)   # True
```

---

### **3️⃣ Greater Than (`>`)**

Checks if the **left operand** is greater than the right operand.

```python
a = 10
b = 8
print(a > b)   # True
```

---

### **4️⃣ Less Than (`<`)**

Checks if the **left operand** is less than the right operand.

```python
a = 4
b = 9
print(a < b)   # True
```

---

### **5️⃣ Greater Than or Equal To (`>=`)**

True if the left operand is **greater than or equal** to the right operand.

```python
a = 10
b = 10
print(a >= b)   # True
```

---

### **6️⃣ Less Than or Equal To (`<=`)**

True if the left operand is **less than or equal** to the right operand.

```python
a = 5
b = 10
print(a <= b)   # True
```

---

### **Example Program: Comparison Operators**

```python
a = 10
b = 20

print("a == b:", a == b)
print("a != b:", a != b)
print("a > b:", a > b)
print("a < b:", a < b)
print("a >= b:", a >= b)
print("a <= b:", a <= b)
```

**Output:**

```
a == b: False
a != b: True
a > b: False
a < b: True
a >= b: False
a <= b: True
```

---

### **Using Comparison Operators with Strings**

Comparison between strings is **lexicographical** (like dictionary order), based on **Unicode values**.

```python
print("apple" > "banana")   # False
print("grape" < "orange")   # True
print("A" < "a")            # True (uppercase letters have smaller Unicode values)
```

---

### **Using Comparison Operators in Conditions**

They are most commonly used inside **if statements**.

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("You are an adult.")
else:
    print("You are a minor.")
```

---

### **Combining Comparisons**

You can combine multiple comparisons using **logical operators** (`and`, `or`, `not`):

```python
num = 15
print(num > 10 and num < 20)  # True
```

✅ Python also allows **chained comparisons**:

```python
x = 5
print(1 < x < 10)   # True (checks both 1 < x and x < 10)
```

---

### **Summary Table**

| **Operator** | **Meaning**              | **Example** | **Result** |
| ------------ | ------------------------ | ----------- | ---------- |
| `==`         | Equal to                 | `5 == 5`    | `True`     |
| `!=`         | Not equal to             | `5 != 3`    | `True`     |
| `>`          | Greater than             | `7 > 3`     | `True`     |
| `<`          | Less than                | `4 < 2`     | `False`    |
| `>=`         | Greater than or equal to | `5 >= 5`    | `True`     |
| `<=`         | Less than or equal to    | `6 <= 7`    | `True`     |

---

### **Quick Practice**

Write a Python program that:

1. Takes two numbers as input.
2. Compares them using all comparison operators.
3. Displays the results clearly.


