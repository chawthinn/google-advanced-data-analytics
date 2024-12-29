# More on Grouping and Aggregation in Pandas

Pandas provides powerful tools like `groupby()` and `agg()` to group, aggregate, summarize, and manipulate data efficiently. This guide reviews their usage and key features.

---

## `groupby()`

### Overview
The `groupby()` function splits data into groups based on specified criteria, applies a function to each group, and combines the results into a data structure. It can be used for:
- **Aggregation**: Compute summary statistics for each group.
- **Transformation**: Apply functions to modify group data.
- **Filtration**: Select groups based on conditions.
- **Iteration**: Iterate over groups or values.

### Example DataFrame
```python
import pandas as pd

clothes = pd.DataFrame({
    'type': ['pants', 'shirt', 'shirt', 'pants', 'shirt', 'pants'],
    'color': ['red', 'blue', 'green', 'blue', 'green', 'red'],
    'price_usd': [20, 35, 50, 40, 100, 75],
    'mass_g': [125, 440, 680, 200, 395, 485]
})
print(clothes)
```

### Basic Usage
Group by a single column:
```python
grouped = clothes.groupby('type')
print(grouped.mean())
```

Group by multiple columns:
```python
print(clothes.groupby(['type', 'color']).min())
```

Get the number of observations in each group:
```python
print(clothes.groupby(['type', 'color']).size())
```

### Built-in Aggregation Functions
Some common aggregation functions include:
- `count()`: Non-null value count.
- `sum()`: Sum of values.
- `mean()`: Average of values.
- `median()`: Median of values.
- `min()`: Minimum value.
- `max()`: Maximum value.
- `std()`: Standard deviation.
- `var()`: Variance.

---

## `agg()`

### Overview
The `agg()` method allows applying multiple functions to a DataFrame or specific columns.

### Syntax
```python
dataframe.agg(func, axis=0)
```
- `func`: Function(s) to apply.
- `axis`: Axis over which to apply the function (default=0 for columns).

### Examples

#### Applying Multiple Functions to Specific Columns
```python
print(clothes[['price_usd', 'mass_g']].agg(['sum', 'mean']))
```

#### Different Functions for Different Columns
```python
print(clothes.agg({
    'price_usd': 'sum',
    'mass_g': ['mean', 'median']
}))
```

#### Aggregating Across Rows
```python
print(clothes[['price_usd', 'mass_g']].agg(['sum', 'mean'], axis=1))
```

---

## `groupby()` with `agg()`

Combining these functions enables complex grouping and aggregation:
```python
print(clothes.groupby('color').agg({
    'price_usd': ['mean', 'max'],
    'mass_g': ['mean', 'max']
}))
```

---

## MultiIndex

### Overview
When grouping by multiple columns, the resulting DataFrame often has a hierarchical index (MultiIndex). This enables complex data manipulations with reduced dimensionality.

### Example
```python
grouped = clothes.groupby(['color', 'type']).agg(['mean', 'min'])
print(grouped)
```

### Accessing MultiIndex Data

#### Select Top-Level Column
```python
grouped.loc[:, 'price_usd']
```

#### Select Specific Value
```python
grouped.loc[('blue', 'shirt'), ('mass_g', 'mean')]
```

#### Removing MultiIndex
Use `as_index=False` to avoid creating a MultiIndex:
```python
print(clothes.groupby(['color', 'type'], as_index=False).mean())
```

---

## Key Takeaways
- **`groupby()`**: An essential method for combining and analyzing grouped data.
- **`agg()`**: Enables dynamic application of multiple functions across a DataFrame.
- Used together, these tools provide deep insights and facilitate efficient data analysis.
- Familiarity with MultiIndex is helpful, though not required for most tasks.