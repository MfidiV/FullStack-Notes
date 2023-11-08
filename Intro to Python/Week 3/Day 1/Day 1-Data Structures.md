# List Methods in Python

Lists are a versatile data structure in Python that allow you to store and manipulate ordered collections of elements. Here are some common list methods and their descriptions:

1. **append(x)**: Adds an element `x` to the end of the list.

2. **extend(iterable)**: Appends all elements from an iterable to the end of the list.

3. **insert(i, x)**: Inserts an element `x` at a specific index `i` in the list.

4. **remove(x)**: Removes the first occurrence of element `x` from the list.

5. **pop([i])**: Removes and returns the element at index `i`. If `i` is not provided, it removes and returns the last element.

6. **index(x[, start[, end]])**: Returns the index of the first occurrence of element `x` within the optional `start` and `end` index range.

7. **count(x)**: Returns the number of times element `x` appears in the list.

8. **sort(key=None, reverse=False)**: Sorts the list in ascending order by default. Use `reverse=True` for descending order. You can specify a custom sorting function using the `key` argument.

9. **reverse()**: Reverses the order of elements in the list.

10. **copy()**: Returns a shallow copy of the list.

11. **clear()**: Removes all elements from the list, leaving it empty.

12. **len(iterable)**: Returns the number of elements in the list.

Here's an example demonstrating some of these list methods:

```python
my_list = [1, 2, 3, 4, 5]

my_list.append(6)           # Adds 6 to the end
my_list.extend([7, 8, 9])   # Extends the list
my_list.insert(0, 0)        # Inserts 0 at index 0
my_list.remove(5)           # Removes the first occurrence of 5
popped_value = my_list.pop(2)  # Removes and returns the element at index 2
index_of_4 = my_list.index(4)  # Finds the index of 4
count_of_3 = my_list.count(3)  # Counts the occurrences of 3
my_list.sort()               # Sorts the list in ascending order
my_list.reverse()            # Reverses the list
shallow_copy = my_list.copy() # Creates a shallow copy
my_list.clear()              # Clears the list, making it empty
```
# Using a List as a Stack and Queue in Python

In Python, you can use a list to implement both a stack and a queue, two fundamental data structures for managing collections of items.

## Using a List as a Stack (Last-In-First-Out - LIFO)

A stack is a data structure that follows the Last-In-First-Out (LIFO) principle. You can use a list as a basic stack by employing the `append()` method to push elements onto the stack and the `pop()` method to remove and retrieve the top element.

### Example of Using a List as a Stack

```python
stack = []

# Push elements onto the stack
stack.append(1)
stack.append(2)
stack.append(3)

# Pop elements from the stack
top_element = stack.pop()
```
## Using a List as a Queue (First-In-First-Out - FIFO)

A queue is a data structure that adheres to the First-In-First-Out (FIFO) principle. You can implement a simple queue using a list by using the append() method to enqueue elements at the back and the pop(0) method to dequeue elements from the front.

### Example of Using a List as a Queue

```python
queue = []

# Enqueue elements at the back of the queue
queue.append(1)
queue.append(2)
queue.append(3)

# Dequeue elements from the front of the queue
front_element = queue.pop(0)

```

It is also possible to use a list as a queue, where the first element added is the first element retrieved (“first-in, first-out”); however, lists are not efficient for this purpose. While appends and pops from the end of list are fast, doing inserts or pops from the beginning of a list is slow (because all of the other elements have to be shifted by one). 
```python
from collections import deque

queue =deque(["Eric","John","Michael"])
print(queue)
queue.append("Terry")
print(queue)
queue.append("Graham")
print(queue)
queue.popleft()
print(queue)
queue.popleft()
print(queue)

Results:
deque(['Eric', 'John', 'Michael'])
deque(['Eric', 'John', 'Michael', 'Terry'])
deque(['Eric', 'John', 'Michael', 'Terry', 'Graham'])
deque(['John', 'Michael', 'Terry', 'Graham'])
deque(['Michael', 'Terry', 'Graham'])
```

# List Comprehension


