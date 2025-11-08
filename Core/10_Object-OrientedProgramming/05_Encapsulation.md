# 🧩 **Encapsulation in Python**

---

## 🧠 **1️⃣ What is Encapsulation?**

**Encapsulation** means **wrapping data (variables)** and **methods (functions)** into a single unit — the **class**.

It allows you to:

* **Hide sensitive data**
* **Restrict direct access** to internal attributes
* **Control modifications** using methods

✅ **In short:**

> Encapsulation = Data protection + Controlled access

---

### 💡 **Real-life Example**

Think of a **bank account**:

* You can **deposit** or **withdraw** money using functions (methods)
* But you **cannot directly access** or modify the balance variable

That’s **encapsulation** — the internal details (balance) are hidden.

---

## ⚙️ **2️⃣ Encapsulation in Python Classes**

Python does not have strict access modifiers (like `private`, `protected`, or `public` in Java or C++).
However, it provides **naming conventions** using underscores to indicate levels of access.

| **Access Type** | **Prefix**            | **Access Level**                       |
| --------------- | --------------------- | -------------------------------------- |
| **Public**      | no underscore         | Accessible from anywhere               |
| **Protected**   | `_single_underscore`  | Accessible within class and subclasses |
| **Private**     | `__double_underscore` | Accessible only inside the class       |

---

## 🟢 **3️⃣ Public Members**

* Can be accessed **from anywhere** (inside or outside the class)
* Default in Python

### **Example:**

```python
class Student:
    def __init__(self, name, age):
        self.name = name      # public
        self.age = age        # public

s1 = Student("Alice", 20)
print(s1.name)
print(s1.age)
```

✅ **Output:**

```
Alice
20
```

🧠 `name` and `age` are public — they can be accessed and modified freely.

---

## 🟡 **4️⃣ Protected Members**

* Defined with a **single underscore (`_variable`)**
* Suggests that the variable **should not be accessed directly**, though it’s **not strictly private**
* Accessible inside the class and subclasses (inheritance)

### **Example:**

```python
class Student:
    def __init__(self, name, age):
        self._age = age   # protected variable
        self.name = name

    def show(self):
        print(f"Name: {self.name}, Age: {self._age}")

class Graduate(Student):
    def graduate_info(self):
        print(f"{self.name} is {self._age} years old and graduating.")

g1 = Graduate("Bob", 23)
g1.show()
g1.graduate_info()

# Accessing protected variable (possible, but discouraged)
print("Accessing protected:", g1._age)
```

✅ **Output:**

```
Name: Bob, Age: 23
Bob is 23 years old and graduating.
Accessing protected: 23
```

🧠 `_age` is **protected** — it *can* be accessed, but should only be used within the class hierarchy.

---

## 🔴 **5️⃣ Private Members**

* Defined with **double underscores (`__variable`)**
* Not directly accessible from **outside the class**
* Python performs **name mangling** to protect private attributes.

---

### **Example:**

```python
class BankAccount:
    def __init__(self, account_holder, balance):
        self.account_holder = account_holder
        self.__balance = balance   # private variable

    def deposit(self, amount):
        self.__balance += amount
        print(f"Deposited {amount}. New balance: {self.__balance}")

    def get_balance(self):
        return self.__balance

acc1 = BankAccount("Alice", 1000)
acc1.deposit(500)

# Access using method
print("Balance:", acc1.get_balance())

# Direct access fails
# print(acc1.__balance)  ❌ AttributeError

# But can access using name mangling (not recommended)
print("Accessing privately (hacky):", acc1._BankAccount__balance)
```

✅ **Output:**

```
Deposited 500. New balance: 1500
Balance: 1500
Accessing privately (hacky): 1500
```

🧠 The private variable `__balance` is renamed internally as `_BankAccount__balance` (name mangling).
It discourages but doesn’t totally prevent access.

---

## 💡 **6️⃣ Encapsulation with Getters and Setters**

Best practice:
Access and modify private variables using **getter** and **setter methods**.

### **Example:**

```python
class Employee:
    def __init__(self, name, salary):
        self.__salary = salary
        self.name = name

    # getter
    def get_salary(self):
        return self.__salary

    # setter
    def set_salary(self, new_salary):
        if new_salary > 0:
            self.__salary = new_salary
        else:
            print("Invalid salary!")

emp = Employee("John", 50000)

print("Initial salary:", emp.get_salary())
emp.set_salary(60000)
print("Updated salary:", emp.get_salary())
emp.set_salary(-20000)  # invalid
```

✅ **Output:**

```
Initial salary: 50000
Updated salary: 60000
Invalid salary!
```

🧠 Using getters and setters ensures **safe and controlled access** to sensitive data.

---

## 🧩 **7️⃣ Encapsulation Example (Complete Program)**

```python
class BankAccount:
    def __init__(self, holder_name, balance):
        self.holder_name = holder_name
        self.__balance = balance   # private

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            print(f"Deposited ${amount}. New balance = ${self.__balance}")
        else:
            print("Invalid deposit amount!")

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
            print(f"Withdrawn ${amount}. Remaining balance = ${self.__balance}")
        else:
            print("Invalid or insufficient balance.")

    def get_balance(self):
        return self.__balance

# Creating object
acc = BankAccount("Alice", 1000)

acc.deposit(500)
acc.withdraw(300)
print("Balance:", acc.get_balance())
```

✅ **Output:**

```
Deposited $500. New balance = $1500
Withdrawn $300. Remaining balance = $1200
Balance: 1200
```

🧠 Here, `__balance` is private, accessed only through methods — a perfect example of **encapsulation**.

---

## ⚙️ **8️⃣ Name Mangling (Private Attribute Access)**

Python automatically converts private variables into a form:
`_ClassName__variable`

### Example:

```python
class Demo:
    def __init__(self):
        self.__secret = "Hidden!"

obj = Demo()
print(obj._Demo__secret)  # accessing mangled name
```

✅ **Output:**

```
Hidden!
```

🧠 Avoid using this unless debugging — it breaks encapsulation principles.

---

## 🧾 **9️⃣ Summary Table**

| **Access Type** | **Prefix** | **Access Level**                | **Accessible Outside?**  | **Example**      |
| --------------- | ---------- | ------------------------------- | ------------------------ | ---------------- |
| **Public**      | none       | Fully accessible                | ✅ Yes                    | `self.name`      |
| **Protected**   | `_`        | Semi-private (for subclasses)   | ⚠️ Yes (not recommended) | `self._age`      |
| **Private**     | `__`       | Strictly private (name mangled) | ❌ No (directly)          | `self.__balance` |

---

## 🧠 **🔟 Benefits of Encapsulation**

✅ Protects data from accidental modification
✅ Controls access via methods (getters/setters)
✅ Increases code modularity and readability
✅ Improves security and data integrity
✅ Helps maintain consistent object states

---

## 🧠 **Practice Questions**

1. Create a class `Person` with private variable `__age`.

   * Use setter to set age (only if positive)
   * Use getter to display it.

2. Create a class `Car` with:

   * Protected variable `_speed`
   * Public method `accelerate()` to increase speed safely

3. Create a class `BankAccount` with private balance, and implement deposit, withdraw, and view balance functions.

4. Demonstrate name mangling by accessing a private variable indirectly.

5. Create a `Student` class with:

   * Private variable `__marks`
   * Setter and getter to manage marks (0–100 only).

---

## ✅ **Summary**

| **Concept**         | **Description**                                   |
| ------------------- | ------------------------------------------------- |
| **Encapsulation**   | Wrapping data and methods together inside a class |
| **Public**          | Accessible from anywhere                          |
| **Protected (`_`)** | Accessible inside class & subclass                |
| **Private (`__`)**  | Hidden (name mangled)                             |
| **Getter / Setter** | Methods for controlled access                     |
| **Name Mangling**   | Internal renaming to protect data                 |

---

### 🔎 **Example Summary Program**

```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.__marks = marks

    def get_marks(self):
        return self.__marks

    def set_marks(self, marks):
        if 0 <= marks <= 100:
            self.__marks = marks
        else:
            print("Invalid marks!")

s1 = Student("Alice", 85)
print(s1.get_marks())

s1.set_marks(95)
print(s1.get_marks())

s1.set_marks(120)  # invalid
```

✅ **Output:**

```
85
95
Invalid marks!
```

---


