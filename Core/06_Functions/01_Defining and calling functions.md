# 🧠 **Defining and Calling Functions in Python**

This section focuses entirely on **how to define** and **call** functions — the most essential concept before parameters, return values, or recursion.

---

## 🪶 **1️⃣ What is a Function?**

A **function** is a block of code that performs a **specific task**.
It runs **only when it is called**.

Functions help you:

* Reuse code
* Organize your program
* Reduce repetition
* Improve readability

---

## ⚙️ **2️⃣ Defining a Function**

In Python, functions are defined using the **`def` keyword**.

### **Syntax**

```python
def function_name():
    # block of code
    statement(s)
```

* `def` → keyword to define a function
* `function_name` → any valid identifier (follow naming rules)
* `()` → parentheses (can hold parameters)
* `:` → indicates start of function block
* Indentation → defines the function body

---

### **Example**

```python
def greet():
    print("Hello, welcome to Python!")
```

Here:

* The function’s name is `greet`
* It contains one statement that prints a message

---

## ▶️ **3️⃣ Calling a Function**

To **execute** the code inside a function, you **call** it by its name followed by parentheses `()`.

### **Example**

```python
def greet():
    print("Hello, welcome to Python!")

# Calling the function
greet()
```

✅ **Output:**

```
Hello, welcome to Python!
```

If you don’t call the function, the code inside it won’t execute.

---

## 💡 **4️⃣ Defining and Calling Multiple Times**

You can call a function **multiple times** in your code.

```python
def greet():
    print("Good morning!")

greet()
greet()
```

✅ **Output:**

```
Good morning!
Good morning!
```

---

## 🧩 **5️⃣ Function with Parameters (Basic Preview)**

You can make functions more flexible by **passing data** using **parameters**.

```python
def greet_user(name):
    print("Hello,", name, "!")
    
greet_user("Alice")
greet_user("Bob")
```

✅ **Output:**

```
Hello, Alice !
Hello, Bob !
```

> Here `name` is a **parameter**, and `"Alice"` / `"Bob"` are **arguments**.

---

## 🔁 **6️⃣ Function with Return Value (Basic Preview)**

Functions can **return a value** using the `return` keyword.

```python
def add():
    a = 10
    b = 20
    return a + b

result = add()
print("Sum =", result)
```

✅ **Output:**

```
Sum = 30
```

---

## ⚡ **7️⃣ Function Flow Summary**

1. Define a function using `def`
2. Write the code inside (indented)
3. Call the function using its name and `()`
4. If it has parameters, pass arguments inside `()`
5. If it returns something, capture the result

---

## 🧩 **8️⃣ Example: Combining Multiple Functions**

```python
def greet():
    print("Welcome!")

def add_numbers():
    x = 10
    y = 20
    print("Sum =", x + y)

# Calling both
greet()
add_numbers()
```

✅ **Output:**

```
Welcome!
Sum = 30
```

---

## 🧠 **9️⃣ Example: Function Calling Another Function**

Functions can call **other functions** too!

```python
def greet():
    print("Hi there!")

def welcome():
    greet()
    print("Welcome to Python tutorials.")

welcome()
```

✅ **Output:**

```
Hi there!
Welcome to Python tutorials.
```

---

## 🧮 **🔟 Practice Questions**

1. Write a function `hello()` that prints “Hello, World!”.
2. Create a function `wish()` that prints “Good morning!” three times.
3. Write a function `display_name()` that prints your name.
4. Write a function `show_message()` that prints a welcome message, then call it twice.
5. Define a function `intro()` that prints your name and city inside it.
6. Create two functions — `add()` and `subtract()` — and call both in one program.
7. Write a function that prints “Python is fun!” only when called.
8. Write a function that calls another function from inside it.
9. Define a function to print the current year (use a print statement).
10. Write a function `repeat_msg()` that prints any message multiple times.

---

## ✅ **Summary Table**

| **Concept**    | **Description**              | **Example**          |
| -------------- | ---------------------------- | -------------------- |
| Define         | Use `def` keyword            | `def greet():`       |
| Call           | Use function name + `()`     | `greet()`            |
| No arguments   | Function without inputs      | `def hello():`       |
| With arguments | Pass data inside parentheses | `def greet(name):`   |
| Return value   | Send back a result           | `return value`       |
| Nested calls   | One function calls another   | `f1()` inside `f2()` |

---


