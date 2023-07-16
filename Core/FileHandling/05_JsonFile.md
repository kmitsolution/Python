# Reading Json Data using json module
To read a JSON file in Python, you can use the built-in json module, which provides methods to work with JSON data. Here's a step-by-step example of how to read a JSON file:

Suppose you have a JSON file named "data.json" with the following content:
```json
{
    "name": "John Doe",
    "age": 30,
    "email": "john.doe@example.com",
    "interests": ["Python", "Data Science", "Reading"]
}
```
Now, let's read the JSON data from the file:
```python

import json

file_path = 'data.json'

# Opening the JSON file and loading the data
with open(file_path, 'r') as file:
    data = json.load(file)

# Printing the loaded data
print("Name:", data['name'])
print("Age:", data['age'])
print("Email:", data['email'])
print("Interests:", data['interests'])
```

### Output:
```
vbnet
Copy code
Name: John Doe
Age: 30
Email: john.doe@example.com
Interests: ['Python', 'Data Science', 'Reading']
```

The json.load(file) method reads the JSON data from the file and parses it into a Python dictionary or list, depending on the JSON data structure. In this example, it's a dictionary.

Please ensure that the "data.json" file exists in the specified location before running the Python script.

If you have JSON data as a string (not in a file), you can use json.loads() to load the JSON data from the string:

```python
import json

json_string = '{"name": "John Doe", "age": 30, "email": "john.doe@example.com"}'
data = json.loads(json_string)

print("Name:", data['name'])
print("Age:", data['age'])
print("Email:", data['email'])
```

### Output:

```makefile
Name: John Doe
Age: 30
Email: john.doe@example.com
```

Remember that JSON keys must be enclosed in double quotes.

# Read and Write Operation for Json file
In Python, you can perform JSON read and write operations using the built-in json module. The json module provides methods to work with JSON data, making it easy to convert Python data structures to JSON and vice versa. Here's how you can perform JSON read and write operations:

JSON Read Operation:
To read JSON data from a file or a JSON-formatted string, you can use the json.load() function for files and json.loads() function for strings.

a. Reading from a JSON file:

Suppose you have a JSON file named "data.json" with the following content:

```json
{
    "name": "John Doe",
    "age": 30,
    "email": "john.doe@example.com"
}
```

### Example:

```python
import json

file_path = 'data.json'

# Opening the JSON file and loading the data
with open(file_path, 'r') as file:
    data = json.load(file)

# Printing the loaded data
print("Name:", data['name'])
print("Age:", data['age'])
print("Email:", data['email'])
```

### Output:

```makefile
Name: John Doe
Age: 30
Email: john.doe@example.com
```

## b. Reading from a JSON-formatted string:

### Example:

```python
import json

json_string = '{"name": "John Doe", "age": 30, "email": "john.doe@example.com"}'
data = json.loads(json_string)

print("Name:", data['name'])
print("Age:", data['age'])
print("Email:", data['email'])
```

### Output:

```makefile
Name: John Doe
Age: 30
Email: john.doe@example.com
```

## JSON Write Operation:
To write data to a JSON file or create a JSON-formatted string, you can use the json.dump() function for files and json.dumps() function for strings.

### a. Writing to a JSON file:

Example:

```python
import json

data = {
    "name": "Jane Smith",
    "age": 25,
    "email": "jane.smith@example.com"
}

file_path = 'output.json'

# Writing data to the JSON file
with open(file_path, 'w') as file:
    json.dump(data, file)
```
This will create a file named "output.json" with the following content:

```json
{"name": "Jane Smith", "age": 25, "email": "jane.smith@example.com"}
```

## b. Writing to a JSON-formatted string:

Example:

```python
import json

data = {
    "name": "Jane Smith",
    "age": 25,
    "email": "jane.smith@example.com"
}

json_string = json.dumps(data)
print(json_string)
```

### Output:

```perl
{"name": "Jane Smith", "age": 25, "email": "jane.smith@example.com"}
```

These are the basic JSON read and write operations in Python using the json module. The module provides additional options and parameters to handle more complex JSON data and customize the serialization and deserialization processes.
