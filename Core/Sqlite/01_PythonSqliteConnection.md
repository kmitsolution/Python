# Sqlite3 connection with Python
To establish a SQLite database connection with Python, you'll need to use the sqlite3 module, which comes built-in with Python. SQLite is a lightweight, serverless database engine that stores data in a single file, making it a popular choice for smaller projects or applications that do not require a full-fledged database server.

Here's a step-by-step guide to connecting to an SQLite database using Python:

### Import the sqlite3 module:
```python
import sqlite3
```
### Connect to the database:

To connect to an existing database or create a new one, you can use the connect() function from the sqlite3 module. If the database file does not exist, connect() will create a new file with the specified name.

```python
# Connecting to an existing database or creating a new one if it doesn't exist
connection = sqlite3.connect("example.db")
```
### Create a cursor object:

After establishing the connection, you need to create a cursor object. The cursor is used to execute SQL commands and fetch data from the database.

```python

cursor = connection.cursor()
```
### Execute SQL commands:

You can execute SQL commands using the execute() method of the cursor object. For example, to create a table, you can execute a CREATE TABLE command:

```python
create_table_query = """
CREATE TABLE IF NOT EXISTS users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER
);
"""

cursor.execute(create_table_query)
```
### Commit changes and close the connection:

After executing the SQL commands, make sure to commit any changes made to the database using the commit() method of the connection object. Also, close the connection when you're done with it.

```python
connection.commit()
connection.close()
```

Putting it all together, here's a complete example:

```python
import sqlite3

# Connect to the database or create a new one if it doesn't exist
connection = sqlite3.connect("example.db")

# Create a cursor object
cursor = connection.cursor()

# Execute SQL commands
create_table_query = """
CREATE TABLE IF NOT EXISTS users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER
);
"""

cursor.execute(create_table_query)

# Commit changes and close the connection
connection.commit()
connection.close()
```

In this example, we've created a table named "users" with three columns: "id," "name," and "age." You can now use the same connection and cursor objects to perform various SQL operations, such as inserting data, querying data, updating records, and more.


### To create an SQLite database and a table, and then insert data into that table using Python, you can follow these steps:

1. Import the sqlite3 module.
2. Connect to the SQLite database or create a new one if it doesn't exist.
3. Create a cursor object.
4. Execute SQL commands to create the table.
5. Insert data into the table using the INSERT INTO statement.
6. Commit the changes to the database.
7. Close the database connection.

Here's a step-by-step example:

```python
import sqlite3

# Step 1: Connect to the database or create a new one if it doesn't exist
connection = sqlite3.connect("example.db")

# Step 2: Create a cursor object
cursor = connection.cursor()

# Step 3: Execute SQL commands to create the table
create_table_query = """
CREATE TABLE IF NOT EXISTS users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER
);
"""

cursor.execute(create_table_query)

# Step 4: Insert data into the table using the INSERT INTO statement
insert_data_query = """
INSERT INTO users (name, age) VALUES (?, ?);
"""

# Sample data to be inserted
data_to_insert = [
    ("John Doe", 25),
    ("Jane Smith", 30),
    ("Michael Johnson", 22)
]

# Execute the query for each data entry
cursor.executemany(insert_data_query, data_to_insert)

# Step 5: Commit the changes to the database
connection.commit()

# Step 6: Close the database connection
connection.close()
```

In this example, we first created a table named "users" with columns "id," "name," and "age." Then, we inserted three records (rows) of data into the "users" table using the executemany() method to insert multiple data entries at once.

Remember to modify the create_table_query, insert_data_query, and data_to_insert based on your specific requirements and the structure of your table. After running this script, you will have an SQLite database file named "example.db" with the "users" table populated with the provided data.
