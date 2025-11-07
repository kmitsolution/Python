
# 📘 **File Handling in Python — Opening and Closing Files**

Working with files allows your Python programs to **store data permanently**, even after the program ends.
You can create, read, write, and modify files easily using Python’s built-in functions.

---

## 🧠 **1️⃣ What is File Handling?**

File handling means performing operations such as:

* **Creating a new file**
* **Opening an existing file**
* **Reading from the file**
* **Writing or appending data**
* **Closing the file properly**

Python provides a built-in function — `open()` — to handle files.

---

## 🪟 **2️⃣ Opening a File**

You open a file using the `open()` function.

### **Syntax:**

```python
file_object = open(filename, mode)
```

### **Parameters:**

* **`filename`** → Name of the file (string).
* **`mode`** → The mode in which you want to open the file.

---

### **File Opening Modes**

| **Mode** | **Description**                                                                 |
| -------- | ------------------------------------------------------------------------------- |
| `'r'`    | Read mode (default). Opens an existing file for reading.                        |
| `'w'`    | Write mode. Creates a new file or overwrites existing content.                  |
| `'a'`    | Append mode. Adds data to the end of the file without erasing existing content. |
| `'x'`    | Create mode. Creates a new file; raises an error if it already exists.          |
| `'r+'`   | Read and write mode. File must exist.                                           |
| `'w+'`   | Write and read mode. Overwrites file.                                           |
| `'a+'`   | Append and read mode. Adds data and allows reading.                             |
| `'b'`    | Binary mode. Use with other modes, e.g., `'rb'`, `'wb'` for non-text files.     |

---

### **Example 1: Opening a file in read mode**

```python
file = open("example.txt", "r")
print("File opened successfully!")
file.close()
```

✅ If `example.txt` exists, it opens successfully.
❌ If it does **not** exist, Python raises a `FileNotFoundError`.

---

### **Example 2: Opening a file in write mode**

```python
file = open("newfile.txt", "w")
file.write("Hello, Python learners!")
file.close()
```

✅ This will create `newfile.txt` if it doesn’t exist.
⚠️ If it already exists, it **overwrites** the content.

---

### **Example 3: Opening a file in append mode**

```python
file = open("newfile.txt", "a")
file.write("\nThis line is added using append mode.")
file.close()
```

✅ Appends data to the end of the file without deleting existing content.

---

## 🧩 **3️⃣ Closing a File**

After finishing operations, always **close** the file using:

```python
file.close()
```

Why? Because:

* It **frees up system resources**.
* It ensures that **data is written** and saved properly.

---

### **Example:**

```python
file = open("sample.txt", "w")
file.write("Python is fun!")
file.close()
print("File closed successfully!")
```

---

## 🧼 **4️⃣ Using the `with` Statement (Best Practice)**

Instead of manually closing files, use the `with` statement.
It **automatically closes** the file once the block is done — even if an error occurs.

### **Example:**

```python
with open("example.txt", "r") as file:
    data = file.read()
    print(data)
```

✅ No need to call `file.close()` explicitly — Python does it for you.

---

## 📂 **5️⃣ Checking if a File Exists**

You can check if a file exists before opening it using the `os` module.

```python
import os

if os.path.exists("example.txt"):
    print("File exists!")
else:
    print("File not found!")
```

---

## ⚙️ **6️⃣ Example Program: Creating, Writing, and Closing a File**

```python
# Create and write to a file
file = open("demo.txt", "w")
file.write("Welcome to Python file handling!\n")
file.write("This is your first file.")
file.close()

print("File created and written successfully!")
```

---

## ⚡ **7️⃣ Example Program Using `with` Statement**

```python
# Open and read file using 'with' (auto-close)
with open("demo.txt", "r") as file:
    content = file.read()
    print("File Content:\n", content)
```

---

## 💡 **8️⃣ Summary**

| **Function/Mode**          | **Purpose**                        |
| -------------------------- | ---------------------------------- |
| `open(filename, mode)`     | Opens a file in the specified mode |
| `file.write()`             | Writes data to file                |
| `file.read()`              | Reads data from file               |
| `file.close()`             | Closes the file                    |
| `'r'`, `'w'`, `'a'`, `'x'` | File access modes                  |
| `'b'`                      | Binary mode                        |
| `with open(...) as f:`     | Automatically handles file closing |

---

## 🧠 **9️⃣ Practice Questions**

1. Write a Python program to:

   * Create a new file called `mydata.txt`.
   * Write your name and age into it.
   * Close the file properly.

2. Write another program to:

   * Open `mydata.txt` and read its contents.
   * Print them on the screen.

3. Use a `with` statement to open and append new data into an existing file.

4. Try to open a non-existent file in `'r'` mode. What happens?

5. Use `os.path.exists()` to check for file existence before opening it.

---


