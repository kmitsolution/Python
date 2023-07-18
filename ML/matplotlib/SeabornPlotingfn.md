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
Both box plots and violin plots in Seaborn are used to visualize the distribution of numerical data. They provide a concise summary of the data's statistical properties, such as median, quartiles, outliers, and overall spread. Let's look at both types of plots:

#### Box Plot:
A box plot (box-and-whisker plot) displays the distribution of data through quartiles (Q1, Q2 or median, and Q3) and visualizes potential outliers. The "box" represents the interquartile range (IQR), which contains the middle 50% of the data. The "whiskers" extend from the box to the minimum and maximum values within a calculated range. Points outside this range are considered outliers and are represented as individual points on the plot.
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = [10, 20, 30, 40, 45, 50, 55, 60, 70, 80, 90, 100]

# Create a box plot
sns.boxplot(data)

# Set plot labels and title
plt.xlabel('Data')
plt.ylabel('Values')
plt.title('Seaborn Box Plot Example')

# Show the plot
plt.show()
```
#### Violin Plot:
A violin plot is similar to a box plot but provides a more detailed view of the data distribution. It combines a box plot with a kernel density plot, showing the density of the data at different values. The width of the "violin" at each value represents the density, while the box still indicates the quartiles.
```python

import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = [10, 20, 30, 40, 45, 50, 55, 60, 70, 80, 90, 100]

# Create a violin plot
sns.violinplot(data)

# Set plot labels and title
plt.xlabel('Data')
plt.ylabel('Values')
plt.title('Seaborn Violin Plot Example')

# Show the plot
plt.show()
```

Both box plots and violin plots are useful for comparing multiple datasets or groups as they provide insights into the data distribution and reveal potential outliers or variations. Choosing between them depends on your preference and the level of detail you wish to show. Violin plots can be more informative, especially when dealing with smaller datasets or when you want a smooth representation of the data distribution. However, box plots are generally more common and familiar in certain contexts.

### Heatmap:

sns.heatmap(): Plots a heatmap to display the correlation matrix or any other rectangular data.

A heatmap is a graphical representation of data in a tabular format, where the individual cells are colored to represent the values. In Seaborn, you can use the sns.heatmap() function to create a heatmap. Heatmaps are often used to visualize correlation matrices, cross-tabulations, or any other 2D data with color intensity indicating the magnitude of the values. Here's how you can create a heatmap in Seaborn:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data (correlation matrix)
data = [
    [1.0, 0.7, 0.5, 0.3],
    [0.7, 1.0, 0.2, 0.1],
    [0.5, 0.2, 1.0, 0.4],
    [0.3, 0.1, 0.4, 1.0]
]

# Create a heatmap
sns.heatmap(data, annot=True, cmap='coolwarm', fmt='.2f')

# Set plot title
plt.title('Seaborn Heatmap Example')

# Show the plot
plt.show()
```

In this example, we have a 2D data matrix (correlation matrix in this case), and we used sns.heatmap() to create a heatmap. The annot=True parameter adds annotations (numbers) to the heatmap cells, displaying the exact values. The cmap='coolwarm' parameter sets the color map to 'coolwarm', which provides a range of colors from cool (blue) to warm (red). The fmt='.2f' parameter formats the annotations to show numbers with two decimal places.

You can further customize the appearance of the heatmap using additional parameters of the sns.heatmap() function, such as vmin, vmax, xticklabels, yticklabels, cbar, and many others. For instance, you can use vmin and vmax to set the range of values displayed in the heatmap or use xticklabels and yticklabels to specify custom labels for the axes.

Here's an example of how to customize the heatmap further:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data (correlation matrix)
data = [
    [1.0, 0.7, 0.5, 0.3],
    [0.7, 1.0, 0.2, 0.1],
    [0.5, 0.2, 1.0, 0.4],
    [0.3, 0.1, 0.4, 1.0]
]

# Create a heatmap with custom settings
sns.heatmap(data, annot=True, cmap='viridis', fmt='.2f', vmin=0, vmax=1,
            xticklabels=['A', 'B', 'C', 'D'], yticklabels=['A', 'B', 'C', 'D'],
            cbar=True)

# Set plot title
plt.title('Custom Seaborn Heatmap Example')

# Show the plot
plt.show()
```

In this example, we customized the color map to 'viridis', set the range of values to display using vmin and vmax, and specified custom labels for the x-axis and y-axis using xticklabels and yticklabels. Additionally, we included the color bar (cbar=True) to provide a reference for the color scale.

### Pair Plot:

sns.pairplot(): Creates a grid of scatter plots for pairwise relationships in the dataset.
A pair plot in Seaborn is a grid of scatter plots that shows the pairwise relationships between multiple numerical variables in a dataset. It's a great way to visualize the interactions and correlations between different variables. Seaborn's sns.pairplot() function simplifies the process of creating these plots. Each scatter plot in the pair plot shows the relationship between two variables, and the diagonal plots display histograms for each variable. Let's see how to use sns.pairplot():

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = sns.load_dataset('iris')  # Iris dataset provided by Seaborn

# Create a pair plot
sns.pairplot(data, hue='species', markers=['o', 's', 'D'])

# Show the plot
plt.show()
```

In this example, we used the Iris dataset, which is a built-in dataset provided by Seaborn. The dataset contains four numerical features ('sepal_length', 'sepal_width', 'petal_length', 'petal_width') and a categorical feature ('species') with three classes ('setosa', 'versicolor', 'virginica'). We passed the entire dataset to sns.pairplot() and used the hue parameter to color the scatter plots based on the 'species' column. The markers parameter is used to specify different markers for each class.

The pair plot will display 4x4 grid scatter plots for the numerical features and histograms along the diagonal. Each scatter plot shows the relationship between two numerical features, and the colors indicate the different species of iris flowers.

You can further customize the pair plot using additional parameters of the sns.pairplot() function, such as palette for changing the color palette, plot_kws for customizing individual scatter plots, and diag_kws for customizing the diagonal plots, among others.

Here's an example of how to customize the pair plot:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = sns.load_dataset('iris')  # Iris dataset provided by Seaborn

# Create a custom pair plot
sns.pairplot(data, hue='species', markers=['o', 's', 'D'], palette='husl',
             diag_kws={'alpha': 0.5, 'histtype': 'stepfilled', 'linewidth': 1.5},
             plot_kws={'alpha': 0.8, 's': 50})

# Show the plot
plt.show()
```

In this customized pair plot, we used the 'husl' color palette (palette='husl'), adjusted the transparency and linewidth of the histograms (diag_kws), and increased the marker size and transparency of the scatter plots (plot_kws). These customizations can help make the pair plot more informative and visually appealing.

### Joint Plot:

sns.jointplot(): Combines a scatter plot with histograms to visualize bivariate distributions.
A joint plot in Seaborn is used to visualize the relationship between two numerical variables. It combines scatter plots for each variable with histograms along the axes to display the univariate distributions. This plot is useful for exploring bivariate relationships and detecting patterns in the data. Seaborn's sns.jointplot() function makes it easy to create joint plots. Let's see how to use it:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5, 6, 7]
y = [2, 4, 5, 4, 5, 6, 7]

# Create a joint plot
sns.jointplot(x=x, y=y, kind='scatter')

# Show the plot
plt.show()
```

In this example, we have two numerical variables, x and y, and we used sns.jointplot() to create a joint plot with these variables. The x values are plotted on the x-axis, and the y values are plotted on the y-axis. The scatter plot shows the relationship between the two variables, and the histograms along the axes display the individual distributions of each variable.

The kind parameter allows you to choose different types of joint plots. Some common options for the kind parameter are:

'scatter' (default): A scatter plot with histograms.
'kde': Kernel Density Estimate plot with histograms.
'hex': Hexbin plot with histograms.

Here's an example of using the 'kde' kind to create a joint plot with kernel density estimates:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5, 6, 7]
y = [2, 4, 5, 4, 5, 6, 7]

# Create a joint plot with kernel density estimates
sns.jointplot(x=x, y=y, kind='kde')

# Show the plot
plt.show()
```

In this case, the joint plot displays kernel density estimates instead of scatter points, which can provide a smoother representation of the data distribution.

You can further customize the joint plot using additional parameters of the sns.jointplot() function, such as color, xlim, ylim, marginal_kws, annot_kws, and many others. These customizations allow you to adjust the appearance and style of the joint plot to better suit your data and analysis.
### Facet Grid:

sns.FacetGrid(): Allows you to create a grid of plots based on the values of one or more categorical variables.
A facet grid in Seaborn is a powerful tool that allows you to create multiple plots (usually with the same plot type) organized in a grid based on one or more categorical variables. Each grid cell corresponds to a unique combination of categories, and the data is plotted separately for each cell. This is particularly useful when you want to compare different groups or subsets of your data in a structured and organized manner. Seaborn's sns.FacetGrid() function facilitates the creation of facet grids. Let's see how to use it:

```python

import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = sns.load_dataset('tips')  # Tips dataset provided by Seaborn

# Create a facet grid
g = sns.FacetGrid(data, col='time', row='day', hue='sex', margin_titles=True)
g.map(sns.scatterplot, 'total_bill', 'tip', alpha=0.7)
g.add_legend()

# Show the plot
plt.show()
```

In this example, we used the Tips dataset provided by Seaborn, which contains information about restaurant tips. We created a facet grid using sns.FacetGrid(), specifying the DataFrame data, and the columns, rows, and hue parameters.

1. col='time': This creates separate columns in the grid for each unique value of the 'time' column (lunch or dinner).
2. row='day': This creates separate rows in the grid for each unique value of the 'day' column (Thursday, Friday, Saturday, and Sunday).
3. hue='sex': This colors the data points based on the 'sex' column (male or female).
4. margin_titles=True: This displays the column and row names as titles on the margins of the grid.

The map() function is used to apply a plotting function (in this case, sns.scatterplot()) to each cell of the facet grid. We're creating scatter plots for the 'total_bill' and 'tip' columns in the dataset. The alpha parameter is used to adjust the transparency of the data points.

Finally, we add a legend to the plot using g.add_legend() to indicate the different colors used for male and female data points.

You can further customize the facet grid and the plots within it using various additional parameters and different plotting functions. This allows you to create complex and informative visualizations that provide valuable insights into your data.
### Categorical Plot:

sns.catplot(): A general function to create various categorical plots such as bar plots, box plots, violin plots, etc.

In Seaborn, a categorical plot is used to visualize the distribution of data for different categories or to compare data between different groups. Seaborn provides the sns.catplot() function, which is a general function that can create various types of categorical plots, such as bar plots, count plots, box plots, violin plots, and more. 

The type of categorical plot is determined by the kind parameter. Let's look at a few examples:

#### Bar Plot:
A bar plot is used to display the distribution of a categorical variable or to compare data between different categories.
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = sns.load_dataset('titanic')  # Titanic dataset provided by Seaborn

# Create a bar plot
sns.catplot(x='class', y='age', data=data, kind='bar')

# Set plot labels and title
plt.xlabel('Passenger Class')
plt.ylabel('Age')
plt.title('Seaborn Bar Plot Example')

# Show the plot
plt.show()
```

#### Count Plot:
A count plot is used to show the count of occurrences of each category in a categorical variable.
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = sns.load_dataset('titanic')  # Titanic dataset provided by Seaborn

# Create a count plot
sns.catplot(x='class', data=data, kind='count')

# Set plot labels and title
plt.xlabel('Passenger Class')
plt.ylabel('Count')
plt.title('Seaborn Count Plot Example')

# Show the plot
plt.show()
```

#### Box Plot:
A box plot is used to display the distribution of data for different categories, showing the median, quartiles, and potential outliers.
```python

import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = sns.load_dataset('titanic')  # Titanic dataset provided by Seaborn

# Create a box plot
sns.catplot(x='class', y='age', data=data, kind='box')

# Set plot labels and title
plt.xlabel('Passenger Class')
plt.ylabel('Age')
plt.title('Seaborn Box Plot Example')

# Show the plot
plt.show()
```

#### Violin Plot:
A violin plot is used to combine a box plot with a kernel density plot, providing more information about the data distribution.
```python

import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = sns.load_dataset('titanic')  # Titanic dataset provided by Seaborn

# Create a violin plot
sns.catplot(x='class', y='age', data=data, kind='violin')

# Set plot labels and title
plt.xlabel('Passenger Class')
plt.ylabel('Age')
plt.title('Seaborn Violin Plot Example')

# Show the plot
plt.show()
```

These are just a few examples of the categorical plots you can create with Seaborn's sns.catplot() function. You can customize these plots further using additional parameters and adjust their appearance to suit your data and analysis.
### Regression Plot:


sns.regplot() is a function in Seaborn used to create a scatter plot with a fitted regression line. It is particularly useful for visualizing the relationship between two numerical variables and for identifying any linear trends in the data.

Here's the basic usage of sns.regplot():

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5, 6, 7]
y = [2, 4, 5, 4, 5, 6, 7]

# Create a scatter plot with a regression line
sns.regplot(x=x, y=y)

# Set plot labels and title
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Seaborn regplot() Example')

# Show the plot
plt.show()
```

In this example, we have two numerical variables, x and y, and we used sns.regplot() to create a scatter plot with these variables. The x values are plotted on the x-axis, and the y values are plotted on the y-axis. Additionally, sns.regplot() fits a regression line to the data points, giving us an idea of the linear relationship between the two variables.

You can further customize the sns.regplot() function using additional parameters, such as color, marker, order, ci, and others:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5, 6, 7]
y = [2, 4, 5, 4, 5, 6, 7]

# Create a scatter plot with a customized regression line
sns.regplot(x=x, y=y, color='red', marker='o', order=2, ci=95)

# Set plot labels and title
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Customized Seaborn regplot() Example')

# Show the plot
plt.show()
```

In this customized example, we set the color of the regression line to red, used circular markers for the data points (marker='o'), specified the order=2 to fit a polynomial regression line of degree 2, and set the confidence interval for the regression line to 95% using ci=95.

sns.regplot() is a convenient function in Seaborn for quickly visualizing the relationship between numerical variables and understanding any underlying trends in the data.

### Pairwise Plot:

sns.pairplot(): Plots pairwise relationships between multiple variables, along with histograms on the diagonal.

In Seaborn, the sns.pairplot() function is used to create a grid of scatter plots that displays the pairwise relationships between multiple numerical variables in a dataset. It's a convenient way to visualize the interactions and correlations between different variables. The pair plot creates scatter plots for each combination of numerical variables, and histograms for the variables on the diagonal. This allows you to observe both the univariate distributions and the bivariate relationships between variables in one plot.

Here's how to use sns.pairplot():

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = sns.load_dataset('iris')  # Iris dataset provided by Seaborn

# Create a pair plot
sns.pairplot(data, hue='species', markers=['o', 's', 'D'])

# Show the plot
plt.show()
```

In this example, we used the Iris dataset, which contains four numerical features ('sepal_length', 'sepal_width', 'petal_length', 'petal_width') and a categorical feature ('species') with three classes ('setosa', 'versicolor', 'virginica'). We passed the entire dataset to sns.pairplot(), and we specified the hue parameter as 'species' to color the scatter plots based on the species of the iris flowers. The markers parameter is used to specify different markers for each class.

The pair plot will display a grid of scatter plots for the numerical features, and histograms along the diagonal. Each scatter plot shows the relationship between two numerical features, and the colors indicate the different species of iris flowers.

You can further customize the pair plot using additional parameters of the sns.pairplot() function, such as palette for changing the color palette, plot_kws for customizing individual scatter plots, and diag_kws for customizing the diagonal plots, among others. This allows you to adjust the appearance and style of the pair plot to better suit your data and analysis.

These are just some of the core plotting functions offered by Seaborn. Each of these functions has various parameters and options to customize the appearance of the plots and accommodate different data types and structures. Seaborn's integration with Pandas DataFrames and its built-in color palettes further simplify the process of creating visually appealing and informative plots.
