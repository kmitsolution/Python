# Analyzing data with Pandas
Analyzing data with Pandas DataFrame involves performing various operations, computations, and transformations to gain insights from the data. Here are some common tasks and methods you can use for data analysis with Pandas DataFrame:

## Exploring the Data:

1. <b>df.head()</b> and <b>df.tail()</b>: View the first or last few rows of the DataFrame.
2. <b>df.info()</b>: Get a summary of the DataFrame, including data types, column names, and non-null values.
3. <b>df.describe()</b>: Generate descriptive statistics of numerical columns, such as count, mean, min, max, etc.
4. <b>df.shape</b>: Get the dimensions of the DataFrame (number of rows and columns).
5. <b>df.columns</b>: Access the column names of the DataFrame.
6. <b>df.dtypes</b>: Retrieve the data types of each column.
7. <b>df.unique()</b>: Find the unique values in a column.

## Data Selection and Filtering:

1. <b>Indexing</b>: Use square brackets [] or the .loc[] and .iloc[] accessor to select specific rows or columns.
2. <b>Conditional Filtering:</b> Filter rows based on specific conditions using Boolean indexing.
3. <b>df.query()</b>: Perform advanced data filtering using a query-like syntax.

## Data Manipulation and Transformation:

1. <b>df.sort_values()</b>: Sort the DataFrame by one or more columns.
2. <b>df.groupby()</b>: Group the data based on one or more columns and apply aggregation functions.
3. <b>df.pivot_table()</b>: Create a pivot table from the DataFrame.
4. <b>df.apply()</b>: Apply a function to each element, row, or column of the DataFrame.
5. <b>df.merge()</b>: Merge or join multiple DataFrames based on common columns.
6. <b>df.drop()</b>: Remove rows or columns from the DataFrame.
7. <b>df.fillna()</b>: Fill missing values in the DataFrame with a specified value or method.
8. <b>df.rename()</b>: Rename columns or index labels.
9. <b>df.astype()</b>: Change the data type of one or more columns.

## Statistical Analysis and Computations:

1. <b>df.mean()</b>, <b>df.median()</b>, <b>df.min()</b>, <b>df.max()</b>: Compute the mean, median, minimum, or maximum values of each column.
2. <b>df.sum()</b>, <b>df.count()</b>, <b>df.std()</b>, <b>df.var()</b>: Calculate the sum, count, standard deviation, or variance of each column.
3. <b>df.corr()</b>, <b>df.cov()</b>: Compute the correlation or covariance matrix of the DataFrame.
4. <b>df.value_counts()</b>: Count the occurrences of unique values in a column.
5. <b>df.isnull()</b>, <b>df.notnull()</b>: Check for missing values in the DataFrame.

## Visualization:

Pandas integrates well with visualization libraries like Matplotlib and Seaborn. You can use the .plot()</b> method or functions from these libraries to create various plots and charts, such as line plots, bar plots, scatter plots, histograms, etc., directly from the DataFrame.

These are just some of the common operations for analyzing data with Pandas DataFrame. The library offers many more functions and methods to handle different scenarios and tasks. Pandas documentation provides comprehensive information and examples for each of these operations: https://pandas.pydata.org/docs/

## Examples
Here are examples of using <b>df.head()</b> and <b>df.tail()</b> to view the first and last few rows of a DataFrame:

Let's consider a sample DataFrame representing student information:

```python
import pandas as pd

data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'Age': [21, 22, 20, 19, 23],
    'Grade': [85, 90, 78, 92, 88]
}

df = pd.DataFrame(data)
```

### Example 1: Using df.head()

```python
print(df.head())


Output:

markdown
Copy code
      Name  Age  Grade
0    Alice   21     85
1      Bob   22     90
2  Charlie   20     78
3    David   19     92
4      Eve   23     88

```
The df.head() method displays the first five rows of the DataFrame by default.

### Example 2: Using df.head(n) to specify the number of rows

```python
print(df.head(3))


Output:

      Name  Age  Grade
0    Alice   21     85
1      Bob   22     90
2  Charlie   20     78
```

By passing the parameter 3 to df.head(), it displays the first three rows of the DataFrame.

### Example 3: Using df.tail()

```python
print(df.tail())


Output:

      Name  Age  Grade
0    Alice   21     85
1      Bob   22     90
2  Charlie   20     78
3    David   19     92
4      Eve   23     88

```
The df.tail() method displays the last five rows of the DataFrame by default.

### Example 4: Using df.tail(n) to specify the number of rows

```python

print(df.tail(2))


Output:

    Name  Age  Grade
3  David   19     92
4    Eve   23     88
```

By passing the parameter 2 to df.tail(), it displays the last two rows of the DataFrame.

These examples illustrate how df.head() and df.tail() can be used to quickly inspect the beginning and end of a DataFrame, which can be helpful for understanding the structure and content of the data.
