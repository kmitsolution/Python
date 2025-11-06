**Arithmetic Operators** 🧮

---

## ➕ **Arithmetic Operators in Python**

Arithmetic operators are used to perform **mathematical calculations** such as addition, subtraction, multiplication, division, etc.

---

### **List of Arithmetic Operators**

| **Operator** | **Name**               | **Example** | **Result**                       |
| ------------ | ---------------------- | ----------- | -------------------------------- |
| `+`          | Addition               | `10 + 5`    | `15`                             |
| `-`          | Subtraction            | `10 - 5`    | `5`                              |
| `*`          | Multiplication         | `10 * 5`    | `50`                             |
| `/`          | Division               | `10 / 5`    | `2.0` (always returns **float**) |
| `//`         | Floor Division         | `10 // 3`   | `3` (removes decimal part)       |
| `%`          | Modulus (Remainder)    | `10 % 3`    | `1`                              |
| `**`         | Exponentiation (Power) | `2 ** 3`    | `8`                              |

---

### **1️⃣ Addition (`+`)**

Used to add two numbers.

```python
a = 10
b = 5
print(a + b)   # 15
```

✅ You can also add strings (concatenation):

```python
print("Hello" + " World")  # Hello World
```

---

### **2️⃣ Subtraction (`-`)**

Used to subtract one number from another.

```python
a = 10
b = 4
print(a - b)   # 6
```

---

### **3️⃣ Multiplication (`*`)**

Used to multiply numbers.

```python
a = 6
b = 7
print(a * b)   # 42
```

✅ You can also repeat strings using `*`:

```python
print("Hi " * 3)
```

Output:

```
Hi Hi Hi 
```

---

### **4️⃣ Division (`/`)**

Used to divide one number by another.
Always returns a **float** value, even if the result is a whole number.

```python
a = 10
b = 2
print(a / b)   # 5.0
```

---

### **5️⃣ Floor Division (`//`)**

Divides and **truncates** (removes) the decimal part.
Always rounds down to the nearest integer.

```python
a = 10
b = 3
print(a // b)   # 3
```

✅ Works with negative numbers too:

```python
print(-10 // 3)  # -4  (because -3.33 → rounded down to -4)
```

---

### **6️⃣ Modulus (`%`)**

Gives the **remainder** after division.

```python
a = 10
b = 3
print(a % b)   # 1
```

✅ Often used to check if a number is even or odd:

```python
num = 7
if num % 2 == 0:
    print("Even")
else:
    print("Odd")
```

---

### **7️⃣ Exponentiation (`**`)**

Raises one number to the power of another.

```python
a = 2
b = 3
print(a ** b)   # 8  (2³ = 8)
```

---

### **Example Program: Using All Arithmetic Operators**

```python
a = 10
b = 3

print("Addition:", a + b)
print("Subtraction:", a - b)
print("Multiplication:", a * b)
print("Division:", a / b)
print("Floor Division:", a // b)
print("Modulus:", a % b)
print("Exponentiation:", a ** b)
```

**Output:**

```
Addition: 13
Subtraction: 7
Multiplication: 30
Division: 3.3333333333333335
Floor Division: 3
Modulus: 1
Exponentiation: 1000
```

---

### **Operator Precedence (Order of Operations)**

Python follows the **PEMDAS** rule (Parentheses, Exponents, Multiplication/Division, Addition/Subtraction):

| **Operator**        | **Precedence Level** |
| ------------------- | -------------------- |
| `()`                | Highest              |
| `**`                | Next                 |
| `*`, `/`, `//`, `%` | Then                 |
| `+`, `-`            | Lowest               |

**Example:**

```python
result = 10 + 3 * 2 ** 2
print(result)
```

**Steps:**

1. Exponentiation: `2 ** 2 = 4`
2. Multiplication: `3 * 4 = 12`
3. Addition: `10 + 12 = 22`

✅ Output:

```
22
```

---

### **Quick Practice**

Write a Python program that:

1. Takes two numbers as input.
2. Performs all arithmetic operations on them.
3. Prints the results clearly labeled.


