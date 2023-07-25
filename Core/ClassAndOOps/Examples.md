# Python Class case Study
Python case study involving a class. We'll create a class to represent a Bank Account with various functionalities. This case study will cover features like account creation, deposit, withdrawal, and account information display.

```python

class BankAccount:
    def __init__(self, account_number, account_holder, balance=0):
        self.account_number = account_number
        self.account_holder = account_holder
        self.balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"Deposit of {amount} successful. Current balance: {self.balance}")
        else:
            print("Invalid amount for deposit.")

    def withdraw(self, amount):
        if amount <= self.balance and amount > 0:
            self.balance -= amount
            print(f"Withdrawal of {amount} successful. Current balance: {self.balance}")
        else:
            print("Insufficient funds or invalid amount for withdrawal.")

    def get_balance(self):
        return self.balance

    def account_info(self):
        print(f"Account Holder: {self.account_holder}")
        print(f"Account Number: {self.account_number}")
        print(f"Current Balance: {self.balance}")

# Example usage:
if __name__ == "__main__":
    # Creating a bank account
    account1 = BankAccount(account_number="123456789", account_holder="John Doe", balance=1000)

    # Depositing money
    account1.deposit(500)

    # Withdrawing money
    account1.withdraw(300)

    # Checking account balance
    balance = account1.get_balance()
    print("Current balance:", balance)

    # Displaying account information
    account1.account_info()
```

In this case study, we have created a BankAccount class with an initializer (__init__) to set the account number, account holder name, and initial balance. The class includes methods to deposit and withdraw money from the account, get the current balance, and display account information.

The example usage demonstrates how to create a bank account, perform transactions (deposit and withdrawal), check the balance, and display the account information.

Please note that this is a basic illustration to showcase class usage in a bank account scenario. In a real-world application, you would need to consider additional security measures, validation, and proper error handling to make the class more robust and secure.

# Class Case Study with Inheritance
Let's create an advanced example with inheritance, involving a base class BankAccount and two subclasses CheckingAccount and SavingsAccount. The CheckingAccount will have an additional overdraft limit, and the SavingsAccount will have an interest rate.

```python
Copy code
class BankAccount:
    def __init__(self, account_number, account_holder, balance=0):
        self.account_number = account_number
        self.account_holder = account_holder
        self.balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"Deposit of {amount} successful. Current balance: {self.balance}")
        else:
            print("Invalid amount for deposit.")

    def withdraw(self, amount):
        if amount <= self.balance and amount > 0:
            self.balance -= amount
            print(f"Withdrawal of {amount} successful. Current balance: {self.balance}")
        else:
            print("Insufficient funds or invalid amount for withdrawal.")

    def get_balance(self):
        return self.balance

    def account_info(self):
        print(f"Account Holder: {self.account_holder}")
        print(f"Account Number: {self.account_number}")
        print(f"Current Balance: {self.balance}")


class CheckingAccount(BankAccount):
    def __init__(self, account_number, account_holder, balance=0, overdraft_limit=0):
        super().__init__(account_number, account_holder, balance)
        self.overdraft_limit = overdraft_limit

    def withdraw(self, amount):
        if amount <= self.balance + self.overdraft_limit and amount > 0:
            self.balance -= amount
            print(f"Withdrawal of {amount} successful. Current balance: {self.balance}")
        else:
            print("Insufficient funds or invalid amount for withdrawal.")

    def account_info(self):
        super().account_info()
        print(f"Overdraft Limit: {self.overdraft_limit}")


class SavingsAccount(BankAccount):
    def __init__(self, account_number, account_holder, balance=0, interest_rate=0.01):
        super().__init__(account_number, account_holder, balance)
        self.interest_rate = interest_rate

    def add_interest(self):
        interest = self.balance * self.interest_rate
        self.balance += interest
        print(f"Interest added. Current balance: {self.balance}")

    def account_info(self):
        super().account_info()
        print(f"Interest Rate: {self.interest_rate}")


# Example usage:
if __name__ == "__main__":
    # Creating a checking account
    checking_account = CheckingAccount(account_number="123456789", account_holder="John Doe", balance=1000, overdraft_limit=500)

    # Creating a savings account
    savings_account = SavingsAccount(account_number="987654321", account_holder="Jane Smith", balance=2000, interest_rate=0.02)

    # Deposit and withdraw from checking account
    checking_account.deposit(500)
    checking_account.withdraw(1500)

    # Deposit and add interest to savings account
    savings_account.deposit(1000)
    savings_account.add_interest()

    # Displaying account information
    checking_account.account_info()
    savings_account.account_info()
```

In this advanced example, we have defined a BankAccount class with common functionalities. Then, we have created two subclasses, CheckingAccount and SavingsAccount, that inherit from the BankAccount class.

The CheckingAccount class overrides the withdraw method to consider the overdraft limit when performing a withdrawal. It also overrides the account_info method to display the overdraft limit.

The SavingsAccount class introduces an add_interest method to calculate and add interest to the account balance. It also overrides the account_info method to display the interest rate.

This inheritance structure allows us to reuse common functionalities from the base class while introducing specific behaviors in the subclasses. This makes the code more organized, maintainable, and follows the principle of DRY (Don't Repeat Yourself).

# Abstraction with Inheritance
Let's create an advanced example involving abstract classes and inheritance in Python. We'll define an abstract class called Shape and create two subclasses Rectangle and Circle to represent specific shapes.

```python

from abc import ABC, abstractmethod
import math

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

    @abstractmethod
    def perimeter(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

    def perimeter(self):
        return 2 * (self.width + self.height)

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return math.pi * self.radius**2

    def perimeter(self):
        return 2 * math.pi * self.radius

# Example usage:
if __name__ == "__main__":
    rect = Rectangle(width=5, height=3)
    print("Rectangle Area:", rect.area())  # Output: 15
    print("Rectangle Perimeter:", rect.perimeter())  # Output: 16

    circle = Circle(radius=2)
    print("Circle Area:", circle.area())  # Output: 12.566370614359172
    print("Circle Perimeter:", circle.perimeter())  # Output: 12.566370614359172
```

In this example, we define an abstract class Shape using the ABC (Abstract Base Class) module from the abc module. The Shape class has two abstract methods, area and perimeter, which do not have implementations. This makes the Shape class an abstract class, and objects of this class cannot be created directly.

We then create two subclasses, Rectangle and Circle, that inherit from the Shape class. These subclasses must implement the abstract methods area and perimeter defined in the Shape class.

By using abstract classes, we ensure that all shapes must have area and perimeter methods, even if they are implemented differently for different shapes. This promotes code consistency and provides a clear contract for classes that inherit from the Shape class.

The example usage demonstrates how we can create instances of the Rectangle and Circle classes, and access their respective area and perimeter methods, which are defined differently for each shape.
# Operator Overloading  Example
Let's create an advanced example involving operator overloading in a Python class. We'll create a class called Vector that represents a 2D vector and overload some common arithmetic operators for vector addition, subtraction, and scalar multiplication.

```python

class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __str__(self):
        return f"Vector({self.x}, {self.y})"

    def __add__(self, other):
        if isinstance(other, Vector):
            return Vector(self.x + other.x, self.y + other.y)
        else:
            raise TypeError("Unsupported operand type for +")

    def __sub__(self, other):
        if isinstance(other, Vector):
            return Vector(self.x - other.x, self.y - other.y)
        else:
            raise TypeError("Unsupported operand type for -")

    def __mul__(self, scalar):
        if isinstance(scalar, (int, float)):
            return Vector(self.x * scalar, self.y * scalar)
        else:
            raise TypeError("Multiplication not supported with this operand type")

    def __rmul__(self, scalar):
        return self.__mul__(scalar)

# Example usage:
if __name__ == "__main__":
    v1 = Vector(2, 3)
    v2 = Vector(1, 4)

    # Vector addition
    result_add = v1 + v2
    print("Addition:", result_add)  # Output: Vector(3, 7)

    # Vector subtraction
    result_sub = v1 - v2
    print("Subtraction:", result_sub)  # Output: Vector(1, -1)

    # Scalar multiplication
    scalar = 3
    result_mul = v1 * scalar
    print("Scalar Multiplication:", result_mul)  # Output: Vector(6, 9)

    # Reverse scalar multiplication (for commutative property)
    result_rmul = scalar * v1
    print("Reverse Scalar Multiplication:", result_rmul)  # Output: Vector(6, 9)
```

In this example, the Vector class overloads the __add__, __sub__, __mul__, and __rmul__ methods. These methods allow us to use the +, -, and * operators with Vector objects and scalar values.

The __add__ method allows us to perform vector addition between two Vector objects.

The __sub__ method allows us to perform vector subtraction between two Vector objects.

The __mul__ method allows us to perform scalar multiplication between a Vector object and a scalar (integer or float) value. The result is a new Vector object.

The __rmul__ method is necessary to support reverse scalar multiplication (scalar * vector), as Python will look for this method when the left operand doesn't have a direct implementation of the multiplication operation.

With operator overloading, we can perform arithmetic operations on instances of the Vector class just as if they were built-in types like integers or floats, making the code more intuitive and expressive.
