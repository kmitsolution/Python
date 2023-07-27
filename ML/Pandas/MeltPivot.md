# melt() in Pandas
In pandas, the melt() function is used to transform (unpivot) a DataFrame from a wide format to a long format, making it easier to work with certain types of data. The melt() function essentially takes columns and converts them into rows, while keeping related information intact by creating identifier variables.

The basic syntax for using melt() is as follows:

```python
pd.melt(frame, id_vars=None, value_vars=None, var_name=None, value_name='value')
```

### Parameters:

1. <b>frame:</b> The DataFrame you want to melt.
2. <b>id_vars:</b> Columns to use as identifier variables (the columns you want to keep intact).
3. <b>value_vars:</b> Columns to unpivot (the columns you want to melt).
4. <b>var_name:</b> Name for the variable column that will be created from the column headers in the melted DataFrame (default is 'variable').
5. <b>value_name:</b> Name for the value column that will be created from the values in the melted DataFrame (default is 'value').

Let's illustrate melt() with an example:

```python
import pandas as pd

# Sample DataFrame in wide format
data = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Math': [90, 80, 95],
    'Science': [85, 70, 92],
    'History': [88, 75, 85]
})

print("Original DataFrame:")
print(data)

# Using melt to convert the DataFrame to long format
melted_data = pd.melt(data, id_vars='Name', value_vars=['Math', 'Science', 'History'], var_name='Subject', value_name='Score')

print("\nMelted DataFrame:")
print(melted_data)
```

Output:

```javascript

Original DataFrame:
       Name  Math  Science  History
0     Alice    90       85       88
1       Bob    80       70       75
2  Charlie    95       92       85

Melted DataFrame:
       Name  Subject  Score
0     Alice     Math     90
1       Bob     Math     80
2  Charlie     Math     95
3     Alice  Science     85
4       Bob  Science     70
5  Charlie  Science     92
6     Alice  History     88
7       Bob  History     75
8  Charlie  History     85

```
In this example, we have a DataFrame with student names and their scores in three subjects (Math, Science, and History). We used melt() to convert the DataFrame to a long format, where each row represents a single subject-score combination. The 'Name' column is kept as an identifier variable, while the 'Math', 'Science', and 'History' columns are melted into the 'Subject' column, and their corresponding values are moved to the 'Score' column.

## Pivot() in pandas
In pandas, the pivot() function is used to reshape data by converting unique values from one column into multiple columns. It allows you to rotate the data table to create a new representation.

The basic syntax for using pivot() is as follows:

```python
pivot_df = df.pivot(index='index_column', columns='columns_to_pivot', values='values_to_fill')
```

#### Parameters:

1. <b>index_column:</b> The column whose unique values will become the new DataFrame's index (rows).
2. <b>columns_to_pivot:</b> The column whose unique values will become new column headers in the pivoted DataFrame.
3. <b>values_to_fill:</b> The column whose values will fill the pivoted DataFrame cells.

Keep in mind that the pivot() function requires unique combinations of 'index_column' and 'columns_to_pivot'. If there are duplicates, you may need to use pivot_table() instead.

Let's illustrate pivot() with an example:

```python
import pandas as pd

# Sample DataFrame
data = pd.DataFrame({
    'Date': ['2023-07-01', '2023-07-01', '2023-07-02', '2023-07-02'],
    'Product': ['A', 'B', 'A', 'B'],
    'Sales': [100, 150, 120, 200]
})

print("Original DataFrame:")
print(data)

# Using pivot to reshape the DataFrame
pivot_data = data.pivot(index='Date', columns='Product', values='Sales')

print("\nPivoted DataFrame:")
print(pivot_data)
```

Output:

```yaml

Original DataFrame:
         Date Product  Sales
0  2023-07-01       A    100
1  2023-07-01       B    150
2  2023-07-02       A    120
3  2023-07-02       B    200

Pivoted DataFrame:
Product           A      B
Date                       
2023-07-01      100    150
2023-07-02      120    200
```

In this example, we have a DataFrame with sales data for different products on different dates. By using pivot(), we reshaped the DataFrame to have dates as rows and products as columns, with the corresponding sales values filling the cells. The 'Date' column became the index, 'Product' column became the columns, and 'Sales' column filled the DataFrame cells.

# melt() vs pivot
Let's consider a real-time example of using the melt() function in pandas to transform data related to sales transactions from wide-format to long-format.

Suppose you have a DataFrame with sales data for different products, and each column represents the sales for a specific month. You want to transform this wide-format data into a long-format where each row represents a unique sales transaction for a particular product in a specific month.

Here's how you can use melt() for this transformation:

```python

import pandas as pd

# Sample DataFrame in wide-format
data = {
    'Product': ['Product A', 'Product B'],
    'January': [100, 150],
    'February': [120, 130],
    'March': [130, 140]
}

df = pd.DataFrame(data)

# Original DataFrame (wide-format):
#      Product  January  February  March
# 0  Product A      100       120    130
# 1  Product B      150       130    140

# Using melt to transform into long-format
melted_df = pd.melt(df, id_vars='Product', var_name='Month', value_name='Sales')

# Melted DataFrame (long-format):
#      Product      Month  Sales
# 0  Product A    January    100
# 1  Product B    January    150
# 2  Product A   February    120
# 3  Product B   February    130
# 4  Product A      March    130
# 5  Product B      March    140
```

In this example, the original DataFrame has the sales data for 'Product A' and 'Product B' for three different months. After using melt(), the data is transformed into a long-format DataFrame, where each row represents a unique sales transaction for a specific product in a particular month. This long-format data is more suitable for performing various analyses, generating visualizations, and handling time-series data.

### pivot
Let's consider a real-time example of using the pivot() function in pandas to transform long-format data of sales transactions back into wide-format.

Using the long-format sales data from the previous example, we'll now use pivot() to transform it back into wide-format, with 'Product' as rows, 'Month' as columns, and 'Sales' as the values.

```python
import pandas as pd

# Sample DataFrame in long-format
data = {
    'Product': ['Product A', 'Product B', 'Product A', 'Product B', 'Product A', 'Product B'],
    'Month': ['January', 'January', 'February', 'February', 'March', 'March'],
    'Sales': [100, 150, 120, 130, 130, 140]
}

df = pd.DataFrame(data)

# Original DataFrame (long-format):
#      Product      Month  Sales
# 0  Product A    January    100
# 1  Product B    January    150
# 2  Product A   February    120
# 3  Product B   February    130
# 4  Product A      March    130
# 5  Product B      March    140

# Using pivot to transform into wide-format
pivoted_df = df.pivot(index='Product', columns='Month', values='Sales')

# Pivoted DataFrame (wide-format):
# Month        February  January  March
# Product
# Product A          120      100    130
# Product B          130      150    140
```

In this example, the original DataFrame has the sales data for 'Product A' and 'Product B' for three different months in long-format. After using pivot(), the data is transformed into a wide-format DataFrame, where each row represents a unique product, and the columns represent the sales for different months. This wide-format data is more suitable for tabular representation, data export, and further analysis.

The pivot() function allows you to reshape and transform data easily and efficiently, making it a valuable tool in data analysis and reporting.
