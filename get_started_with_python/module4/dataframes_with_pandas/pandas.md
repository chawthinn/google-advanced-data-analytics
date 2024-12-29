# The Fundamentals of Pandas

Pandas is a powerful open-source library for data manipulation and analysis in Python. This guide reviews the basics of pandas DataFrames and their primary data structures, attributes, and methods.

---

## Primary Data Structures

### Series
- **Definition**: A one-dimensional labeled array that can hold any data type.
- **Similar to**: A column in a spreadsheet or a one-dimensional NumPy array.
- **Index**: Each element has an associated label (index) for efficient data manipulation.

### DataFrame
- **Definition**: A two-dimensional labeled data structure (like a table) where rows and columns are Series.

---

## Creating a DataFrame

### Importing Pandas
To use pandas, first import it:
```python
import pandas as pd
```

### From a Dictionary
```python
d = {'col1': [1, 2], 'col2': [3, 4]}
df = pd.DataFrame(data=d)
print(df)
```

### From a NumPy Array
```python
import numpy as np
df2 = pd.DataFrame(np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]]),
                   columns=['a', 'b', 'c'])
print(df2)
```

### From a CSV File
```python
df3 = pd.read_csv('/file_path/file_name.csv')
```

---

## Attributes and Methods

### Common Attributes

| **Attribute** | **Description** |
|---------------|-----------------|
| `columns`     | Returns column labels. |
| `dtypes`      | Returns data types in the DataFrame. |
| `iloc`        | Integer-based indexing for rows and columns. |
| `loc`         | Label-based indexing for rows and columns. |
| `shape`       | Returns a tuple of DataFrame dimensions. |
| `values`      | Returns a NumPy representation of the DataFrame. |

### Common Methods

| **Method**         | **Description** |
|--------------------|-----------------|
| `apply()`          | Applies a function along an axis of the DataFrame. |
| `copy()`           | Creates a copy of the DataFrame. |
| `describe()`       | Returns descriptive statistics. |
| `drop()`           | Removes specified rows or columns. |
| `groupby()`        | Groups data for aggregation. |
| `head(n=5)`        | Returns the first `n` rows (default: 5). |
| `info()`           | Provides a summary of the DataFrame. |
| `isna()`           | Identifies missing values. |
| `sort_values()`    | Sorts data by a specific column. |
| `value_counts()`   | Counts unique values in a column. |
| `where()`          | Replaces values based on a condition. |

---

## Selection Statements

### Row Selection

#### `loc[]`
Select rows by label:
```python
df.loc['row_1']        # Single row as a Series
print(df.loc[['row_1']])  # Single row as a DataFrame
print(df.loc['row_0':'row_3'])  # Range of rows (inclusive)
```

#### `iloc[]`
Select rows by position:
```python
print(df.iloc[1])         # Single row as a Series
print(df.iloc[[1]])       # Single row as a DataFrame
print(df.iloc[0:3])       # Range of rows (exclusive)
```

### Column Selection

#### Bracket Notation
```python
print(df['C'])            # Single column
print(df[['A', 'C']])     # Multiple columns
```

#### Dot Notation
```python
print(df.A)               # Access column `A`
```
Note: Bracket notation is preferred for readability in complex code.

#### `loc[]` and `iloc[]`
```python
print(df.loc[:, ['B', 'D']])  # All rows, selected columns
print(df.iloc[:, [1, 3]])     # All rows, selected columns by index
```

### Selecting Rows and Columns Together

#### `loc[]`
```python
print(df.loc['row_0':'row_2', ['A', 'C']])
```

#### `iloc[]`
```python
print(df.iloc[[2, 4], 0:3])
```

---

## Key Takeaways
- Pandas DataFrames provide a powerful way to work with tabular data.
- Rows and columns are represented as pandas Series.
- DataFrames have extensive methods and attributes to streamline data analysis.
- Selection statements (`loc[]` and `iloc[]`) allow for intuitive slicing and indexing.
- Practice and exploration of pandas tools will enhance your data manipulation skills.