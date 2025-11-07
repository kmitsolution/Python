
## 🧠 **Looping Statements in Python**

---

### **Definition**

A **loop** is used to **execute a block of code repeatedly** as long as a given condition is true.

Loops are fundamental in programming for tasks like:

* Iterating through lists or strings
* Performing repetitive calculations
* Automating tasks (e.g., printing, summing, or searching)

---

## 🔁 **Types of Loops in Python**

1. **for loop**
2. **while loop**
3. **Nested loops**
4. **Loop control statements**

   * `break`
   * `continue`
   * `pass`

---

## 1️⃣ **`for` Loop**

The `for` loop in Python is used to **iterate over a sequence** (like a list, tuple, string, or range).

---

### **Syntax:**

```python
for variable in sequence:
    # code block
```

---

### **Example 1: Iterating over a list**

```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

✅ **Output:**

```
apple
banana
cherry
```

---

### **Example 2: Using `range()` function**

`range(start, stop, step)` generates a sequence of numbers.

```python
for i in range(5):
    print(i)
```

✅ **Output:**

```
0
1
2
3
4
```

🧩 **Explanation:**
`range(5)` generates numbers `0, 1, 2, 3, 4`.

---

### **Example 3: Range with start and step**

```python
for i in range(2, 10, 2):
    print(i)
```

✅ **Output:**

```
2
4
6
8
```

---

### **Example 4: Looping through a string**

```python
for char in "Python":
    print(char)
```

✅ **Output:**

```
P
y
t
h
o
n
```

---

## 2️⃣ **`while` Loop**

A `while` loop executes as long as a given condition remains **True**.

---

### **Syntax:**

```python
while condition:
    # code block
```

---

### **Example 1: Simple while loop**

```python
i = 1
while i <= 5:
    print(i)
    i += 1
```

✅ **Output:**

```
1
2
3
4
5
```

🧩 **Explanation:**
The loop runs while `i <= 5`.
The counter `i` increases by 1 each time.

---

### **Example 2: Countdown**

```python
n = 5
while n > 0:
    print(n)
    n -= 1
print("Blast off!")
```

✅ **Output:**

```
5
4
3
2
1
Blast off!
```

---

## 3️⃣ **Nested Loops**

A loop **inside another loop**.

---

### **Example:**

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(f"i={i}, j={j}")
```

✅ **Output:**

```
i=1, j=1
i=1, j=2
i=1, j=3
i=2, j=1
i=2, j=2
i=2, j=3
i=3, j=1
i=3, j=2
i=3, j=3
```

🧩 **Explanation:**
For each value of `i`, the inner loop runs completely.

---

## ⚙️ **Loop Control Statements**

Python provides special keywords to control loop flow:

| **Statement** | **Description**                                     |
| ------------- | --------------------------------------------------- |
| `break`       | Stops the loop immediately                          |
| `continue`    | Skips the rest of the code in the current iteration |
| `pass`        | Does nothing (placeholder)                          |

---

### **1. `break` Example**

Stops the loop when the condition is met.

```python
for i in range(1, 10):
    if i == 5:
        break
    print(i)
```

✅ **Output:**

```
1
2
3
4
```

🧩 **Explanation:**
When `i == 5`, loop stops completely.

---

### **2. `continue` Example**

Skips current iteration and moves to the next.

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
When `i == 3`, the `print(i)` statement is skipped.

---

### **3. `pass` Example**

Used when a statement is required syntactically but you want **no action**.

```python
for i in range(3):
    pass  # Placeholder for future code
print("Loop finished")
```

✅ **Output:**

```
Loop finished
```

---

## 🔁 **Using else with loops**

Python allows an `else` block **after a loop**, which executes only if the loop completes **without break**.

---

### **Example:**

```python
for i in range(5):
    print(i)
else:
    print("Loop finished normally")
```

✅ **Output:**

```
0
1
2
3
4
Loop finished normally
```

If a `break` occurs, the `else` block **won’t execute**.

---

### **Example with break**

```python
for i in range(5):
    if i == 3:
        break
    print(i)
else:
    print("Loop finished normally")
```

✅ **Output:**

```
0
1
2
```

🧩 `else` didn’t execute because loop broke early.

---

## 🧮 **Practical Examples**

### **Example 1: Sum of first N natural numbers**

```python
n = int(input("Enter N: "))
sum = 0

for i in range(1, n+1):
    sum += i

print("Sum =", sum)
```

---

### **Example 2: Multiplication table**

```python
num = int(input("Enter a number: "))

for i in range(1, 11):
    print(f"{num} x {i} = {num*i}")
```

---

### **Example 3: While loop factorial**

```python
n = int(input("Enter a number: "))
fact = 1
i = 1

while i <= n:
    fact *= i
    i += 1

print("Factorial =", fact)
```

---

## ✅ **Summary Table**

| **Loop Type** | **Use Case**                         | **Example**             |
| ------------- | ------------------------------------ | ----------------------- |
| `for`         | Iterating over a sequence            | `for x in range(5):`    |
| `while`       | Repeat while condition is True       | `while x < 5:`          |
| `nested`      | Loop inside another loop             | `for i in … for j in …` |
| `break`       | Exit loop early                      | Stops loop              |
| `continue`    | Skip current iteration               | Goes to next iteration  |
| `pass`        | Placeholder                          | Does nothing            |
| `else`        | Executes when loop finishes normally | `for … else:`           |

---

### 💪 **Practice Task**

Write a Python program that:

1. Takes a number as input.
2. Prints all even numbers from 1 to that number using a loop.
3. Skips numbers divisible by 6 using `continue`.


