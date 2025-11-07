
## 🧾 **Assignment Operators in Python**

---

### **What Are Assignment Operators?**

**Assignment operators** are used to **assign values** to variables.
They can also **combine assignment with arithmetic or logical operations**.

---

### **Basic Assignment**

The **`=`** operator assigns a value to a variable.

```python
x = 10
y = 5
print(x, y)
```

✅ Output:

```
10 5
```

---

### **List of Assignment Operators**

| **Operator** | **Example** | **Equivalent To** | **Explanation**                    |        |    |                        |
| ------------ | ----------- | ----------------- | ---------------------------------- | ------ | -- | ---------------------- |
| `=`          | `x = 5`     | `x = 5`           | Assigns value 5 to x               |        |    |                        |
| `+=`         | `x += 3`    | `x = x + 3`       | Adds and assigns                   |        |    |                        |
| `-=`         | `x -= 3`    | `x = x - 3`       | Subtracts and assigns              |        |    |                        |
| `*=`         | `x *= 3`    | `x = x * 3`       | Multiplies and assigns             |        |    |                        |
| `/=`         | `x /= 3`    | `x = x / 3`       | Divides and assigns (float result) |        |    |                        |
| `//=`        | `x //= 3`   | `x = x // 3`      | Floor divides and assigns          |        |    |                        |
| `%=`         | `x %= 3`    | `x = x % 3`       | Finds remainder and assigns        |        |    |                        |
| `**=`        | `x **= 3`   | `x = x ** 3`      | Raises to power and assigns        |        |    |                        |
| `&=`         | `x &= 3`    | `x = x & 3`       | Bitwise AND and assigns            |        |    |                        |
| `            | =`          | `x                | = 3`                               | `x = x | 3` | Bitwise OR and assigns |
| `^=`         | `x ^= 3`    | `x = x ^ 3`       | Bitwise XOR and assigns            |        |    |                        |
| `>>=`        | `x >>= 2`   | `x = x >> 2`      | Bitwise right shift and assigns    |        |    |                        |
| `<<=`        | `x <<= 2`   | `x = x << 2`      | Bitwise left shift and assigns     |        |    |                        |

---

### **Examples of Arithmetic Assignment Operators**

#### **1️⃣ Addition Assignment (`+=`)**

```python
x = 10
x += 5
print(x)  # 15
```

---

#### **2️⃣ Subtraction Assignment (`-=`)**

```python
x = 10
x -= 3
print(x)  # 7
```

---

#### **3️⃣ Multiplication Assignment (`*=`)**

```python
x = 4
x *= 3
print(x)  # 12
```

---

#### **4️⃣ Division Assignment (`/=`)**

```python
x = 10
x /= 4
print(x)  # 2.5
```

> 💡 Always returns a **float**, even if division is exact.

---

#### **5️⃣ Floor Division Assignment (`//=`)**

```python
x = 10
x //= 3
print(x)  # 3
```

---

#### **6️⃣ Modulus Assignment (`%=`)**

```python
x = 10
x %= 4
print(x)  # 2
```

---

#### **7️⃣ Exponent Assignment (`**=`)**

```python
x = 2
x **= 4
print(x)  # 16
```

---

### **Examples of Bitwise Assignment Operators**

#### **1️⃣ Bitwise AND (`&=`)**

```python
x = 5   # 0101
x &= 3  # 0011
print(x)  # 1
```

---

#### **2️⃣ Bitwise OR (`|=`)**

```python
x = 5   # 0101
x |= 3  # 0011
print(x)  # 7 (0111)
```

---

#### **3️⃣ Bitwise XOR (`^=`)**

```python
x = 5   # 0101
x ^= 3  # 0011
print(x)  # 6 (0110)
```

---

#### **4️⃣ Right Shift (`>>=`)**

```python
x = 8   # 1000
x >>= 2
print(x)  # 2 (0010)
```

---

#### **5️⃣ Left Shift (`<<=`)**

```python
x = 3   # 0011
x <<= 2
print(x)  # 12 (1100)
```

---

### **Example Program: Assignment Operators**

```python
x = 10
print("Initial value of x:", x)

x += 5
print("After x += 5:", x)

x -= 3
print("After x -= 3:", x)

x *= 2
print("After x *= 2:", x)

x /= 4
print("After x /= 4:", x)

x **= 3
print("After x **= 3:", x)
```

**Output:**

```
Initial value of x: 10
After x += 5: 15
After x -= 3: 12
After x *= 2: 24
After x /= 4: 6.0
After x **= 3: 216.0
```

---

### **Why Use Compound Assignment Operators?**

✅ Makes code **shorter and cleaner**
✅ **Avoids repetition** of variable names
✅ Easier to read and maintain

**Example:**

```python
# Instead of this
x = x + 10

# You can write
x += 10
```

---

### **Summary Table**

| **Operator** | **Meaning**             | **Example** | **Result (if x=10)** |      |                   |
| ------------ | ----------------------- | ----------- | -------------------- | ---- | ----------------- |
| `=`          | Assign                  | `x = 10`    | 10                   |      |                   |
| `+=`         | Add and assign          | `x += 5`    | 15                   |      |                   |
| `-=`         | Subtract and assign     | `x -= 3`    | 7                    |      |                   |
| `*=`         | Multiply and assign     | `x *= 2`    | 20                   |      |                   |
| `/=`         | Divide and assign       | `x /= 4`    | 2.5                  |      |                   |
| `//=`        | Floor divide and assign | `x //= 3`   | 3                    |      |                   |
| `%=`         | Modulus and assign      | `x %= 4`    | 2                    |      |                   |
| `**=`        | Power and assign        | `x **= 3`   | 1000                 |      |                   |
| `&=`         | Bitwise AND             | `x &= 2`    | Depends on binary    |      |                   |
| `            | =`                      | Bitwise OR  | `x                   | = 2` | Depends on binary |
| `^=`         | Bitwise XOR             | `x ^= 2`    | Depends on binary    |      |                   |

---

### **Quick Practice**

Write a Python program that:

1. Takes a number as input.
2. Uses `+=`, `-=`, `*=`, `/=`, and `**=` operators to modify it step by step.
3. Prints the value after each operation.


