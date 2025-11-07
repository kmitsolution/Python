## 🧠 **Operator Precedence and Associativity in Python**

---

### **What is Operator Precedence?**

**Operator precedence** determines the **order in which operators are evaluated** in an expression.

Just like in mathematics:

```
2 + 3 * 4  →  2 + (3 * 4) = 14
```

Here, `*` (multiplication) has **higher precedence** than `+` (addition).

---

### **What is Associativity?**

When two operators have the **same precedence**,
**associativity** decides the **direction** of evaluation —
either **left to right** or **right to left**.

Example:

```
100 / 10 * 2
```

Both `/` and `*` have the same precedence and **left-to-right** associativity:

```
(100 / 10) * 2 = 20
```

---

## ⚙️ **Operator Precedence Table (Highest → Lowest)**

| **Precedence Level** | **Operator**                             | **Description**                                   | **Associativity** |               |
| -------------------- | ---------------------------------------- | ------------------------------------------------- | ----------------- | ------------- |
| 1️⃣ (Highest)        | `()`                                     | Parentheses (grouping)                            | Left to Right     |               |
| 2️⃣                  | `**`                                     | Exponentiation                                    | **Right to Left** |               |
| 3️⃣                  | `~`, `+`, `-`                            | Unary operators                                   | Right to Left     |               |
| 4️⃣                  | `*`, `/`, `//`, `%`                      | Multiplication, Division, Floor Division, Modulus | Left to Right     |               |
| 5️⃣                  | `+`, `-`                                 | Addition and Subtraction                          | Left to Right     |               |
| 6️⃣                  | `<<`, `>>`                               | Bitwise shift operators                           | Left to Right     |               |
| 7️⃣                  | `&`                                      | Bitwise AND                                       | Left to Right     |               |
| 8️⃣                  | `^`                                      | Bitwise XOR                                       | Left to Right     |               |
| 9️⃣                  | `                                        | `                                                 | Bitwise OR        | Left to Right |
| 🔟                   | `<`, `<=`, `>`, `>=`, `==`, `!=`         | Comparison operators                              | Left to Right     |               |
| 11️⃣                 | `not`                                    | Logical NOT                                       | Right to Left     |               |
| 12️⃣                 | `and`                                    | Logical AND                                       | Left to Right     |               |
| 13️⃣                 | `or`                                     | Logical OR                                        | Left to Right     |               |
| 14️⃣                 | `if … else`                              | Conditional expression                            | Right to Left     |               |
| 15️⃣ (Lowest)        | `=`, `+=`, `-=`, `*=`, `/=`, `//=`, `%=` | Assignment operators                              | Right to Left     |               |

---

### 🧮 **Examples of Operator Precedence**

#### **1️⃣ Multiplication before addition**

```python
result = 10 + 5 * 2
print(result)
```

✅ **Output:**

```
20
```

➡️ `*` has higher precedence than `+`, so:

```
10 + (5 * 2) = 20
```

---

#### **2️⃣ Parentheses change precedence**

```python
result = (10 + 5) * 2
print(result)
```

✅ **Output:**

```
30
```

➡️ Parentheses are evaluated **first**.

---

#### **3️⃣ Exponentiation (`**`) is right-associative**

```python
result = 2 ** 3 ** 2
print(result)
```

✅ **Output:**

```
512
```

➡️ Because it is evaluated as:

```
2 ** (3 ** 2) = 2 ** 9 = 512
```

---

#### **4️⃣ Unary minus and exponent**

```python
result = -2 ** 3
print(result)
```

✅ **Output:**

```
-8
```

➡️ Evaluated as:

```
-(2 ** 3) = -8
```

not `(-2) ** 3`.

---

#### **5️⃣ Mixed arithmetic**

```python
result = 10 + 2 * 3 - 6 / 2
print(result)
```

✅ **Output:**

```
13.0
```

➡️ Step by step:

```
10 + (2 * 3) - (6 / 2)
10 + 6 - 3
= 13.0
```

---

#### **6️⃣ Comparison and Logical Operators**

```python
result = 5 > 3 and 10 < 20
print(result)
```

✅ **Output:**

```
True
```

➡️ Comparison happens **before** logical `and`.

---

#### **7️⃣ Assignment has lowest precedence**

```python
x = 10
y = 20
z = x + y * 2
print(z)
```

✅ **Output:**

```
50
```

➡️ Multiplication first → addition → then assignment.

---

### ⚡ **Associativity Examples**

#### **Left-to-Right**

```python
print(100 / 10 * 2)
```

✅ **Output:**

```
20.0
```

➡️ `(100 / 10)` → `10 * 2 = 20.0`

---

#### **Right-to-Left**

```python
print(2 ** 3 ** 2)
```

✅ **Output:**

```
512
```

➡️ `2 ** (3 ** 2)`

---

### 🧩 **Example: Combined Expression**

```python
result = 10 + 3 * 2 ** 2 > 15 and not False
print(result)
```

Let’s evaluate step by step:

1️⃣ `2 ** 2` → `4`
2️⃣ `3 * 4` → `12`
3️⃣ `10 + 12` → `22`
4️⃣ `22 > 15` → `True`
5️⃣ `not False` → `True`
6️⃣ `True and True` → `True`

✅ **Output:**

```
True
```

---

### 💡 **Best Practice**

Even though Python follows strict precedence rules,
✅ **always use parentheses** `()` to make expressions clearer.

Example:

```python
result = (a + b) * c
```

This improves readability and avoids confusion.

---

### **Summary Table: Quick Reference**

| **Priority** | **Operator(s)**                  | **Associativity** |               |
| ------------ | -------------------------------- | ----------------- | ------------- |
| 1            | `()`                             | Left to Right     |               |
| 2            | `**`                             | Right to Left     |               |
| 3            | `+x`, `-x`, `~x`                 | Right to Left     |               |
| 4            | `*`, `/`, `//`, `%`              | Left to Right     |               |
| 5            | `+`, `-`                         | Left to Right     |               |
| 6            | `<<`, `>>`                       | Left to Right     |               |
| 7            | `&`                              | Left to Right     |               |
| 8            | `^`                              | Left to Right     |               |
| 9            | `                                | `                 | Left to Right |
| 10           | `<`, `<=`, `>`, `>=`, `==`, `!=` | Left to Right     |               |
| 11           | `not`                            | Right to Left     |               |
| 12           | `and`                            | Left to Right     |               |
| 13           | `or`                             | Left to Right     |               |
| 14           | `=`, `+=`, `-=`, `*=`, `/=`      | Right to Left     |               |

---

### **Quick Practice 💪**

Write a Python program to evaluate:

```python
result = 5 + 2 * 3 ** 2 and not False or 4 < 2
```

