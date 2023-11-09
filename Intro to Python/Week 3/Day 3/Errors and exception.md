# Errors and Exceptions in Python

- Errors and exceptions are a fundamental part of programming in Python. 
- They occur when something goes wrong in your code, and Python raises an error to alert you to the issue. 
- Understanding and handling errors and exceptions is crucial for writing reliable and robust Python programs.

## Syntax Error

A **Syntax Error** also known as **parsing errors** occurs when your code violates the syntax rules of the Python programming language. It often results from typos, missing colons, or incorrect indentation.

**Example:**
```python
if x = 5:  # SyntaxError: invalid syntax
```

## Indentation Error

An **indentation error** occurs when there are inconsistencies in the use of spaces or tabs for code indentation within a block.

**Example**
```python
def my_function():
print("Hello, World!")  # IndentationError: unexpected indent
```

## Name error

A **NameError** is raised when you try to use a variable or name that is not defined in the current scope.

**Example**
```python
print(x)  # NameError: name 'x' is not defined
```

## TypeError

A **TypeError** occurs when an operation or function is applied to an object of the wrong data type.

**Example**
```python
x = "5"
y = 3
print(x + y)  # TypeError: can only concatenate str (not "int") to str
```

## IndexError

An **IndexError** is raised when you attempt to access an index that is outside the range of a sequence (e.g., a list or string).

**Example**
```python
my_list = [1, 2, 3]
print(my_list[5])  # IndexError: list index out of range
```

## KeyError

A **KeyError** is raised when you try to access a dictionary key that does not exist.

**Example**
```python
my_dict = {"name": "Alice"}
print(my_dict["age"])  # KeyError: 'age'
```

## ValueError
A **ValueError** is raised when you pass an argument to a function, and the argument's value is inappropriate.

**Example**
```python
int("abc")  # ValueError: invalid literal for int() with base 10: 'abc'

```

## FileNotFoundError
A **FileNotFoundError** is raised when you try to access a file that doesn't exist.

**Example**
```python
with open("nonexistent.txt", "r") as file:  # FileNotFoundError
    content = file read()
```

## ZeroDivisionError
A **ZeroDivisionError** occurs when you attempt to divide by zero.

**Example**
```python
result = 5 / 0  # ZeroDivisionError: division by zero
```

# Exceptions

 Errors detected during execution are called exceptions and are not unconditionally fatal


Python provides a way to handle exceptions using **try** and **except** blocks. You can catch and handle specific exceptions gracefully.

Effective use of exception handling is essential for writing reliable and maintainable code. It allows you to gracefully handle errors, provide meaningful error messages, and ensure that your programs don't crash unexpectedly. Always aim to catch only the exceptions you expect and handle them appropriately.

## Exception Handling

The basic structure of exception handling in Python involves the use of **try** and **except** blocks

**Example**
```python
try:
    x = 5 / 0
except ZeroDivisionError:
    print("Cannot divide by zero.")
```
In this example, if the code inside the try block encounters a ZeroDivisionError, the code inside the except block is executed.


##  Handling Multiple Exceptions:

You can handle multiple exceptions by specifying them in a tuple or using multiple except blocks.

```python
try:
    # Code that might raise an exception
    result = int("abc")
except (ValueError, TypeError):
    # Code to handle ValueError or TypeError
    print("Error: Invalid conversion")
except ZeroDivisionError:
    # Code to handle ZeroDivisionError
    print("Error: Division by zero")
```

## Catching All Exceptions:

You can catch all exceptions by using a generic except block, but this is generally discouraged unless you have a good reason.

**Example**

```python
try:
    # Code that might raise an exception
    result = 10 / 0
except Exception as e:
    # Code to handle any exception
    print(f"An error occurred: {e}")
```

## Finally Block:

The finally block is used to define cleanup actions that are guaranteed to be executed, whether an exception occurs or not.

```python

try:
    # Code that might raise an exception
    result = 10 / 0
except ZeroDivisionError:
    # Code to handle ZeroDivisionError
    print("Error: Division by zero")
finally:
    # Code that will be executed no matter what
    print("Cleanup: This will always run")
```

## Else Block:
The else block is executed if no exceptions are raised in the try block.

```python
try:
    # Code that might raise an exception
    result = 10 / 2
except ZeroDivisionError:
    # Code to handle ZeroDivisionError
    print("Error: Division by zero")
else:
    # Code to execute if no exception occurred
    print(f"Result: {result}")
```
## Custom Exceptions:
You can create your own custom exceptions by creating a new class that inherits from the Exception class.

```python
class CustomError(Exception):
    pass

try:
    raise CustomError("This is a custom exception")
except CustomError as ce:
    print(f"Caught custom exception: {ce}")
```    
## Raising Exceptions:
You can raise exceptions using the raise statement.

```python
def divide(x, y):
    if y == 0:
        raise ValueError("Cannot divide by zero")
    return x / y

try:
    result = divide(10, 0)
except ValueError as ve:
    print(f"Error: {ve}")
```    