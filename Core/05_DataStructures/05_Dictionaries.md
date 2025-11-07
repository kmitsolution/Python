## 🪶 **1️⃣ What is a Dictionary?**

A **dictionary** is an **unordered**, **mutable**, and **indexed** collection of **key–value pairs**.
Each **key** must be **unique** and **immutable** (like strings, numbers, or tuples).

---

### ✅ **Example**

```python
student = {
    "name": "Alice",
    "age": 20,
    "course": "Python"
}
print(student)
```

✅ **Output:**

```
{'name': 'Alice', 'age': 20, 'course': 'Python'}
```

---

## 🔑 **2️⃣ Dictionary Characteristics**

| Property                  | Description                                                |
| ------------------------- | ---------------------------------------------------------- |
| **Mutable**               | Can be changed after creation                              |
| **Unordered**             | No fixed order (in Python 3.7+, maintains insertion order) |
| **Key must be unique**    | Duplicate keys overwrite previous ones                     |
| **Key must be immutable** | You can use str, int, tuple, etc. — not lists or dicts     |

---

## ✏️ **3️⃣ Creating Dictionaries**

### **Using Curly Braces**

```python
person = {"name": "John", "age": 25}
```

### **Using dict() Constructor**

```python
person = dict(name="John", age=25)
```

### **Empty Dictionary**

```python
empty = {}
```

### **With Mixed Types**

```python
data = {"id": 101, "marks": [85, 90, 92], "passed": True}
```

---

## 🎯 **4️⃣ Accessing Dictionary Elements**

### **Using Key**

```python
student = {"name": "Bob", "age": 22}
print(student["name"])
```

✅ Output:

```
Bob
```

### **Using `get()` Method**

```python
print(student.get("age"))      # 22
print(student.get("grade", "N/A"))  # Returns default if not found
```

---

## 🧩 **5️⃣ Modifying Dictionary Elements**

### **Add or Update Values**

```python
student["age"] = 23          # Update
student["city"] = "London"   # Add new key-value
print(student)
```

✅ Output:

```
{'name': 'Bob', 'age': 23, 'city': 'London'}
```

---

## 🗑️ **6️⃣ Removing Items**

| Method      | Description                        | Example               |
| ----------- | ---------------------------------- | --------------------- |
| `pop(key)`  | Removes and returns value of key   | `student.pop("age")`  |
| `popitem()` | Removes the **last inserted item** | `student.popitem()`   |
| `del`       | Deletes item by key                | `del student["name"]` |
| `clear()`   | Removes all items                  | `student.clear()`     |

---

### **Example**

```python
student = {"name": "Bob", "age": 22, "city": "London"}
student.pop("city")
print(student)
```

✅ Output:

```
{'name': 'Bob', 'age': 22}
```

---

## 🔁 **7️⃣ Looping Through a Dictionary**

### **Looping Keys**

```python
for key in student:
    print(key)
```

### **Looping Values**

```python
for value in student.values():
    print(value)
```

### **Looping Key–Value Pairs**

```python
for key, value in student.items():
    print(key, ":", value)
```

✅ Output:

```
name : Bob
age : 22
```

---

## ⚙️ **8️⃣ Dictionary Methods**

| Method         | Description                     | Example                          |
| -------------- | ------------------------------- | -------------------------------- |
| `keys()`       | Returns all keys                | `student.keys()`                 |
| `values()`     | Returns all values              | `student.values()`               |
| `items()`      | Returns all (key, value) pairs  | `student.items()`                |
| `update(dict)` | Updates from another dictionary | `student.update({"city": "NY"})` |
| `pop(key)`     | Removes an element              | `student.pop("age")`             |
| `clear()`      | Clears dictionary               | `student.clear()`                |
| `copy()`       | Returns a shallow copy          | `new = student.copy()`           |

---

### **Example**

```python
car = {"brand": "Toyota", "model": "Camry", "year": 2020}
print(car.keys())
print(car.values())
print(car.items())
```

✅ Output:

```
dict_keys(['brand', 'model', 'year'])
dict_values(['Toyota', 'Camry', 2020])
dict_items([('brand', 'model', 'year')])
```

---

## 🧮 **9️⃣ Nesting Dictionaries**

Dictionaries can contain **other dictionaries**.

```python
students = {
    "s1": {"name": "Alice", "age": 20},
    "s2": {"name": "Bob", "age": 22}
}
print(students["s1"]["name"])
```

✅ Output:

```
Alice
```

---

## 💡 **🔟 Dictionary Comprehensions**

Just like list comprehensions, but for **key-value pairs**.

---

### **Syntax**

```python
{key_expression: value_expression for item in iterable if condition}
```

---

### **Example 1: Squares of Numbers**

```python
squares = {x: x**2 for x in range(1, 6)}
print(squares)
```

✅ Output:

```
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

---

### **Example 2: Convert Strings to Length**

```python
words = ["apple", "banana", "cherry"]
lengths = {word: len(word) for word in words}
print(lengths)
```

✅ Output:

```
{'apple': 5, 'banana': 6, 'cherry': 6}
```

---

### **Example 3: Conditional Dictionary Comprehension**

```python
numbers = {x: "even" if x % 2 == 0 else "odd" for x in range(1, 6)}
print(numbers)
```

✅ Output:

```
{1: 'odd', 2: 'even', 3: 'odd', 4: 'even', 5: 'odd'}
```

---

### **Example 4: Swap Keys and Values**

```python
data = {"a": 1, "b": 2, "c": 3}
swapped = {v: k for k, v in data.items()}
print(swapped)
```

✅ Output:

```
{1: 'a', 2: 'b', 3: 'c'}
```

---

## 🧩 **🔟 Practice Questions**

1. Create a dictionary of student data (`name`, `age`, `marks`) and:

   * Add a new key `grade`
   * Update `marks`
   * Remove `age`

2. Merge two dictionaries using `update()`.

3. Write a program to print all **keys and values** of a dictionary using loops.

4. Create a dictionary comprehension that maps numbers **1–10** to their **squares**.

5. Convert the following two lists into a dictionary:

   ```python
   keys = ["name", "age", "course"]
   values = ["Alice", 20, "Python"]
   ```

6. Create a dictionary of word counts from a sentence (use `split()` and dictionary comprehension).

7. Write a nested dictionary for 3 students with keys `name`, `age`, `marks`, and print each student’s details.

---

## ✅ **Summary Table**

| **Concept**   | **Description**                 | **Example**                  |
| ------------- | ------------------------------- | ---------------------------- |
| Create        | `{}` or `dict()`                | `{"name": "Alice"}`          |
| Access        | `d[key]` or `d.get()`           | `student["name"]`            |
| Modify        | Add/update keys                 | `d["age"] = 21`              |
| Remove        | `pop()`, `del`, `clear()`       | `d.pop("key")`               |
| Loop          | `keys()`, `values()`, `items()` | `for k, v in d.items()`      |
| Comprehension | `{k:v for ...}`                 | `{x:x**2 for x in range(5)}` |
| Nested Dict   | Dict inside dict                | `{ "s1": {"name": "A"} }`    |

---


