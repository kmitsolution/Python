# Scatter plot
Creating a scatter plot in matplotlib is a straightforward process. A scatter plot is used to visualize the relationship between two variables, displaying individual data points as dots on a 2D plane. Each dot represents a data point with its x and y coordinates corresponding to the values of the two variables being compared.

Here's an example of creating a scatter plot using matplotlib:

```python

import matplotlib.pyplot as plt

# Sample data
x_values = [1, 2, 3, 4, 5]
y_values = [2, 4, 1, 5, 3]

# Create a scatter plot
plt.scatter(x_values, y_values)

# Add labels and a title
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Scatter Plot Example')

# Show the plot
plt.show()
```

In this example, we use the plt.scatter function to create a scatter plot with x_values on the x-axis and y_values on the y-axis. Each data point in the scatter plot represents a pair of corresponding values from x_values and y_values.

You can further customize the scatter plot by using various optional parameters in plt.scatter. For example, you can adjust the size and color of the markers, add labels, set axis limits, and more. Here's an example with additional customization:

```python
import matplotlib.pyplot as plt

# Sample data
x_values = [1, 2, 3, 4, 5]
y_values = [2, 4, 1, 5, 3]

# Create a scatter plot with red squares as markers
plt.scatter(x_values, y_values, marker='s', color='red', s=100, label='Data Points')

# Add labels and a title
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Customized Scatter Plot')

# Add a legend to show the label of the data points
plt.legend()

# Set the x and y axis limits
plt.xlim(0, 6)
plt.ylim(0, 6)

# Show the plot
plt.show()
```

In this example, we customized the scatter plot by specifying red squares ('s') as markers with a size of 100. We also added a legend to show the label of the data points and set the x and y axis limits to better fit the data.

The matplotlib library provides a wide range of customization options for scatter plots, allowing you to create visually appealing and informative visualizations. You can find more information and examples in the official matplotlib documentation: https://matplotlib.org/stable/contents.html
