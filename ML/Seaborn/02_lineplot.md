# Seaborn lineplot()
Seaborn is a Python data visualization library built on top of matplotlib. It provides a high-level interface for creating attractive and informative statistical graphics. To create a line plot using Seaborn, you can use the sns.lineplot() function. Let's go through an example step by step:

### Install and import the necessary libraries:

```
pip install seaborn
```

```python
import seaborn as sns
import matplotlib.pyplot as plt
```
### Example -1
Creating a simple linear chart by providing x and y axis
```python
import seaborn as sns
from matplotlib import pyplot as plt
x = [1,2,3,4]
y = [2,4,6,8]
sns.lineplot(x=x,y=y)
import seaborn as sns
from matplotlib import pyplot as plt
x = [1,2,3,4]
y = [2,4,6,8]
sns.lineplot(x=x,y=y)
plt.show()
```

### Example -2
Create some sample data:
```python
import numpy as np

x = np.linspace(0, 10, 100)
y = np.sin(x)
#Use sns.lineplot() to create the line plot:
sns.lineplot(x=x, y=y)
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Line Plot with Seaborn')
plt.show()
```

In this example, we use sns.lineplot() to create a line plot with the x and y data. We also added labels and a title to the plot for better visualization.

You can also use Seaborn to draw line plots for multiple lines or add more customization to the plot. Here's an example with multiple lines and more customization:

```python

# Create additional data
y2 = np.cos(x)

# Create the line plot with multiple lines and customize the style
sns.lineplot(x=x, y=y, label='sin(x)', linestyle='-', color='blue')
sns.lineplot(x=x, y=y2, label='cos(x)', linestyle='--', color='red')

plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Line Plot with Multiple Lines')
plt.legend()  # Add legend to show labels for each line
plt.show()
```

In this example, we created an additional y2 data representing the cosine function. We used sns.lineplot() twice to plot both y and y2 with different line styles and colors. We also added a legend to distinguish between the two lines.

### Example 
Convert array to Panda Dataframe and then draw the line graph
```python
import seaborn as sns
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
days = [1,2,3,4]
temp = [30,31,32,30]
# Create a panda data frame 
temp_df = pd.DataFrame({"days": days, "temp":temp})
# pass Data frame to sns lineplot
sns.lineplot(x="days",y="temp", data=temp_df)
plt.show()
```
### Example
Load the data from seaborn github dataset <a href=https://github.com/mwaskom/seaborn-data.git> Seaborn DataSet </a>
```python
import seaborn as sns
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
# load the data from seaborn github
tips_df = sns.load_dataset("tips")
# pass Data frame to sns lineplot
sns.lineplot(x="size",y="total_bill", data=tips_df , hue="sex") # hue is for category
#sns.lineplot(x="size",y="total_bill", data=tips_df , hue="sex",style="sex") # style will create the dotted lines for one of the sex
#sns.lineplot(x="size",y="total_bill", data=tips_df , hue="sex",style="sex",markers=["o",">"]) # set the markers for sex
plt.show()
```
Seaborn offers many other plotting functions and styles for various types of data visualizations. It's worth exploring the Seaborn documentation to discover its full potential and to create beautiful and informative plots effortlessly.

