# Markers in matplotlib
In matplotlib, markers are used to highlight individual data points in a plot. They are small symbols that can be added to line plots, scatter plots, and other types of plots to make the data points more visible and distinguishable. The marker parameter in various plotting functions is used to specify the type of marker to be used. Here are some commonly used markers in matplotlib:

'.': Point marker (small dot)
',': Pixel marker (pixel-sized dot)
'o': Circle marker
'x': Cross marker (x symbol)
'+': Plus marker (plus symbol)
'*': Star marker
's': Square marker
'd': Diamond marker
'^': Upward-pointing triangle marker
'v': Downward-pointing triangle marker
'>': Right-pointing triangle marker
'<': Left-pointing triangle marker

You can use these markers in different plotting functions like plot or scatter. Here's an example of using markers in a scatter plot:

```python

import matplotlib.pyplot as plt

# Sample data
x_values = [1, 2, 3, 4, 5]
y_values = [2, 4, 1, 5, 3]

# Create a scatter plot with circles as markers
plt.scatter(x_values, y_values, marker='o', label='Circle Marker')

# Add labels and a title
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Scatter Plot with Markers')

# Add a legend to show the marker type
plt.legend()

# Show the plot
plt.show()
```

In this example, we used 'o' as the marker type in plt.scatter to create a scatter plot with circles as markers. You can replace 'o' with any other marker symbol from the list above to use a different marker type.

You can also customize the size, color, and other properties of the markers using additional parameters in the plotting functions. The official matplotlib documentation provides more information and examples on working with markers: https://matplotlib.org/stable/api/markers_api.html
