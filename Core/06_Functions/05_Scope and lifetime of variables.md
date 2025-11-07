# 🧠 **Scope and Lifetime of Variables in Python**

This topic explains **where** a variable can be accessed (scope) and **how long** it exists in memory (lifetime).

---

## 🪶 **1️⃣ What is Variable Scope?**

The **scope** of a variable refers to the **region of a program** where that variable can be accessed or used.

Python has **four levels of variable scope**, following the **LEGB Rule**:

| **Level** | **Full Form** | **Meaning**                                       |
| --------- | ------------- | ------------------------------------------------- |
| **L**     | Local         | Inside a function                                 |
| **E**     | Enclosing     | Inside nested functions                           |
| **G**     | Global        | Defined at the top level of the script            |
| **B**     | Built-in      | Predefined names in Python (e.g., `len`, `print`) |

👉 **Python checks for a variable in this LEGB order** (Local → Enclosing → Global → Built-in).

---

## ⚙️ **2️⃣ Local Variables**

A **local variable** is declared **inside a function** and can be accessed **only within** that function.

### **Example:**

```python
def show():
    x = 10  # Local variable
    print("Inside function:", x)

show()
print("Outside function:", x)  # ❌ Error
```

✅ **Output:**

```
Inside function: 10
Traceback (most recent call last):
NameError: name 'x' is not defined
```

> 🧩 Explanation:
> `x` is **local** to the `show()` function — it doesn’t exist outside it.

---

## 🌍 **3️⃣ Global Variables**

A **global variable** is defined **outside** of all functions and can be accessed **anywhere** in the program.

### **Example:**

```python
x = 100  # Global variable

def display():
    print("Inside function:", x)

display()
print("Outside function:", x)
```

✅ **Output:**

```
Inside function: 100
Outside function: 100
```

---

## ⚠️ **4️⃣ Modifying Global Variables Inside a Function**

If you want to **change** a global variable from inside a function,
you must declare it as **`global`**.

### **Example:**

```python
count = 10

def modify():
    global count
    count = count + 5
    print("Inside function:", count)

modify()
print("Outside function:", count)
```

✅ **Output:**

```
Inside function: 15
Outside function: 15
```

> Without the `global` keyword, Python would treat `count` as a **new local variable**, causing an error.

---

## 🔁 **5️⃣ Enclosing Scope (Nonlocal Variables)**

When you have **nested functions**, the **inner function** can access variables from the **enclosing function** (outer function).
If you want to modify them, use the **`nonlocal`** keyword.

### **Example:**

```python
def outer():
    x = 5   # Enclosing variable
    def inner():
        nonlocal x
        x += 1
        print("Inside inner:", x)
    inner()
    print("Inside outer:", x)

outer()
```

✅ **Output:**

```
Inside inner: 6
Inside outer: 6
```

> 🧩 `nonlocal` allows modification of variables from the **enclosing scope** (not global).

---

## ⚡ **6️⃣ Built-in Scope**

These are Python’s **predefined names**, available anywhere (e.g., `len`, `max`, `print`, etc.).

Example:

```python
print(len([1, 2, 3]))  # len() is a built-in function
```

✅ **Output:**

```
3
```

If you create a variable with the same name, it shadows (hides) the built-in one:

```python
len = 100
print(len([1, 2, 3]))  # ❌ Error
```

✅ **Output:**

```
TypeError: 'int' object is not callable
```

---

## ⏱️ **7️⃣ Lifetime of Variables**

The **lifetime** of a variable refers to **how long it exists in memory** during program execution.

| **Type**   | **Where Created**           | **When Destroyed**     |
| ---------- | --------------------------- | ---------------------- |
| **Local**  | When the function is called | When the function ends |
| **Global** | When the program starts     | When the program ends  |

### **Example:**

```python
def test():
    x = 10   # local variable
    print("Inside function:", x)

test()
print("Outside function: function ended")  # 'x' is destroyed
```

✅ **Output:**

```
Inside function: 10
Outside function: function ended
```

---

## 🧩 **8️⃣ Example: Local vs Global**

```python
x = 50  # Global

def func():
    x = 10  # Local
    print("Inside function:", x)

func()
print("Outside function:", x)
```

✅ **Output:**

```
Inside function: 10
Outside function: 50
```

> Local and global variables with the same name are **independent**.

---

## 💡 **9️⃣ Example: Global, Local, and Nonlocal Together**

```python
x = "global"

def outer():
    x = "outer"

    def inner():
        nonlocal x
        x = "inner"
        print("Inside inner:", x)

    inner()
    print("Inside outer:", x)

outer()
print("Outside all:", x)
```

✅ **Output:**

```
Inside inner: inner
Inside outer: inner
Outside all: global
```

---

## 🧠 **🔟 Practice Questions**

1. Write a program to demonstrate local and global variables.
2. Show how to modify a global variable inside a function.
3. Create nested functions and use a **nonlocal** variable.
4. Write a program that prints the LEGB variable resolution order.
5. Define a variable inside a function and try accessing it outside (observe error).
6. Create two functions using the same global variable — show shared access.
7. Demonstrate what happens if a local variable has the same name as a global one.
8. Use `nonlocal` to modify a variable from an enclosing scope.
9. Write a program that creates and destroys local variables (lifetime demo).
10. Show what happens if you override a built-in function name like `len` or `sum`.

---

## ✅ **Summary Table**

| **Scope Type** | **Defined Where**              | **Accessible Where**      | **Keyword** |
| -------------- | ------------------------------ | ------------------------- | ----------- |
| **Local**      | Inside a function              | Only inside that function | —           |
| **Enclosing**  | Inside nested (outer) function | Inner functions           | `nonlocal`  |
| **Global**     | Outside all functions          | Everywhere in file        | `global`    |
| **Built-in**   | Python system-level            | Everywhere                | —           |

---


