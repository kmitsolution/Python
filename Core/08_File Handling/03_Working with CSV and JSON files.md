
# 📁 **Working with CSV and JSON Files in Python**

---

## 🧩 **1️⃣ Introduction**

* **CSV (Comma-Separated Values)** → Stores tabular data (rows and columns).
* **JSON (JavaScript Object Notation)** → Stores structured data using key–value pairs.

Both formats are **lightweight**, **human-readable**, and **easy to handle in Python**.

---

## 🧮 **2️⃣ Working with CSV Files**

### 🧠 What is a CSV File?

A **CSV (Comma-Separated Values)** file stores data in a table-like structure:

```
Name,Age,City
Alice,25,New York
Bob,30,London
Charlie,28,Paris
```

Each line = one row
Each value = one column (separated by commas)

---

### 📦 Python Module for CSV: `csv`

Python provides a built-in module named **`csv`** to handle CSV files easily.

---

### **A. Writing to a CSV File**

```python
import csv

# Data to write
data = [
    ["Name", "Age", "City"],
    ["Alice", 25, "New York"],
    ["Bob", 30, "London"],
    ["Charlie", 28, "Paris"]
]

# Writing to CSV
with open("people.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerows(data)

print("CSV file created successfully!")
```

✅ **Output (people.csv):**

```
Name,Age,City
Alice,25,New York
Bob,30,London
Charlie,28,Paris
```

---

### **B. Reading from a CSV File**

```python
import csv

with open("people.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

✅ **Output:**

```
['Name', 'Age', 'City']
['Alice', '25', 'New York']
['Bob', '30', 'London']
['Charlie', '28', 'Paris']
```

---

### **C. Writing with Dictionary (using `DictWriter`)**

```python
import csv

data = [
    {"Name": "Alice", "Age": 25, "City": "New York"},
    {"Name": "Bob", "Age": 30, "City": "London"},
    {"Name": "Charlie", "Age": 28, "City": "Paris"}
]

with open("people_dict.csv", "w", newline="") as file:
    fieldnames = ["Name", "Age", "City"]
    writer = csv.DictWriter(file, fieldnames=fieldnames)
    writer.writeheader()
    writer.writerows(data)

print("Dictionary-based CSV written successfully!")
```

---

### **D. Reading with Dictionary (using `DictReader`)**

```python
import csv

with open("people_dict.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        print(row["Name"], "is", row["Age"], "years old from", row["City"])
```

✅ **Output:**

```
Alice is 25 years old from New York
Bob is 30 years old from London
Charlie is 28 years old from Paris
```

---

### ✅ **Summary of CSV Operations**

| **Function/Method**  | **Purpose**              |
| -------------------- | ------------------------ |
| `csv.writer()`       | Create writer object     |
| `writer.writerow()`  | Write a single row       |
| `writer.writerows()` | Write multiple rows      |
| `csv.reader()`       | Read rows as lists       |
| `csv.DictWriter()`   | Write using dictionaries |
| `csv.DictReader()`   | Read into dictionaries   |

---

## 🌐 **3️⃣ Working with JSON Files**

### 🧠 What is a JSON File?

**JSON (JavaScript Object Notation)** is a lightweight data-interchange format that represents data as:

* **Objects** (dictionaries in Python)
* **Arrays** (lists in Python)

Example JSON content:

```json
{
  "name": "Alice",
  "age": 25,
  "city": "New York"
}
```

---

### 📦 Python Module for JSON: `json`

Python provides a built-in **`json`** module to convert between JSON and Python objects.

---

### **A. Writing to a JSON File**

```python
import json

data = {
    "name": "Alice",
    "age": 25,
    "city": "New York",
    "skills": ["Python", "Data Analysis"]
}

# Write JSON data to file
with open("data.json", "w") as file:
    json.dump(data, file, indent=4)

print("JSON file created successfully!")
```

✅ **Output (data.json):**

```json
{
    "name": "Alice",
    "age": 25,
    "city": "New York",
    "skills": [
        "Python",
        "Data Analysis"
    ]
}
```

---

### **B. Reading from a JSON File**

```python
import json

# Read JSON data from file
with open("data.json", "r") as file:
    data = json.load(file)

print(data)
print("Name:", data["name"])
```

✅ **Output:**

```
{'name': 'Alice', 'age': 25, 'city': 'New York', 'skills': ['Python', 'Data Analysis']}
Name: Alice
```

---

### **C. Converting Python Object → JSON String**

```python
import json

person = {"name": "Bob", "age": 30}
json_str = json.dumps(person, indent=2)
print(json_str)
```

✅ **Output:**

```json
{
  "name": "Bob",
  "age": 30
}
```

---

### **D. Converting JSON String → Python Object**

```python
import json

json_str = '{"name": "Charlie", "age": 28}'
data = json.loads(json_str)
print(data["name"])
```

✅ **Output:**

```
Charlie
```

---

### ✅ **Summary of JSON Operations**

| **Function**           | **Description**                      |
| ---------------------- | ------------------------------------ |
| `json.dump(obj, file)` | Write JSON data to a file            |
| `json.load(file)`      | Read JSON data from a file           |
| `json.dumps(obj)`      | Convert Python object to JSON string |
| `json.loads(str)`      | Convert JSON string to Python object |

---

## 💡 **4️⃣ Comparison: CSV vs JSON**

| **Feature**       | **CSV**                  | **JSON**                         |
| ----------------- | ------------------------ | -------------------------------- |
| **Structure**     | Tabular (rows & columns) | Hierarchical (key–value)         |
| **File Type**     | `.csv`                   | `.json`                          |
| **Best For**      | Simple tabular data      | Complex or nested data           |
| **Python Module** | `csv`                    | `json`                           |
| **Readable by**   | Excel, Pandas            | Web APIs, Configs, Data Exchange |

---

## 🧠 **5️⃣ Practice Questions**

1. Write a Python program to:

   * Create a CSV file `students.csv` with columns Name, Age, Marks.
   * Add at least 3 student records.

2. Write a program to:

   * Read and display all records from `students.csv`.

3. Create a JSON file `employee.json` storing:

   ```python
   {"name": "John", "id": 101, "skills": ["Python", "Flask"]}
   ```

   Then read and print its content.

4. Write a program to convert a Python dictionary into a JSON string and back into a dictionary.

5. Bonus: Create a small script that converts a **CSV file into JSON** format.

---

## ✅ **6️⃣ Summary**

| **Concept**                     | **Module**                             | **Purpose**                      |
| ------------------------------- | -------------------------------------- | -------------------------------- |
| CSV File                        | `csv`                                  | Handle tabular data              |
| JSON File                       | `json`                                 | Handle structured key-value data |
| `csv.reader()` / `csv.writer()` | Read/write CSV rows                    |                                  |
| `json.dump()` / `json.load()`   | Read/write JSON files                  |                                  |
| `json.dumps()` / `json.loads()` | Convert between string and Python data |                                  |

---

