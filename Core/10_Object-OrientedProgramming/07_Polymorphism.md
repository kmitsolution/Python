
# 🧩 **Polymorphism and Duck Typing in Python**

---

## 🧠 **1️⃣ What is Polymorphism?**

The word **Polymorphism** comes from Greek —
“**Poly**” = many, and “**morph**” = forms.

So, **Polymorphism** means *“many forms”*.

In programming, it allows:

> The **same function or method name** to behave **differently** based on the object that calls it.

✅ It helps achieve **code flexibility** and **reusability**.

---

## 💡 **2️⃣ Example: Polymorphism with Methods**

```python
class Dog:
    def speak(self):
        return "Woof!"

class Cat:
    def speak(self):
        return "Meow!"

# Common function that works for both
def animal_sound(animal):
    print(animal.speak())

dog = Dog()
cat = Cat()

animal_sound(dog)
animal_sound(cat)
```

✅ **Output:**

```
Woof!
Meow!
```

🧠 The same function `animal_sound()` works for **different objects**
(because both have a `speak()` method).

---

## ⚙️ **3️⃣ Polymorphism with Inheritance (Method Overriding)**

Polymorphism often happens through **method overriding** —
where a child class redefines a method from its parent.

---

### **Example:**

```python
class Shape:
    def area(self):
        print("Area not defined for generic shape.")

class Circle(Shape):
    def area(self):
        print("Area of Circle = πr²")

class Rectangle(Shape):
    def area(self):
        print("Area of Rectangle = l × b")

shapes = [Circle(), Rectangle(), Shape()]

for s in shapes:
    s.area()
```

✅ **Output:**

```
Area of Circle = πr²
Area of Rectangle = l × b
Area not defined for generic shape.
```

🧠 All objects use the **same method name (`area`)**,
but produce **different behaviors** depending on their class.

---

## 🧩 **4️⃣ Polymorphism with Built-in Functions**

Even Python’s **built-in functions** exhibit polymorphism!

### **Example:**

```python
print(len("Python"))      # works for string
print(len([1, 2, 3, 4]))  # works for list
print(len({"a": 1, "b": 2}))  # works for dictionary
```

✅ **Output:**

```
6
4
2
```

🧠 `len()` works differently for **different data types**,
but you always use it the **same way** — this is **polymorphism**.

---

## ⚙️ **5️⃣ Polymorphism with Operators (Operator Overloading)**

Even **operators** in Python are polymorphic.

### **Example:**

```python
print(10 + 5)        # addition for integers
print("Hello " + "World")  # concatenation for strings
print([1, 2] + [3, 4])     # merging for lists
```

✅ **Output:**

```
15
Hello World
[1, 2, 3, 4]
```

🧠 The `+` operator works differently depending on the data type —
that’s **operator polymorphism**.

---

## 💡 **6️⃣ Example: Polymorphism in Practice**

Let’s create a more realistic example — different payment methods in an e-commerce system.

```python
class Payment:
    def pay(self):
        raise NotImplementedError("Subclass must implement this method.")

class CreditCard(Payment):
    def pay(self):
        print("Payment done using Credit Card.")

class PayPal(Payment):
    def pay(self):
        print("Payment done using PayPal.")

class UPI(Payment):
    def pay(self):
        print("Payment done using UPI.")

# Single interface, multiple behaviors
payments = [CreditCard(), PayPal(), UPI()]

for p in payments:
    p.pay()
```

✅ **Output:**

```
Payment done using Credit Card.
Payment done using PayPal.
Payment done using UPI.
```

🧠 The `pay()` method is **polymorphic** — behaves differently for each class.

---

## 🧠 **7️⃣ Duck Typing in Python**

> 🦆 **Duck Typing** is Python’s dynamic form of polymorphism.

It comes from the saying:

> “If it looks like a duck, swims like a duck, and quacks like a duck — it’s a duck.”

In simple terms:
✅ If an object **has the required method or behavior**, Python doesn’t care about its actual type.

---

### **Example 1: Duck Typing**

```python
class Bird:
    def fly(self):
        print("Bird is flying!")

class Airplane:
    def fly(self):
        print("Airplane is flying!")

class Fish:
    def swim(self):
        print("Fish is swimming!")

def let_it_fly(entity):
    entity.fly()

bird = Bird()
plane = Airplane()

let_it_fly(bird)
let_it_fly(plane)
```

✅ **Output:**

```
Bird is flying!
Airplane is flying!
```

🧠 The function `let_it_fly()` doesn’t care if the object is a `Bird` or `Airplane` —
as long as it has a `fly()` method, it works!
That’s **Duck Typing**.

---

### **Example 2: Duck Typing with Exception Handling**

```python
class Dog:
    def speak(self):
        print("Bark!")

class Cat:
    def speak(self):
        print("Meow!")

class Car:
    def drive(self):
        print("Vroom!")

def make_sound(animal):
    try:
        animal.speak()
    except AttributeError:
        print("This object can't speak!")

dog = Dog()
cat = Cat()
car = Car()

make_sound(dog)
make_sound(cat)
make_sound(car)
```

✅ **Output:**

```
Bark!
Meow!
This object can't speak!
```

🧠 `make_sound()` checks dynamically whether an object can “speak” —
no inheritance required — purely **behavior-based** programming.

---

## 🧩 **8️⃣ Polymorphism with Abstract Base Classes (Optional)**

You can also enforce polymorphism using the **`abc`** (Abstract Base Class) module.

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Circle(Shape):
    def area(self):
        print("Area of Circle")

class Square(Shape):
    def area(self):
        print("Area of Square")

# shape = Shape() ❌ (cannot instantiate abstract class)
c = Circle()
s = Square()
c.area()
s.area()
```

✅ **Output:**

```
Area of Circle
Area of Square
```

🧠 Abstract base classes ensure all child classes **implement required methods**.

---

## ⚙️ **9️⃣ Comparison: Polymorphism vs Duck Typing**

| **Feature**               | **Polymorphism**                      | **Duck Typing**                   |
| ------------------------- | ------------------------------------- | --------------------------------- |
| **Definition**            | Same method name, different behaviors | Behavior matters, not the class   |
| **Requires Inheritance?** | ✅ Usually yes                         | ❌ No                              |
| **Binding Type**          | Static or dynamic                     | Dynamic only                      |
| **Example**               | `speak()` in `Dog` and `Cat` classes  | Any object with `.speak()` method |
| **Used For**              | Class hierarchies                     | Dynamic, flexible functions       |

---

## 🧠 **🔟 Real-World Analogy**

Think of **Polymorphism** like a “universal remote”:
The same button (method name) controls different devices (objects) in their own way.

Duck typing is like **trusting behavior**:
You don’t ask if it’s a “TV” or “Speaker”; you just say, “If it has a play button, I’ll press it!”

---

## 🧾 **11️⃣ Summary Table**

| **Concept**               | **Description**                                      | **Example**                       |
| ------------------------- | ---------------------------------------------------- | --------------------------------- |
| **Polymorphism**          | One method behaves differently for different objects | `animal.speak()`                  |
| **Method Overriding**     | Child class redefines parent method                  | `def area(self):`                 |
| **Operator Polymorphism** | Same operator works for multiple types               | `+` works for strings and numbers |
| **Duck Typing**           | Object type doesn’t matter — only behavior does      | Any object with `fly()` method    |
| **super()**               | Used to call parent method inside overriding method  | `super().area()`                  |

---

## 🧠 **12️⃣ Practice Questions**

1. Create a base class `Animal` with method `make_sound()`, and subclasses `Dog` and `Cat` that override it.
2. Create a function that accepts any object with a `move()` method — demonstrate duck typing with different classes.
3. Demonstrate polymorphism using a list of objects (e.g., `Circle`, `Square`, `Triangle`) and calling a common `area()` method.
4. Write an example of polymorphism using built-in functions like `len()` or operators like `+`.
5. Use the `abc` module to create an abstract class `Shape` and subclasses that implement `area()`.

---

## ✅ **13️⃣ Summary**

| **Concept**               | **Meaning**                                                       |
| ------------------------- | ----------------------------------------------------------------- |
| **Polymorphism**          | Same function or method behaves differently for different objects |
| **Duck Typing**           | Python’s flexible form of polymorphism based on behavior          |
| **Method Overriding**     | Redefining parent methods in child class                          |
| **Operator Polymorphism** | Same operator behaves differently for different data types        |
| **Benefit**               | Cleaner, flexible, and more reusable code                         |

---

### 🔎 **Example Summary Program**

```python
class Bird:
    def fly(self):
        print("Bird can fly!")

class Airplane:
    def fly(self):
        print("Airplane can fly!")

class Fish:
    def swim(self):
        print("Fish can swim!")

# Duck typing example
def let_it_fly(obj):
    try:
        obj.fly()
    except AttributeError:
        print("This object can't fly!")

b = Bird()
a = Airplane()
f = Fish()

let_it_fly(b)
let_it_fly(a)
let_it_fly(f)
```

✅ **Output:**

```
Bird can fly!
Airplane can fly!
This object can't fly!
```

🧠 Simple, dynamic, flexible — **that’s the beauty of polymorphism and duck typing** in Python!

---


