# Boolean Masking in Pandas

Boolean masking, also called Boolean indexing, is a powerful tool in pandas that allows data selection based on conditions. By overlaying a Boolean grid onto a DataFrame's index, you can filter rows that satisfy specified criteria.

---

## Boolean Masks

A Boolean mask is a pandas Series object containing `True` or `False` values that align with the DataFrame's index. Rows corresponding to `True` values are kept, while rows corresponding to `False` values are filtered out.

### Example DataFrame
```python
import pandas as pd

data = {
    'planet': ['Mercury', 'Venus', 'Earth', 'Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune'],
    'radius_km': [2440, 6052, 6371, 3390, 69911, 58232, 25362, 24622],
    'moons': [0, 0, 1, 2, 80, 83, 27, 14]
}
df = pd.DataFrame(data)
print(df)
```

### Filtering Rows
To filter planets with fewer than 20 moons:
```python
mask = df['moons'] < 20
filtered_df = df[mask]
print(filtered_df)
```
This results in a new DataFrame containing only the rows where the condition is `True`.

### Selecting Specific Columns
To select only the `planet` column for planets with fewer than 20 moons:
```python
planets_with_few_moons = df.loc[mask, 'planet']
print(planets_with_few_moons)
```

---

## Complex Logical Statements

Pandas provides logical operators for multi-conditional selection:

| Operator | Logic      |
|----------|------------|
| `&`      | and        |
| `|`      | or         |
| `~`      | not        |

### Examples

#### Example 1: Planets with fewer than 10 moons or more than 50 moons
```python
mask = (df['moons'] < 10) | (df['moons'] > 50)
filtered_df = df[mask]
print(filtered_df)
```

#### Example 2: Planets with more than 20 moons, excluding those with exactly 80 moons or a radius less than 50,000 km
```python
mask = (df['moons'] > 20) & ~(df['moons'] == 80) & ~(df['radius_km'] < 50000)
filtered_df = df[mask]
print(filtered_df)
```
Alternatively:
```python
mask = (df['moons'] > 20) & (df['moons'] != 80) & (df['radius_km'] >= 50000)
filtered_df = df[mask]
print(filtered_df)
```

---

## Key Takeaways

- **Boolean Masking**: Apply filters to DataFrames by overlaying a Boolean grid to select rows based on conditions.
- **Logical Operators**: Use `&` (and), `|` (or), and `~` (not) for multi-conditional filtering.
- **Parentheses**: Enclose each condition in parentheses to ensure correct evaluation.
- Boolean masking is a core activity for data manipulation and analysis in pandas.