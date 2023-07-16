# Polymorphism
Polymorphism is another important concept in object-oriented programming (OOP) that allows objects of different classes to be treated as objects of a common superclass. In Python, polymorphism is achieved through method overriding and the use of abstract classes and interfaces. Polymorphism enables code to be more flexible and generic, allowing the same code to work with different types of objects.

There are two main types of polymorphism in Python:

## Run-time Polymorphism (Method Overriding):
1. Run-time polymorphism occurs when a method in a derived class has the same name as a method in its base class, and the derived class provides its own implementation for the method.
2. The method in the derived class "overrides" the method in the base class, and the appropriate method is called at runtime based on the type of the object.
3. The super() function is often used to call the overridden method from the base class.
```python
class Animal:
    def speak(self):
        return "Animal speaks"

class Dog(Animal):
    def speak(self):
        return "Dog barks"

class Cat(Animal):
    def speak(self):
        return "Cat meows"

# Polymorphism in action
dog = Dog()
cat = Cat()

print(dog.speak())  # Output: "Dog barks"
print(cat.speak())  # Output: "Cat meows"
```
## Compile-time Polymorphism (Method Overloading):
1. Compile-time polymorphism occurs when a class has multiple methods with the same name but different parameter lists.
2. Python does not natively support method overloading based on the number or types of parameters, unlike some other programming languages like Java or C++.

However, you can achieve a form of compile-time polymorphism in Python using default arguments and variable-length arguments.
```python

class MathOperations:
    def add(self, a, b):
        return a + b

    def add(self, a, b, c):
        return a + b + c

# This will only use the second version of add() due to method overloading
math = MathOperations()
print(math.add(1, 2, 3))  # Output: 6
```

It's important to note that Python supports duck typing, which is a form of dynamic polymorphism. In duck typing, the type or class of an object is determined by its behavior or the presence of certain methods or attributes, rather than its explicit type. This allows Python code to be more flexible and less constrained by explicit type declarations.

Overall, polymorphism in Python enhances code flexibility, reusability, and extensibility by allowing objects of different classes to be treated interchangeably when they share a common interface.
