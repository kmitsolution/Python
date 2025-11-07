# 🧠 **Variable-Length Arguments in Python (`*args` and `**kwargs`)**

Sometimes you don’t know **how many arguments** will be passed to your function.
Python solves this using:

* `*args` → for **any number of positional arguments**
* `**kwargs` → for **any number of keyword arguments**

---

## 🪶 **1️⃣ The Need for Variable-Length Arguments**

Normally, functions have a fixed number of parameters:

```python
def add(a, b):
    return a + b

print(add(2, 3))   # ✅ Works
print(add(2, 3, 4)) # ❌ Error
```

✅ Solution → use `*args` or `**kwargs` to make them flexible!

---

## ⚙️ **2️⃣ `*args` – Variable-Length Positional Arguments**

* `*args` allows you to pass **any number of positional arguments**.
* Inside the function, all values are stored as a **tuple**.

---

### **Syntax**

```python
def function_name(*args):
    # args is a tuple
```

---

### **Example 1: Sum of All Numbers**

```python
def add_all(*numbers):
    total = 0
    for n in numbers:
        total += n
    print("Sum =", total)

add_all(2, 4, 6)
add_all(1, 2, 3, 4, 5)
```

✅ **Output:**

```
Sum = 12
Sum = 15
```

---

### **Example 2: Printing Multiple Arguments**

```python
def show_names(*names):
    print("Names:", names)

show_names("Alice", "Bob", "Charlie")
```

✅ **Output:**

```
Names: ('Alice', 'Bob', 'Charlie')
```

> Here `args` becomes a tuple: `('Alice', 'Bob', 'Charlie')`

---

### **Example 3: Accessing Individual Arguments**

```python
def show_numbers(*nums):
    for n in nums:
        print(n, end=" ")

show_numbers(10, 20, 30)
```

✅ **Output:**

```
10 20 30
```

---

### **Example 4: Using `*args` with Other Parameters**

```python
def greet(message, *names):
    for name in names:
        print(message, name)

greet("Hello", "Ravi", "Sita", "John")
```

✅ **Output:**

```
Hello Ravi
Hello Sita
Hello John
```

---

## 🧩 **3️⃣ `**kwargs` – Variable-Length Keyword Arguments**

* `**kwargs` allows passing **multiple keyword arguments**.
* Inside the function, all are stored as a **dictionary** (`key: value` pairs).

---

### **Syntax**

```python
def function_name(**kwargs):
    # kwargs is a dictionary
```

---

### **Example 1: Displaying Keyword Arguments**

```python
def show_info(**details):
    print(details)

show_info(name="Alice", age=25, city="Paris")
```

✅ **Output:**

```
{'name': 'Alice', 'age': 25, 'city': 'Paris'}
```

---

### **Example 2: Iterating Over `**kwargs`**

```python
def show_details(**info):
    for key, value in info.items():
        print(key, ":", value)

show_details(name="John", age=30, country="India")
```

✅ **Output:**

```
name : John
age : 30
country : India
```

---

### **Example 3: Default + Keyword Combination**

```python
def profile(greeting="Hello", **person):
    print(greeting)
    for key, value in person.items():
        print(f"{key}: {value}")

profile(name="Sara", age=22, city="London")
```

✅ **Output:**

```
Hello
name: Sara
age: 22
city: London
```

---

## 🔄 **4️⃣ Combining Normal, `*args`, and `**kwargs`**

You can use all together — **but in this order:**

```
positional → *args → keyword → **kwargs
```

---

### **Example:**

```python
def example(a, b, *args, **kwargs):
    print("a =", a)
    print("b =", b)
    print("args =", args)
    print("kwargs =", kwargs)

example(10, 20, 30, 40, x=100, y=200)
```

✅ **Output:**

```
a = 10
b = 20
args = (30, 40)
kwargs = {'x': 100, 'y': 200}
```

---

## 💡 **5️⃣ Unpacking with `*` and `**`**

You can also **unpack** values when calling functions.

### **Example 1: Unpacking Lists**

```python
def multiply(a, b, c):
    print(a * b * c)

nums = [2, 3, 4]
multiply(*nums)  # Unpacks list
```

✅ **Output:**

```
24
```

---

### **Example 2: Unpacking Dictionaries**

```python
def intro(name, age, city):
    print(f"My name is {name}, I'm {age}, from {city}")

data = {'name': 'John', 'age': 25, 'city': 'Delhi'}
intro(**data)
```

✅ **Output:**

```
My name is John, I'm 25, from Delhi
```

---

## ⚡ **6️⃣ Practical Example**

```python
def order(food, *extras, **details):
    print("Food:", food)
    print("Extras:", extras)
    print("Details:", details)

order("Pizza", "Cheese", "Olives", size="Medium", drink="Coke")
```

✅ **Output:**

```
Food: Pizza
Extras: ('Cheese', 'Olives')
Details: {'size': 'Medium', 'drink': 'Coke'}
```

---

## 🧠 **7️⃣ Practice Questions**

1. Write a function `sum_all(*nums)` that returns the sum of any number of numbers.
2. Create a function `details(**info)` that prints name, age, and city.
3. Define a function that takes both `*args` and `**kwargs` and prints them.
4. Write a function `add(*values)` that returns their average.
5. Make a function `print_names(*names)` that prints each name on a new line.
6. Create a function `profile(name, **data)` that prints profile details.
7. Define a function that mixes positional, `*args`, and `**kwargs` arguments.
8. Write a function `invoice(product, *items, **details)` to show bill summary.
9. Show how to unpack a list and dictionary into function arguments.
10. Write a program using `*args` to multiply any number of inputs.

---

## ✅ **Summary Table**

| **Type**   | **Syntax**                  | **Stored As** | **Example Call**        |
| ---------- | --------------------------- | ------------- | ----------------------- |
| `*args`    | `def func(*args):`          | Tuple         | `func(1, 2, 3)`         |
| `**kwargs` | `def func(**kwargs):`       | Dictionary    | `func(a=1, b=2)`        |
| **Order**  | `normal → *args → **kwargs` | —             | `func(10, 20, 30, x=5)` |

---

