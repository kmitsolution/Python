
## 🧠 **Bitwise Operators in Python**

---

### **Definition**

Bitwise operators are used to **perform operations on binary numbers (bits)**.
They operate directly on the **bits of integers**, not on decimal values.

Each number in memory is stored as **0s and 1s**,
and bitwise operators allow us to manipulate those bits directly.

---

### **List of Bitwise Operators**

| **Operator** | **Name**    | **Description**                         | **Example**                           |    |    |
| ------------ | ----------- | --------------------------------------- | ------------------------------------- | -- | -- |
| `&`          | AND         | Sets each bit to 1 if both bits are 1   | `a & b`                               |    |    |
| `            | `           | OR                                      | Sets each bit to 1 if either bit is 1 | `a | b` |
| `^`          | XOR         | Sets each bit to 1 if only one bit is 1 | `a ^ b`                               |    |    |
| `~`          | NOT         | Inverts all the bits (1 → 0, 0 → 1)     | `~a`                                  |    |    |
| `<<`         | Left Shift  | Shifts bits to the left by n places     | `a << n`                              |    |    |
| `>>`         | Right Shift | Shifts bits to the right by n places    | `a >> n`                              |    |    |

---

### **Bitwise AND (`&`)**

✅ Returns `1` only if **both bits are 1**, else `0`.

```python
a = 5    # 0101
b = 3    # 0011

print(a & b)
```

**Binary calculation:**

```
   0101
 & 0011
 = 0001
```

✅ **Output:**

```
1
```

---

### **Bitwise OR (`|`)**

✅ Returns `1` if **either** of the bits is 1.

```python
a = 5    # 0101
b = 3    # 0011

print(a | b)
```

**Binary calculation:**

```
   0101
 | 0011
 = 0111
```

✅ **Output:**

```
7
```

---

### **Bitwise XOR (`^`)**

✅ Returns `1` if **only one** of the bits is 1 (not both).

```python
a = 5    # 0101
b = 3    # 0011

print(a ^ b)
```

**Binary calculation:**

```
   0101
 ^ 0011
 = 0110
```

✅ **Output:**

```
6
```

---

### **Bitwise NOT (`~`)**

✅ Inverts all bits (flips 1 → 0 and 0 → 1).
Also equivalent to `-(n + 1)` in Python (because of how negative numbers are represented).

```python
a = 5    # 0101
print(~a)
```

**Binary concept:**

```
~0101 = 1010
```

✅ **Output:**

```
-6
```

🧩 **Explanation:**
`~5` = `-(5 + 1)` = `-6`

---

### **Bitwise Left Shift (`<<`)**

✅ Shifts bits **to the left** by the specified number of positions.
Each shift left multiplies the number by **2**.

```python
a = 5    # 0101
print(a << 1)
print(a << 2)
```

**Binary calculation:**

```
0101 << 1 → 1010 (10)
0101 << 2 → 10100 (20)
```

✅ **Output:**

```
10
20
```

---

### **Bitwise Right Shift (`>>`)**

✅ Shifts bits **to the right** by the specified number of positions.
Each shift right divides the number by **2** (floor division).

```python
a = 10   # 1010
print(a >> 1)
print(a >> 2)
```

**Binary calculation:**

```
1010 >> 1 → 0101 (5)
1010 >> 2 → 0010 (2)
```

✅ **Output:**

```
5
2
```

---

### **Bitwise Operations Example**

```python
a = 12  # 1100
b = 6   # 0110

print("a & b =", a & b)
print("a | b =", a | b)
print("a ^ b =", a ^ b)
print("~a =", ~a)
print("a << 2 =", a << 2)
print("a >> 2 =", a >> 2)
```

**Output:**

```
a & b = 4
a | b = 14
a ^ b = 10
~a = -13
a << 2 = 48
a >> 2 = 3
```

---

### **Bitwise Truth Table**

| **a** | **b** | **a & b** | **a | b** | **a ^ b** |
| ----- | ----- | --------- | --------- | --------- |
| 0     | 0     | 0         | 0         | 0         |
| 0     | 1     | 0         | 1         | 1         |
| 1     | 0     | 0         | 1         | 1         |
| 1     | 1     | 1         | 1         | 0         |

---

### **Using Bitwise Operators in Practice**

#### ✅ **Check if a number is even or odd**

```python
num = 7
if num & 1:
    print("Odd number")
else:
    print("Even number")
```

**Output:**

```
Odd number
```

(If the last bit is 1 → Odd, if 0 → Even)

---

#### ✅ **Multiply or divide by 2 using bit shifts**

```python
num = 8
print(num << 1)  # Multiply by 2 → 16
print(num >> 1)  # Divide by 2 → 4
```

---

### **Summary Table**

| **Operator** | **Meaning** | **Example (a=5, b=3)** | **Result** |    |   |
| ------------ | ----------- | ---------------------- | ---------- | -- | - |
| `&`          | Bitwise AND | `a & b`                | 1          |    |   |
| `            | `           | Bitwise OR             | `a         | b` | 7 |
| `^`          | Bitwise XOR | `a ^ b`                | 6          |    |   |
| `~`          | Bitwise NOT | `~a`                   | -6         |    |   |
| `<<`         | Left Shift  | `a << 1`               | 10         |    |   |
| `>>`         | Right Shift | `a >> 1`               | 2          |    |   |

---

### **Quick Practice 💡**

Write a Python program to:

1. Take two integer inputs `a` and `b`.
2. Perform all bitwise operations (`&`, `|`, `^`, `~`, `<<`, `>>`).
3. Display the results with explanations.


