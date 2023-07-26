# Interpolation in Scipy
In scipy, interpolation is performed using the scipy.interpolate submodule, which provides various interpolation functions to estimate values between data points. Interpolation is the process of estimating values of a function for points within a given range based on known data points.

The scipy.interpolate module supports different types of interpolation methods, such as linear, polynomial, spline, and more. Here's a brief overview of some commonly used interpolation functions:
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.interpolate import interp1d
x = np.arange(11)
y=np.array([2.0,1.9,1.7,1.5,0.5,0.0,0.8,2.0,0.9,0.2,2.0])
#plt.plot(x,y)
#plt.show()
# Linear,Nearest,Zero,Slinear,Cubic
predict = interp1d  (x,y, kind="quadratic")
#predict is a function if we pass x it returns y
X2= np.linspace(0,10,100)
Y2=np.array([predict(x) for x in X2])
plt.plot(x,y,"o:")
plt.plot(X2,Y2,"o:")
plt.show()
print(f"X: 1.5, Y={predict(1.5)}")
```
