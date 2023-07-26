# scipy.special functions
Special is a submodule of the scipy library in Python that provides a collection of mathematical functions that are not available in the standard Python math module. These special functions are commonly used in various scientific and engineering applications. The scipy.special module includes functions from various mathematical areas, such as Bessel functions, gamma functions, error functions, and more.

```python
import numpy as np
import scipy.special as special
#Find the cube root
print("Cube root =",special.cbrt(np.array([64,125,729])))
#Compute 10**x
print("Exp10 function", special.exp10(np.array([2,3])))
#Comb special.comb(N,K)
#N is number of objects
#K is the number of objects picked
print("Combination=",special.comb(10,3))
#Comb special.perm(N,K)
#N is number of objects
#K is the number of objects picked
print("Combination=",special.perm(10,3))
# logsumexp
print("logexp sum=",special.logsumexp([1,2,3]))
# lambert function (inverse of x * e^x)
print("Lambertz fn=",special.lambertw(1))
```
