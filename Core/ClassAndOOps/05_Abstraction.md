# Abstraction in Class
Abstraction is one of the key concepts of object-oriented programming (OOP) and is implemented in Python classes. It allows you to hide the implementation details of a class and expose only the relevant features or functionalities to the outside world. Abstraction provides a simplified interface to interact with the class, making it easier to use and understand.

In Python, abstraction is achieved by defining abstract methods and abstract classes using the abc (Abstract Base Classes) module. The abc module provides the ABC class, which serves as a metaclass for creating abstract classes and methods.

Here's how abstraction works in Python:

## Abstract Classes:
1. An abstract class is a class that cannot be instantiated directly. It serves as a blueprint for other classes and provides a set of common attributes and methods.
2. You can define an abstract class using the ABC metaclass and decorate abstract methods with the @abstractmethod decorator.
```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

    @abstractmethod
    def perimeter(self):
        pass
```
## Concrete Classes:
1. A concrete class is a subclass of an abstract class that provides implementations for all the abstract methods in the parent class.
2. A concrete class can be instantiated and used as usual.
```python
class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

    def perimeter(self):
        return 2 * (self.width + self.height)
```
## Abstraction in Action:
With abstraction, users of the Shape class don't need to know the specific implementations of area() and perimeter(). They only need to know that Shape provides these methods.
```python
# Cannot create an instance of the abstract class directly
# shape = Shape()  # Raises TypeError

# Instantiate the concrete class
rectangle = Rectangle(5, 3)

# Call the abstract methods without knowing their implementation details
print(rectangle.area())       # Output: 15
print(rectangle.perimeter())  # Output: 16

```
Using abstraction in Python classes allows you to define common interfaces for related classes while hiding the internal implementation. This enhances code reusability, maintainability, and readability by promoting a clear separation between the interface and the implementation of the classes.
