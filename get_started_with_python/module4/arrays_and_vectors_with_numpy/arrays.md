# Reference Guide: NumPy Arrays

NumPy is a powerful library for advanced numerical computing, offering fast operations on vectors, arrays, and matrices. This guide covers the essential features and operations of NumPy arrays.

---

## Create an Array

### Import NumPy
Standard practice is to import NumPy with an alias:
```python
import numpy as np
```

### Creating Arrays
- **1-D Array:**
  ```python
  array_1d = np.array([1, 2, 3])
  ```
- **2-D Array:**
  ```python
  array_2d = np.array([(1, 2, 3), (4, 5, 6)])
  ```
- **3-D Array:**
  ```python
  array_3d = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
  ```

### Pre-filled Arrays
- **Zeros:**
  ```python
  np.zeros((3, 2))
  ```
- **Ones:**
  ```python
  np.ones((2, 2))
  ```
- **Custom Values:**
  ```python
  np.full((5, 3), 8)
  ```
These are useful for initializing arrays or allocating memory.

---

## Array Methods

### Common Methods
- **Flatten:** Convert to 1-D:
  ```python
  array_2d.flatten()
  ```
- **Reshape:** Change shape without altering data:
  ```python
  array_2d.reshape(3, 2)
  array_2d.reshape(3, -1)  # NumPy infers the value of -1
  ```
- **To List:** Convert to a Python list:
  ```python
  array_2d.tolist()
  ```

### Mathematical Functions
- `ndarray.max()`: Maximum value
- `ndarray.mean()`: Mean value
- `ndarray.min()`: Minimum value
- `ndarray.std()`: Standard deviation
  ```python
  a = np.array([(1, 2, 3), (4, 5, 6)])
  print(a.max())
  print(a.mean())
  print(a.min())
  print(a.std())
  ```

---

## Array Attributes

- **Shape:** Dimensions of the array:
  ```python
  array_2d.shape
  ```
- **Data Type:** Type of the array elements:
  ```python
  array_2d.dtype
  ```
- **Size:** Total number of elements:
  ```python
  array_2d.size
  ```
- **Transpose:** Rows become columns:
  ```python
  array_2d.T
  ```

---

## Indexing and Slicing

- **Indexing:** Access individual elements:
  ```python
  a[1]       # Second row
  a[0, 1]    # First row, second element
  a[1, 2]    # Second row, third element
  ```
- **Slicing:** Extract subarrays:
  ```python
  a[:, 1:]  # All rows, columns from index 1 onward
  ```

---

## Array Operations

NumPy arrays support element-wise arithmetic:
```python
a = np.array([(1, 2, 3), (4, 5, 6)])
b = np.array([[1, 2, 3], [1, 2, 3]])

print(a + b)  # Addition
print(a * b)  # Multiplication
```

---

## Mutability

- **Mutable Elements:** Modify existing elements:
  ```python
a[1][1] = 100
  ```
- **Fixed Length:** Arrays cannot be lengthened or shortened:
  ```python
a[3] = 100  # Throws an error
  ```
To change length, create a new array:
```python
np.append(a, [new_values])
```

---

## Memory Efficiency

NumPy arrays allocate a contiguous block of memory during instantiation, unlike Python lists. This:
- Increases performance for operations on large datasets.
- Restricts the ability to resize the array in-place.

To lengthen an array, copy it to a new memory address:
```python
np.append(existing_array, [additional_values])