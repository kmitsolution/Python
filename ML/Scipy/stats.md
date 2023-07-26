# scipy.stats
The scipy.stats module in Python provides a wide range of statistical functions and distributions. These functions are useful for various statistical analyses, hypothesis testing, probability distributions, and more. The module includes methods for both continuous and discrete probability distributions, as well as statistical tests and descriptive statistics.

Here's an overview of some commonly used functions in scipy.stats:

```python
from scipy.stats import describe
# 1- D Array
data = [0.2, -1.91, 0.41, -0.7, -0.03, 0.53, -0.1]
# 2- D Array
data =[[1,2],[3,4]]
# descriptive function
desc = describe(data)
for key,value in desc._asdict().items():
    print(key,value)
```
```python
from scipy.stats import norm
import numpy as np

distribution = norm(0,2) #(mean,std)
array=np.array([-1,0.0,1,2,3])
print("Cumulative Distribution=",distribution.cdf(array))
print("PPF:", distribution.ppf(0.5))
print("sample:", distribution.rvs(size=5))
```
