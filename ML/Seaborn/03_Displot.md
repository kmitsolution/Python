# displot in Seaborn
In Seaborn, displot is a function used to create a histogram or kernel density estimate (KDE) plot, along with optional rug plots, for univariate data visualization. It is a flexible and convenient way to visualize the distribution of a single variable.

To use displot, you first need to install Seaborn if you haven't already:
```
pip install seaborn
```

Next, you import Seaborn and other necessary libraries:

```python
import seaborn as sns
import matplotlib.pyplot as plt
```

Now, let's demonstrate how to use displot with some sample data:

```python
import numpy as np

# Create some sample data (randomly generated here)
data = np.random.normal(loc=0, scale=1, size=1000)

# Create a histogram with displot
sns.displot(data, kde=False, rug=True)
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.title('Histogram with Rug Plot')
plt.show()
```

In this example, we used sns.displot() to create a histogram of the data variable. By default, it will display both the histogram and a rug plot (a small vertical tick at each data point on the x-axis). The kde parameter is set to False, indicating that we don't want to plot the Kernel Density Estimate (KDE) along with the histogram.

If you want to display the KDE instead of the histogram or both, you can adjust the kde parameter accordingly:

```python

# Create a KDE plot with displot
sns.displot(data, kde=True)
plt.xlabel('Value')
plt.ylabel('Density')
plt.title('Kernel Density Estimate (KDE) Plot')
plt.show()
```

In this case, we set kde=True to show the KDE plot without the histogram.

displot offers various customization options, such as changing the number of bins for the histogram, adjusting the bandwidth of the KDE, and more. You can explore the Seaborn documentation to learn about all the available parameters and styles to customize your plots to best suit your data.
