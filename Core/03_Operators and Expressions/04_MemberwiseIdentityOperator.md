
## 🧠 **Membership and Identity Operators**

Python provides special operators to check:

* Whether a **value exists** in a sequence (like a list, string, or tuple).
* Whether two **variables refer to the same object** in memory.

Let’s learn both one by one 👇

---

## 🧩 **Membership Operators**

---

### **Definition:**

Membership operators are used to **test whether a value is present in a sequence** (like a list, tuple, string, or set).

---

### **Operators:**

| **Operator** | **Description**                                              | **Example**          | **Result** |
| ------------ | ------------------------------------------------------------ | -------------------- | ---------- |
| `in`         | Returns `True` if the value is found in the sequence         | `'a' in 'apple'`     | `True`     |
| `not in`     | Returns `True` if the value is **not** found in the sequence | `'x' not in 'apple'` | `True`     |

---

### **Examples:**

#### **1️⃣ Using `in` with a string**

```python
name = "Python"
print('P' in name)      # True
print('z' in name)      # False
```

---

#### **2️⃣ Using `not in` with a string**

```python
print('a' not in "Data")   # False (because 'a' is present)
```

---

#### **3️⃣ Using `in` with a list**

```python
numbers = [1, 2, 3, 4, 5]
print(3 in numbers)     # True
print(10 in numbers)    # False
```

---

#### **4️⃣ Using `not in` with a list**

```python
numbers = [1, 2, 3, 4, 5]
print(7 not in numbers)   # True
```

---

#### **5️⃣ Using with tuple and dictionary**

```python
fruits = ('apple', 'banana', 'cherry')
print('apple' in fruits)  # True

student = {'name': 'Alice', 'age': 20}
print('name' in student)  # True (checks keys, not values)
print('Alice' in student) # False
```

✅ **Note:** For dictionaries, `in` checks only the **keys**, not the values.

---

### **Example Program: Membership Operators**

```python
my_list = [10, 20, 30, 40, 50]

print(20 in my_list)       # True
print(25 not in my_list)   # True
print(50 not in my_list)   # False
```

**Output:**

```
True
True
False
```

---

## 🪞 **Identity Operators**

---

### **Definition:**

Identity operators check **whether two variables refer to the same object in memory** (not just equal values).

---

### **Operators:**

| **Operator** | **Description**                                            | **Example**  | **Result**   |
| ------------ | ---------------------------------------------------------- | ------------ | ------------ |
| `is`         | True if both variables **point to the same object**        | `x is y`     | True / False |
| `is not`     | True if both variables **do not point to the same object** | `x is not y` | True / False |

---

### **Examples:**

#### **1️⃣ Using `is`**

```python
x = [1, 2, 3]
y = x
print(x is y)   # True (same object)
```

Both `x` and `y` refer to the **same list** in memory.

---

#### **2️⃣ Using `is not`**

```python
a = [1, 2, 3]
b = [1, 2, 3]
print(a is not b)  # True (different objects)
```

✅ Even though `a` and `b` have the **same values**, they are **different objects**.

---

#### **3️⃣ Comparing Immutable Objects**

```python
x = 10
y = 10
print(x is y)   # True (same object, because integers are cached)
```

> ⚡ For small integers and short strings, Python **reuses memory**,
> so variables with the same value may point to the same object.

---

#### **4️⃣ Checking Identity with `None`**

```python
x = None
print(x is None)      # True
print(x is not None)  # False
```

✅ **Best practice:**
Always use `is` and `is not` to compare with `None` instead of `==`.

---

### **Example Program: Identity Operators**

```python
x = [10, 20, 30]
y = x
z = [10, 20, 30]

print(x is y)     # True
print(x is z)     # False
print(x == z)     # True
```

**Output:**

```
True
False
True
```

🧩 **Explanation:**

* `x is y` → same memory location
* `x is z` → different memory
* `x == z` → values are equal

---

### **Checking Memory Address (for curiosity)**

You can use the `id()` function to see the memory location:

```python
x = [1, 2, 3]
y = [1, 2, 3]
print(id(x))
print(id(y))
print(x is y)
```

Different `id` values → different memory locations.

---

## ✅ **Summary Table**

| **Operator Type** | **Operator** | **Meaning**                 | **Example**          | **Result**     |
| ----------------- | ------------ | --------------------------- | -------------------- | -------------- |
| **Membership**    | `in`         | Value found in sequence     | `'a' in 'apple'`     | `True`         |
| **Membership**    | `not in`     | Value not found in sequence | `'z' not in 'apple'` | `True`         |
| **Identity**      | `is`         | Same object                 | `x is y`             | `True / False` |
| **Identity**      | `is not`     | Different objects           | `x is not y`         | `True / False` |

---

### **Quick Practice:**

Write a Python program that:

1. Creates a list of numbers.
2. Checks if a given number is in the list using `in`.
3. Creates two variables with the same value and checks if they are the same object using `is`.


