## 🧠 **Conditional Statements in Python**

---

### **Definition**

Conditional statements allow your program to **execute certain blocks of code only when specific conditions are true**.

They help your program **"decide what to do next"**, similar to real-life decision-making.

---

### ✅ **Types of Conditional Statements**

1. **if statement**
2. **if–else statement**
3. **if–elif–else statement**
4. **Nested if statement**

---

## 1️⃣ **`if` Statement**

Used to execute a block of code **only if** a condition is `True`.

**Syntax:**

```python
if condition:
    # code block (executes if condition is True)
```

**Example:**

```python
age = 18

if age >= 18:
    print("You are eligible to vote.")
```

✅ **Output:**

```
You are eligible to vote.
```

If the condition is `False`, the code inside the `if` block is **skipped**.

---

## 2️⃣ **`if–else` Statement**

Used when you want to execute **one block if the condition is true**
and **another block if it’s false**.

**Syntax:**

```python
if condition:
    # code if True
else:
    # code if False
```

**Example:**

```python
age = 16

if age >= 18:
    print("You can vote.")
else:
    print("You cannot vote yet.")
```

✅ **Output:**

```
You cannot vote yet.
```

---

## 3️⃣ **`if–elif–else` Statement**

Used when you have **multiple conditions** to check.

**Syntax:**

```python
if condition1:
    # code block 1
elif condition2:
    # code block 2
elif condition3:
    # code block 3
else:
    # default block
```

**Example:**

```python
marks = 85

if marks >= 90:
    print("Grade: A+")
elif marks >= 80:
    print("Grade: A")
elif marks >= 70:
    print("Grade: B")
else:
    print("Grade: C or below")
```

✅ **Output:**

```
Grade: A
```

🧩 Only one block executes — the **first condition that’s true**.

---

## 4️⃣ **Nested `if` Statement**

You can use one `if` statement **inside another**.

**Syntax:**

```python
if condition1:
    if condition2:
        # code block
```

**Example:**

```python
age = 25
citizen = True

if age >= 18:
    if citizen:
        print("You can vote in national elections.")
    else:
        print("Only citizens can vote.")
else:
    print("You are too young to vote.")
```

✅ **Output:**

```
You can vote in national elections.
```

---

## 🧮 **Using Logical Operators in Conditions**

You can combine conditions using `and`, `or`, `not`.

**Example:**

```python
age = 22
has_id = True

if age >= 18 and has_id:
    print("Access granted!")
else:
    print("Access denied!")
```

✅ **Output:**

```
Access granted!
```

---

## ⚙️ **Short-Hand (One-Line) if Statement**

Python allows a compact version of `if` and `if–else`.

**Example 1: Simple if**

```python
x = 10
if x > 5: print("x is greater than 5")
```

✅ **Output:**

```
x is greater than 5
```

---

**Example 2: if–else in one line**

```python
a = 10
b = 20

print("a is greater") if a > b else print("b is greater")
```

✅ **Output:**

```
b is greater
```

---

## 💡 **Example Program: Conditional Statements**

```python
num = int(input("Enter a number: "))

if num > 0:
    print("Positive number")
elif num == 0:
    print("Zero")
else:
    print("Negative number")
```

**Output (Example Run):**

```
Enter a number: -5
Negative number
```

---

## 🧩 **Example: Even or Odd Checker**

```python
num = int(input("Enter a number: "))

if num % 2 == 0:
    print("Even number")
else:
    print("Odd number")
```

✅ **Output:**

```
Enter a number: 6
Even number
```

---

## ⚡ **Example: Largest of Three Numbers**

```python
a = 10
b = 25
c = 15

if a >= b and a >= c:
    print("a is the largest")
elif b >= a and b >= c:
    print("b is the largest")
else:
    print("c is the largest")
```

✅ **Output:**

```
b is the largest
```

---

## 🔍 **Indentation is Important**

Python uses **indentation (spaces)** to define blocks of code, not braces `{}`.
If you don’t indent properly, you’ll get an error:

❌ Wrong:

```python
if True:
print("Hello")
```

✅ Correct:

```python
if True:
    print("Hello")
```

---

## ✅ **Summary Table**

| **Statement Type** | **Use Case**                       | **Example**                              |
| ------------------ | ---------------------------------- | ---------------------------------------- |
| `if`               | Single condition                   | `if x > 0:`                              |
| `if–else`          | Either/or logic                    | `if x > 0: … else: …`                    |
| `if–elif–else`     | Multiple conditions                | `if x > 0: … elif x < 0: … else: …`      |
| **Nested if**      | Condition inside another condition | `if x > 0: if y > 0: …`                  |
| **One-line if**    | Compact syntax                     | `print("Yes") if x > 0 else print("No")` |

---

### 💪 **Quick Practice**

Write a Python program to:

1. Ask the user for their age.
2. If the age is less than 13 → print **"Child"**.
3. If between 13–19 → print **"Teenager"**.
4. If 20 or older → print **"Adult"**.


