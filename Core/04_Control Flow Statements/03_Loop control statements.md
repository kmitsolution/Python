## 🧭 **Loop Control Statements in Python**

---

### **Definition**

Loop control statements are used to **change the normal sequence of loop execution**.
They let you **skip**, **stop**, or **pause** the loop as needed.

---

### **Types of Loop Control Statements**

| **Statement** | **Description**                                   |
| ------------- | ------------------------------------------------- |
| `break`       | Immediately stops the loop                        |
| `continue`    | Skips the current iteration and moves to the next |
| `pass`        | Does nothing — used as a placeholder              |

---

## 1️⃣ **`break` Statement**

---

### **Definition:**

The `break` statement **terminates the loop immediately**, regardless of the condition.

Once `break` is executed, the loop **stops** and the control moves to the next statement after the loop.

---

### **Syntax:**

```python
for variable in sequence:
    if condition:
        break
```

---

### **Example 1: Using `break` in a for loop**

```python
for i in range(1, 11):
    if i == 5:
        break
    print(i)
print("Loop ended.")
```

✅ **Output:**

```
1
2
3
4
Loop ended.
```

🧩 **Explanation:**
When `i == 5`, the `break` statement stops the loop entirely.

---

### **Example 2: Using `break` in a while loop**

```python
i = 1
while i <= 10:
    if i == 6:
        break
    print(i)
    i += 1
print("Stopped at i =", i)
```

✅ **Output:**

```
1
2
3
4
5
Stopped at i = 6
```

---

## 2️⃣ **`continue` Statement**

---

### **Definition:**

The `continue` statement **skips the current iteration** of the loop and jumps to the **next iteration**.

It doesn’t terminate the loop — it just **skips** the rest of the code for the current iteration.

---

### **Syntax:**

```python
for variable in sequence:
    if condition:
        continue
```

---

### **Example 1: Skipping numbers**

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
```

✅ **Output:**

```
1
2
4
5
```

🧩 **Explanation:**
When `i == 3`, the loop skips the `print(i)` and continues to the next number.

---

### **Example 2: Continue in a while loop**

```python
i = 0
while i < 5:
    i += 1
    if i == 3:
        continue
    print(i)
```

✅ **Output:**

```
1
2
4
5
```

🧩 **Explanation:**
When `i == 3`, the loop skips printing and goes back to the condition check.

---

## 3️⃣ **`pass` Statement**

---

### **Definition:**

The `pass` statement is a **null operation** — it does nothing when executed.
It’s used as a **placeholder** for code that will be added later.

---

### **Syntax:**

```python
for variable in sequence:
    pass
```

---

### **Example 1: Using `pass` in a loop**

```python
for i in range(5):
    pass  # To be implemented later
print("Loop executed successfully.")
```

✅ **Output:**

```
Loop executed successfully.
```

🧩 **Explanation:**
The loop runs, but since `pass` does nothing, no output appears inside the loop.

---

### **Example 2: Pass in an if statement**

```python
x = 10
if x > 5:
    pass  # We'll add code here later
else:
    print("x is small")
```

✅ **Output:**

```
(nothing happens)
```

---

## 💡 **Comparing break, continue, and pass**

| **Statement** | **Effect**                            | **Used in**       |
| ------------- | ------------------------------------- | ----------------- |
| `break`       | Exits the loop completely             | for / while       |
| `continue`    | Skips current iteration, goes to next | for / while       |
| `pass`        | Does nothing, acts as placeholder     | Any control block |

---

### **Example: All three together**

```python
for i in range(1, 8):
    if i == 3:
        continue    # Skip 3
    elif i == 5:
        pass        # Do nothing for 5
    elif i == 6:
        break       # Stop loop at 6
    print(i)
```

✅ **Output:**

```
1
2
4
5
```

🧩 **Explanation:**

* When `i == 3` → skip (continue)
* When `i == 5` → do nothing (pass)
* When `i == 6` → stop loop (break)

---

## 🧩 **Practical Example**

### **Example: Find the first even number in a list**

```python
numbers = [1, 3, 5, 8, 10, 12]

for n in numbers:
    if n % 2 == 0:
        print("First even number:", n)
        break
```

✅ **Output:**

```
First even number: 8
```

---

### **Example: Skip vowels in a string**

```python
text = "python"

for ch in text:
    if ch in "aeiou":
        continue
    print(ch)
```

✅ **Output:**

```
p
y
t
h
n
```

---

## ✅ **Summary Table**

| **Keyword** | **Meaning**              | **Behavior**                |
| ----------- | ------------------------ | --------------------------- |
| `break`     | Exit the loop completely | Ends loop immediately       |
| `continue`  | Skip current iteration   | Jumps to next iteration     |
| `pass`      | Do nothing               | Placeholder for future code |

---

### 💪 **Practice Task**

Write a Python program that:

1. Loops numbers from 1 to 10.
2. Skips numbers divisible by 3 using `continue`.
3. Stops the loop if the number reaches 9 using `break`.
4. Use `pass` for even numbers (just as a placeholder).


