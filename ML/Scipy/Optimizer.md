# Optimization in Scipy
In scipy, optimization refers to the process of finding the minimum or maximum of a given function. The scipy.optimize module provides a wide range of optimization algorithms to solve various optimization problems, including unconstrained and constrained optimization.

The main function for optimization in scipy is scipy.optimize.minimize(), which allows you to find the minimum (or maximum) of a function with or without constraints. Here's an overview of how to use scipy.optimize.minimize() for basic optimization tasks:

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.optimize import minimize
# minimize a**2 + b**2
def objective(x):
    a=x[0]
    b=x[1]
    return a**2 + b**2
x0=np.array([200,500])
solution=minimize(objective,x0,method="SLSQP")
print(solution)
```

### Constraint in the optimization
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.optimize import minimize


# minimize a**2 + b**2
def objective(x):
    a = x[0]
    b = x[1]
    return a ** 2 + b ** 2


def constraint1(x):
    a = x[0]
    b = x[1]
    return a + b - 100


cons = [
    {
        "type": "eq",
        "fun": constraint1
    }
]

x0 = np.array([200, 500])
solution = minimize(objective, x0, method="SLSQP", constraints=cons)
print(solution)

```
