# Numpy
NumPy arrays have several important properties and functions that make them powerful for numerical computations. Here are some commonly used properties and functions:

## Properties:

1. <b>ndim:</b> Returns the number of dimensions of the array.
2. <b>shape:</b> Returns a tuple representing the size of each dimension of the array.
3. <b>size:</b> Returns the total number of elements in the array.
4. <b>dtype:</b> Returns the data type of the elements in the array.
5. <b>itemsize:</b> Returns the size (in bytes) of each element in the array.
6. <b>nbytes:</b> Returns the total size (in bytes) of the array.

# Example

```python
import numpy as np
#Creating 1-d Array
nd = np.array(range(5))
print("1-D Array") 
print(nd)  #[0 1 2 3 4]
print("Dimension=",nd.ndim)  #Dimension= 1
print(nd.dtype)  # 'int32'
print(nd.size) # 5
print(nd.itemsize) # 4
print(nd[3]) #3

#Creating 2d Array
rint("Array:")
print(arr)
# Output:
# [[1 2 3]
#  [4 5 6]]

# Accessing properties
print("Number of dimensions:", arr.ndim)
# Output: Number of dimensions: 2

print("Shape of the array:", arr.shape)
# Output: Shape of the array: (2, 3)

print("Total number of elements:", arr.size)
# Output: Total number of elements: 6

print("Data type of elements:", arr.dtype)
# Output: Data type of elements: int64

print("Size (in bytes) of each element:", arr.itemsize)
# Output: Size (in bytes) of each element: 8

print("Total size (in bytes) of the array:", arr.nbytes)
# Output: Total size (in bytes) of the array: 48

```
In this example, we create a 2-dimensional NumPy array arr and then access its properties. We retrieve the number of dimensions using ndim, the shape using shape, the total number of elements using size, the data type of elements using dtype, the size (in bytes) of each element using itemsize, and the total size (in bytes) of the array using nbytes.


Functions:

np.zeros(shape): Creates an array of zeros with the specified shape.
np.ones(shape): Creates an array of ones with the specified shape.
np.arange(start, stop, step): Creates an array with evenly spaced values within a specified range.
np.linspace(start, stop, num): Creates an array with evenly spaced values within a specified range, with a specified number of elements.
np.reshape(array, new_shape): Returns a new array with a modified shape.
np.concatenate((array1, array2), axis): Concatenates two or more arrays along a specified axis.
np.transpose(array): Returns the transpose of the array (rows become columns, and vice versa).
np.mean(array): Computes the arithmetic mean of the array's elements.
np.sum(array): Computes the sum of the array's elements.
np.min(array): Finds the minimum value in the array.
np.max(array): Finds the maximum value in the array.
np.argmin(array): Returns the index of the minimum value in the array.
np.argmax(array): Returns the index of the maximum value in the array.
np.sort(array): Sorts the elements of the array in ascending order.
np.unique(array): Returns the unique elements of the array.

These are just a few examples of the many properties and functions available in NumPy for manipulating arrays. The library provides a rich set of mathematical and statistical operations, broadcasting capabilities, and advanced indexing techniques to work with arrays efficiently. You can refer to the NumPy documentation for a comprehensive list of functions and their usage.
