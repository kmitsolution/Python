# Number division
```python
try:
    x = 1
    y = 0
    z = x / y
    print(f"z={z}")
except ZeroDivisionError:
    print("Denominator cannot be 0")
except:
    print("Opps there is an error")
```
# Sqlite create db
```python
import sqlite3

create_table = """
Create table IF NOT EXISTS Numbers(
num1 int,
fact int,
isPrime int)
"""
connection = sqlite3.connect("C:\\MSD_Python01\\example.db")
cursor = connection.cursor()
cursor.execute(create_table)
insert_data_query = """
INSERT INTO Numbers VALUES (?,?, ?);
"""
data_to_insert = [
    (0, 1, 0),
    (1, 1, 0),
    (2, 2, 0),
    (3, 6, 1),
    (4, 24, 0),
    (5, 120, 1)
]
#cursor.executemany(insert_data_query, data_to_insert)


connection.commit()
connection.close()


# factorial of a number
def fact(number):
    f = 1
    for x in range(1, number):
        f *= x
    return f
# Reading the database
connection = sqlite3.connect("C:\\MSD_Python01\\example.db")
# connection = sqlite3.connect("example.db")

# Create a cursor object
cursor = connection.cursor()

# Execute the SELECT query to retrieve data
select_query = "SELECT * FROM Numbers where num1=5;"
cursor.execute(select_query)

# Fetch one row from the result set
one_row = cursor.fetchone()
# print(one_row)
n1,f,p =one_row
print(n1,f,p)
connection.close()
```

# Operator overloading
```python
class Numbers:
    def __init__(self, num1,num2):
        self.num1=num1
        self.num2=num2
        self.result=0
    # Operator overloading
    def __add__(self, other):
         self.result= self.num1 + other.num1 + self.num2 + other.num2
         return self
    def __str__(self):
        
```
