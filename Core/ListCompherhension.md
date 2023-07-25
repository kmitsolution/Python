# List Comprehensions
List comprehensions in Python allow you to create new lists by performing transformations or filtering elements from an existing list or other iterable. Here are some advanced examples to demonstrate the versatility of list comprehensions:

### Squares of even numbers:
```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
squares_of_evens = [num ** 2 for num in numbers if num % 2 == 0]
print(squares_of_evens)  # Output: [4, 16, 36, 64, 100]
```
### Flatten a 2D list:
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flattened = [element for row in matrix for element in row]
print(flattened)  # Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### Extract initials from a list of names:
```python
names = ['John Doe', 'Jane Smith', 'Michael Johnson']
initials = [name.split()[0][0] + name.split()[1][0] for name in names]
print(initials)  # Output: ['JD', 'JS', 'MJ']
```
### Filter and modify elements:
```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
modified_numbers = [num * 2 if num % 2 == 0 else num for num in numbers]
print(modified_numbers)  # Output: [1, 4, 3, 8, 5, 12, 7, 16, 9, 20]
```

### Dictionary comprehension with filtering:
```python
names = ['John', 'Jane', 'Alice', 'Bob', 'Eve', 'Michael']
name_lengths = {name: len(name) for name in names if len(name) > 3}
print(name_lengths)  # Output: {'John': 4, 'Jane': 4, 'Alice': 5, 'Michael': 7}
```
### Nested list comprehension:
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
transposed = [[row[i] for row in matrix] for i in range(len(matrix[0]))]
print(transposed)  # Output: [[1, 4, 7], [2, 5, 8], [3, 6, 9]]
```
### Flatten and filter lists simultaneously:
```python
nested_lists = [[1, 2, 3], [4, 5], [6, 7, 8], [9]]
filtered_and_flattened = [num for sublist in nested_lists if len(sublist) > 1 for num in sublist]
print(filtered_and_flattened)  # Output: [1, 2, 3, 6, 7, 8]
```

List comprehensions are a powerful feature in Python, and they can often make your code more concise and readable. However, be cautious not to make them overly complex, as readability should always be a priority.
