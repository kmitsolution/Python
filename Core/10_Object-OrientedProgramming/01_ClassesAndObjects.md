# 🧩 **Object-Oriented Programming (OOP) — Classes and Objects**

---

## 🧠 **1️⃣ What is OOP?**

**Object-Oriented Programming (OOP)** is a programming paradigm that organizes code into **objects** — reusable components that combine **data** and **behavior**.

### In simple terms:

* **Objects** are like *real-world things* (Car, Dog, Student, BankAccount).
* **Classes** are *blueprints* for creating those objects.

OOP makes code:
✅ Easier to read
✅ Easier to maintain
✅ More reusable and scalable

---

## ⚙️ **2️⃣ The Four Pillars of OOP**

| **Concept**       | **Meaning**                                             |
| ----------------- | ------------------------------------------------------- |
| **Encapsulation** | Binding data and methods together                       |
| **Abstraction**   | Hiding implementation details                           |
| **Inheritance**   | Reusing code by inheriting properties                   |
| **Polymorphism**  | Same function behaves differently for different objects |

We’ll cover these one by one — starting with **classes and objects**, the foundation of OOP.

---

## 🏗️ **3️⃣ What is a Class?**

A **class** is a **blueprint or template** for creating objects.
It defines **attributes** (data) and **methods** (functions) that describe the object’s behavior.

### **Syntax:**

```python
class ClassName:
    # class attributes and methods
    pass
```

---

### **Example 1: Creating a Simple Class**

```python
class Car:
    # Class attribute
    wheels = 4

    # Instance method
    def __init__(self, brand, color):
        self.brand = brand
        self.color = color

    def start(self):
        print(f"{self.brand} car is starting...")

# Creating objects (instances)
car1 = Car("Toyota", "Red")
car2 = Car("BMW", "Black")

# Accessing attributes and methods
print(car1.brand)
print(car2.color)
car1.start()
```

✅ **Output:**

```
Toyota
Black
Toyota car is starting...
```

---

## 🚗 **4️⃣ What is an Object?**

An **object** is an **instance** of a class.
Each object has its own **unique data**, but shares the **same methods** defined in the class.

| **Concept**                   | **Explanation**                                        |
| ----------------------------- | ------------------------------------------------------ |
| `car1 = Car("Toyota", "Red")` | Creates a new object of `Car` class                    |
| `self`                        | Refers to the current object (instance) inside a class |

---

## 🧩 **5️⃣ The `__init__()` Constructor Method**

* Automatically called when an object is created.
* Used to initialize object attributes.

### Example:

```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

s1 = Student("Alice", 20)
s2 = Student("Bob", 22)

print(s1.name, s1.age)
print(s2.name, s2.age)
```

✅ **Output:**

```
Alice 20
Bob 22
```

---

## 💡 **6️⃣ Class vs Instance Attributes**

| **Type**               | **Defined**                                 | **Shared by all objects?** |
| ---------------------- | ------------------------------------------- | -------------------------- |
| **Class attribute**    | Inside the class, outside any method        | ✅ Yes                      |
| **Instance attribute** | Inside the `__init__()` method using `self` | ❌ No                       |

### Example:

```python
class Dog:
    species = "Canine"  # class attribute

    def __init__(self, name, age):
        self.name = name  # instance attribute
        self.age = age

dog1 = Dog("Buddy", 3)
dog2 = Dog("Max", 5)

print(dog1.species, dog1.name)
print(dog2.species, dog2.name)
```

✅ **Output:**

```
Canine Buddy
Canine Max
```

---

## ⚙️ **7️⃣ Defining Methods in Classes**

A **method** is a function defined inside a class.

### Example:

```python
class Calculator:
    def add(self, a, b):
        return a + b

    def multiply(self, a, b):
        return a * b

calc = Calculator()
print(calc.add(10, 5))
print(calc.multiply(3, 4))
```

✅ **Output:**

```
15
12
```

---

## 🧠 **8️⃣ The `self` Keyword**

* `self` refers to the **current instance** of the class.
* It lets you access instance variables and methods.

### Example:

```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        print("Hello, my name is", self.name)

p1 = Person("John")
p1.greet()
```

✅ **Output:**

```
Hello, my name is John
```

---

## 🧮 **9️⃣ Example: Real-world Class**

```python
class BankAccount:
    def __init__(self, account_holder, balance=0):
        self.account_holder = account_holder
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
        print(f"Deposited ${amount}. New balance = ${self.balance}")

    def withdraw(self, amount):
        if amount > self.balance:
            print("Insufficient balance!")
        else:
            self.balance -= amount
            print(f"Withdrew ${amount}. Remaining balance = ${self.balance}")

# Creating objects
acc1 = BankAccount("Alice", 1000)
acc1.deposit(500)
acc1.withdraw(300)
acc1.withdraw(2000)
```

✅ **Output:**

```
Deposited $500. New balance = $1500
Withdrew $300. Remaining balance = $1200
Insufficient balance!
```

---

## 🧩 **🔟 The `__str__()` Method**

Used to give objects a **readable string representation** when printed.

### Example:

```python
class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author

    def __str__(self):
        return f"'{self.title}' by {self.author}"

book1 = Book("Python Basics", "John Smith")
print(book1)
```

✅ **Output:**

```
'Python Basics' by John Smith
```

---

## 🧱 **11️⃣ Example: Student Class**

```python
class Student:
    def __init__(self, name, roll, marks):
        self.name = name
        self.roll = roll
        self.marks = marks

    def display(self):
        print(f"Name: {self.name}, Roll: {self.roll}, Marks: {self.marks}")

s1 = Student("Alice", 101, 85)
s2 = Student("Bob", 102, 90)

s1.display()
s2.display()
```

✅ **Output:**

```
Name: Alice, Roll: 101, Marks: 85
Name: Bob, Roll: 102, Marks: 90
```

---

## 🧠 **12️⃣ Updating and Deleting Attributes**

```python
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

emp1 = Employee("David", 50000)

# Updating
emp1.salary = 60000

# Deleting
del emp1.name

print(emp1.salary)
```

✅ **Output:**

```
60000
```

---

## 🧾 **13️⃣ Summary Table**

| **Concept**            | **Description**                 | **Example**           |
| ---------------------- | ------------------------------- | --------------------- |
| **Class**              | Blueprint for objects           | `class Car:`          |
| **Object**             | Instance of a class             | `mycar = Car()`       |
| **Attributes**         | Data (variables) inside a class | `self.name, self.age` |
| **Methods**            | Functions inside a class        | `def start(self):`    |
| **Constructor**        | Initializes object (`__init__`) | `def __init__(...)`   |
| **self**               | Refers to current object        | `self.name = name`    |
| **Class attribute**    | Shared by all objects           | `species = "Canine"`  |
| **Instance attribute** | Unique to each object           | `self.name`           |

---

## 🧠 **14️⃣ Practice Questions**

1. Create a class `Person` with attributes `name` and `age`, and a method `greet()` that prints a message.
2. Create a class `Rectangle` that has attributes `length` and `width` and a method to calculate the area.
3. Create a class `Employee` with attributes `name`, `salary`, and a method to display them.
4. Modify the `BankAccount` class to include a method for checking balance.
5. Create a class `Laptop` with attributes `brand`, `RAM`, `price`, and a method to display laptop details.

---

## ✅ **15️⃣ Summary**

| **Term**         | **Meaning**                                             |
| ---------------- | ------------------------------------------------------- |
| **Class**        | Template that defines structure and behavior of objects |
| **Object**       | Instance of a class                                     |
| **self**         | Refers to current object                                |
| **`__init__()`** | Constructor method, initializes attributes              |
| **Attributes**   | Variables inside a class/object                         |
| **Methods**      | Functions that define object behavior                   |

---

✅ **In short:**

> A class is the **blueprint** for creating objects.
> An object is a **real instance** with data and behavior.

---


