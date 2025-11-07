
## 🧩 **Nested Loops and Conditional Expressions**

---

## 🔁 **1️⃣ Nested Loops**

---

### **Definition:**

A **nested loop** is a loop **inside another loop**.
It allows you to execute an inner loop **multiple times for each iteration** of the outer loop.

---

### **Syntax:**

```python
for outer in sequence1:
    for inner in sequence2:
        # code block
```

---

### **Example 1: Simple Nested for Loop**

```python
for i in range(1, 4):        # Outer loop
    for j in range(1, 4):    # Inner loop
        print(f"i = {i}, j = {j}")
```

✅ **Output:**

```
i = 1, j = 1
i = 1, j = 2
i = 1, j = 3
i = 2, j = 1
i = 2, j = 2
i = 2, j = 3
i = 3, j = 1
i = 3, j = 2
i = 3, j = 3
```

🧠 **Explanation:**
For each iteration of the outer loop (`i`), the inner loop (`j`) runs completely.

---

### **Example 2: Nested while Loop**

```python
i = 1
while i <= 3:
    j = 1
    while j <= 2:
        print(f"i = {i}, j = {j}")
        j += 1
    i += 1
```

✅ **Output:**

```
i = 1, j = 1
i = 1, j = 2
i = 2, j = 1
i = 2, j = 2
i = 3, j = 1
i = 3, j = 2
```

---

### **Example 3: Printing a Pattern**

```python
for i in range(1, 6):
    for j in range(1, i + 1):
        print("*", end=" ")
    print()
```

✅ **Output:**

```
*
* *
* * *
* * * *
* * * * *
```

🧩 **Explanation:**

* Outer loop controls the number of rows
* Inner loop controls the number of `*` printed per row

---

### **Example 4: Multiplication Table (Nested Loops)**

```python
for i in range(1, 4):
    for j in range(1, 6):
        print(f"{i} x {j} = {i*j}")
    print("------")
```

✅ **Output:**

```
1 x 1 = 1
1 x 2 = 2
1 x 3 = 3
1 x 4 = 4
1 x 5 = 5
------
2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10
------
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
------
```

---

### ⚙️ **Nested Loop with Condition**

You can add conditional statements inside nested loops.

**Example:**

```python
for i in range(1, 6):
    for j in range(1, 6):
        if i == j:
            print("*", end=" ")
        else:
            print("-", end=" ")
    print()
```

✅ **Output:**

```
* - - - -
- * - - -
- - * - -
- - - * -
- - - - *
```

---

## 💡 **Advantages of Nested Loops**

✅ Useful for **matrix operations**
✅ Common in **pattern printing**
✅ Helpful in **data structures** like lists within lists

---

## 🧠 **2️⃣ Conditional Expressions (Ternary Operator)**

---

### **Definition:**

A **conditional expression** (also called a **ternary operator**) provides a **short, single-line** way to write `if-else` statements.

---

### **Syntax:**

```python
value_if_true if condition else value_if_false
```

---

### **Example 1: Simple usage**

```python
x = 10
y = 20

result = "x is greater" if x > y else "y is greater"
print(result)
```

✅ **Output:**

```
y is greater
```

---

### **Example 2: Checking Even or Odd**

```python
num = int(input("Enter a number: "))

result = "Even" if num % 2 == 0 else "Odd"
print(result)
```

✅ **Output:**

```
Enter a number: 5
Odd
```

---

### **Example 3: Using in print() directly**

```python
age = 18
print("Adult" if age >= 18 else "Minor")
```

✅ **Output:**

```
Adult
```

---

### **Example 4: Nested Conditional Expression**

You can chain multiple ternary operators, but keep it readable.

```python
marks = 85

grade = "A+" if marks >= 90 else "A" if marks >= 80 else "B"
print(grade)
```

✅ **Output:**

```
A
```

---

### **Example 5: Conditional Expression with Function**

```python
def absolute(x):
    return x if x >= 0 else -x

print(absolute(-5))
```

✅ **Output:**

```
5
```

---

## ✅ **Comparison: if-else vs Conditional Expression**

| **Normal if-else** | **Ternary Expression** |
| ------------------ | ---------------------- |
| ```python          |                        |
| if x > y:          |                        |

```
result = x
```

else:
result = y
`|`python
result = x if x > y else y

```|

🧩 **Both are valid**, but the ternary form is more compact.

---

## ⚡ **Practice Example:**

Write a program to:
1. Use **nested loops** to print a 3×3 matrix.  
2. Use a **conditional expression** to print `"Even"` for even numbers and `"Odd"` for odd ones.

**Example Output:**
```

1 Odd
2 Even
3 Odd
4 Even
5 Odd
6 Even
7 Odd
8 Even
9 Odd

```

---



```
