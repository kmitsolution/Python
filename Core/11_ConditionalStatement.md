## Conditional Statements
Conditional statements in Python are used to make decisions and execute different blocks of code based on certain conditions. They allow you to control the flow of execution and perform actions selectively. The main conditional statements in Python are:

### If Statement
The if statement in Python is used to conditionally execute a block of code based on a specified condition. It allows you to control the flow of execution and perform actions selectively. The basic syntax of an if statement is as follows:
```python
if condition:
    # Code to execute if the condition is True
else:
    # Code to execute if the condition is False
```
```python
x = 5

if x > 0:
    print("x is positive")
else:
    print("x is not positive")
```

In the above example, if the condition x > 0 is true, the code block under the if statement is executed, which prints "x is positive." Otherwise, the code block under the else statement is executed, which prints "x is not positive."

You can also have multiple conditions using the elif (else if) clause. Here's an example:
```python
x = 5

if x > 0:
    print("x is positive")
elif x == 0:
    print("x is zero")
else:
    print("x is negative")
```

In this case, if x is greater than 0, "x is positive" is printed. If x is equal to 0, "x is zero" is printed. Otherwise, if none of the previous conditions are true, "x is negative" is printed.

You can also nest if statements within each other to handle more complex scenarios and multiple levels of conditions. The indentation is used to determine the scope of each code block.

The if statement allows you to make decisions based on specific conditions, enabling your program to perform different actions based on different situations.

### Nested If
Nested if statements in Python are used when you want to include another if statement inside the block of code executed by an outer if statement. This allows for multiple levels of conditions and more complex decision-making. Here's an example of nested if statements:

```python
x = 10
y = 5

if x > 0:
    print("x is positive")
    if y > 0:
        print("y is positive")
    else:
        print("y is not positive")
else:
    print("x is not positive")
```

In the above example, the outer if statement checks if x is greater than 0. If the condition is true, it executes the block of code indented under it, which prints "x is positive". Inside this block, there is another if statement that checks if y is greater than 0. If this nested condition is true, it executes the corresponding block of code, printing "y is positive". If the nested condition is false, it executes the else block, printing "y is not positive". If the outer if condition is false, it executes the else block, printing "x is not positive".

Nested if statements allow you to handle more complex scenarios where certain conditions depend on the fulfillment of other conditions. The indentation is crucial in Python to define the scope of each code block within the nested structure.
