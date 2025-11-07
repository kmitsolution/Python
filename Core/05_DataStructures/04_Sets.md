
# 🧠 **Sets in Python**

---

## 🪶 **1️⃣ What is a Set?**

A **set** is an **unordered**, **mutable**, and **unindexed** collection of **unique elements**.

* Duplicate elements are **automatically removed**.
* Sets are written using **curly braces `{}`** or the **`set()`** constructor.

---

### **Example**

```python
my_set = {1, 2, 3, 4, 5}
print(my_set)
```

✅ **Output:**

```
{1, 2, 3, 4, 5}
```

---

### **Duplicate Elements Are Removed**

```python
nums = {1, 2, 2, 3, 4, 4}
print(nums)
```

✅ **Output:**

```
{1, 2, 3, 4}
```

---

### **Different Data Types Allowed**

```python
mix = {10, "apple", 3.14, True}
print(mix)
```

✅ **Output:**

```
{10, 3.14, 'apple', True}
```

---

## 🪄 **2️⃣ Creating Sets**

### **Using Curly Braces**

```python
s = {1, 2, 3}
```

### **Using Constructor**

```python
s = set([1, 2, 3])
```

### **Empty Set**

```python
empty = set()     # ✅ Correct way
empty2 = {}       # ❌ Creates a dictionary, not a set
```

---

## 🔍 **3️⃣ Accessing Set Elements**

Sets are **unordered**, so elements **cannot be accessed by index**.
You can **loop through** them instead.

```python
fruits = {"apple", "banana", "cherry"}
for f in fruits:
    print(f)
```

✅ **Output:**

```
apple
banana
cherry
```

---

## ✏️ **4️⃣ Modifying Sets**

Sets are mutable — you can **add** or **remove** elements,
but you **cannot change** existing ones (no indexing).

---

### **Add Elements**

```python
fruits = {"apple", "banana"}
fruits.add("cherry")
print(fruits)
```

✅ **Output:**

```
{'apple', 'banana', 'cherry'}
```

---

### **Add Multiple Elements**

```python
fruits.update(["mango", "orange"])
print(fruits)
```

✅ **Output:**

```
{'banana', 'cherry', 'orange', 'apple', 'mango'}
```

---

### **Remove Elements**

```python
fruits.remove("banana")   # Removes specific item; error if not found
print(fruits)

fruits.discard("kiwi")    # No error if item not found
print(fruits)

fruits.pop()              # Removes a random item
print(fruits)
```

---

### **Clear and Delete**

```python
fruits.clear()  # Empty the set
print(fruits)   # set()
```

---

## ⚙️ **5️⃣ Set Operations**

Python provides powerful **mathematical operations** on sets.

Let’s take two example sets:

```python
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}
```

---

### **Union (A ∪ B)**

Combines elements from both sets (no duplicates).

```python
print(A | B)
print(A.union(B))
```

✅ **Output:**

```
{1, 2, 3, 4, 5, 6, 7, 8}
```

---

### **Intersection (A ∩ B)**

Common elements in both sets.

```python
print(A & B)
print(A.intersection(B))
```

✅ **Output:**

```
{4, 5}
```

---

### **Difference (A - B)**

Elements in A but not in B.

```python
print(A - B)
print(A.difference(B))
```

✅ **Output:**

```
{1, 2, 3}
```

---

### **Symmetric Difference (A △ B)**

Elements in A or B but not both.

```python
print(A ^ B)
print(A.symmetric_difference(B))
```

✅ **Output:**

```
{1, 2, 3, 6, 7, 8}
```

---

### **Subset and Superset**

```python
A = {1, 2, 3}
B = {1, 2, 3, 4, 5}

print(A.issubset(B))   # True
print(B.issuperset(A)) # True
```

---

### **Disjoint Sets**

```python
X = {1, 2}
Y = {3, 4}
print(X.isdisjoint(Y))  # True (no common elements)
```

---

## 🧰 **6️⃣ Set Methods Summary**

| **Method**                | **Description**                         |
| ------------------------- | --------------------------------------- |
| `add(x)`                  | Adds an element                         |
| `update(iterable)`        | Adds multiple elements                  |
| `remove(x)`               | Removes item; raises error if not found |
| `discard(x)`              | Removes item; no error if not found     |
| `pop()`                   | Removes a random element                |
| `clear()`                 | Removes all elements                    |
| `union(s)`                | Combines sets                           |
| `intersection(s)`         | Common elements                         |
| `difference(s)`           | Elements in one but not other           |
| `symmetric_difference(s)` | Elements not common                     |
| `issubset(s)`             | Checks if one is subset of another      |
| `issuperset(s)`           | Checks if one is superset of another    |
| `isdisjoint(s)`           | True if no elements in common           |

---

## 🧮 **7️⃣ Frozen Sets**

A **frozenset** is an **immutable** version of a set — its elements cannot be changed.

```python
fs = frozenset([1, 2, 3, 4])
print(fs)
# fs.add(5) ❌ Error
```

✅ **Output:**

```
frozenset({1, 2, 3, 4})
```

---

## 💡 **8️⃣ Set Comprehensions**

Like **list comprehensions**, but use `{}` instead of `[]`.

---

### **Syntax**

```python
{expression for item in iterable if condition}
```

---

### **Example 1: Squares of Numbers**

```python
squares = {x**2 for x in range(1, 6)}
print(squares)
```

✅ **Output:**

```
{1, 4, 9, 16, 25}
```

---

### **Example 2: Filter Even Numbers**

```python
evens = {x for x in range(10) if x % 2 == 0}
print(evens)
```

✅ **Output:**

```
{0, 2, 4, 6, 8}
```

---

### **Example 3: Remove Duplicates Using Set Comprehension**

```python
data = [1, 2, 2, 3, 4, 4, 5]
unique = {x for x in data}
print(unique)
```

✅ **Output:**

```
{1, 2, 3, 4, 5}
```

---

### **Example 4: Conditional Expression**

```python
nums = {x if x > 3 else 0 for x in range(6)}
print(nums)
```

✅ **Output:**

```
{0, 4, 5}
```

---

## 🧩 **9️⃣ Practice Questions**

1. Create two sets and find:

   * Union
   * Intersection
   * Difference
   * Symmetric Difference

2. Check if `{1, 2}` is a **subset** of `{1, 2, 3, 4}`.

3. Write a Python program to **remove duplicates from a list** using a set.

4. Use **set comprehension** to create a set of squares of numbers **divisible by 3** from 1–20.

5. Given a list of words, use a set to **find all unique words**.

6. Create two sets of even and odd numbers (1–10) and perform all **set operations** on them.

7. Write a program to check if two sets are **disjoint**.

---

## ✅ **Summary Table**

| **Concept**    | **Description**            | **Example**          |
| -------------- | -------------------------- | -------------------- |
| Create         | Use `{}` or `set()`        | `s = {1,2,3}`        |
| Unique         | Removes duplicates         | `{1,2,2}` → `{1,2}`  |
| Unordered      | No indexing                | ❌ `s[0]`             |
| Methods        | Add/remove/union/etc.      | `s.add(5)`           |
| Comprehension  | `{x**2 for x in range(5)}` | `{0,1,4,9,16}`       |
| Immutable form | `frozenset()`              | `frozenset({1,2,3})` |

---


