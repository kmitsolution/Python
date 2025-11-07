
## 🧩 **1️⃣ What is a Lambda Function?**

A **lambda function** is a **small, anonymous (nameless)** function in Python.
It can have **any number of arguments** but **only one expression**.

📘 **Syntax:**

```python
lambda arguments: expression
```

* `lambda` → keyword to define an anonymous function
* `arguments` → input values (like function parameters)
* `expression` → a single line that is evaluated and returned automatically

---

## 💡 **2️⃣ Example: Basic Lambda Function**

```python
# Normal function
def square(x):
    return x * x

# Lambda equivalent
square_lambda = lambda x: x * x

print(square_lambda(5))
```

✅ **Output:**

```
25
```

> Both `square()` and `square_lambda()` do the same thing.

---

## 🔢 **3️⃣ Lambda with Multiple Arguments**

```python
add = lambda a, b: a + b
print(add(10, 20))
```

✅ **Output:**

```
30
```

---

## 🧠 **4️⃣ Lambda Functions vs Normal Functions**

| **Feature** | **Normal Function**        | **Lambda Function**       |
| ----------- | -------------------------- | ------------------------- |
| Name        | Has a name (`def func()`)  | Anonymous (no name)       |
| Syntax      | `def func():`              | `lambda args: expression` |
| Statements  | Can contain multiple lines | Only one expression       |
| Use Case    | General functions          | Short, quick tasks        |

---

## ⚙️ **5️⃣ Lambda Inside Other Functions**

Lambda functions are often used **inside another function**, especially for **short operations**.

### Example:

```python
def multiplier(n):
    return lambda a: a * n

times3 = multiplier(3)
times5 = multiplier(5)

print(times3(10))  # 10 * 3
print(times5(10))  # 10 * 5
```

✅ **Output:**

```
30
50
```

> Here, `multiplier()` returns a lambda that multiplies any number by `n`.

---

## 🧮 **6️⃣ Using Lambda with `map()`, `filter()`, and `reduce()`**

These are built-in functions that often use lambdas for compact, readable code.

---

### 🧩 **(a) map() — Apply a Function to All Items**

```python
numbers = [1, 2, 3, 4, 5]
squares = list(map(lambda x: x ** 2, numbers))
print(squares)
```

✅ **Output:**

```
[1, 4, 9, 16, 25]
```

---

### 🧩 **(b) filter() — Filter Items That Match a Condition**

```python
numbers = [10, 15, 20, 25, 30]
even = list(filter(lambda x: x % 2 == 0, numbers))
print(even)
```

✅ **Output:**

```
[10, 20, 30]
```

---

### 🧩 **(c) reduce() — Combine All Items into One Value**

To use `reduce()`, import it from `functools`:

```python
from functools import reduce

numbers = [1, 2, 3, 4, 5]
sum_all = reduce(lambda x, y: x + y, numbers)
print(sum_all)
```

✅ **Output:**

```
15
```

> Explanation: `reduce()` repeatedly applies the lambda:
> `(((1+2)+3)+4)+5`

---

## 🔍 **7️⃣ Lambda with Conditional Expressions**

Lambdas can include **conditional logic** using `if–else`.

```python
max_num = lambda a, b: a if a > b else b
print(max_num(10, 25))
```

✅ **Output:**

```
25
```

---

## 💬 **8️⃣ Lambda Returning Tuples**

You can return multiple values (as a tuple):

```python
calc = lambda x, y: (x + y, x * y, x - y)
print(calc(5, 3))
```

✅ **Output:**

```
(8, 15, 2)
```

---

## 🚀 **9️⃣ Lambda in Sorting**

Using `sorted()` with `key` parameter:

```python
students = [("Alice", 25), ("Bob", 20), ("Carol", 22)]
sorted_students = sorted(students, key=lambda x: x[1])
print(sorted_students)
```

✅ **Output:**

```
[('Bob', 20), ('Carol', 22), ('Alice', 25)]
```

---

## ⚡ **🔟 Lambda for Quick Operations**

```python
double = lambda x: x * 2
is_even = lambda x: x % 2 == 0

print(double(6))
print(is_even(9))
```

✅ **Output:**

```
12
False
```

---

## 🧠 **11️⃣ Practice Questions**

1. Write a lambda to find the cube of a number.
2. Use `lambda` and `filter()` to extract odd numbers from a list.
3. Use `map()` and `lambda` to convert a list of strings to uppercase.
4. Write a lambda that returns `"Even"` if a number is even, else `"Odd"`.
5. Use `reduce()` and `lambda` to find the product of numbers in a list.
6. Sort a list of tuples by the second element using a lambda.
7. Create a function that returns a lambda to multiply a number by a given factor.
8. Write a lambda that returns the maximum of three numbers.
9. Use a lambda to format a name as `"Last, First"`.
10. Write a lambda function to calculate the area of a circle given radius `r`.

---

## ✅ **Summary**

| **Feature**     | **Lambda Functions**                |
| --------------- | ----------------------------------- |
| Defined using   | `lambda` keyword                    |
| Can have        | Multiple arguments                  |
| Can return      | Only one expression                 |
| Common use      | Short anonymous functions           |
| Often used with | `map()`, `filter()`, `reduce()`     |
| Advantage       | Concise, inline function definition |

---


