
# 🧩 **Instance and Class Variables in Python**

---

## 🧠 **1️⃣ What Are Variables in a Class?**

In object-oriented programming, variables defined inside a class are called **attributes**.
There are **two main types**:

| **Type**              | **Belongs To**               | **Shared?** | **Example**                      |
| --------------------- | ---------------------------- | ----------- | -------------------------------- |
| **Instance Variable** | A specific object (instance) | ❌ No        | `self.name`, `self.age`          |
| **Class Variable**    | The entire class             | ✅ Yes       | `Car.wheels`, `Employee.company` |

---

## 🧩 **2️⃣ Instance Variables**

* Defined **inside methods**, usually inside `__init__()`.
* Prefixed with `self.`
* **Each object has its own copy** of these variables.

### **Example 1: Instance Variables**

```python
class Student:
    def __init__(self, name, marks):
        self.name = name          # instance variable
        self.marks = marks        # instance variable

s1 = Student("Alice", 90)
s2 = Student("Bob", 85)

print(s1.name, s1.marks)
print(s2.name, s2.marks)
```

✅ **Output:**

```
Alice 90
Bob 85
```

🧠 `s1` and `s2` have their **own separate copies** of `name` and `marks`.

---

## ⚙️ **3️⃣ Class Variables**

* Declared **inside the class**, but **outside any method**.
* **Shared by all objects** of that class.
* Accessed using the class name or through any object.

### **Example 2: Class Variables**

```python
class Student:
    school = "ABC Public School"     # class variable

    def __init__(self, name, marks):
        self.name = name             # instance variable
        self.marks = marks

s1 = Student("Alice", 90)
s2 = Student("Bob", 85)

print(s1.school)
print(s2.school)
print(Student.school)
```

✅ **Output:**

```
ABC Public School
ABC Public School
ABC Public School
```

🧠 Both objects share the same `school` variable.

---

## 💡 **4️⃣ Modifying Instance and Class Variables**

Let’s see what happens when we **change** them.

---

### **A. Modifying Instance Variable**

Changes affect **only that object**.

```python
class Employee:
    company = "TechCorp"   # class variable

    def __init__(self, name, salary):
        self.name = name   # instance variable
        self.salary = salary

emp1 = Employee("Alice", 50000)
emp2 = Employee("Bob", 60000)

emp1.salary = 55000  # change only emp1's salary

print(emp1.name, emp1.salary)
print(emp2.name, emp2.salary)
```

✅ **Output:**

```
Alice 55000
Bob 60000
```

---

### **B. Modifying Class Variable**

Changes affect **all objects**, because class variables are shared.

```python
class Employee:
    company = "TechCorp"

    def __init__(self, name):
        self.name = name

emp1 = Employee("Alice")
emp2 = Employee("Bob")

Employee.company = "NextGenTech"  # change class variable

print(emp1.company)
print(emp2.company)
```

✅ **Output:**

```
NextGenTech
NextGenTech
```

---

## ⚙️ **5️⃣ Accessing Class and Instance Variables**

| **Access Type**             | **Syntax**           | **Example**        |
| --------------------------- | -------------------- | ------------------ |
| Class variable (via class)  | `ClassName.variable` | `Employee.company` |
| Class variable (via object) | `object.variable`    | `emp1.company`     |
| Instance variable           | `self.variable`      | `self.name`        |

---

## 🧠 **6️⃣ Example: Mixing Class and Instance Variables**

```python
class Car:
    wheels = 4  # class variable

    def __init__(self, brand, color):
        self.brand = brand     # instance variable
        self.color = color

car1 = Car("Toyota", "Red")
car2 = Car("BMW", "Black")

print(car1.brand, car1.wheels)
print(car2.brand, car2.wheels)

Car.wheels = 6  # changing class variable affects all

print(car1.wheels)
print(car2.wheels)
```

✅ **Output:**

```
Toyota 4
BMW 4
6
6
```

🧠 Both cars now have **6 wheels**, since `wheels` is a class variable.

---

## 💡 **7️⃣ Example: Unique Instance Variables**

```python
class Dog:
    species = "Canine"  # class variable

    def __init__(self, name, age):
        self.name = name  # instance
        self.age = age    # instance

dog1 = Dog("Buddy", 3)
dog2 = Dog("Max", 5)

dog1.age = 4   # modify instance variable only for dog1

print(dog1.name, dog1.age)
print(dog2.name, dog2.age)
```

✅ **Output:**

```
Buddy 4
Max 5
```

---

## 🧩 **8️⃣ Checking Variables with `__dict__`**

Use `__dict__` to see the variables that belong to an object or a class.

```python
class Demo:
    x = 10   # class variable
    def __init__(self, y):
        self.y = y  # instance variable

obj1 = Demo(20)
print("Instance:", obj1.__dict__)
print("Class:", Demo.__dict__)
```

✅ **Output (example):**

```
Instance: {'y': 20}
Class: {'__module__': '__main__', 'x': 10, ...}
```

---

## ⚙️ **9️⃣ Example: Counting Number of Objects**

A class variable is often used to **count how many objects** have been created.

```python
class Student:
    count = 0  # class variable

    def __init__(self, name):
        self.name = name
        Student.count += 1

s1 = Student("Alice")
s2 = Student("Bob")
s3 = Student("Charlie")

print("Total Students:", Student.count)
```

✅ **Output:**

```
Total Students: 3
```

🧠 `Student.count` increments every time a new object is created.

---

## 🧾 **🔟 Summary Table**

| **Feature**              | **Instance Variable**            | **Class Variable**                      |
| ------------------------ | -------------------------------- | --------------------------------------- |
| **Defined**              | Inside `__init__()` using `self` | Inside class, outside methods           |
| **Belongs To**           | Specific object                  | Class itself                            |
| **Shared Among Objects** | ❌ No                             | ✅ Yes                                   |
| **Accessed Using**       | `self.variable`                  | `ClassName.variable` or `self.variable` |
| **Stored In**            | Object’s namespace (`__dict__`)  | Class’s namespace                       |
| **Use Case**             | Object-specific data             | Common/shared data                      |

---

## 🧠 **11️⃣ Practice Questions**

1. Create a class `Employee` with:

   * Class variable: `company_name`
   * Instance variables: `name` and `salary`
   * Method: `display()` to print employee info
     Create two employees and display their details.

2. Create a class `Car` with:

   * Class variable: `wheels = 4`
   * Instance variables: `brand`, `color`
     Print values for two objects and change `wheels` to 6.

3. Create a class `School` with:

   * Class variable: `total_students = 0`
   * Increment it in the constructor for each new student.

4. Create a class `Mobile` with:

   * Instance variable: `model`
   * Class variable: `brand = "Samsung"`
     Show that changing `brand` affects all mobiles.

5. Print the `__dict__` of both class and object to view attributes.

---

## ✅ **12️⃣ Summary**

| **Concept**              | **Meaning**                                     |
| ------------------------ | ----------------------------------------------- |
| **Instance Variable**    | Belongs to each individual object (unique data) |
| **Class Variable**       | Shared among all objects of a class             |
| **`self`**               | Used to access instance variables               |
| **`ClassName.variable`** | Used to access class variable                   |
| **`__dict__`**           | Shows attributes of object/class                |

---

### 🔎 **Example Summary Program**

```python
class Employee:
    company = "TechCorp"  # class variable

    def __init__(self, name, salary):
        self.name = name      # instance variable
        self.salary = salary

    def display(self):
        print(f"Name: {self.name}, Salary: {self.salary}, Company: {Employee.company}")

# Create objects
emp1 = Employee("Alice", 50000)
emp2 = Employee("Bob", 60000)

emp1.display()
emp2.display()

Employee.company = "NextGenTech"  # change class variable
emp1.display()
emp2.display()
```

✅ **Output:**

```
Name: Alice, Salary: 50000, Company: TechCorp
Name: Bob, Salary: 60000, Company: TechCorp
Name: Alice, Salary: 50000, Company: NextGenTech
Name: Bob, Salary: 60000, Company: NextGenTech
```

---


