# PieChart in matplotlib
Creating a pie chart in Matplotlib is a straightforward process. A pie chart is useful for showing the proportion of different categories in a dataset. Here's a step-by-step guide on how to create a pie chart using Matplotlib:

First, ensure you have Matplotlib installed. If not, you can install it using pip:

```bash
pip install matplotlib
```

Now, let's create a simple example to plot a pie chart:

```python

import matplotlib.pyplot as plt

# Sample data (replace this with your own dataset)
categories = ['Category A', 'Category B', 'Category C', 'Category D']
sizes = [30, 25, 15, 30]  # These represent the proportions of each category

# Create the pie chart
plt.figure(figsize=(6, 6))  # Set the figure size (optional)
plt.pie(sizes, labels=categories, autopct='%1.1f%%', startangle=140, shadow=True)

# Add title
plt.title('Pie Chart Example')

# Show the plot
plt.show()
```

In this example, we imported Matplotlib, provided some sample data as categories and sizes, and used the plt.pie() function to create the pie chart. The labels parameter specifies the category labels, and the sizes parameter specifies the proportions of each category. The autopct parameter formats the percentage display on the chart. The startangle parameter sets the angle at which the first category starts, and shadow=True adds a shadow effect to the chart.

## Examples

<b>Example 1:</b> Explode Slices and Custom Colors

In this example, we will explode (pull out) a slice from the pie chart and use custom colors for each category.

```python
import matplotlib.pyplot as plt

# Sample data (replace this with your own dataset)
categories = ['Category A', 'Category B', 'Category C', 'Category D']
sizes = [30, 25, 15, 30]  # These represent the proportions of each category
colors = ['gold', 'lightcoral', 'lightskyblue', 'lightgreen']
explode = (0.1, 0, 0, 0)  # Pull the first slice out

# Create the pie chart
plt.figure(figsize=(6, 6))  # Set the figure size (optional)
plt.pie(sizes, labels=categories, colors=colors, explode=explode, autopct='%1.1f%%', startangle=140, shadow=True)

# Add title
plt.title('Advanced Pie Chart Example')

# Show the plot
plt.show()
```

<b>Example 2: Donut Chart</b>

A donut chart is a modified version of a pie chart with a hole in the center. You can create a donut chart by adding a white circle to the center of the pie chart.

```python
import matplotlib.pyplot as plt

# Sample data (replace this with your own dataset)
categories = ['Category A', 'Category B', 'Category C', 'Category D']
sizes = [30, 25, 15, 30]  # These represent the proportions of each category
colors = ['gold', 'lightcoral', 'lightskyblue', 'lightgreen']

# Create the pie chart
plt.figure(figsize=(6, 6))  # Set the figure size (optional)
plt.pie(sizes, labels=categories, colors=colors, autopct='%1.1f%%', startangle=140, shadow=True)

# Draw a white circle at the center to create the donut effect
center_circle = plt.Circle((0, 0), 0.7, color='white')
fig = plt.gcf()
fig.gca().add_artist(center_circle)

# Add title
plt.title('Donut Chart Example')

# Show the plot
plt.show()
```

### Example 3: Nested Pie Chart

In this example, we will create a nested pie chart, showing multiple levels of categories within each slice.

```python
import matplotlib.pyplot as plt

# Sample data (replace this with your own dataset)
main_categories = ['Main Category 1', 'Main Category 2', 'Main Category 3']
main_sizes = [40, 30, 30]  # Proportions of main categories
sub_categories = ['Sub Category A', 'Sub Category B', 'Sub Category C', 'Sub Category D']
sub_sizes = [20, 10, 5, 15]  # Proportions of sub-categories

# Create the outer pie chart for main categories
plt.figure(figsize=(6, 6))  # Set the figure size (optional)
outer_colors = ['gold', 'lightcoral', 'lightskyblue']
plt.pie(main_sizes, labels=main_categories, colors=outer_colors, autopct='%1.1f%%', startangle=140, pctdistance=0.85)

# Create the inner pie chart for sub-categories
plt.gca().add_artist(plt.Circle((0, 0), 0.70, color='white'))
inner_colors = ['lightgreen', 'orange', 'lightblue', 'pink']
plt.pie(sub_sizes, colors=inner_colors, autopct='%1.1f%%', startangle=140, pctdistance=0.78)

# Add title
plt.title('Nested Pie Chart Example')

# Show the plot
plt.show()
```

These examples demonstrate some advanced techniques for creating pie charts in Matplotlib. You can further customize the appearance and labels to fit your specific data and visualization requirements. Matplotlib provides a lot of flexibility and options for data visualization. Explore the Matplotlib documentation for more information: https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.pie.html

You can adjust the figure size and other properties as per your requirement. Matplotlib provides many customization options, such as colors, explode slices, etc. Refer to the Matplotlib documentation for more details and options: https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.pie.html
