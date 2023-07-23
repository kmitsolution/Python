# Bokeh
Bokeh is a Python data visualization library that provides interactive and high-performance charts and plots. It is well-suited for creating interactive visualizations for web applications and dashboards. Bokeh supports various types of charts, including line charts, scatter plots, bar plots, histograms, and more. To use Bokeh, you'll need to have it installed. If you haven't installed it yet, you can do so using the following command:

```bash
pip install bokeh
```

Once you have Bokeh installed, here are some examples of creating different types of charts using Bokeh:

### Line Chart:
```python
from bokeh.plotting import figure, show
from bokeh.io import output_file

# Sample data
x = [1, 2, 3, 4, 5]
y = [6, 7, 2, 4, 5]

# Create a line chart
p = figure(title='Line Chart Example', x_axis_label='X-axis', y_axis_label='Y-axis')
p.line(x, y, line_width=2)

# Save the output to an HTML file (optional)
output_file('line_chart.html')

# Show the plot
show(p)
```

```python
from bokeh.plotting import figure, show
from bokeh.io import output_file
from bokeh.models import ColumnDataSource, HoverTool
from bokeh.palettes import Category10
import pandas as pd

# Sample data
data = {
    'x': [1, 2, 3, 4, 5],
    'y1': [6, 7, 2, 4, 5],
    'y2': [8, 4, 5, 1, 2],
    'y3': [3, 2, 9, 6, 7]
}
df = pd.DataFrame(data)

# Create a ColumnDataSource from the DataFrame
source = ColumnDataSource(df)

# Create the figure
p = figure(title='Advanced Line Chart Example', x_axis_label='X-axis', y_axis_label='Y-axis')

# Plot multiple lines
lines = []
line_labels = ['Line 1', 'Line 2', 'Line 3']
line_colors = Category10[3]  # Use the Category10 palette for 3 colors

for i, line_label in enumerate(line_labels):
    line = p.line(x='x', y=f'y{i+1}', source=source, line_width=2, line_color=line_colors[i], legend_label=line_label)
    lines.append(line)

# Add hover tool to display values
hover = HoverTool()
hover.tooltips = [("X", "@x"), ("Y", "$y")]
p.add_tools(hover)

# Customize the plot
p.legend.title = 'Lines'
p.legend.location = 'top_left'
p.legend.click_policy = 'hide'  # Clicking on a legend label will hide/show the corresponding line
p.toolbar.autohide = True  # Auto-hide the toolbar for a cleaner look

# Save the output to an HTML file (optional)
output_file('advanced_line_chart.html')

# Show the plot
show(p)

```
n this example, we use Bokeh to create an advanced line chart with multiple lines. We start by defining sample data in a dictionary format and convert it to a pandas DataFrame. Then, we create a ColumnDataSource from the DataFrame, which allows us to use the data directly with Bokeh's plotting functions.

Next, we create the figure and add multiple lines to the plot using a loop. Each line corresponds to a different y-column in the DataFrame, and we customize the line colors and labels.

We also add a hover tool to display the exact x and y values when hovering over the data points.

Finally, we customize the legend, enable hiding/showing lines on click, and auto-hide the toolbar for a cleaner look.

When you run this code, it will generate an interactive line chart with three lines, and you can interact with it using the hover tool and the legend to show/hide individual lines. The plot will be saved to an HTML file named "advanced_line_chart.html," and it will also be displayed in your default web browser using show(p).
### Scatter Plot:
```python
from bokeh.plotting import figure, show
from bokeh.io import output_file

# Sample data
x = [1, 2, 3, 4, 5]
y = [6, 7, 2, 4, 5]

# Create a scatter plot
p = figure(title='Scatter Plot Example', x_axis_label='X-axis', y_axis_label='Y-axis')
p.circle(x, y, size=10, color='navy', alpha=0.8)

# Save the output to an HTML file (optional)
output_file('scatter_plot.html')

# Show the plot
show(p)
```

### Bar Plot:
```python

from bokeh.plotting import figure, show
from bokeh.io import output_file

# Sample data
categories = ['Category A', 'Category B', 'Category C', 'Category D']
values = [30, 50, 20, 40]

# Create a bar plot
p = figure(x_range=categories, title='Bar Plot Example', x_axis_label='Categories', y_axis_label='Values')
p.vbar(x=categories, top=values, width=0.5, color='orange')

# Save the output to an HTML file (optional)
output_file('bar_plot.html')

# Show the plot
show(p)
```

These are just a few examples of what you can do with Bokeh. The library offers many more options for customizing and enhancing your visualizations, including interactivity, tooltips, and zooming, among others. You can find more information and examples in the Bokeh documentation: https://docs.bokeh.org/
