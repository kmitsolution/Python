# 📝 **Reading and Writing Text Files in Python**

File handling becomes truly useful when you can **store information** and **retrieve it later** — like saving user data, logs, or reports.
Python makes this process simple using built-in functions for **reading** and **writing** text files.

---

## 🧠 **1️⃣ Understanding Text Files**

A **text file** is a file that contains characters readable by humans — for example:

```
Hello, this is a text file.
It contains multiple lines of text.
```

Common extensions: `.txt`, `.csv`, `.log`, `.py`, etc.

---

## 📂 **2️⃣ Writing to a Text File**

To write to a file, open it in one of the following modes:

* `'w'` → write mode (creates or overwrites)
* `'a'` → append mode (adds to existing content)

---

### **Example 1: Writing to a New File**

```python
file = open("notes.txt", "w")   # open file in write mode
file.write("Hello, this is my first file.\n")
file.write("Python makes file handling easy!")
file.close()
print("Data written successfully.")
```

✅ **Output:**
A file named `notes.txt` will be created with the following content:

```
Hello, this is my first file.
Python makes file handling easy!
```

---

### **Example 2: Appending to an Existing File**

```python
file = open("notes.txt", "a")   # open file in append mode
file.write("\nThis line is added later.")
file.close()
print("Data appended successfully.")
```

✅ Appends a new line without deleting existing content.

---

### **Example 3: Writing Using the `with` Statement**

```python
with open("diary.txt", "w") as f:
    f.write("Day 1: Started learning Python.\n")
    f.write("Day 2: Learned about file handling.")
```

✅ Automatically closes the file after writing.

---

## 📖 **3️⃣ Reading from a Text File**

To read data, open the file in `'r'` mode (read mode).

---

### **Method 1: `read()` → Read Entire File**

```python
file = open("notes.txt", "r")
content = file.read()
print(content)
file.close()
```

✅ Reads the **entire file content** as a single string.

---

### **Method 2: `readline()` → Read One Line at a Time**

```python
file = open("notes.txt", "r")
line1 = file.readline()
line2 = file.readline()
print(line1)
print(line2)
file.close()
```

✅ Reads **one line per call**.

---

### **Method 3: `readlines()` → Read All Lines into a List**

```python
file = open("notes.txt", "r")
lines = file.readlines()
print(lines)
file.close()
```

✅ Each line becomes an **element of a list**, including the newline characters (`\n`).

---

### **Method 4: Using a Loop to Read Line by Line**

```python
with open("notes.txt", "r") as f:
    for line in f:
        print(line.strip())
```

✅ Automatically closes the file and **removes extra newlines** with `strip()`.

---

## ⚙️ **4️⃣ Example: Writing and Reading Together**

```python
# Writing
with open("example.txt", "w") as file:
    file.write("Line 1: Python is great!\n")
    file.write("Line 2: File handling is simple.\n")

# Reading
with open("example.txt", "r") as file:
    data = file.read()
    print("File Content:\n", data)
```

✅ Output:

```
File Content:
 Line 1: Python is great!
 Line 2: File handling is simple.
```

---

## ✏️ **5️⃣ Writing Multiple Lines at Once**

You can use `writelines()` to write a list of strings to a file.

```python
lines = ["First line\n", "Second line\n", "Third line\n"]
with open("lines.txt", "w") as file:
    file.writelines(lines)
```

✅ Writes all items in the list to the file.

---

## 🔍 **6️⃣ Reading Large Files (Best Practice)**

When working with **large text files**, reading line by line is more efficient.

```python
with open("largefile.txt", "r") as file:
    for line in file:
        print(line.strip())
```

✅ Saves memory by reading one line at a time.

---

## ⚠️ **7️⃣ Handling File Errors**

If you try to read a non-existent file, Python raises an error.

```python
try:
    with open("nofile.txt", "r") as f:
        print(f.read())
except FileNotFoundError:
    print("File does not exist.")
```

✅ Output:

```
File does not exist.
```

---

## 🧩 **8️⃣ Useful Summary Table**

| **Operation**        | **Function / Mode**    | **Description**           |
| -------------------- | ---------------------- | ------------------------- |
| Open a file          | `open(filename, mode)` | Opens file in given mode  |
| Read file            | `file.read()`          | Reads entire content      |
| Read one line        | `file.readline()`      | Reads one line at a time  |
| Read all lines       | `file.readlines()`     | Returns list of all lines |
| Write to file        | `file.write()`         | Writes string to file     |
| Write multiple lines | `file.writelines()`    | Writes list of strings    |
| Append data          | Open in `'a'` mode     | Adds new content to end   |
| Close file           | `file.close()`         | Closes the file           |
| Use with block       | `with open() as f:`    | Auto-closes file          |

---

## 🧠 **9️⃣ Practice Questions**

1. Write a program to:

   * Create a new text file `student.txt`.
   * Write 3 student names into it (one per line).

2. Write a program to:

   * Read `student.txt` and print all lines on the screen.

3. Write a program that:

   * Appends a new name to `student.txt` using append mode.

4. Write a program that:

   * Reads a text file line by line and counts the number of lines.

5. Modify your program to handle the case when the file doesn’t exist using `try-except`.

---

## ✅ **Summary**

| **Concept**                           | **Purpose**                      |
| ------------------------------------- | -------------------------------- |
| `'w'` mode                            | Write (overwrites existing file) |
| `'a'` mode                            | Append (adds to existing file)   |
| `'r'` mode                            | Read (opens existing file)       |
| `read()`, `readline()`, `readlines()` | Reading options                  |
| `with open(...) as f:`                | Safely open and close files      |

---

