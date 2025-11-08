
# 🧩 **Methods in Python (Instance, Class, and Static Methods)**

---

## 🧠 **1️⃣ What is a Method?**

A **method** is simply a **function defined inside a class** that operates on data (attributes) belonging to that class.

Depending on **what they operate on**, methods are divided into:

1. **Instance Methods** → Work on *instance variables*
2. **Class Methods** → Work on *class variables*
3. **Static Methods** → Utility functions that don’t depend on class or instance data

---

## ⚙️ **2️⃣ Instance Methods**

* The most common type of method.
* Defined normally using `def`.
* **Always take `self`** as the first parameter.
* Can **access and modify instance variables** and also class variables.

---

### **Example 1: Instance Method**

```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    # Instance method
    def display(self):
        print(f"Name: {self.name}, Marks: {self.marks}")

s1 = Student("Alice", 90)
s1.display()
```

✅ **Output:**

```
Name: Alice, Marks: 90
```

🧠 Here, `display()` uses `self` to access **instance attributes** (`name` and `marks`).

---

### **Example 2: Instance Method Modifying Data**

```python
class Account:
    def __init__(self, balance):
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
        print(f"Deposited {amount}. New balance: {self.balance}")

a1 = Account(1000)
a1.deposit(500)
```

✅ **Output:**

```
Deposited 500. New balance: 1500
```

🧠 Instance methods **operate on individual object data**.

---

## 🧩 **3️⃣ Class Methods**

* Defined using the **@classmethod** decorator.
* Take `cls` (class reference) as the first parameter instead of `self`.
* Can **access and modify class variables** (shared by all objects).
* Cannot directly access instance variables.

---

### **Syntax:**

```python
@classmethod
def method_name(cls):
    # work with class variables
```

---

### **Example 1: Basic Class Method**

```python
class Employee:
    company = "TechCorp"

    def __init__(self, name):
        self.name = name

    @classmethod
    def change_company(cls, new_name):
        cls.company = new_name

e1 = Employee("Alice")
e2 = Employee("Bob")

Employee.change_company("NextGenTech")

print(e1.company)
print(e2.company)
```

✅ **Output:**

```
NextGenTech
NextGenTech
```

🧠 `cls` refers to the **class itself**, and changes made affect all objects.

---

### **Example 2: Creating Objects in an Alternative Way**

You can use class methods as **alternative constructors**.

```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    @classmethod
    def from_string(cls, data_str):
        name, marks = data_str.split('-')
        return cls(name, int(marks))

s1 = Student.from_string("Alice-85")
print(s1.name, s1.marks)
```

✅ **Output:**

```
Alice 85
```

🧠 The class method here acts as a **second constructor** that builds objects from string data.

---

## ⚙️ **4️⃣ Static Methods**

* Defined using the **@staticmethod** decorator.
* **Do not take `self` or `cls`** as parameters.
* Cannot access instance or class variables.
* Used for **utility or helper functions** that perform general tasks related to the class.

---

### **Syntax:**

```python
@staticmethod
def method_name():
    # code that does not depend on class or instance data
```

---

### **Example 1: Simple Static Method**

```python
class MathOperations:
    @staticmethod
    def add(a, b):
        return a + b

    @staticmethod
    def multiply(a, b):
        return a * b

print(MathOperations.add(5, 3))
print(MathOperations.multiply(4, 2))
```

✅ **Output:**

```
8
8
```

🧠 `add()` and `multiply()` are **utility methods** — they don’t depend on instance or class data.

---

### **Example 2: Static Method Inside Class**

```python
class Student:
    @staticmethod
    def greet():
        print("Welcome to Python OOP Concepts!")

Student.greet()
```

✅ **Output:**

```
Welcome to Python OOP Concepts!
```

🧠 You can call static methods directly from the class — no need to create an object.

---

## 💡 **5️⃣ Example with All Three Method Types**

```python
class Employee:
    company = "TechCorp"  # class variable

    def __init__(self, name, salary):
        self.name = name      # instance variable
        self.salary = salary

    # Instance method
    def display(self):
        print(f"Name: {self.name}, Salary: {self.salary}, Company: {Employee.company}")

    # Class method
    @classmethod
    def change_company(cls, new_company):
        cls.company = new_company

    # Static method
    @staticmethod
    def company_policy():
        print("Company policy: Work 8 hours a day!")

# Using the methods
e1 = Employee("Alice", 50000)
e2 = Employee("Bob", 60000)

e1.display()

Employee.change_company("NextGenTech")
e2.display()

Employee.company_policy()
```

✅ **Output:**

```
Name: Alice, Salary: 50000, Company: TechCorp
Name: Bob, Salary: 60000, Company: NextGenTech
Company policy: Work 8 hours a day!
```

---

## 🧠 **6️⃣ Summary of Method Types**

| **Type**            | **Decorator**   | **First Parameter** | **Access To**               | **Called Using** | **Purpose**               |
| ------------------- | --------------- | ------------------- | --------------------------- | ---------------- | ------------------------- |
| **Instance Method** | *(none)*        | `self`              | Instance + Class variables  | Object           | Works on object data      |
| **Class Method**    | `@classmethod`  | `cls`               | Class variables only        | Class or Object  | Modifies class-level data |
| **Static Method**   | `@staticmethod` | None                | No access to instance/class | Class or Object  | Utility / Helper function |

---

## ⚙️ **7️⃣ Visual Representation**

```
Class: Employee
|
|__ class variable → company
|__ instance variable → name, salary
|
|__ instance method (uses self)
|__ class method (uses cls)
|__ static method (no self/cls)
```

---

## 🧩 **8️⃣ Practical Example: Student Management**

```python
class Student:
    school_name = "ABC High School"

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    # Instance method
    def display(self):
        print(f"{self.name} scored {self.marks} marks.")

    # Class method
    @classmethod
    def change_school(cls, new_name):
        cls.school_name = new_name

    # Static method
    @staticmethod
    def info():
        print("This is a student class for managing records.")

# Using methods
Student.info()

s1 = Student("Alice", 90)
s2 = Student("Bob", 85)

s1.display()
s2.display()

Student.change_school("XYZ International School")
print("New School:", Student.school_name)
```

✅ **Output:**

```
This is a student class for managing records.
Alice scored 90 marks.
Bob scored 85 marks.
New School: XYZ International School
```

---

## 🧾 **9️⃣ Quick Recap Table**

| **Method Type**     | **Decorator**   | **First Arg** | **Accesses**          | **Use Case**            |
| ------------------- | --------------- | ------------- | --------------------- | ----------------------- |
| **Instance Method** | none            | `self`        | Instance + Class Data | Modify object data      |
| **Class Method**    | `@classmethod`  | `cls`         | Class Data Only       | Change class-level info |
| **Static Method**   | `@staticmethod` | None          | No Data Access        | Utility function        |

---

## 🧠 **🔟 Practice Questions**

1. Create a class `Circle` with:

   * Instance variable: `radius`
   * Class variable: `pi = 3.14`
   * Instance method: `area()` → returns area of circle
   * Class method: to change the value of `pi`
   * Static method: to print a message “This calculates area of a circle”

2. Create a class `Employee` with:

   * Instance method to show employee info
   * Class method to change company name
   * Static method to show company policies

3. Create a class `MathOperations` with static methods for add, subtract, multiply, and divide.

4. Create a class `Student` where:

   * `@classmethod` counts total students created.
   * `@staticmethod` prints a welcome message.

---

## ✅ **11️⃣ Summary**

| **Concept**         | **Description**                                                    |
| ------------------- | ------------------------------------------------------------------ |
| **Instance Method** | Works with instance (object) data using `self`.                    |
| **Class Method**    | Works with class-level data using `cls`.                           |
| **Static Method**   | Independent helper function; no `self` or `cls`.                   |
| **Decorators Used** | `@classmethod` and `@staticmethod`.                                |
| **Best Practice**   | Use static/class methods for logical grouping and clean structure. |

---

### 🔎 **Example Summary Program**

```python
class Calculator:
    def __init__(self, a, b):
        self.a = a
        self.b = b

    # Instance method
    def add(self):
        return self.a + self.b

    # Class method
    @classmethod
    def info(cls):
        print("This is a calculator class that adds two numbers.")

    # Static method
    @staticmethod
    def greet():
        print("Welcome to the Calculator Program!")

# Using the methods
Calculator.greet()
Calculator.info()

calc1 = Calculator(10, 20)
print("Sum:", calc1.add())
```

✅ **Output:**

```
Welcome to the Calculator Program!
This is a calculator class that adds two numbers.
Sum: 30
```

---


