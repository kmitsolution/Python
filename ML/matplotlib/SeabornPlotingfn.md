# Plotting functions in Seaborn
Seaborn provides a wide range of plotting functions that make it easy to create visually appealing statistical visualizations. Here are some of the most commonly used plotting functions in Seaborn:

### Scatter Plot:
sns.scatterplot(): Creates a scatter plot to show the relationship between two variables.
It creates a scatter plot where each data point represents a pair of values from the two variables. Here's how you can do it:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5, 6, 7]
y = [2, 4, 5, 4, 5, 6, 7]

# Create a scatter plot
sns.scatterplot(x=x, y=y)

# Set plot labels and title
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Seaborn Scatter Plot Example')

# Show the plot
plt.show()
```

In this example, we have two numerical variables, x and y, and we used sns.scatterplot() to create a scatter plot with these variables. The x values are plotted on the x-axis, and the y values are plotted on the y-axis.

You can further customize the scatter plot by using additional parameters of the sns.scatterplot() function, such as hue, size, and style, to add more dimensions to the visualization. For example, you can color the points based on another categorical variable using the hue parameter or vary the size and style of the points based on other numerical variables.

Here's an example of how to add a hue to the scatter plot:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5, 6, 7]
y = [2, 4, 5, 4, 5, 6, 7]
category = ['A', 'B', 'A', 'B', 'A', 'B', 'A']

# Create a scatter plot with hue
sns.scatterplot(x=x, y=y, hue=category)

# Set plot labels and title
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Seaborn Scatter Plot with Hue')

# Show the plot
plt.show()
```

In this example, we added a category variable, and we used the hue parameter to color the points based on the values of this categorical variable. The hue parameter provides additional information to the scatter plot, making it more informative and visually appealing.

### Line Plot:
sns.lineplot(): Draws a line plot, useful for visualizing trends or time series data.
To create a line plot in Seaborn, you can use the sns.lineplot() function. The lineplot function is used to visualize the relationship between two numerical variables, typically to show trends or changes over time. Here's how you can use it:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5, 6, 7]
y = [2, 4, 5, 4, 5, 6, 7]

# Create a line plot
sns.lineplot(x=x, y=y)

# Set plot labels and title
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Seaborn Line Plot Example')

# Show the plot
plt.show()
```

In this example, we have two numerical variables, x and y, and we used sns.lineplot() to create a line plot with these variables. The x values are plotted on the x-axis, and the y values are plotted on the y-axis. The line plot shows the trend or pattern in the data points.

You can further customize the line plot using additional parameters of the sns.lineplot() function, such as hue, style, markers, and ci, to add more dimensions and information to the visualization. For example, you can color the lines based on another categorical variable using the hue parameter or use different line styles for different categories using the style parameter.

Here's an example of how to add a hue to the line plot:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5, 6, 7]
y = [2, 4, 5, 4, 5, 6, 7]
category = ['A', 'B', 'A', 'B', 'A', 'B', 'A']

# Create a line plot with hue
sns.lineplot(x=x, y=y, hue=category)

# Set plot labels and title
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Seaborn Line Plot with Hue')

# Show the plot
plt.show()

```
In this example, we added a category variable, and we used the hue parameter to create separate lines for each category. The hue parameter provides additional information to the line plot, allowing us to observe trends and changes in the data for different categories.

### Bar Plot:

sns.barplot(): Creates a bar plot to display the distribution of categorical data.
sns.countplot(): Similar to barplot, but it shows the count of occurrences for each category.
To create a bar plot in Seaborn, you can use the sns.barplot() function. A bar plot is useful for visualizing the distribution of categorical data or the relationship between a categorical variable and a numerical variable. Here's how you can use it:

```python
Copy code
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
categories = ['Category 1', 'Category 2', 'Category 3', 'Category 4']
values = [10, 25, 15, 30]

# Create a bar plot
sns.barplot(x=categories, y=values)

# Set plot labels and title
plt.xlabel('Categories')
plt.ylabel('Values')
plt.title('Seaborn Bar Plot Example')

# Show the plot
plt.show()
```

In this example, we have a list of categories and their corresponding values. We used sns.barplot() to create a bar plot with these data. The categories are plotted on the x-axis, and the values are plotted on the y-axis. Each bar represents the value for a specific category.

By default, sns.barplot() will display the mean of the values for each category. If you have multiple data points for each category and want to display individual points or error bars, you can use the estimator parameter to specify a different aggregation function (e.g., sum, median, max, etc.).

You can also customize the appearance of the bar plot using additional parameters of the sns.barplot() function, such as hue, palette, and ci, among others. For example, you can use the hue parameter to create grouped bar plots based on another categorical variable or the palette parameter to specify the colors of the bars.

Here's an example of how to create a grouped bar plot with a hue:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
categories = ['Category 1', 'Category 2', 'Category 3', 'Category 4']
values1 = [10, 25, 15, 30]
values2 = [5, 20, 12, 25]
group = ['Group A', 'Group A', 'Group B', 'Group B']

# Create a grouped bar plot with hue
sns.barplot(x=categories, y=values1, hue=group)

# Set plot labels and title
plt.xlabel('Categories')
plt.ylabel('Values')
plt.title('Seaborn Grouped Bar Plot with Hue')

# Show the plot
plt.show()
```

In this example, we have two sets of values (values1 and values2) for each category. We added a group variable, and we used the hue parameter to create grouped bars for each group within each category. The hue parameter provides additional information to the bar plot, making it more informative and visually appealing.
### Histogram:

sns.histplot(): Creates a histogram to display the distribution of a single numerical variable.

To create a histogram chart in Seaborn, you can use the sns.histplot() function. A histogram is used to visualize the distribution of a single numerical variable. It divides the data into bins and shows the frequency or count of data points falling within each bin. Here's how you can use it:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = [10, 15, 20, 25, 30, 30, 35, 40, 45, 50, 50, 55, 60]

# Create a histogram
sns.histplot(data, bins=5, kde=False)

# Set plot labels and title
plt.xlabel('Values')
plt.ylabel('Frequency')
plt.title('Seaborn Histogram Example')

# Show the plot
plt.show()

```
In this example, we have a list of data, and we used sns.histplot() to create a histogram with this data. The data is plotted on the x-axis, and the frequency (count of data points) falling within each bin is plotted on the y-axis. The bins parameter specifies the number of bins to divide the data, and the kde parameter set to False disables the kernel density estimation curve.

You can further customize the histogram using additional parameters of the sns.histplot() function, such as color, stat, element, and multiple, among others. For example, you can change the color of the bars using the color parameter or show a density curve along with the histogram using the kde parameter set to True.

Here's an example of how to create a histogram with a density curve:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = [10, 15, 20, 25, 30, 30, 35, 40, 45, 50, 50, 55, 60]

# Create a histogram with density curve
sns.histplot(data, bins=5, kde=True)

# Set plot labels and title
plt.xlabel('Values')
plt.ylabel('Density')
plt.title('Seaborn Histogram with Density Curve')

# Show the plot
plt.show()
```

In this example, we set the kde parameter to True, which adds a density curve to the histogram. The density curve provides an estimation of the underlying probability density function of the data, giving a smoother representation of the data distribution.

### Box Plot and Violin Plot:

sns.boxplot(): Draws a box plot to visualize the distribution of data across categories.
sns.violinplot(): Shows a combination of a box plot and a kernel density plot.

### Heatmap:

sns.heatmap(): Plots a heatmap to display the correlation matrix or any other rectangular data.

### Pair Plot:

sns.pairplot(): Creates a grid of scatter plots for pairwise relationships in the dataset.

### Joint Plot:

sns.jointplot(): Combines a scatter plot with histograms to visualize bivariate distributions.

### Facet Grid:

sns.FacetGrid(): Allows you to create a grid of plots based on the values of one or more categorical variables.

### Categorical Plot:

sns.catplot(): A general function to create various categorical plots such as bar plots, box plots, violin plots, etc.

### Regression Plot:

sns.regplot(): Creates a scatter plot with a linear regression line fitted to the data.

### Pairwise Plot:

sns.pairplot(): Plots pairwise relationships between multiple variables, along with histograms on the diagonal.

These are just some of the core plotting functions offered by Seaborn. Each of these functions has various parameters and options to customize the appearance of the plots and accommodate different data types and structures. Seaborn's integration with Pandas DataFrames and its built-in color palettes further simplify the process of creating visually appealing and informative plots.
