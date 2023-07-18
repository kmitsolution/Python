# Seaborn

Seaborn is a high-level data visualization library built on top of Matplotlib. It provides a more convenient interface for creating aesthetically pleasing statistical graphics with minimal code. Seaborn is particularly useful for working with complex datasets and includes various built-in themes and color palettes.

Here's the same example using Seaborn:

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5]
y = [10, 15, 13, 8, 20]

# Create a line plot with Seaborn
sns.lineplot(x=x, y=y)
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Simple Seaborn Plot')
plt.show()
```

As you can see, the Seaborn code is shorter and produces a plot with an improved default style compared to the basic Matplotlib plot. Seaborn simplifies many aspects of data visualization, but it still relies on Matplotlib for the underlying plotting functionality.

In summary, use Matplotlib when you need fine-grained control over your plots or if you are building a custom visualization from scratch. Use Seaborn when you want to quickly create attractive statistical plots, especially for exploring data or presenting results.

### Another Example
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5, 6, 7]
y = [2, 4, 5, 4, 5, 6, 7]

# Create a scatterplot with a linear regression line
sns.regplot(x=x, y=y, ci=None, line_kws={'color': 'red'})

# Set plot labels and title
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Seaborn Scatterplot Example with Linear Regression Line')

# Show the plot
plt.show()
```

In this example, we used Seaborn's regplot function to create a scatterplot with a linear regression line fitted to the data points. The x and y variables represent the sample data. The ci=None argument specifies not to display the confidence interval around the regression line. The line_kws argument allows us to customize the properties of the regression line, and here we set the color to red.

When you run this code, it will display a scatterplot with data points and a red linear regression line fitted to those points.

