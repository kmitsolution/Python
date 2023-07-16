# Inheritance in Class
Inheritance is a fundamental concept in object-oriented programming (OOP) that allows a class to inherit attributes and methods from another class. The class that inherits from another class is called the derived class or subclass, while the class being inherited from is called the base class or superclass. In Python, inheritance is achieved using the following syntax:

```python
class BaseClass:
    # Base class attributes and methods
    pass

class DerivedClass(BaseClass):
    # Derived class attributes and methods
    pass
```

Here's how inheritance works in Python:

## Base Class:
The base class contains attributes and methods that are meant to be shared by multiple subclasses.
It can have both instance and class attributes, as well as instance and class methods.
```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        pass

class Bird(Animal):
    def speak(self):
        return "Chirp!"

class Dog(Animal):
    def speak(self):
        return "Woof!"
```

## Derived Class:

1. The derived class inherits attributes and methods from the base class using the BaseClass in the class declaration.
2. It can override or extend the attributes and methods inherited from the base class.

## Method Overriding:

1. Method overriding allows the derived class to provide its own implementation for a method already defined in the base class.
2. When a method with the same name is defined in the derived class, it takes precedence over the method in the base class.

## Accessing Base Class Methods:

The derived class can access the methods of the base class using the super() function.
```python

class Bird(Animal):
    def speak(self):
        return "Chirp!"

    def speak_twice(self):
        return f"{self.speak()} {self.speak()}"

class Dog(Animal):
    def speak(self):
        return "Woof!"

    def speak_loudly(self):
        return f"{super().speak()}!!!"
```
## Multiple Inheritance:
1. Python supports multiple inheritance, which allows a class to inherit from multiple base classes.
2. To achieve multiple inheritance, list the base classes separated by commas in the class declaration.
```python

class FlyingDog(Dog, Bird):
    pass

flying_dog = FlyingDog("Air Bud")
print(flying_dog.speak_twice())    # Output: "Chirp! Chirp!"
print(flying_dog.speak_loudly())   # Output: "Woof!!!"

```
In summary, inheritance in Python allows you to create hierarchies of classes, promoting code reuse, and making the code more organized and modular. It helps create specialized classes (subclasses) from more general classes (base classes) by inheriting their attributes and methods.
