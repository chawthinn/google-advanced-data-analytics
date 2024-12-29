# Reference guide: Lists

A list is a data structure that helps store and manipulate an ordered collection of items. 

These items can be of any data type such as integers, floats, strings, and even other lists. 

## Create a list
There are two main ways to create lists in Python:
- Square brackets: []
- The list function:  list()
When instantiating a list using brackets, separate each element with a comma. For example, the following code creates a list of strings:
```python
list_a = ['olive', 'palm', 'coconut']
```
You can also create a list of integers:
```python
list_b = [8, 6, 7, 5, 3, 0, 8]
```
Or a list of mixed data types:
```python
list_c = ['Abidjan', 14.2, [1, 2, None], 'Zagreb']
```
To create an empty list, use empty brackets or the list() function:
```python
empty_list_1 = []
empty_list_2 = list()
```
The list() function can also convert iterable data types to lists:
```python
my_string = 'Wilson'
my_list = list(my_string)
print(my_list)
```
## Indexing and slicing
Just as with strings, you can access elements in a list using indexing and slicing. 

The first element of a list has index zero, the second element has index one, and so on. Use square brackets to index:
```python
phrase = ['Astra', 'inclinant', 'sed', 'non', 'obligant']
print(phrase[1])
```
You can also use negative indices to access items from the end of a list:
```python
phrase = ['Astra', 'inclinant', 'sed', 'non', 'obligant']
print(phrase[-1])
```
Use slicing to extract a sublist. To slice, use square brackets containing a range of indices separated by a colon:
```python
phrase = ['Astra', 'inclinant', 'sed', 'non', 'obligant']
print(phrase[1:4])
```
Notice that this code returned a sublist containing the elements at indices one, two, and three of phrase. The **ending index** of the slice is *not* included.

Omitting the starting index in a slice implies an index of zero, and omitting the ending index implies an index of len(my_list):
```python
phrase = ['Astra', 'inclinant', 'sed', 'non', 'obligant']
print(phrase[:3])
print(phrase[3:])
```
## List mutability
Lists are **mutable**, which means that you can change their contents after they are created. 

You can change an individual item in a list by specifying its index and assigning a new value to it. For example:
```python
my_list = ['Macduff', 'Malcolm', 'Duncan', 'Banquo']
my_list[2] = 'Macbeth'
print(my_list)
```
You can even change a slice of a list using the same logic. The slice can be of any length. 

The elements in the new list will be inserted in place of the indicated slice: 
```python
my_list = ['Macduff', 'Malcolm', 'Macbeth', 'Banquo']
my_list[1:3] = [1, 2, 3, 4]
print(my_list)
```
## List operations
Lists can be combined using the addition operator (+):
```python
num_list = [1, 2, 3]
char_list = ['a', 'b', 'c']
num_list + char_list
```
They can also be multiplied using the multiplication operator (*):
```python
list_a = ['a', 'b', 'c']
list_a * 2
```
But they *cannot* be subtracted or divided. 

You can check whether a value is contained in a list by using the in operator:
```python
num_list = [2, 4, 6]
print(5 in num_list)
print(5 not in num_list)
```
## List methods
Lists are a core Python class. Classes package data together with tools to work with it. Methods are functions that belong to a class.

Lists have a number of built-in methods that are very useful. These include:

### append()
Add an element to the end of a list:
```python
my_list = [0, 1, 1, 2, 3]
variable = 5
my_list.append(variable)
print(my_list)
```

### insert() 
Insert an element at a given position:
```python
my_list = ['a', 'b', 'd']
my_list.insert(2, 'c')
print(my_list)
```

### remove() 
Remove the first occurrence of an item:
```python
my_list = ['a', 'b', 'd', 'a']
my_list.remove('a')
print(my_list)
pop() 
```
Remove the item at the given position in the list, and return it. If no index is specified, a `.pop()` removes and returns the last item in the list:
```python
my_list = ['a', 'b', 'c']
my_list.pop()
print(my_list)
clear() 
```
Remove all items:
```python
my_list = ['a', 'b', 'c']
my_list.clear()
print(my_list)
```

### index() 
Return the index of the first occurrence of an item in the list:
```python
my_list = ['a', 'b', 'c', 'a']
my_list.index('a')
```

### count() 
Return the number of times an item occurs in the list:
```python
my_list = ['a', 'b', 'c', 'a']
my_list.count('a')
sort() 
char_list = ['b', 'c', 'a']
num_list = [2, 3, 1]
char_list.sort()
num_list.sort(reverse=True)
print(char_list)
print(num_list)
```