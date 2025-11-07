# 🧠 **Default and Keyword Arguments in Python**

Functions can be made more **versatile** using default values and keyword-based calling.
Let’s explore both in detail 👇

---

## 🪶 **1️⃣ Default Arguments**

A **default argument** is a parameter that **assumes a default value** if **no value** is provided when the function is called.

---

### **Syntax**

```python
def function_name(parameter=default_value):
    # body
```

---

### **Example 1: Basic Default Argument**

```python
def greet(name="Guest"):
    print("Hello,", name, "!")
    
greet("Alice")   # Argument provided
greet()          # No argument provided
```

✅ **Output:**

```
Hello, Alice !
Hello, Guest !
```

> 👉 Here, `"Guest"` is the **default value** used when no argument is passed.

---

### **Example 2: Multiple Default Arguments**

```python
def info(name, age=18, country="India"):
    print("Name:", name)
    print("Age:", age)
    print("Country:", country)

info("Riya")
```

✅ **Output:**

```
Name: Riya
Age: 18
Country: India
```

If you pass other arguments:

```python
info("John", 25, "USA")
```

✅ **Output:**

```
Name: John
Age: 25
Country: USA
```

---

### ⚠️ **Note on Argument Order**

**All default parameters must come after non-default parameters**.

❌ Invalid:

```python
def example(a=10, b):
    print(a, b)
```

✅ Correct:

```python
def example(a, b=10):
    print(a, b)
```

---

### **Example 3: Default with Expressions**

Default values can be results of expressions too.

```python
def multiply(a, b=2):
    return a * b

print(multiply(5))
print(multiply(5, 4))
```

✅ **Output:**

```
10
20
```

---

## ⚙️ **2️⃣ Keyword Arguments**

When calling a function, you can specify the **parameter names** with values.
This makes the call **clearer** and avoids confusion about argument order.

---

### **Example 1: Simple Keyword Argument**

```python
def display(name, age):
    print("Name:", name)
    print("Age:", age)

display(name="Alice", age=22)
```

✅ **Output:**

```
Name: Alice
Age: 22
```

---

### **Example 2: Changing Argument Order**

With keyword arguments, you can **swap order** safely.

```python
display(age=25, name="John")
```

✅ **Output:**

```
Name: John
Age: 25
```

---

### **Example 3: Mixing Positional and Keyword Arguments**

You can combine both — but **positional arguments must come first!**

✅ Correct:

```python
def student(name, course):
    print(name, "is enrolled in", course)

student("Ravi", course="Python")
```

❌ Invalid:

```python
student(name="Ravi", "Python")
```

```
SyntaxError: positional argument follows keyword argument
```

---

## 🧩 **3️⃣ Default + Keyword Combined Example**

```python
def person(name, age=20, city="Delhi"):
    print("Name:", name)
    print("Age:", age)
    print("City:", city)

person("Neha")  
person("Amit", city="Mumbai")  
person("John", 30, "London")
```

✅ **Output:**

```
Name: Neha
Age: 20
City: Delhi
Name: Amit
Age: 20
City: Mumbai
Name: John
Age: 30
City: London
```

---

## 🧮 **4️⃣ Example: Default Argument in Calculation**

```python
def power(base, exp=2):
    return base ** exp

print(power(4))     # Default exponent 2
print(power(4, 3))  # Overridden exponent
```

✅ **Output:**

```
16
64
```

---

## 💡 **5️⃣ Practical Example**

```python
def book_ticket(name, seat_type="Regular", fare=100):
    print(f"Ticket for {name}")
    print(f"Seat Type: {seat_type}")
    print(f"Fare: ₹{fare}")

book_ticket("Ankit")
book_ticket("Sita", seat_type="VIP", fare=250)
book_ticket(name="Raj", fare=150)
```

✅ **Output:**

```
Ticket for Ankit
Seat Type: Regular
Fare: ₹100

Ticket for Sita
Seat Type: VIP
Fare: ₹250

Ticket for Raj
Seat Type: Regular
Fare: ₹150
```

---

## ⚡ **6️⃣ Key Differences**

| **Aspect**           | **Default Argument**         | **Keyword Argument**              |
| -------------------- | ---------------------------- | --------------------------------- |
| **Definition**       | Has a default value          | Passed by name                    |
| **Used when**        | Argument may not be provided | To specify argument order clearly |
| **Example**          | `def add(a, b=5):`           | `add(b=10, a=2)`                  |
| **Order importance** | Default must come last       | Order doesn’t matter              |

---

## 🧠 **7️⃣ Practice Questions**

1. Define a function `welcome(name="Guest")` that prints a greeting.
2. Write a function `area(length, width=5)` that calculates the area of a rectangle.
3. Create a function `employee(name, salary=25000, dept="HR")` and test with different calls.
4. Write a function `power(num, exp=2)` that returns the square by default.
5. Define a function `student(name, age, course="Python")` and call it using keyword arguments.
6. Make a function `travel(destination="Goa", days=3, mode="Train")` and test various combinations.
7. Combine positional and keyword arguments in one function.
8. Demonstrate what happens when a positional argument follows a keyword argument (error case).
9. Write a function `bill(amount, tax=10)` that calculates total with tax.
10. Show how keyword arguments can change order safely.

---


