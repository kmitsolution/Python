# NumPy Array
A NumPy array is a fundamental data structure in the NumPy library, which is a powerful Python library for scientific computing. NumPy arrays are homogeneous, multidimensional collections of elements with a fixed size. NumPy arrays provide various methods and operations for performing mathematical computations and manipulations efficiently.
Below are the properties for NumPy Array
1. Array Elements are fixed size means we cannot change the size of the array.
2. Array Elements can be modified
3. Array Elements are of same data type
4. Array can be represented as one-dimensional or multidimensional array.

## Example
```python
import numpy as np

# Create a 1-dimensional array
arr1 = np.array([1, 2, 3, 4, 5])
print(arr1)
# Output: [1 2 3 4 5]

# Create a 2-dimensional array
arr2 = np.array([[1, 2, 3], [4, 5, 6]])
print(arr2)
# Output:
# [[1 2 3]
#  [4 5 6]]

# Create an array of zeros
zeros_arr = np.zeros((3, 4))
print(zeros_arr)
# Output:
# [[0. 0. 0. 0.]
#  [0. 0. 0. 0.]
#  [0. 0. 0. 0.]]

# Create an array of ones
ones_arr = np.ones((2, 3))
print(ones_arr)
# Output:
# [[1. 1. 1.]
#  [1. 1. 1.]]

# Create an array with a range of values
range_arr = np.arange(0, 10, 2)
print(range_arr)
# Output: [0 2 4 6 8]

```
