# Class Methods and its types
In Python, methods are functions defined within a class that define the behavior of objects (instances) created from that class. They can access the attributes of the class and work with them. Python supports different types of methods:

## Instance Methods:
1. Instance methods are the most common type of methods in Python classes.
2. They take the instance (self) as the first parameter and can access and modify instance attributes.
3. They are used to perform actions specific to individual objects.
4. Instance methods are defined without any special decorators.
```python
class MyClass:
    def __init__(self, value):
        self.value = value

    def instance_method(self):
        return f"Value: {self.value}"
```
## Class Methods:
1. Class methods are bound to the class itself rather than an instance.
2. They take the class (cls) as the first parameter and can access and modify class attributes.
3. They are used when the method needs to work with or modify class-level data that is shared among all instances.
4. Class methods are defined using the @classmethod decorator.
```python
class MyClass:
    class_attr = 0

    def __init__(self, value):
        self.value = value

    @classmethod
    def class_method(cls):
        cls.class_attr += 1
        return cls.class_attr
```

## Static Methods:
1. Static methods are not bound to either the class or the instance.
2. They don't have access to instance or class attributes, and they behave like regular functions.
3. They are mainly used for utility functions that are related to the class but don't require access to class-specific data.
4. Static methods are defined using the @staticmethod decorator.
```python
class MathOperations:
    @staticmethod
    def add(a, b):
        return a + b

    @staticmethod
    def multiply(a, b):
        return a * b
```

To call these methods, you need to create objects of the respective classes. For instance methods, you call the method on the instance of the class:

```python

obj = MyClass(42)
print(obj.instance_method())  # Output: "Value: 42"
```

For class methods, you can call the method on the class itself:

```python
print(MyClass.class_method())  # Output: 1
print(MyClass.class_method())  # Output: 2 (class_attr was modified)
```

For static methods, you can call them directly on the class without creating an instance:

```python
print(MathOperations.add(5, 3))  # Output: 8
print(MathOperations.multiply(2, 4))  # Output: 8
```

These are the three main types of methods in Python classes. Understanding when to use each type is essential for designing efficient and maintainable class structures.
