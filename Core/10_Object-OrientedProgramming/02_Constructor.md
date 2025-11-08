
# 🧩 **`__init__()` Constructor and `self` Keyword in Python**

---

## 🧠 **1️⃣ What is the `__init__()` Method?**

The `__init__()` method is a **special built-in method** in Python classes, also known as the **constructor**.

It is automatically called **when a new object is created**, and it’s used to **initialize** the object’s attributes.

---

### 🔹 **Syntax:**

```python
class ClassName:
    def __init__(self, parameters):
        # initialization code
        self.attribute = parameters
```

✅ **It always starts and ends with double underscores** (`__init__`), meaning it’s a *special method*.

---

### 🔹 **Example 1: Basic Constructor**

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

# Creating objects
p1 = Person("Alice", 25)
p2 = Person("Bob", 30)

print(p1.name, p1.age)
print(p2.name, p2.age)
```

✅ **Output:**

```
Alice 25
Bob 30
```

🧠 Here, `__init__()` runs automatically when `p1` and `p2` are created.

---

## ⚙️ **2️⃣ Why Use a Constructor?**

Constructors are used to:

* **Initialize object attributes** at creation time
* **Avoid redundant code**
* Ensure every object starts in a valid state

---

### 🔹 **Example 2: Without Constructor (less efficient)**

```python
class Student:
    pass

s1 = Student()
s1.name = "John"
s1.grade = "A"
```

✅ Works, but not ideal — attributes are added *after* object creation.
Better to use `__init__()` to set attributes automatically.

---

### 🔹 **Example 3: With Constructor (better approach)**

```python
class Student:
    def __init__(self, name, grade):
        self.name = name
        self.grade = grade

s1 = Student("John", "A")
s2 = Student("Emma", "B")

print(s1.name, s1.grade)
print(s2.name, s2.grade)
```

✅ Cleaner and safer. Every `Student` object is created with the required data.

---

## 🧩 **3️⃣ What is the `self` Keyword?**

`self` represents the **current instance** (object) of the class.

It is used to:

* Access **instance variables**
* Call **instance methods**
* Differentiate between **class variables** and **local variables**

---

### 🔹 **Example 4: Using `self`**

```python
class Dog:
    def __init__(self, name, breed):
        self.name = name       # instance variable
        self.breed = breed

    def bark(self):
        print(f"{self.name} says Woof!")

dog1 = Dog("Buddy", "Labrador")
dog2 = Dog("Max", "Bulldog")

dog1.bark()
dog2.bark()
```

✅ **Output:**

```
Buddy says Woof!
Max says Woof!
```

🧠 `self.name` and `self.breed` refer to the attributes of *each individual object*.

---

## ⚙️ **4️⃣ How `self` Works Internally**

When you call a method like:

```python
dog1.bark()
```

Python automatically converts it to:

```python
Dog.bark(dog1)
```

That’s why the first parameter of every instance method must be **`self`** — Python passes the object automatically.

---

### 🔹 **Example 5: Demonstrating Automatic Self-Passing**

```python
class Demo:
    def show(self):
        print("Method called for object:", self)

obj = Demo()
obj.show()       # same as Demo.show(obj)
```

✅ **Output:**

```
Method called for object: <__main__.Demo object at 0x000002>
```

---

## 💡 **5️⃣ Default Values in Constructors**

You can provide **default parameter values** in the constructor.

```python
class Employee:
    def __init__(self, name, salary=50000):
        self.name = name
        self.salary = salary

e1 = Employee("Alice")
e2 = Employee("Bob", 75000)

print(e1.name, e1.salary)
print(e2.name, e2.salary)
```

✅ **Output:**

```
Alice 50000
Bob 75000
```

---

## 🧠 **6️⃣ Constructor Overloading (Pythonic Way)**

Python doesn’t support multiple constructors directly,
but you can achieve similar behavior with **default arguments** or **`*args`**.

### Example:

```python
class Student:
    def __init__(self, name, age=None):
        self.name = name
        self.age = age if age is not None else "Unknown"

s1 = Student("John", 18)
s2 = Student("Alice")

print(s1.name, s1.age)
print(s2.name, s2.age)
```

✅ **Output:**

```
John 18
Alice Unknown
```

---

## 🧩 **7️⃣ Using `self` to Access Other Methods**

You can use `self` to call **another method** from within a class.

```python
class Circle:
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * (self.radius ** 2)

    def display(self):
        print(f"Area of circle: {self.area()}")

c1 = Circle(5)
c1.display()
```

✅ **Output:**

```
Area of circle: 78.5
```

---

## ⚙️ **8️⃣ Deleting Attributes and Objects**

You can delete object attributes or the entire object using `del`.

```python
class Person:
    def __init__(self, name):
        self.name = name

p1 = Person("Alice")
print(p1.name)

del p1.name     # Delete attribute
del p1          # Delete object
```

---

## 🧾 **9️⃣ Summary Table**

| **Concept**                | **Description**                                          | **Example**                |
| -------------------------- | -------------------------------------------------------- | -------------------------- |
| `__init__()`               | Constructor, called automatically when object is created | `def __init__(self, x):`   |
| `self`                     | Refers to current object                                 | `self.name = name`         |
| **Instance Variable**      | Unique to each object                                    | `self.age`                 |
| **Class Variable**         | Shared by all objects                                    | `Car.wheels = 4`           |
| **Default Values**         | Optional parameters in constructor                       | `def __init__(self, a=10)` |
| **Call Methods with self** | Access other class methods                               | `self.method_name()`       |

---

## 🧠 **🔟 Practice Questions**

1. Create a class `Person` with attributes `name` and `age`. Initialize them using the constructor and display them.
2. Create a class `Rectangle` with attributes `length` and `width`. Add methods to calculate and display the area.
3. Create a class `Laptop` with a default value for `RAM` (e.g., 8GB) and another attribute for price.
4. Create a class `Employee` that displays salary information. Use `self` to call another method that calculates bonus.
5. Demonstrate that `self` refers to the specific object by creating multiple objects with different values.

---

## ✅ **11️⃣ Summary**

| **Term**                   | **Meaning**                                                        |
| -------------------------- | ------------------------------------------------------------------ |
| `__init__()`               | Constructor method, called automatically when an object is created |
| `self`                     | Refers to the current object inside the class                      |
| **Purpose of constructor** | Initializes attributes of new objects                              |
| **Purpose of self**        | Access object data and methods                                     |
| **Called automatically**   | `__init__()` runs on object creation                               |
| **Customizable**           | Can include parameters, defaults, and logic                        |

---

### 🔎 **Example Summary Program**

```python
class Car:
    def __init__(self, brand, model, price=10000):
        self.brand = brand
        self.model = model
        self.price = price

    def display(self):
        print(f"Brand: {self.brand}, Model: {self.model}, Price: ${self.price}")

# Creating objects
car1 = Car("Toyota", "Corolla", 18000)
car2 = Car("BMW", "X5")

car1.display()
car2.display()
```

✅ **Output:**

```
Brand: Toyota, Model: Corolla, Price: $18000
Brand: BMW, Model: X5, Price: $10000
```

---


