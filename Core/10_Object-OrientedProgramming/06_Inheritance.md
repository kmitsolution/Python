
# 🧩 **Inheritance and Method Overriding in Python**

---

## 🧠 **1️⃣ What is Inheritance?**

**Inheritance** allows a class (child or subclass) to **acquire the properties and methods** of another class (parent or base class).

It helps in:
✅ Code reusability
✅ Better organization
✅ Extending or customizing behavior

---

### **Syntax:**

```python
class Parent:
    # parent members
    pass

class Child(Parent):
    # child members
    pass
```

🧠 The child class automatically gets access to the parent’s attributes and methods.

---

## 💡 **2️⃣ Example: Simple (Single) Inheritance**

```python
class Parent:
    def display_parent(self):
        print("This is the parent class.")

class Child(Parent):
    def display_child(self):
        print("This is the child class.")

obj = Child()
obj.display_parent()
obj.display_child()
```

✅ **Output:**

```
This is the parent class.
This is the child class.
```

🧠 The `Child` class inherits all functionality from `Parent`.

---

## ⚙️ **3️⃣ The `super()` Function**

When you override a method or define your own constructor in the child class,
you can still call the **parent’s version** using `super()`.

---

### **Example: Using `super()` in Constructor**

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def show(self):
        print(f"Name: {self.name}, Age: {self.age}")

class Student(Person):
    def __init__(self, name, age, marks):
        super().__init__(name, age)     # call parent constructor
        self.marks = marks

    def show(self):
        super().show()                  # call parent method
        print(f"Marks: {self.marks}")

s1 = Student("Alice", 20, 90)
s1.show()
```

✅ **Output:**

```
Name: Alice, Age: 20
Marks: 90
```

🧠 `super()` ensures that the parent’s constructor and methods are used properly inside the child class.

---

## 🧩 **4️⃣ Types of Inheritance in Python**

Python supports several forms of inheritance:

| **Type**                     | **Description**                      | **Diagram**           |
| ---------------------------- | ------------------------------------ | --------------------- |
| **Single Inheritance**       | One parent → one child               | A → B                 |
| **Multiple Inheritance**     | Child inherits from multiple parents | A, B → C              |
| **Multilevel Inheritance**   | Parent → Child → Grandchild          | A → B → C             |
| **Hierarchical Inheritance** | One parent → multiple children       | A → B, C              |
| **Hybrid Inheritance**       | Combination of above types           | Mix of multiple forms |

---

### 🧩 **Example 1: Single Inheritance**

```python
class A:
    def feature1(self):
        print("Feature 1 from Class A")

class B(A):
    def feature2(self):
        print("Feature 2 from Class B")

obj = B()
obj.feature1()
obj.feature2()
```

✅ **Output:**

```
Feature 1 from Class A
Feature 2 from Class B
```

---

### 🧩 **Example 2: Multilevel Inheritance**

```python
class A:
    def feature1(self):
        print("Feature 1 from A")

class B(A):
    def feature2(self):
        print("Feature 2 from B")

class C(B):
    def feature3(self):
        print("Feature 3 from C")

obj = C()
obj.feature1()
obj.feature2()
obj.feature3()
```

✅ **Output:**

```
Feature 1 from A
Feature 2 from B
Feature 3 from C
```

---

### 🧩 **Example 3: Multiple Inheritance**

```python
class Father:
    def gardening(self):
        print("I enjoy gardening.")

class Mother:
    def cooking(self):
        print("I love cooking.")

class Child(Father, Mother):
    def sports(self):
        print("I like playing football.")

obj = Child()
obj.gardening()
obj.cooking()
obj.sports()
```

✅ **Output:**

```
I enjoy gardening.
I love cooking.
I like playing football.
```

🧠 The `Child` inherits from **both** `Father` and `Mother`.

---

### 🧩 **Example 4: Hierarchical Inheritance**

```python
class Parent:
    def show(self):
        print("Parent method.")

class Child1(Parent):
    def feature1(self):
        print("Child 1 feature.")

class Child2(Parent):
    def feature2(self):
        print("Child 2 feature.")

c1 = Child1()
c2 = Child2()

c1.show()
c2.show()
```

✅ **Output:**

```
Parent method.
Parent method.
```

🧠 Both `Child1` and `Child2` share the parent’s `show()` method.

---

## ⚙️ **5️⃣ Method Overriding**

When a child class **defines a method with the same name** as a method in its parent class,
the **child’s version overrides** the parent’s version.

---

### **Example: Method Overriding**

```python
class Animal:
    def speak(self):
        print("Animals make sounds")

class Dog(Animal):
    def speak(self):
        print("Dog barks")

a1 = Dog()
a1.speak()
```

✅ **Output:**

```
Dog barks
```

🧠 The `Dog` class **overrides** the `speak()` method of the `Animal` class.

---

### 💡 **Example: Overriding with `super()`**

You can call the parent method before or after your own implementation.

```python
class Animal:
    def speak(self):
        print("Animals make sounds")

class Dog(Animal):
    def speak(self):
        super().speak()
        print("Dog barks")

d1 = Dog()
d1.speak()
```

✅ **Output:**

```
Animals make sounds
Dog barks
```

---

## 🧩 **6️⃣ Example: Constructor Overriding**

If the child class defines its own `__init__()` constructor,
it **overrides** the parent’s constructor.

---

### **Example:**

```python
class Person:
    def __init__(self):
        print("Person constructor called")

class Student(Person):
    def __init__(self):
        super().__init__()
        print("Student constructor called")

s = Student()
```

✅ **Output:**

```
Person constructor called
Student constructor called
```

🧠 Using `super()` calls the parent’s constructor as part of the initialization process.

---

## 🧠 **7️⃣ Example: Real-World Inheritance and Overriding**

```python
class Vehicle:
    def __init__(self, brand):
        self.brand = brand

    def info(self):
        print(f"Vehicle Brand: {self.brand}")

class Car(Vehicle):
    def __init__(self, brand, model):
        super().__init__(brand)
        self.model = model

    def info(self):
        print(f"Car Brand: {self.brand}, Model: {self.model}")

v1 = Vehicle("Tata")
c1 = Car("Toyota", "Corolla")

v1.info()
c1.info()
```

✅ **Output:**

```
Vehicle Brand: Tata
Car Brand: Toyota, Model: Corolla
```

🧠 The `Car` class **overrides** the parent’s `info()` method but still **inherits** structure from `Vehicle`.

---

## 🧾 **8️⃣ Summary Table**

| **Concept**                | **Description**                    | **Example / Keyword** |
| -------------------------- | ---------------------------------- | --------------------- |
| **Inheritance**            | Reusing parent class features      | `class Child(Parent)` |
| **Single Inheritance**     | One parent, one child              | `class B(A)`          |
| **Multiple Inheritance**   | Multiple parents                   | `class C(A, B)`       |
| **Multilevel Inheritance** | Chain of inheritance               | `A → B → C`           |
| **Method Overriding**      | Redefine parent method             | `def method(self):`   |
| **super()**                | Access parent’s constructor/method | `super().method()`    |
| **Constructor Overriding** | Redefine `__init__()` in subclass  | `super().__init__()`  |

---

## 💡 **9️⃣ Benefits of Inheritance**

✅ Promotes **code reusability**
✅ Reduces redundancy
✅ Easier maintenance and updates
✅ Supports **polymorphism** (same method name, different behavior)
✅ Organizes code in **hierarchical structure**

---

## 🧠 **🔟 Practice Questions**

1. Create a class `Animal` with a method `sound()`.
   Create subclasses `Dog` and `Cat` that override the method with different sounds.

2. Create a `Vehicle` class and a subclass `Car` that adds its own features and overrides a method.

3. Create a class hierarchy: `Person → Employee → Manager`,
   each with its own `display()` method (use `super()` in child classes).

4. Demonstrate **multiple inheritance** using `Father` and `Mother` classes.

5. Demonstrate **constructor overriding** using `super()` in the child class.

---

## ✅ **11️⃣ Summary**

| **Concept**                | **Explanation**                                     |
| -------------------------- | --------------------------------------------------- |
| **Inheritance**            | Child class inherits methods/attributes from parent |
| **Method Overriding**      | Child redefines parent method                       |
| **Constructor Overriding** | Child defines its own `__init__()`                  |
| **super()**                | Used to access parent methods or constructors       |
| **Types of Inheritance**   | Single, Multiple, Multilevel, Hierarchical, Hybrid  |
| **Advantage**              | Reusability, extensibility, cleaner design          |

---

### 🔎 **Example Summary Program**

```python
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

    def display(self):
        print(f"Employee Name: {self.name}, Salary: {self.salary}")

class Manager(Employee):
    def __init__(self, name, salary, department):
        super().__init__(name, salary)
        self.department = department

    def display(self):
        super().display()
        print(f"Department: {self.department}")

m1 = Manager("Alice", 80000, "HR")
m1.display()
```

✅ **Output:**

```
Employee Name: Alice, Salary: 80000
Department: HR
```

---


