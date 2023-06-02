Python has several built-in primitive data types that are used to represent different kinds of values. 
## These primitive data types include:

### Numeric Types:
1. <b>int:</b> 
In Python, the int data type is used to represent integers, which are whole numbers without any decimal points. Here's an example that demonstrates the usage of the int data type

#### Integer assignment
```python
x = 5
y = -10
z = 0
```
#### Mathematical operations
```python
sum = x + y
difference = x - y
product = x * y
quotient = x / y
remainder = x % y
power = x ** 2
```
#### Output
```python
print("x =", x)              # Output: x = 5
print("y =", y)              # Output: y = -10
print("sum =", sum)          # Output: sum = -5
print("difference =", difference)    # Output: difference = 15
print("product =", product)          # Output: product = -50
print("quotient =", quotient)        # Output: quotient = -0.5
print("remainder =", remainder)      # Output: remainder = 5
print("power =", power)              # Output: power = 25
```

### float:
In Python, the float data type is used to represent floating-point numbers, which are numbers with decimal points or fractional parts. Here's an example that demonstrates the usage of the float data type:

#### Float assignment
```python
x = 3.14
y = -2.5
z = 0.0
```
#### Mathematical operations
```python
sum = x + y
difference = x - y
product = x * y
quotient = x / y
power = x ** 2
```
#### Output
```python
print("x =", x)              # Output: x = 3.14
print("y =", y)              # Output: y = -2.5
print("sum =", sum)          # Output: sum = 0.64
print("difference =", difference)    # Output: difference = 5.64
print("product =", product)          # Output: product = -7.85
print("quotient =", quotient)        # Output: quotient = -1.256
print("power =", power)              # Output: power = 9.8596
```
In this example, we declare three variables x, y, and z and assign them floating-point values. We then perform various mathematical operations using these variables, such as addition, subtraction, multiplication, division, and exponentiation.

The <b>float</b> data type supports all basic arithmetic operations, just like the int data type. However, due to the nature of floating-point representation in computers, there may be some precision limitations and potential rounding errors when performing calculations with float values.

You can also use the <b>float</b> data type in conjunction with other data types, such as storing floating-point numbers in lists, dictionaries, or other data structures.

It's worth noting that Python also provides a decimal module for precise decimal arithmetic, which can be used when exact decimal calculations are required and to mitigate the precision issues associated with float numbers.
5. <b>complex:</b> Represents complex numbers in the form a + bj, where a and b are real numbers and j represents the imaginary unit.

### Boolean Type:
<b>bool:</b> Represents Boolean values that can be either True or False. Boolean values are used in logical operations and conditional statements.

### Text Type:

str: Represents strings of characters, such as "Hello, World!". Strings are used to store and manipulate textual data.
Sequence Types:

list: Represents ordered, mutable collections of elements. Lists can contain elements of different types and can be modified after creation.
tuple: Represents ordered, immutable collections of elements. Tuples are similar to lists but cannot be modified after creation.
range: Represents a sequence of numbers and is commonly used in loops and iterations.
Mapping Type:

dict: Represents key-value pairs, also known as dictionaries or associative arrays. Dictionaries are unordered collections of elements, where each element is identified by a unique key.
Set Types:

set: Represents unordered collections of unique elements. Sets are useful for performing mathematical operations like union, intersection, and difference.
frozenset: Represents an immutable version of a set. Once created, a frozenset cannot be modified.
None Type:

None: Represents a special value indicating the absence of a value. It is commonly used to denote the absence of a return value or to initialize variables.
These primitive data types provide the foundation for representing and manipulating different types of data in Python. Depending on the requirements of your program, you can choose the appropriate data type to store and process your data effectively.

