---

## 💬 **Input and Output Functions in Python**

---

### **What Are Input and Output Functions?**

* **Input** → Taking data **from the user**.
* **Output** → Displaying data **to the user**.

Python provides two built-in functions for this:

* `input()` → for input
* `print()` → for output

---

### **1️⃣ The `input()` Function**

The `input()` function allows the program to accept data from the user via the keyboard.

**Syntax:**

```python
variable = input("message")
```

* Displays the **message** (prompt) to the user.
* Waits for input and stores it as a **string**.

---

### **Example: Basic Input**

```python
name = input("Enter your name: ")
print("Hello,", name)
```

**Output:**

```
Enter your name: Alice
Hello, Alice
```

> 💡 Note: `input()` **always returns a string**, even if you type a number.

---

### **Example: Numeric Input**

If you need a number, you must **convert** it using type casting:

```python
age = int(input("Enter your age: "))
print("Next year, you will be", age + 1)
```

**Output:**

```
Enter your age: 21
Next year, you will be 22
```

✅ Here, `int()` converts the string input into an integer.

---

### **Multiple Inputs in One Line**

You can take multiple inputs at once using **split()**:

```python
a, b = input("Enter two numbers separated by space: ").split()
print("You entered:", a, b)
```

**Output:**

```
Enter two numbers separated by space: 10 20
You entered: 10 20
```

> 💡 By default, `split()` separates values using **spaces**, but you can specify a custom separator:

```python
x, y = input("Enter two numbers separated by comma: ").split(',')
```

---

### **Example: Numeric Multiple Inputs**

```python
a, b = map(int, input("Enter two numbers: ").split())
print("Sum:", a + b)
```

**Output:**

```
Enter two numbers: 5 10
Sum: 15
```

✅ `map(int, …)` converts each input to integer.

---

### **2️⃣ The `print()` Function**

The `print()` function displays data on the screen.

**Syntax:**

```python
print(value1, value2, ..., sep=' ', end='\n')
```

**Parameters:**

| **Parameter**         | **Meaning**                                        |
| --------------------- | -------------------------------------------------- |
| `value1, value2, ...` | One or more values to print                        |
| `sep`                 | Separator between values (default: space `' '`)    |
| `end`                 | What to print at the end (default: newline `'\n'`) |

---

### **Example: Basic Output**

```python
print("Welcome to Python Programming!")
```

Output:

```
Welcome to Python Programming!
```

---

### **Example: Printing Multiple Values**

```python
name = "Alice"
age = 21
print("Name:", name, "Age:", age)
```

Output:

```
Name: Alice Age: 21
```

---

### **Using `sep` Parameter**

```python
print("Python", "is", "fun", sep="-")
```

Output:

```
Python-is-fun
```

---

### **Using `end` Parameter**

```python
print("Hello", end=" ")
print("World")
```

Output:

```
Hello World
```

✅ `end=" "` prevents the newline and adds a space instead.

---

### **String Formatting in Output**

You can make your output look cleaner using **string formatting**.

---

#### **1. f-strings (Python 3.6+)**

```python
name = "Alice"
age = 21
print(f"My name is {name} and I am {age} years old.")
```

Output:

```
My name is Alice and I am 21 years old.
```

---

#### **2. Using `format()` Method**

```python
name = "Bob"
marks = 85.5
print("Student: {} | Marks: {}".format(name, marks))
```

Output:

```
Student: Bob | Marks: 85.5
```

✅ You can also specify positions:

```python
print("{1} scored {0}%".format(95, "Alice"))
```

Output:

```
Alice scored 95%
```

---

#### **3. Old-style formatting (`%`)**

```python
name = "Charlie"
age = 30
print("Name: %s, Age: %d" % (name, age))
```

Output:

```
Name: Charlie, Age: 30
```

---

### **Example: Combining Input and Output**

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
print(f"Hello {name}, you are {age} years old!")
```

**Output:**

```
Enter your name: Alice
Enter your age: 21
Hello Alice, you are 21 years old!
```

---

### **Summary**

| **Function** | **Purpose**                   | **Returns**             | **Example**                    |
| ------------ | ----------------------------- | ----------------------- | ------------------------------ |
| `input()`    | Accepts user input            | Always returns a string | `name = input("Enter name: ")` |
| `print()`    | Displays output               | Prints to console       | `print("Hello")`               |
| `split()`    | Splits multiple inputs        | List of strings         | `a, b = input().split()`       |
| `map()`      | Applies function to each item | Converted values        | `map(int, input().split())`    |

---

### **Quick Practice**

Write a program that:

1. Takes the user’s name and three subject marks as input.
2. Calculates the average.
3. Prints a formatted message like:
   `"Hello Alice, your average score is 86.67"`


