# Reference Guide: Dictionaries

Dictionaries are a powerful and versatile data structure in Python, allowing you to store and retrieve data using key-value pairs. This guide provides an overview of their creation, usage, and key methods.

---

## Create a Dictionary

### Methods to Create Dictionaries
1. **Using Braces (`{}`):**
   ```python
   smallest_countries = {
       'Africa': 'Seychelles',
       'Asia': 'Maldives',
       'Europe': 'Vatican City',
       'Oceania': 'Nauru',
       'North America': 'St. Kitts and Nevis',
       'South America': 'Suriname'
   }
   ```

2. **Using `dict()` Function:**
   ```python
   smallest_countries = dict(
       africa='Seychelles',
       asia='Maldives',
       europe='Vatican City',
       oceania='Nauru',
       north_america='St. Kitts and Nevis',
       south_america='Suriname'
   )
   ```

### Empty Dictionaries
```python
empty_dict_1 = {}
empty_dict_2 = dict()
```

### Notes on Keys and Values
- **Keys:** Must be of any immutable data type (e.g., strings, numbers, tuples).
- **Values:** Can be of any data type (mutable or immutable).
- **Single Value per Key:**
  - Invalid: `{'numbers': 1, 2, 3}`
  - Valid: `{'numbers': [1, 2, 3]}`

---

## Work with Dictionaries

### Access Values
- Access specific value using a key:
  ```python
  my_dict = {'nums': [1, 2, 3], 'abc': ['a', 'b', 'c']}
  print(my_dict['abc'])
  ```

- Access all values:
  ```python
  print(my_dict.values())
  ```

### Assign New Keys
Dictionaries are mutable. Add new keys as follows:
```python
my_dict['floats'] = [1.0, 2.0, 3.0]
print(my_dict)
```

### Check Key Existence
Use the `in` keyword to check if a key exists:
```python
print('Antarctica' in smallest_countries)
print('Asia' not in smallest_countries)
```

### Delete Key-Value Pair
Use `del` to remove a key-value pair:
```python
del my_dict['abc']
print(my_dict)
```

---

## Dictionary Methods

### Commonly Used Methods
1. **`items()`:** Returns a view of (key, value) pairs.
   ```python
   print(my_dict.items())
   ```

2. **`keys()`:** Returns a view of keys.
   ```python
   print(my_dict.keys())
   ```

3. **`values()`:** Returns a view of values.
   ```python
   print(my_dict.values())
   ```

### Notes on View Objects
- Reflect dynamic changes to the dictionary.
- Can be iterated over and support membership tests.