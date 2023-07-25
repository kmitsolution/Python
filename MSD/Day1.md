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
create_table="""
Create table Numbers(
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
    (0,1,0),
    (1,1,0),
    (2,2,0),
    (3,6,1),
    (4,24,0),
    (5,120,1)
]
cursor.executemany(insert_data_query, data_to_insert)

insert_query="""
Insert into Numbers Values(?,?)
"""
connection.commit()
connection.close()
```
