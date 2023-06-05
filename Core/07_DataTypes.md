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

### complex:
In Python, the <b>complex</b> data type is used to represent complex numbers. A <b>complex number</b> is a number of the form a + bj, where a and b are real numbers, and j represents the imaginary unit. Here's an example that demonstrates the usage of the complex data type:

#### Complex number assignment
```python
z1 = 3 + 2j
z2 = -1 + 4j
```

#### Mathematical operations
```python
sum = z1 + z2
difference = z1 - z2
product = z1 * z2
quotient = z1 / z2
conjugate = z1.conjugate()
```
#### Output
```python
print("z1 =", z1)                      # Output: z1 = (3+2j)
print("z2 =", z2)                      # Output: z2 = (-1+4j)
print("sum =", sum)                    # Output: sum = (2+6j)
print("difference =", difference)        # Output: difference = (4-2j)
print("product =", product)              # Output: product = (-11+2j)
print("quotient =", quotient)            # Output: quotient = (-0.2-0.6j)
print("conjugate of z1 =", conjugate)    # Output: conjugate of z1 = (3-2j)
```

In this example, we assign two complex numbers <b>z1</b> and <b>z2</b> using the <b>complex</b> data type. We then perform various mathematical operations with these complex numbers, such as addition, subtraction, multiplication, division, and conjugation.

The <b>complex</b> data type supports all basic arithmetic operations, including addition (+), subtraction (-), multiplication (*), and division (/), just like other numeric types. The conjugate of a complex number can be obtained using the <b>conjugate()</b> method.

Complex numbers are commonly used in mathematical calculations and scientific applications that involve imaginary numbers and complex algebra.

It's important to note that Python uses <b>j</b> to represent the imaginary unit, whereas some other programming languages use <b>i</b>.
### Boolean Type:

In Python, the <b>bool</b> data type is used to represent Boolean values, which can have two possible states: <b>True</b> or <b>False</b>. Booleans are often used in conditional statements, logical operations, and control flow. Here are some examples that demonstrate the usage of the <b>bool</b> data type:
#### Boolean assignment
```python
is_valid = True
is_ready = False
```

#### Conditional statements
```python
if is_valid:
    print("Data is valid")   # Output: Data is valid

if not is_ready:
    print("System not ready")   # Output: System not ready
```
#### Logical operations
```python
result1 = True and False
result2 = True or False
result3 = not True

print("result1 =", result1)    # Output: result1 = False
print("result2 =", result2)    # Output: result2 = True
print("result3 =", result3)    # Output: result3 = False

```
In this example, we declare two <b>Boolean</b> variables <b>is_valid</b> and <b>is_ready</b> and assign them the Boolean values True and False, respectively.

We then use these Boolean values in conditional statements. The first if statement checks if is_valid is True and prints "Data is valid" if it is true. The second if statement uses the not operator to check if is_ready is False and prints "System not ready" if it evaluates to true.

We also perform logical operations using the Boolean values. The and operator returns <b>True</b> if both operands are <b>True</b> and <b>False</b> otherwise. The or operator returns True if at least one of the operands is True. The not operator returns the opposite Boolean value.

<b>Boolean</b> values are the result of logical expressions and are often used to control the flow of a program based on certain conditions. They play a crucial role in decision-making and allow programs to execute different branches of code depending on whether certain conditions are <b>true or false.</b>
### Text Type:
In Python, there are several data types for representing text or string data. The main text data types in Python are str,bytes,bytearray,memoryview:

#### str:
Represents strings of characters, such as "Hello, World!". Strings are used to store and manipulate textual data. Below are some examples of string data type

##### Creating a string variable
```python
my_string = 'Hello, world!'

# Printing the string
print(my_string)
```

##### Accessing individual characters
```python
print(my_string[0])  # Output: 'H'
print(my_string[7])  # Output: 'w'
```
##### Slicing the string
```python
print(my_string[7:12])  # Output: 'world'
```
##### Concatenating strings
```python
greeting = 'Hello'
name = 'Alice'
message = greeting + ', ' + name + '!'
print(message)  # Output: 'Hello, Alice!'
```

##### String length
```python
print(len(my_string))  # Output: 13
```

##### Changing case
```python
print(my_string.upper())  # Output: 'HELLO, WORLD!'
print(my_string.lower())  # Output: 'hello, world!'
```

##### Checking if a substring exists in a string
```python
print('world' in my_string)  # Output: True
```
##### Splitting a string into a list of words
```python
words = my_string.split()
print(words)  # Output: ['Hello,', 'world!']
```

##### Joining a list of strings into a single string
```python
new_string = ' '.join(words)
print(new_string)  # Output: 'Hello, world!'
```
#### bytes
The bytes data type represents a sequence of bytes, which is used to store binary data or text encoded in a specific character encoding. Bytes objects are immutable. You can create a bytes object by prefixing a string literal with the letter 'b'. 
##### Creating a bytes variable
```python
my_bytes = b'Hello, world!'
```
##### Printing the bytes
```python
print(my_bytes)    # output: b'Hello, world!'
```
##### Accessing individual bytes (elements)
```python
print(my_bytes[0])  # Output: 72
print(my_bytes[7])  # Output: 119
```
##### Slicing the bytes
```python
print(my_bytes[7:12])  # Output: b'world'
```
##### Converting bytes to string
```python
my_string = my_bytes.decode()
print(my_string)  # Output: 'Hello, world!'
```
##### Creating bytes from a string
```python
new_bytes = my_string.encode()
print(new_bytes)  # Output: b'Hello, world!'
```
##### Modifying bytes
```python
my_modified_bytes = bytearray(my_bytes)
my_modified_bytes[0] = 74
print(my_modified_bytes)  # Output: bytearray(b'Jello, world!')
```
##### Concatenating bytes
```python
new_bytes = my_bytes + b' Welcome!'
print(new_bytes)  # Output: b'Hello, world! Welcome!'
```
#### bytearray: 
The <b>bytearray</b> data type is similar to the bytes type, but it is mutable, meaning you can modify its content. It is often used when you need to modify the binary data. You can create a bytearray object by calling the bytearray() constructor.

##### Creating a bytearray variable
```python
my_bytearray = bytearray(b'Hello, world!')
```
##### Printing the bytearray
```python
print(my_bytearray)
```

##### Accessing individual bytes (elements)
```python
print(my_bytearray[0])  # Output: 72
print(my_bytearray[7])  # Output: 119
```

##### Slicing the bytearray
```python
print(my_bytearray[7:12])  # Output: bytearray(b'world')
```
##### Modifying the bytearray
```python
my_bytearray[0] = 74
print(my_bytearray)  # Output: bytearray(b'Jello, world!')
```

##### Appending bytes to the bytearray
```python
my_bytearray.append(33)
print(my_bytearray)  # Output: bytearray(b'Jello, world!!')
```
##### Changing the content of a slice
```python
my_bytearray[7:12] = b'Python'
print(my_bytearray)  # Output: bytearray(b'Jello, Python!!')
```
##### Converting a bytearray to bytes
```python
my_bytes = bytes(my_bytearray)
print(my_bytes)  # Output: b'Jello, Python!!'
```
#### memoryview: 
The <b>memoryview</b> data type provides a way to access the internal data of an object, such as bytes or bytearray, without making a copy of it. It allows you to manipulate the data directly. You can create a memoryview object by calling the memoryview() constructor. 

##### Creating a bytes object
```python
my_bytes = b'Hello, world!'
```
##### Creating a memoryview object
```python
my_memoryview = memoryview(my_bytes)
```
##### Accessing individual bytes using memoryview
```python
print(my_memoryview[0])  # Output: 72
print(my_memoryview[7])  # Output: 119
```
##### Slicing the memoryview
```python
print(my_memoryview[7:12])  # Output: <memory at 0x...>
```
##### Converting memoryview to bytes
```python
new_bytes = bytes(my_memoryview[7:12])
print(new_bytes)  # Output: b'world'
```
##### Modifying the memoryview
```python
my_memoryview[0] = 74
print(my_bytes)  # Output: b'Jello, world!'
```
##### Changing the content of a slice
```python
my_memoryview[7:12] = b'Python'
print(my_bytes)  # Output: b'Jello, Python!'
```
##### Obtaining the size of the memoryview
```python
print(len(my_memoryview))  # Output: 13
```
### Sequence Types:
In Python, there are several built-in sequence data types (list,tuple,range,dict,set ) that allow you to store and manipulate collections of items.
#### list
In Python, the list data type is a built-in sequence type that allows you to store and manipulate a collection of items. Lists are ordered, mutable, and can contain elements of different data types. Lists are very versatile and offer various operations like accessing elements by index, modifying elements, appending and removing elements, slicing, checking for membership, obtaining the length, and concatenating lists. The ability to modify lists in-place makes them a powerful and flexible data structure in Python. Here's an example of using the list data type in Python:
##### Creating a list
```python
my_list = [1, 2, 3, 'four', 5.5]
```
##### Accessing list elements
```python
print(my_list[0])  # Output: 1
print(my_list[3])  # Output: 'four'
```
##### Modifying list elements
```python
my_list[1] = 'two'
print(my_list)  # Output: [1, 'two', 3, 'four', 5.5]
```
##### Appending an element to the end of the list
```python
my_list.append(6)
print(my_list)  # Output: [1, 'two', 3, 'four', 5.5, 6]
```
##### Removing an element from the list
```python
my_list.remove('four')
print(my_list)  # Output: [1, 'two', 3, 5.5, 6]
```
##### Slicing a list
```python
print(my_list[1:4])  # Output: ['two', 3, 5.5]
```
##### Checking if an element exists in the list
```python
print('two' in my_list)  # Output: True
```
##### Length of the list
```python
print(len(my_list))  # Output: 5
```
##### Concatenating two lists
```python
other_list = ['seven', 8]
combined_list = my_list + other_list
print(combined_list)  # Output: [1, 'two', 3, 5.5, 6, 'seven', 8]
```

#### tuple: 
In Python, a tuple is an ordered and immutable collection of elements. Tuples are defined using parentheses () and the elements are separated by commas. Tuples are useful when you need to store a collection of related values that shouldn't be modified. They are commonly used for returning multiple values from a function, as dictionary keys (since they are immutable), and for representing fixed sets of values. While tuples are immutable, you can perform operations like accessing elements, obtaining the length, slicing, checking membership, and concatenating tuples.Here's an example of using the tuple data type in Python:
##### Creating a tuple
```python
my_tuple = (1, 2, 'three', 4.5)
```
##### Accessing tuple elements
print(my_tuple[0])  # Output: 1
print(my_tuple[2])  # Output: 'three'

##### Tuples are immutable, so you cannot modify their elements
```python
# Uncommenting the following line will raise a TypeError
# my_tuple[0] = 5
```
##### Length of the tuple
```python
print(len(my_tuple))  # Output: 4
```
##### Slicing a tuple
```python
print(my_tuple[1:3])  # Output: (2, 'three')
```
##### Checking if an element exists in the tuple
```python
print('three' in my_tuple)  # Output: True
```
##### Concatenating tuples
```python
other_tuple = ('four', 5.5)
combined_tuple = my_tuple + other_tuple
print(combined_tuple)  # Output: (1, 2, 'three', 4.5, 'four', 5.5)
```

#### range
In Python, the range type represents an immutable sequence of numbers. It is often used for iterating over a sequence of numbers in a loop or generating a sequence of integers. The range() function is used to create a range object. Here's an example of using the range type in Python:

##### Creating a range object
```python
my_range = range(1, 5)  # Represents the numbers 1, 2, 3, 4
```
##### Accessing range elements
```python
print(my_range[0])  # Output: 1
print(my_range[2])  # Output: 3
```

##### Length of the range
```python
print(len(my_range))  # Output: 4
```

##### Iterating over the range
```python
for num in my_range:
    print(num)  # Output: 1, 2, 3, 4
```
##### Checking if a number exists in the range
```python
print(3 in my_range)  # Output: True
```
##### Converting range to a list
```python
my_list = list(my_range)
print(my_list)  # Output: [1, 2, 3, 4]
```
##### Creating a range with a step
```python
my_range_with_step = range(1, 10, 2)  # Represents the numbers 1, 3, 5, 7, 9
print(list(my_range_with_step))  # Output: [1, 3, 5, 7, 9]
```

range: Represents a sequence of numbers and is commonly used in loops and iterations.
Mapping Type:

dict: Represents key-value pairs, also known as dictionaries or associative arrays. Dictionaries are unordered collections of elements, where each element is identified by a unique key.
Set Types:

set: Represents unordered collections of unique elements. Sets are useful for performing mathematical operations like union, intersection, and difference.
frozenset: Represents an immutable version of a set. Once created, a frozenset cannot be modified.
None Type:

None: Represents a special value indicating the absence of a value. It is commonly used to denote the absence of a return value or to initialize variables.
These primitive data types provide the foundation for representing and manipulating different types of data in Python. Depending on the requirements of your program, you can choose the appropriate data type to store and process your data effectively.

