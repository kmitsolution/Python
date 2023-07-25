# Dictionary comprehension
Dictionary comprehension is similar to list comprehension, but instead of creating a new list, it creates a new dictionary. It allows you to generate dictionaries in a concise and readable way based on an iterable. The syntax for dictionary comprehension is surrounded by curly braces {} and consists of key-value pairs separated by colons.

Here's the general syntax for a dictionary comprehension:

```python
{key_expression: value_expression for item in iterable if condition}
```

Let's look at some examples of dictionary comprehension:

## Squares of numbers as key-value pairs:
```python
numbers = [1, 2, 3, 4, 5]
squares_dict = {num: num ** 2 for num in numbers}
print(squares_dict)  # Output: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```
## Mapping names to their lengths:
```python
names = ['Alice', 'Bob', 'Charlie', 'David']
name_lengths = {name: len(name) for name in names}
print(name_lengths)  # Output: {'Alice': 5, 'Bob': 3, 'Charlie': 7, 'David': 5}
```
## Converting a list to a dictionary with a custom value:
```python
fruits = ['apple', 'banana', 'orange']
default_stock = 10
fruit_stock = {fruit: default_stock for fruit in fruits}
print(fruit_stock)  # Output: {'apple': 10, 'banana': 10, 'orange': 10}
```
## Filtering items based on a condition:
```python
numbers = [1, 2, 3, 4, 5, 6]
even_squares = {num: num ** 2 for num in numbers if num % 2 == 0}
print(even_squares)  # Output: {2: 4, 4: 16, 6: 36}
```
## Creating a dictionary from a list of tuples:
```python
data = [('a', 1), ('b', 2), ('c', 3)]
dict_from_tuples = {key: value for key, value in data}
print(dict_from_tuples)  # Output: {'a': 1, 'b': 2, 'c': 3}
```

Remember that the key_expression should be unique for each item in the iterable; otherwise, you may overwrite values. Also, you can include an optional if condition to filter the items before adding them to the dictionary. Dictionary comprehension is a powerful tool to create dictionaries efficiently, especially when the logic for generating key-value pairs can be expressed concisely in a single line.
