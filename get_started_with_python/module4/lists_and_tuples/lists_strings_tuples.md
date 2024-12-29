# Comparing Strings, Lists, and Tuples

## Strings

### Syntax/Instantiation
- Single, double, or triple quotes:
  ```python
  empty_str = ''
  my_string1 = 'minerals'
  my_string2 = "martin"
  my_string3 = """
  marathon
golfcart
  """
  ```
  - Using triple quotes to write a string over multiple lines inserts newlines (`\n`).

- The `str()` function can be used for instantiation and conversion:
  ```python
  empty_str = str()
  my_string = str(125)
  ```

### Content
Strings can contain any character—letters, numbers, punctuation marks, spaces—but everything between the opening and closing quotation marks is part of the same single string.

### Mutability
Strings are **immutable**. Once created, they cannot be modified. Any operation that appears to modify a string creates a new string object.

### Usage
Strings are most commonly used to represent text data.

### Methods
The Python string class has many useful methods to manipulate string data. Refer to [Common String Operations](https://docs.python.org/3/library/stdtypes.html#string-methods) in the Python documentation for more details.

---

## Lists

### Syntax/Instantiation
- Brackets, with each element separated by a comma:
  ```python
  empty_list = []
  my_list = [1, 2, 3, 4, 5]
  ```

- The `list()` function can be used for instantiation and conversion (works on iterable data types):
  ```python
  print(list('rocks'))
  print(list(('stones', 'water', 'underground')))
  ```

### Content
Lists can contain any data type, and in any combination (e.g., strings, integers, floats, tuples, dictionaries, and other lists):
  ```python
  my_list = [1, 2, 1, 2, 'And through', ['and', 'through']]
  ```

### Mutability
Lists are **mutable**, meaning they can be modified after creation:
  ```python
  num_list = [1, 2, 3]
  num_list[0] = 5446
  print(num_list)
  ```

### Usage
Lists are versatile and commonly used for:
- Storing collections of related items
- Iterating over elements in an ordered manner (e.g., `for` loops or list comprehensions)
- Sorting and searching
- Modifying existing data
- Storing computation results

### Methods
For a full list of list methods, refer to [More on Lists](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists) in the Python documentation.

---

## Tuples

### Syntax/Instantiation
- Parentheses, with each element separated by a comma:
  ```python
  empty_tuple = ()
  my_tuple = (1, 'z')
  ```

- To declare a tuple with a single element, use a trailing comma:
  ```python
  test1 = (1)  # Not a tuple
  test2 = (2,)  # Tuple
  print(type(test1))
  print(type(test2))
  ```

- Without parentheses, use commas to separate elements (even for single-element tuples):
  ```python
  tuple1 = 1,
  tuple2 = 2, 3
  print(type(tuple1))
  print(type(tuple2))
  ```

- The `tuple()` function can be used for instantiation and conversion of iterable data types:
  ```python
  empty_tuple = tuple()
  my_tuple = tuple([1, 'z'])
  ```

### Content
Tuples can contain any data type and combination (e.g., strings, integers, floats, lists, dictionaries, and other tuples):
  ```python
  my_tuple = (1871, 'all', 'mimsy', ('were', 'the'), ['borogroves'])
  ```

### Mutability
Tuples are **immutable**, meaning they cannot be modified once created.

### Usage
Tuples are commonly used for:
- Returning multiple values from a function
- Packing and unpacking sequences
- Dictionary keys (due to immutability)
- Safeguarding data integrity

### Methods
Tuples have only two built-in methods:
- `count()` - Returns the number of times a specified value occurs in the tuple.
- `index()` - Searches for a specified value and returns the index of its first occurrence.

---

## Key Takeaways
- **Strings**, **lists**, and **tuples** are iterable sequential data structures with many similarities but also key differences.
- When selecting a data structure, consider:
  - **Syntax/Instantiation**
  - **Content**
  - **Mutability**
  - **Use case**