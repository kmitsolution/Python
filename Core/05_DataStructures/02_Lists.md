# 🧠 **Lists in Python**

---

## 📋 **1️⃣ What is a List?**

A **list** is a **collection** of **ordered**, **mutable** (changeable) elements.
Lists can store **different data types** — numbers, strings, booleans, even other lists!

---

### **Example**

```python
numbers = [10, 20, 30, 40]
fruits = ["apple", "banana", "cherry"]
mixed = [1, "Hello", 3.14, True]
```

✅ **Output**

```
[10, 20, 30, 40]
['apple', 'banana', 'cherry']
[1, 'Hello', 3.14, True]
```

---

## 🪶 **2️⃣ Creating Lists**

You can create lists in several ways:

```python
empty = []                   # Empty list
numbers = [1, 2, 3, 4, 5]    # With elements
words = list(("Python", "is", "fun"))  # Using list() constructor
```

---

### **Nested Lists**

Lists inside lists — useful for matrix-like data.

```python
matrix = [[1, 2, 3], [4, 5, 6]]
print(matrix[0])     # [1, 2, 3]
print(matrix[0][1])  # 2
```

---

## 🔍 **3️⃣ Accessing List Elements**

Elements are accessed using **index numbers**.

### **Example**

```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])   # apple
print(fruits[2])   # cherry
```

### **Negative Indexing**

```python
print(fruits[-1])  # cherry
print(fruits[-2])  # banana
```

---

## ✂️ **4️⃣ Slicing Lists**

You can extract portions of a list using slicing.

### **Syntax:**

```python
list[start:end:step]
```

### **Example**

```python
numbers = [10, 20, 30, 40, 50, 60]
print(numbers[1:4])     # [20, 30, 40]
print(numbers[:3])      # [10, 20, 30]
print(numbers[3:])      # [40, 50, 60]
print(numbers[::-1])    # [60, 50, 40, 30, 20, 10]
```

---

## ✏️ **5️⃣ Modifying Lists**

Lists are **mutable**, so you can **change**, **add**, or **remove** elements.

---

### **Changing Elements**

```python
fruits = ["apple", "banana", "cherry"]
fruits[1] = "orange"
print(fruits)
```

✅ **Output**

```
['apple', 'orange', 'cherry']
```

---

### **Adding Elements**

```python
fruits.append("mango")        # Add to end
fruits.insert(1, "kiwi")      # Add at position
print(fruits)
```

✅ **Output**

```
['apple', 'kiwi', 'orange', 'cherry', 'mango']
```

---

### **Extending a List**

```python
a = [1, 2, 3]
b = [4, 5]
a.extend(b)
print(a)
```

✅ **Output**

```
[1, 2, 3, 4, 5]
```

---

### **Removing Elements**

```python
fruits.remove("orange")   # Remove by value
print(fruits)

popped = fruits.pop()     # Remove last item
print(popped)

del fruits[0]             # Remove by index
print(fruits)
```

✅ **Output**

```
['apple', 'kiwi', 'cherry', 'mango']
mango
['kiwi', 'cherry']
```

---

### **Clearing a List**

```python
fruits.clear()
print(fruits)   # []
```

---

## 🧰 **6️⃣ Useful List Methods**

Let’s summarize commonly used **list methods**:

| **Method**         | **Description**                         | **Example**           |
| ------------------ | --------------------------------------- | --------------------- |
| `append(x)`        | Adds an item at the end                 | `lst.append(10)`      |
| `insert(i, x)`     | Inserts item at index `i`               | `lst.insert(1, 20)`   |
| `extend(iterable)` | Adds multiple items                     | `lst.extend([1,2,3])` |
| `remove(x)`        | Removes first occurrence                | `lst.remove(2)`       |
| `pop(i)`           | Removes element at index (default last) | `lst.pop()`           |
| `clear()`          | Removes all items                       | `lst.clear()`         |
| `index(x)`         | Returns index of first occurrence       | `lst.index(3)`        |
| `count(x)`         | Counts occurrences of item              | `lst.count(5)`        |
| `sort()`           | Sorts list ascending                    | `lst.sort()`          |
| `reverse()`        | Reverses list                           | `lst.reverse()`       |
| `copy()`           | Returns shallow copy                    | `new = lst.copy()`    |

---

### **Example:**

```python
nums = [3, 1, 4, 1, 5]
nums.sort()
print(nums)           # [1, 1, 3, 4, 5]
nums.reverse()
print(nums)           # [5, 4, 3, 1, 1]
print(nums.count(1))  # 2
```

---

## ⚙️ **7️⃣ Looping Through Lists**

You can iterate through lists using `for` or `while`.

### **Example**

```python
fruits = ["apple", "banana", "cherry"]
for item in fruits:
    print(item)
```

✅ **Output**

```
apple
banana
cherry
```

---

## 💡 **8️⃣ List Comprehensions (Very Important)**

A **list comprehension** provides a **compact way** to create lists.
It replaces loops and makes code shorter and cleaner.

---

### **Syntax:**

```python
[expression for item in iterable if condition]
```

---

### **Example 1: Squares of Numbers**

```python
squares = [x**2 for x in range(1, 6)]
print(squares)
```

✅ **Output**

```
[1, 4, 9, 16, 25]
```

---

### **Example 2: Even Numbers**

```python
evens = [x for x in range(10) if x % 2 == 0]
print(evens)
```

✅ **Output**

```
[0, 2, 4, 6, 8]
```

---

### **Example 3: Strings to Uppercase**

```python
words = ["apple", "banana", "cherry"]
upper_words = [w.upper() for w in words]
print(upper_words)
```

✅ **Output**

```
['APPLE', 'BANANA', 'CHERRY']
```

---

### **Example 4: Nested Comprehensions**

```python
matrix = [[1, 2, 3], [4, 5, 6]]
flat = [num for row in matrix for num in row]
print(flat)
```

✅ **Output**

```
[1, 2, 3, 4, 5, 6]
```

---

### **Example 5: Conditional Expression**

```python
nums = [10, 15, 20, 25]
labels = ["Even" if n % 2 == 0 else "Odd" for n in nums]
print(labels)
```

✅ **Output**

```
['Even', 'Odd', 'Even', 'Odd']
```

---

## 🧩 **9️⃣ Practice Questions**

Try these to test your understanding 👇

1. **Create a list of 10 numbers** and print only the even ones using list comprehension.
2. Given a list of words, **count how many contain the letter ‘a’**.
3. **Find the largest and smallest element** in a list without using `max()` or `min()`.
4. Create a list of **square numbers from 1–20**, but only include **numbers greater than 100**.
5. Given a nested list, **flatten it** using a list comprehension.
6. Use `list comprehension` to convert a list of strings `["1", "2", "3"]` into integers `[1, 2, 3]`.

---

## ✅ **Summary Table**

| **Concept**    | **Description**            | **Example**                |
| -------------- | -------------------------- | -------------------------- |
| Create List    | Use `[]` or `list()`       | `lst = [1,2,3]`            |
| Access         | Use index                  | `lst[0]`                   |
| Slice          | Get sublist                | `lst[1:3]`                 |
| Modify         | Change items               | `lst[2] = 10`              |
| Methods        | Built-in functions         | `append(), sort()`         |
| Comprehensions | Short syntax for new lists | `[x**2 for x in range(5)]` |

---


