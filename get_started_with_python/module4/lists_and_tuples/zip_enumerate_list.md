# Using `zip()`, `enumerate()`, and List Comprehension

## `zip()`

The `zip()` function is a built-in Python function that performs an element-wise combination of sequences, producing an iterator that generates tuples containing elements from each input sequence.

### Example
```python
cities = ['Paris', 'Lagos', 'Mumbai']
countries = ['France', 'Nigeria', 'India']
places = zip(cities, countries)

print(places)
print(list(places))
```

### Key Points
- Works with two or more iterable objects. The resulting iterator is as long as the shortest input.
- Can accept a single iterable, producing tuples containing one element each.

### Unzipping
You can unzip a sequence with the `*` operator.

#### Example
```python
scientists = [('Nikola', 'Tesla'), ('Charles', 'Darwin'), ('Marie', 'Curie')]
given_names, surnames = zip(*scientists)
print(given_names)
print(surnames)
```
This separates the data into different variables.

---

## `enumerate()`

The `enumerate()` function allows iteration over a sequence while keeping track of each element’s index.

### Example
```python
letters = ['a', 'b', 'c']
for index, letter in enumerate(letters):
    print(index, letter)
```

### Starting Index
You can specify a custom starting index.

#### Example
```python
letters = ['a', 'b', 'c']
for index, letter in enumerate(letters, 2):
    print(index, letter)
```
This starts indexing from 2.

### Use Case
Useful when the index of an element is needed to determine how it should be processed.

---

## List Comprehension

List comprehension is a concise way to create a new list based on the values in an existing iterable.

### Syntax
```python
my_list = [expression for element in iterable if condition]
```
- **expression**: Operation or transformation to perform on each element.
- **element**: Variable representing each item in the iterable.
- **iterable**: The sequence to iterate over.
- **condition**: Optional filter to include only elements that satisfy the condition.

### Examples

#### Adding to Each Number
```python
numbers = [1, 2, 3, 4, 5]
new_list = [x + 10 for x in numbers]
print(new_list)
```

#### Extracting Letters from Words
```python
words = ['Emotan', 'Amina', 'Ibeno', 'Sankwala']
new_list = [(word[0], word[-1]) for word in words if len(word) > 5]
print(new_list)
```
This creates tuples of the first and last letters of words longer than 5 letters.

---

## Key Takeaways
- `zip()`, `enumerate()`, and list comprehension simplify working with iterables and reduce the need for explicit loops.
- They improve efficiency and make your code more concise and dynamic.