# Modules

Modules are a way to organize and reuse code by breaking it into smaller, manageable pieces.
A module in programming refers to a self-contained unit of code that typically contains functions, classes, and variables related to a specific purpose. Modules are used to organize and manage code in a structured manner, enabling code reusability, maintainability, and collaboration among developers. Here's a brief introduction to modules

# Using Functions
We create functions by providing three pieces of information. The name of the function, a list of zero or more parameters, and, optionally, a block of code which provides the return value (a function can return nothing).
We must make a firm distinction between an argument value and a parameter:
+ Arguments - The argument is the object used in an application of a function; it may be referenced by other variables or objects.
+ Parameters - The parameter is a variable name that is part of the function and is a local variable within the function body.

  We define a function by using the following syntax:
    
```python
    def function_name(parameter <,...>):

#suite
```
There are three types of functions in Python:
+ Ordinary functions - functions that follow mathematical procedures. They will receive an argument, perform a specific calculation with the argument, and return a result.
+ Procedure functions - functions normally do not return a result; they are called to execute a procedure. For example a function can be created to set up a connection to a database.
+ Factory functions -  functions do not take parameters. The function generates values. Some factory functions work by accessing an object encapsulated in a module. For example, you will access the random number generator encapsulated in the random module.

Function must be defined before its called.

# Random modules
The basic random() function generates a random floating point number as output. Python uses the Mersenne Twister as the core generator.

The functions supplied by the random module are actually bound methods of a hidden instance of the random.Random class.
```Python
    
 

import random

def lotto_number():
  """The result from a lotto number draw is returned."""
    num = random.randrange(1,47)
    return str(num)

for n in range(1,6):

  print (lotto_number())

  
```
```python
import random

# Generate a random integer between 1 and 10
random_number = random.randint(1, 10)
print(random_number)

  ## Random functions
  + randint(self, x, y) - Return random integer in range [x, y], including both end points.

    + sample(self, popu, i) - 
```
## Recursive functions
A recursive function or method is a programming construct where a function calls itself in order to solve a problem. Recursion is a powerful and elegant technique that can be used to solve problems that can be broken down into smaller, similar subproblems.