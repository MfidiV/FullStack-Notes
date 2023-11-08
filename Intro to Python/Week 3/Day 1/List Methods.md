1. **append(x)**: Adds an element `x` to the end of the list.

```Python
    currencies = ['Dollar', 'Euro', 'Pound']

# append 'Yen' to the list
currencies.append('Yen')

print(currencies)

# Output: ['Dollar', 'Euro', 'Pound', 'Yen']
```

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