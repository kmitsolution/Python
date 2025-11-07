# 🧠 **Function Arguments and Return Values in Python**

Functions become powerful when you can pass **data** to them and get **results** back.
Let’s explore that in detail 👇

---

## 🪶 **1️⃣ Function Arguments (Passing Data to Functions)**

When defining a function, you can specify **parameters** inside parentheses `()` — these act as **variables** that hold the data passed into the function.

When calling the function, you provide **arguments**, which are **actual values** given to the parameters.

---

### **Example**

```python
def greet(name):
    print("Hello,", name, "!")
    
greet("Alice")
greet("Bob")
```

✅ **Output:**

```
Hello, Alice !
Hello, Bob !
```

Here:

* `name` → parameter
* `"Alice"`, `"Bob"` → arguments

---

## ⚙️ **2️⃣ Types of Function Arguments**

Python supports several types of arguments. Let’s go through them one by one:

---

### **a) Positional Arguments**

The most common type — values are passed **in order**.

```python
def add(a, b):
    print("Sum =", a + b)

add(10, 20)
```

✅ **Output:**

```
Sum = 30
```

If the number or order of arguments doesn’t match, Python raises an error.

❌ **Example:**

```python
add(10)
```

```
TypeError: add() missing 1 required positional argument: 'b'
```

---

### **b) Keyword Arguments**

You can specify which parameter each value belongs to by using **parameter names**.

```python
def student(name, age):
    print("Name:", name)
    print("Age:", age)

student(age=20, name="John")
```

✅ **Output:**

```
Name: John
Age: 20
```

👉 Order doesn’t matter when you use **keyword arguments**.

---

### **c) Default Arguments**

You can assign **default values** to parameters.
If no argument is passed, the default is used.

```python
def greet(name="Guest"):
    print("Hello,", name, "!")
    
greet("Alice")
greet()
```

✅ **Output:**

```
Hello, Alice !
Hello, Guest !
```

---

### **d) Variable-Length Arguments**

Used when you **don’t know how many arguments** you’ll pass.

#### 1️⃣ *args (Non-keyword arguments)

Used to accept multiple positional arguments.

```python
def add(*numbers):
    total = 0
    for n in numbers:
        total += n
    print("Sum =", total)

add(2, 4, 6)
add(10, 20, 30, 40)
```

✅ **Output:**

```
Sum = 12
Sum = 100
```

👉 `*args` collects all extra arguments into a **tuple**.

---

#### 2️⃣ **kwargs (Keyword arguments)**

Used when you want to pass multiple **named arguments**.

```python
def details(**info):
    for key, value in info.items():
        print(key, ":", value)

details(name="Alice", age=25, city="Paris")
```

✅ **Output:**

```
name : Alice
age : 25
city : Paris
```

👉 `**kwargs` collects keyword arguments into a **dictionary**.

---

### **e) Combination of Argument Types**

You can mix all types, but they must appear in the correct order:

```
positional → *args → keyword → **kwargs
```

Example:

```python
def example(a, b=10, *args, **kwargs):
    print(a, b, args, kwargs)

example(1, 2, 3, 4, x=5, y=6)
```

✅ **Output:**

```
1 2 (3, 4) {'x': 5, 'y': 6}
```

---

## 🧩 **3️⃣ Return Values**

Functions can **return data** back to the caller using the `return` keyword.

### **Syntax**

```python
def function_name(parameters):
    # statements
    return value
```

---

### **Example 1: Returning a Single Value**

```python
def add(a, b):
    return a + b

result = add(5, 3)
print("Result =", result)
```

✅ **Output:**

```
Result = 8
```

---

### **Example 2: Returning Multiple Values**

A function can return **multiple values** separated by commas — Python packs them into a **tuple**.

```python
def calc(a, b):
    return a + b, a - b, a * b

result = calc(10, 5)
print(result)
```

✅ **Output:**

```
(15, 5, 50)
```

You can **unpack** them too:

```python
sum_, diff, prod = calc(10, 5)
print(sum_, diff, prod)
```

✅ **Output:**

```
15 5 50
```

---

### **Example 3: Returning Strings or Lists**

```python
def names_list():
    return ["Alice", "Bob", "Charlie"]

print(names_list())
```

✅ **Output:**

```
['Alice', 'Bob', 'Charlie']
```

---

## 🧮 **4️⃣ Return vs Print**

| **print()**               | **return**                 |
| ------------------------- | -------------------------- |
| Displays output on screen | Sends value back to caller |
| Does not store result     | Allows storing in variable |
| Used for showing messages | Used for calculations      |

Example:

```python
def add_print(a, b):
    print(a + b)

def add_return(a, b):
    return a + b

x = add_print(2, 3)   # Prints 5
y = add_return(2, 3)  # Returns 5

print("x =", x)
print("y =", y)
```

✅ **Output:**

```
5
x = None
y = 5
```

---

## 🧠 **5️⃣ Practice Questions**

1. Write a function `add(a, b)` that returns their sum.
2. Create a function `greet(name, age)` using keyword arguments.
3. Write a function `multiply(*nums)` that multiplies any number of arguments.
4. Define a function `info(**details)` that prints user information.
5. Create a function `rectangle(l, w=5)` that returns area (default width=5).
6. Write a function `calc(a, b)` that returns sum, difference, and product.
7. Make a function that takes a list and returns the largest number.
8. Write a function that returns both the square and cube of a number.
9. Write a function that accepts any number of keyword arguments and prints them.
10. Define a function that returns whether a number is even or odd.

---

## ✅ **Summary Table**

| **Type**                | **Symbol** | **Stores As**     | **Example Call**    |
| ----------------------- | ---------- | ----------------- | ------------------- |
| Positional              | —          | Individual values | `func(1, 2)`        |
| Keyword                 | —          | Individual values | `func(a=1, b=2)`    |
| Default                 | —          | Individual values | `def func(a, b=5):` |
| Variable-length         | `*args`    | Tuple             | `func(1, 2, 3)`     |
| Keyword variable-length | `**kwargs` | Dictionary        | `func(x=1, y=2)`    |

---


