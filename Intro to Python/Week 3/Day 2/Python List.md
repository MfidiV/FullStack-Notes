# Python List Operations

## Creating a List
You can create a list in Python by enclosing items in square brackets and separating them with commas. For example:
```python
my_list = [1, 2, 3, "apple", "banana"]
```

## Accessing a list

List elements can be accessed by their index, starting from 0. For example:
```python
first_item = my_list[0]
# Output: 1

```

## Negative indexing
Negative indices can be used to access elements from the end of the list. For example:

```python
    last_item = my_list[-1]
# Output: "banana"

```

## Slicing List
You can extract a subset of a list using slicing. The syntax is list[start:stop:step]. For example:

```python
    sliced_list = my_list[1:4]

```
## Adding/Change list elements
You can add elements to a list using the append() method or change an element by assigning a new value to a specific index. For example:
```python
my_list.append(4)  # Add 4 to the end
my_list[1] = 5  # Change the second element to 5


```

## Delete/Remove list elements

```python
del my_list[2]  # Deletes the element at index 2
my_list.remove("apple")  # Removes the element with the value "apple"

```
## Python List Methods
Python provides various methods for working with lists, such as append(), extend(), insert(), remove(), pop(), index(), count(), sort(), and reverse().

```python
squares = [x**2 for x in range(1, 6)]  # Generates the squares of numbers from 1 to 5

```

