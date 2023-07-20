# constants in Scipy
In SciPy, the constants module provides a collection of physical and mathematical constants. These constants can be useful when performing scientific calculations or simulations that require known and precise values. You can access these constants by importing the scipy.constants module.

Here are some commonly used constants available in the scipy.constants module:

## Mathematical Constants:
```python

import scipy.constants as const

print("Pi:", const.pi)
print("Euler's number:", const.e)
```
## Physical Constants:
```python
print("Speed of light in vacuum (m/s):", const.speed_of_light)
print("Gravitational constant (m^3 kg^(-1) s^(-2)):", const.gravitational_constant)
print("Planck constant (J·s):", const.h)
print("Boltzmann constant (J/K):", const.k)
print("Avogadro constant (mol^(-1)):", const.Avogadro)
```
## Units:
```python
print(constants.liter)            #0.001
print(constants.litre)            #0.001
print(constants.gallon)           #0.0037854117839999997
print(constants.gallon_US)        #0.0037854117839999997
print(constants.gallon_imp)       #0.00454609
print(constants.fluid_ounce)      #2.9573529562499998e-05
print(constants.fluid_ounce_US)   #2.9573529562499998e-05
print(constants.fluid_ounce_imp)  #2.84130625e-05
print(constants.barrel)           #0.15898729492799998
print(constants.bbl)              #0.15898729492799998
```

These constants are stored as floating-point numbers and can be used in your calculations. For example:

```python

radius_of_earth = 6371000  # meters
circumference = 2 * const.pi * radius_of_earth
print("Circumference of the Earth:", circumference, "meters")
```

Remember to prefix the constants with const. when using them.

You can find more constants in the scipy.constants module by referring to the official documentation: https://docs.scipy.org/doc/scipy/reference/constants.html
