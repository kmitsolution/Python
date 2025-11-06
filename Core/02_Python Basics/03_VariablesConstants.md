## 🧮 **Variables and Constants in Python**

---

### **What Are Variables?**

A **variable** is a **named location in memory** used to store data that can change during program execution.
It acts as a **container** for values.

Example:

```python
name = "Alice"
age = 25
```

Here:

* `name` → variable storing a string `"Alice"`
* `age` → variable storing an integer `25`

---

### **How Variables Work**

When you assign a value to a variable, Python automatically:

1. Creates a **reference** to that value in memory.
2. Associates it with the variable name.

Example:

```python
x = 10
y = x
print(y)
```

Output:

```
10
```

Both `x` and `y` now reference the same integer value.

---

### **Variable Declaration and Initialization**

Unlike many other languages, **Python doesn’t require explicit declaration** of variables.
You create them when you assign a value.

Example:

```python
message = "Hello, World!"  # declared and initialized
```

> 💡 Python automatically determines the data type from the value assigned.

---

### **Changing the Value of a Variable**

You can reassign new values to the same variable name:

```python
x = 10
x = "Ten"
print(x)
```

Output:

```
Ten
```

> 🧠 Python allows **dynamic typing**, meaning the same variable can hold values of different data types at different times.

---

### **Multiple Assignments**

You can assign multiple values in one line:

```python
a, b, c = 5, 10, 15
print(a, b, c)
```

Output:

```
5 10 15
```

You can also assign one value to multiple variables:

```python
x = y = z = 100
print(x, y, z)
```

Output:

```
100 100 100
```

---

### **Rules for Naming Variables**

✅ Follow these rules (same as identifiers):

* Must start with a **letter or underscore**
* Can contain **letters, digits, and underscores**
* **Case-sensitive**
* Cannot be a **keyword**

Example:

```python
name = "John"     # valid
_name = "Alice"   # valid
1name = "Bob"     # ❌ invalid
```

---

### **Constants in Python**

A **constant** is a value that should **not change** during program execution.
Python doesn’t have built-in constant types, but by **convention**, we use **uppercase letters** for constants.

Example:

```python
PI = 3.14159
GRAVITY = 9.8
```

> Note: Python does not enforce constants — you can still change them, but it’s **strongly discouraged**.

---

### **Example: Variables and Constants Together**

```python
# Constants
PI = 3.14159
GRAVITY = 9.8

# Variables
radius = 5
height = 10

# Calculations
volume = PI * radius ** 2 * height

print("Volume of the cylinder:", volume)
```

**Output:**

```
Volume of the cylinder: 785.3975
```

---

### **Deleting Variables**

You can delete a variable using the `del` keyword:

```python
x = 100
del x
print(x)   # ❌ This will cause an error
```

Output:

```
NameError: name 'x' is not defined
```

---

### **Type Casting Variables**

You can convert variable types using built-in functions:

```python
x = 10      # int
y = float(x)  # convert to float
z = str(x)    # convert to string
print(y, z)
```

Output:

```
10.0 10
```

---

### **Best Practices**

✅ **Use descriptive variable names**
Good: `total_marks`, `student_name`
Bad: `x`, `temp`, `data1`

✅ **Follow PEP 8 style guide**

* Variables → lowercase with underscores
* Constants → uppercase
* Avoid overwriting built-in names (`list`, `sum`, `input`, etc.)

✅ **Group related variables logically**

```python
# Example: Employee Data
emp_name = "Alice"
emp_id = 1234
emp_salary = 50000
```

---

### **Summary**

| **Concept**             | **Description**                                  | **Example**                |
| ----------------------- | ------------------------------------------------ | -------------------------- |
| **Variable**            | Named memory location to store data              | `x = 5`                    |
| **Constant**            | Fixed value that should not change               | `PI = 3.14159`             |
| **Dynamic typing**      | Variable type changes automatically              | `x = 10`, then `x = "Ten"` |
| **Multiple assignment** | Assign many values at once                       | `a, b = 1, 2`              |
| **PEP 8 naming**        | lowercase for variables, uppercase for constants | `user_age`, `PI`           |

---

### **Quick Practice**

Write a program that:

1. Defines a constant `TAX_RATE = 0.05`
2. Takes a variable `price = 100`
3. Calculates the total price including tax
4. Prints the total price


