# Histogram in matplotlib
A histogram is a graphical representation of the distribution of a dataset. It displays the frequency of values within specific bins or intervals. In Python, you can create a histogram using the popular data visualization library Matplotlib. Here's a step-by-step guide on how to create a histogram using Matplotlib:

First, make sure you have Matplotlib installed. If not, you can install it using pip:

```bash
pip install matplotlib
```

Now, let's create a simple example to plot a histogram:

```python
import matplotlib.pyplot as plt

# Sample data (replace this with your own dataset)
data = [23, 27, 21, 34, 25, 32, 29, 28, 36, 31, 27, 22, 26, 33, 35, 30, 31, 24, 27, 33]

# Create the histogram
plt.hist(data, bins=10, edgecolor='black')  # The 'bins' parameter sets the number of bins for the histogram

# Add labels and title
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.title('Histogram Example')

# Show the plot
plt.show()
```

In this example, we imported Matplotlib, provided some sample data, used the plt.hist() function to create the histogram with 10 bins, and then added labels and a title using plt.xlabel(), plt.ylabel(), and plt.title(), respectively. Finally, plt.show() displays the plot.

You can adjust the number of bins to get a better representation of the data. If you don't specify the bins parameter, Matplotlib will choose a default number of bins.

# Example
```python
ml_students = np.random.randint(28,45,20)
dev_students = np.random.randint(18,30,10)
plt.hist(ml_students, rwidth=0.8, histtype="bar", orientation="horizontal", color="blue", label="ML Students")
plt.legend()
plt.show()
```

```python
# To Show both dev and ml student data.
ml_students = np.random.randint(28,45,20)
dev_students = np.random.randint(28,45,20)
plt.figure(figsize= (16,9)) # histogram size

plt.hist([ml_students,dev_students], rwidth=0.8, histtype="bar", orientation="vertical", color=["r","b"], label=["ML","Dev"])

plt.legend()
plt.show()
```
