# Reference Guide: Sets

Sets are a powerful data structure in Python, used to identify unique data elements, separate data, and clean datasets. Unlike lists and dictionaries, sets do not support key-value pairs or indexing and are unordered. This guide provides an overview of sets, their creation, and key methods.

---

## Sets Review
A set is a collection of unique, unordered data elements. Python provides two set classes:
- **Set** (mutable)
- **Frozenset** (immutable)

Sets are also a fundamental concept in mathematics, used to identify unique elements.

---

## Create a Set

### Using Braces
```python
my_set = {5, 10, 10, 20}  # Duplicate values are removed
```
> **Note:** An empty set cannot be created with `{}` as this will be interpreted as an empty dictionary.

### Using `set()` and `frozenset()`

#### `set()`
- **Mutable**: Allows adding and removing elements.
- **Unordered and non-indexable**.
- Removes duplicate elements from any iterable object.
- Elements must be hashable (immutable).

#### Examples
```python
example_a = [1, 2, 2.0, '2']
print(set(example_a))  # {1, 2.0, '2'}

example_b = ('apple', (1, 2, 2, 2, 3), 2)
print(set(example_b))  # {'apple', 2, (1, 2, 2, 2, 3)}

example_c = [1.5, {'a', 'b', 'c'}, 1.5]
print(set(example_c))  # Throws an error; sets cannot contain mutable elements.
```

#### Adding Elements
```python
example_d = {'mother', 'hamster', 'father'}
example_d.add('elderberries')
print(example_d)  # {'mother', 'hamster', 'father', 'elderberries'}
```

#### `frozenset()`
- **Immutable**: Cannot be modified after creation.
- Can be used as dictionary keys or set elements.

#### Example
```python
example_e = [1.5, frozenset(['a', 'b', 'c']), 1.5]
print(set(example_e))  # {1.5, frozenset({'a', 'b', 'c'})}
```

---

## Set Methods
Sets provide numerous methods to compare and manipulate data, including `union`, `intersection`, `difference`, and `symmetric_difference`.

### `union()`
Returns a new set with elements from both sets.
```python
set_1 = {'a', 'b', 'c'}
set_2 = {'b', 'c', 'd'}

print(set_1.union(set_2))  # {'a', 'b', 'c', 'd'}
print(set_1 | set_2)       # {'a', 'b', 'c', 'd'}
```

### `intersection()`
Returns a new set with elements common to both sets.
```python
print(set_1.intersection(set_2))  # {'b', 'c'}
print(set_1 & set_2)             # {'b', 'c'}
```

### `difference()`
Returns a new set with elements in the first set but not in the second.
```python
print(set_1.difference(set_2))  # {'a'}
print(set_1 - set_2)           # {'a'}
```

### `symmetric_difference()`
Returns a new set with elements in either set but not both.
```python
print(set_1.symmetric_difference(set_2))  # {'a', 'd'}
print(set_1 ^ set_2)                     # {'a', 'd'}
```