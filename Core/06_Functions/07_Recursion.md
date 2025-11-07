
## 🧠 **1️⃣ What is Recursion?**

**Recursion** means a **function calling itself** directly or indirectly to solve a problem.

It’s often used to solve problems that can be broken into **smaller subproblems** of the same type — for example:
✅ Calculating factorials
✅ Finding Fibonacci numbers
✅ Traversing nested data or trees

---

## ⚙️ **2️⃣ Syntax of a Recursive Function**

```python
def function_name(parameters):
    if (base_condition):
        return some_value     # Base case
    else:
        return function_name(modified_parameters)  # Recursive call
```

### 🧩 Explanation:

* **Base case** → Stops the recursion (prevents infinite loop).
* **Recursive case** → Calls the function again with a smaller/simpler version of the problem.

---

## 🔢 **3️⃣ Example: Factorial of a Number**

**Mathematical Formula:**
n! = n × (n−1) × (n−2) × … × 1
or
n! = n × (n−1)! and 1! = 1

### **Code:**

```python
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n - 1)

print("Factorial of 5:", factorial(5))
```

✅ **Output:**

```
Factorial of 5: 120
```

> 🧩 Here, `factorial(5)` calls `factorial(4)`, then `factorial(3)`, … until it reaches the base case (`n == 1`).

---

## 🧮 **4️⃣ Recursive Process (Step by Step)**

For `factorial(4)`:

```
factorial(4)
= 4 * factorial(3)
= 4 * (3 * factorial(2))
= 4 * (3 * (2 * factorial(1)))
= 4 * 3 * 2 * 1 = 24
```

---

## 💡 **5️⃣ Example: Fibonacci Series**

The Fibonacci sequence:

```
0, 1, 1, 2, 3, 5, 8, 13, ...
```

Each term = sum of the previous two.

**Formula:**

```
fib(n) = fib(n-1) + fib(n-2)
```

with base cases:

```
fib(0) = 0
fib(1) = 1
```

### **Code:**

```python
def fib(n):
    if n <= 1:
        return n
    else:
        return fib(n-1) + fib(n-2)

for i in range(10):
    print(fib(i), end=" ")
```

✅ **Output:**

```
0 1 1 2 3 5 8 13 21 34
```

---

## 🧩 **6️⃣ Example: Sum of Natural Numbers**

### **Code:**

```python
def sum_n(n):
    if n == 1:
        return 1
    else:
        return n + sum_n(n - 1)

print(sum_n(5))
```

✅ **Output:**

```
15
```

> 5 + 4 + 3 + 2 + 1 = 15

---

## 🪞 **7️⃣ Example: Reversing a String Using Recursion**

```python
def reverse_string(s):
    if len(s) == 0:
        return s
    else:
        return reverse_string(s[1:]) + s[0]

print(reverse_string("python"))
```

✅ **Output:**

```
nohtyp
```

---

## 🔍 **8️⃣ Recursive vs Iterative Approach**

| **Aspect**     | **Recursive**           | **Iterative**           |
| -------------- | ----------------------- | ----------------------- |
| **Definition** | Function calls itself   | Uses loops              |
| **Memory use** | More (stack frames)     | Less                    |
| **Speed**      | Slower for large inputs | Faster                  |
| **Code**       | Short and elegant       | Often longer            |
| **Best for**   | Hierarchical problems   | Repetitive calculations |

---

## ⚠️ **9️⃣ Common Issue: Infinite Recursion**

If there’s **no base condition**, recursion never stops and causes:

```
RecursionError: maximum recursion depth exceeded
```

### **Example:**

```python
def infinite():
    print("Hello")
    infinite()

infinite()
```

🚫 **Output:**

```
RecursionError
```

---

## 🧠 **🔟 Real-Life Analogy**

Imagine **standing between two mirrors** — your reflection repeats infinitely.
In recursion, a function “reflects” itself until a **base case** (like covering one mirror) stops it.

---

## 🧩 **11️⃣ Python’s Recursion Limit**

Python limits recursion depth (default ≈ 1000 calls).

You can check it with:

```python
import sys
print(sys.getrecursionlimit())
```

You can increase it (⚠️ risky):

```python
sys.setrecursionlimit(2000)
```

---

## 🧠 **12️⃣ Practice Questions**

1. Write a recursive function to find the factorial of a number.
2. Write a recursive function to print Fibonacci numbers up to `n`.
3. Create a recursive function to calculate the sum of natural numbers.
4. Write a recursive function to find the power of a number (`x^n`).
5. Write a recursive function to reverse a string.
6. Write a recursive function to count the digits in a number.
7. Write a recursive function to find the GCD (Greatest Common Divisor) of two numbers.
8. Write a recursive function to check if a string is a palindrome.
9. Write a recursive function to find the maximum number in a list.
10. Write a recursive function to calculate the sum of elements in a list.

---

## ✅ **Summary**

| **Concept**        | **Description**                             |
| ------------------ | ------------------------------------------- |
| **Recursion**      | Function calling itself                     |
| **Base case**      | Stops recursion                             |
| **Recursive case** | Calls the same function                     |
| **Common uses**    | Factorial, Fibonacci, Trees, File Traversal |
| **Advantages**     | Simpler, cleaner code                       |
| **Disadvantages**  | More memory use, risk of infinite recursion |

---


