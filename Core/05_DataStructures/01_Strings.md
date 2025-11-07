 **Strings**

Let’s explore them in detail step by step:
**String Creation → Indexing & Slicing → Methods → Formatting**

---

## 🧠 **Strings in Python**

---

### **Definition**

A **string** is a sequence of **characters** enclosed in **quotes**.
Strings are **immutable**, meaning once created, they cannot be changed.

---

### **Example:**

```python
name = "Python"
print(name)
```

✅ **Output:**

```
Python
```

---

## 🪶 **1️⃣ String Creation**

You can create strings using **single**, **double**, or **triple quotes**.

### **Examples:**

```python
str1 = 'Hello'
str2 = "World"
str3 = '''Welcome to Python!'''
```

✅ All are valid strings.

---

### **Multiline String**

Use **triple quotes** (`'''` or `"""`) for multi-line text.

```python
msg = """This is
a multi-line
string."""
print(msg)
```

✅ **Output:**

```
This is
a multi-line
string.
```

---

### **Empty String**

```python
empty = ""
print(len(empty))
```

✅ **Output:**

```
0
```

---

## 🎯 **2️⃣ String Indexing**

Each character in a string has a **position (index)**.
Indexes start from **0** for the first character.

```
 P   y   t   h   o   n
 0   1   2   3   4   5
```

---

### **Accessing Characters**

```python
text = "Python"
print(text[0])   # First character
print(text[5])   # Last character
```

✅ **Output:**

```
P
n
```

---

### **Negative Indexing**

You can also access characters from the **end**.

```
 P   y   t   h   o   n
-6  -5  -4  -3  -2  -1
```

```python
text = "Python"
print(text[-1])  # Last character
print(text[-3])  # Third from end
```

✅ **Output:**

```
n
h
```

---

## ✂️ **3️⃣ String Slicing**

Slicing extracts **a portion** of a string.

### **Syntax:**

```python
string[start:end:step]
```

* **start** → index to begin (included)
* **end** → index to stop (excluded)
* **step** → interval (default = 1)

---

### **Examples:**

```python
text = "Python"

print(text[0:4])   # Characters from index 0 to 3
print(text[:4])    # Same as [0:4]
print(text[2:])    # From index 2 to end
print(text[-4:-1]) # From index -4 to -2
print(text[::-1])  # Reverse string
```

✅ **Output:**

```
Pyth
Pyth
thon
tho
nohtyP
```

---

## 🧰 **4️⃣ String Methods**

Python provides many **built-in string methods** for manipulation.

Let’s see the most common and useful ones:

---

### **Case Conversion**

```python
s = "hello python"
print(s.upper())   # HELLO PYTHON
print(s.lower())   # hello python
print(s.title())   # Hello Python
print(s.capitalize()) # Hello python
print(s.swapcase()) # HELLO PYTHON → hello python
```

---

### **Check Type of Content**

```python
s = "Python3"
print(s.isalpha())   # False (contains number)
print(s.isdigit())   # False
print("123".isdigit())  # True
print("abc".isalpha())  # True
print(" ".isspace())    # True
```

---

### **Searching and Replacing**

```python
text = "I love Python programming"
print(text.find("Python"))   # 7 (index)
print(text.replace("Python", "Java"))  # I love Java programming
```

---

### **String Testing**

```python
msg = "hello world"
print(msg.startswith("he"))  # True
print(msg.endswith("ld"))    # True
```

---

### **Removing Whitespace**

```python
data = "   Python   "
print(data.strip())   # Remove both sides
print(data.lstrip())  # Remove left
print(data.rstrip())  # Remove right
```

✅ **Output:**

```
Python
Python   
   Python
```

---

### **Splitting and Joining**

```python
text = "Python is fun"
words = text.split()       # Split into list
print(words)

joined = "-".join(words)   # Join with '-'
print(joined)
```

✅ **Output:**

```
['Python', 'is', 'fun']
Python-is-fun
```

---

### **Counting and Length**

```python
text = "banana"
print(len(text))         # 6
print(text.count("a"))   # 3
```

---

### **Checking Substring**

```python
s = "Python programming"
print("Python" in s)      # True
print("Java" not in s)    # True
```

---

## 🎨 **5️⃣ String Formatting**

Formatting allows inserting variables or values into strings.

---

### **Method 1: f-Strings (Recommended ✅)**

```python
name = "Alice"
age = 25
print(f"My name is {name} and I am {age} years old.")
```

✅ **Output:**

```
My name is Alice and I am 25 years old.
```

You can even perform expressions:

```python
print(f"Next year I’ll be {age + 1}.")
```

---

### **Method 2: `format()` Method**

```python
name = "Bob"
score = 90
print("Student: {}, Score: {}".format(name, score))
print("Student: {1}, Score: {0}".format(score, name))  # Positional
print("Student: {n}, Score: {s}".format(n=name, s=score))  # Named
```

✅ **Output:**

```
Student: Bob, Score: 90
Student: Bob, Score: 90
Student: Bob, Score: 90
```

---

### **Method 3: % Formatting (Old Style)**

```python
name = "Carol"
age = 30
print("Name: %s, Age: %d" % (name, age))
```

✅ **Output:**

```
Name: Carol, Age: 30
```

---

## 🧩 **Practice Examples**

### **Example 1: Reverse a String**

```python
s = input("Enter a string: ")
print("Reversed:", s[::-1])
```

---

### **Example 2: Count Vowels**

```python
s = input("Enter a string: ")
count = 0
for ch in s.lower():
    if ch in "aeiou":
        count += 1
print("Vowel count:", count)
```

---

### **Example 3: Format Output**

```python
name = input("Enter name: ")
marks = float(input("Enter marks: "))
print(f"Student {name} scored {marks:.2f} marks.")
```

✅ Example Output:

```
Student John scored 89.50 marks.
```

---

## ✅ **Summary Table**

| **Concept**     | **Description**          | **Example**            |
| --------------- | ------------------------ | ---------------------- |
| String creation | Using quotes             | `s = "Hello"`          |
| Indexing        | Access characters        | `s[0]`                 |
| Slicing         | Extract substring        | `s[1:4]`               |
| Immutability    | Cannot modify            | ❌ `s[0] = 'p'`         |
| Methods         | Built-in string tools    | `s.upper(), s.strip()` |
| Formatting      | Combine text & variables | `f"My name is {name}"` |

---


