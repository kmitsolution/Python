
# 🧠 **Tuples in Python**

---

## 🪶 **1️⃣ What is a Tuple?**

A **tuple** is an **ordered**, **immutable** collection of elements.
Like lists, tuples can store **different data types**, including strings, numbers, and even other tuples.

---

### **Example:**

```python
my_tuple = (10, 20, 30, 40)
print(my_tuple)
```

✅ **Output:**

```
(10, 20, 30, 40)
```

---

## 📋 **2️⃣ Creating Tuples**

You can create tuples using **parentheses `()`** or the **`tuple()`** constructor.

### **Examples:**

```python
t1 = (1, 2, 3, 4)
t2 = ("apple", "banana", "cherry")
t3 = (1, "Hello", 3.14, True)
```

---

### **Empty Tuple**

```python
empty = ()
print(empty)
```

✅ **Output:**

```
()
```

---

### **Single-Element Tuple (Important!)**

When creating a tuple with only **one element**, include a **comma** after the element.
Otherwise, Python treats it as a regular value.

```python
t1 = (5)      # Not a tuple
t2 = (5,)     # ✅ Tuple
print(type(t1))  # int
print(type(t2))  # tuple
```

✅ **Output:**

```
<class 'int'>
<class 'tuple'>
```

---

### **Using the tuple() Constructor**

```python
t = tuple([1, 2, 3])
print(t)
```

✅ **Output:**

```
(1, 2, 3)
```

---

## 🔍 **3️⃣ Accessing Tuple Elements**

Tuples support **indexing** and **slicing** like lists.

```python
t = (10, 20, 30, 40, 50)
print(t[0])    # 10
print(t[-1])   # 50
print(t[1:4])  # (20, 30, 40)
```

✅ **Output:**

```
10
50
(20, 30, 40)
```

---

## ✏️ **4️⃣ Immutability**

Once created, you **cannot modify**, **add**, or **remove** elements in a tuple.

```python
t = (1, 2, 3)
t[0] = 10      # ❌ Error
```

✅ **Output:**

```
TypeError: 'tuple' object does not support item assignment
```

🧠 **Why immutability matters:**

* Tuples are **faster** than lists.
* They can be used as **dictionary keys** and **set elements**.

---

## 🔁 **5️⃣ Iterating Through Tuples**

```python
colors = ("red", "green", "blue")
for c in colors:
    print(c)
```

✅ **Output:**

```
red
green
blue
```

---

## 🧮 **6️⃣ Tuple Operations**

Tuples support several operations just like lists (except modification).

---

### **Concatenation**

```python
t1 = (1, 2, 3)
t2 = (4, 5)
print(t1 + t2)
```

✅ **Output:**

```
(1, 2, 3, 4, 5)
```

---

### **Repetition**

```python
t = ("Hi",) * 3
print(t)
```

✅ **Output:**

```
('Hi', 'Hi', 'Hi')
```

---

### **Membership Test**

```python
t = (10, 20, 30)
print(20 in t)   # True
print(50 not in t)  # True
```

---

### **Length**

```python
t = (1, 2, 3, 4)
print(len(t))
```

✅ **Output:**

```
4
```

---

### **Nested Tuples**

Tuples can contain other tuples.

```python
nested = ((1, 2), (3, 4))
print(nested[0][1])
```

✅ **Output:**

```
2
```

---

## 🧰 **7️⃣ Tuple Methods**

Tuples have only **two built-in methods**:

| **Method** | **Description**                         | **Example**                |
| ---------- | --------------------------------------- | -------------------------- |
| `count(x)` | Returns the number of times `x` appears | `(1,2,2,3).count(2)` → `2` |
| `index(x)` | Returns the first index of `x`          | `(1,2,3,2).index(3)` → `2` |

---

### **Example**

```python
t = (1, 2, 3, 2, 2, 4)
print(t.count(2))   # 3
print(t.index(3))   # 2
```

✅ **Output:**

```
3
2
```

---

## 🎯 **8️⃣ Tuple Packing and Unpacking**

---

### **Tuple Packing**

Putting multiple values together into one tuple.

```python
person = ("Alice", 25, "Engineer")
print(person)
```

---

### **Tuple Unpacking**

Extracting tuple values into separate variables.

```python
name, age, job = person
print(name)
print(age)
print(job)
```

✅ **Output:**

```
Alice
25
Engineer
```

---

### **Unpacking with `*` Operator**

```python
numbers = (1, 2, 3, 4, 5)
a, *b, c = numbers
print(a)  # 1
print(b)  # [2, 3, 4]
print(c)  # 5
```

✅ **Output:**

```
1
[2, 3, 4]
5
```

---

## 🧩 **9️⃣ Tuple vs List**

| **Feature** | **List**          | **Tuple**  |
| ----------- | ----------------- | ---------- |
| Brackets    | `[]`              | `()`       |
| Mutable     | ✅ Yes             | ❌ No       |
| Methods     | Many              | Few        |
| Speed       | Slower            | Faster     |
| Use case    | Data that changes | Fixed data |

---

## 💡 **🔟 Converting Between Lists and Tuples**

You can convert easily using built-in functions.

```python
# Tuple to List
t = (1, 2, 3)
lst = list(t)
print(lst)

# List to Tuple
new_tuple = tuple(lst)
print(new_tuple)
```

✅ **Output:**

```
[1, 2, 3]
(1, 2, 3)
```

---

## 🧮 **11️⃣ Built-in Functions for Tuples**

| **Function** | **Description**              | **Example** |
| ------------ | ---------------------------- | ----------- |
| `len()`      | Number of items              | `len(t)`    |
| `max()`      | Largest item                 | `max(t)`    |
| `min()`      | Smallest item                | `min(t)`    |
| `sum()`      | Sum of elements (if numeric) | `sum(t)`    |
| `sorted()`   | Returns sorted list          | `sorted(t)` |

---

### **Example**

```python
t = (4, 1, 7, 3)
print(max(t))     # 7
print(min(t))     # 1
print(sum(t))     # 15
print(sorted(t))  # [1, 3, 4, 7]
```

---

## 🧠 **12️⃣ Practice Questions**

Try these to test your understanding 👇

1. Create a tuple of numbers and **find their sum** and **average**.
2. Write a program to **count how many times an element appears** in a tuple.
3. Create two tuples and **concatenate** them.
4. Given a nested tuple `((1,2), (3,4), (5,6))`, extract the **second element** of each inner tuple into a new tuple.
5. Convert a list `[‘a’, ‘b’, ‘c’]` into a tuple and verify its type.
6. Unpack a tuple `(10, 20, 30, 40, 50)` into variables and use `*` to collect middle values.
7. Sort a tuple of integers `(5,3,8,1)` in ascending order.
8. Find the **index** of the first occurrence of `10` in `(5,10,15,10,20)`.

---

## ✅ **Summary Table**

| **Concept**       | **Description**        | **Example**   |
| ----------------- | ---------------------- | ------------- |
| Creation          | Use `()`               | `(1, 2, 3)`   |
| Access            | Use index              | `t[0]`        |
| Immutable         | Cannot change          | ❌ `t[0] = 5`  |
| Methods           | `count()`, `index()`   | `t.count(2)`  |
| Packing/Unpacking | Group & extract values | `a,b = (1,2)` |
| Conversion        | Between list & tuple   | `tuple(list)` |

---


