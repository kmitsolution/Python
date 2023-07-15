There are many ways to read the file in python

# 1. Read file by read()
In Python, the read() method is used to read the content of a file. It allows you to read the entire content of a file or a specific number of characters from the file. The read() method returns a string containing the file's content.

Here's the syntax of the read() method:
```python
file.read(size)
```
## Parameters:

<b>size (optional):</b> The number of characters to read from the file. If size is not specified, the method reads the entire content of the file.

Now, let's see some examples of using the read() method:

### Example 1: Reading the entire content of a file:

```python
file_path = 'example.txt'
with open(file_path, 'r') as file:
    file_content = file.read()
    print(file_content)
```

In this example, the read() method is called without any argument, so it will read the entire content of the file.

### Example 2: Reading a specific number of characters from a file:

```python
file_path = 'example.txt'
with open(file_path, 'r') as file:
    # Read the first 100 characters from the file
    partial_content = file.read(100)
    print(partial_content)
```

In this example, the read(100) method reads the first 100 characters from the file.
<b>Note:</b>
Keep in mind that when you call read() without specifying the size, it reads the entire file content into memory as a string. For large files, this can consume a lot of memory. If you are dealing with very large files, consider reading the file line by line or in chunks using a loop and readline() or read(size) respectively.

# Read file by readline()
In Python, the readline() method is used to read a single line from a file. It reads characters from the file until it encounters a newline ('\n') character or reaches the end of the file. The readline() method returns the line as a string.

Here's the syntax of the readline() method:

```python
file.readline()
```

Let's see an example of how to use the readline() method:

Suppose we have a file named "example.txt" with the following content:

```
Line 1: This is the first line.
Line 2: This is the second line.
Line 3: This is the third line.
```

### Example:

```python
file_path = 'example.txt'
with open(file_path, 'r') as file:
    # Read the first line from the file
    line1 = file.readline()
    print(line1)  # Output: "Line 1: This is the first line.\n"

    # Read the next line from the file
    line2 = file.readline()
    print(line2)  # Output: "Line 2: This is the second line.\n"
```

In this example, we use the readline() method twice. The first call reads the first line from the file, and the second call reads the next line.

To read all the lines in a file, you can use a loop and keep calling readline() until it returns an empty string, indicating that there are no more lines to read.

### Example: Reading all lines from a file using a loop:

```python
file_path = 'example.txt'
with open(file_path, 'r') as file:
    while True:
        line = file.readline()
        if not line:
            break  # Reached end of file
        print(line.strip())  # Using strip() to remove the newline character
```

The strip() method is used to remove the newline character ('\n') from each line before printing. This helps in formatting the output properly.

# Read file by readlines()
In Python, the readlines() method is used to read all the lines from a file and return them as a list of strings. Each string in the list corresponds to a single line from the file, including the newline character ('\n') at the end of each line.

Here's the syntax of the readlines() method:

```python
file.readlines()
```

Let's see an example of how to use the readlines() method:

Suppose we have a file named "example.txt" with the following content:

```
Line 1: This is the first line.
Line 2: This is the second line.
Line 3: This is the third line.
```

### Example:

```python
file_path = 'example.txt'
with open(file_path, 'r') as file:
    lines = file.readlines()
    print(lines)
```

### Output:

```css
['Line 1: This is the first line.\n', 'Line 2: This is the second line.\n', 'Line 3: This is the third line.\n']
```

In this example, the readlines() method reads all the lines from the file and stores them in a list called lines. Each element of the list corresponds to one line from the file, including the newline character.

You can then process the lines in the list as needed, such as printing them, performing some operations on them, or writing them to another file.

To get rid of the newline characters from each line, you can use the strip() method on each line before processing it:

```python
file_path = 'example.txt'
with open(file_path, 'r') as file:
    lines = file.readlines()
    for line in lines:
        print(line.strip())  # Using strip() to remove the newline character
```

This will print the lines without the trailing newline character.
