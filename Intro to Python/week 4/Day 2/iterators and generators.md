
# Difference Between Iterator VS Generator

A process that is repeated more than one time by applying the same logic is called an **Iteration**. 

 In programming languages like python, a loop is created with few conditions to perform iteration till it exceeds the limit
 
 . If the loop is executed 6 times continuously, then we could say the particular block has iterated 6 times. 

## Iterator
An iterator is an **object** which contains a countable number of values and it is used to iterate over iterable objects like list, tuples, sets, etc. 

Iterators are implemented using a class and a local variable for iterating is not required here, It follows lazy evaluation where the evaluation of the expression will be on hold and stored in the memory until the item is called specifically which helps us to avoid repeated evaluation.

 As lazy evaluation is implemented, it requires only 1 memory location to process the value and when we are using a large dataset then, wastage of RAM space will be reduced the need to load the entire dataset at the same time will not be there.

**Using an iterator:**

+ **iter()** keyword is used to create an iterator containing an iterable object.
+ **next()** keyword is used to call the next element in the iterable object.
After the iterable object is completed, to use them again reassign them to the same object.

```python
iter_list = iter(['Geeks', 'For', 'Geeks']) 
print(next(iter_list)) 
print(next(iter_list)) 
print(next(iter_list)) 

Output:

Geeks
For
Geeks  
```
## Generators
It is another way of creating iterators in a simple way where it uses the keyword **“yield”** instead of returning it in a defined function.

 Generators are implemented using a function. Just as iterators, generators also follow lazy evaluation. 
 
 Here, the yield function returns the data without affecting or exiting the function.
  
 It will return a sequence of data in an iterable format where we need to iterate over the sequence to use the data as they won’t store the entire sequence in the

 ```python
 def sq_numbers(n): 
	for i in range(1, n+1): 
		yield i*i 


a = sq_numbers(3) 

print("The square of numbers 1,2,3 are : ") 
print(next(a)) 
print(next(a)) 
print(next(a)) 


Output:

The square of numbers 1,2,3 are :  
1
4
9
 ```

 ## Table of difference between Iterator vs Generators

 | Feature                    | Iterator                                      | Generator                                     |
| -------------------------- | --------------------------------------------- | --------------------------------------------- |
| **Implementation**         | Implemented using a class.                    | Implemented using a function with `yield`.    |
| **Local Variables**        | No local variables used.                      | Local variables before `yield` are stored.    |
| **Memory Usage**           | Stores all values in memory.                  | Uses lazy evaluation, not storing all values. |
| **Lazy Evaluation**        | No lazy evaluation.                            | Follows lazy evaluation.                      |
| **Usage**                  | Iterates or converts other objects to iterator using `iter()`. | Used in loops to generate an iterator by returning values without affecting the loop. |
| **Functions**              | Uses `iter()` and `next()` functions.         | Uses `yield` keyword.                         |
| **Relationship**           | Every iterator is not a generator.             | Every generator is an iterator.               |
