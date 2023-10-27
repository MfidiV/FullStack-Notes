## Casting in Python

Casting, also known as type casting or type conversion, is the process of explicitly assigning a data type to a variable or converting a value from one data type to another. In Python, you can use casting functions to change the data type of a variable or value.

## Python Casting Functions

Python provides several built-in casting functions, including:

1. **`int()`:** Converts a value to an integer data type.

2. **`float()`:** Converts a value to a floating-point (decimal) data type.

3. **`str()`:** Converts a value to a string data type.

4. **`bool()`:** Converts a value to a boolean data type (True or False).

### Casting

- You can convert a string to an integer using the `int()` function.
- Example: `num_str = "42"`; `num = int(num_str)` results in `num` being an integer.
- You can convert an integer to a string using the `str()` function.
- Example: `x = 42`; `x_str = str(x)` results in `x_str` being a string.
### Casting Examples


```python
num_str = "42"
num = int(num_str)  # Converts the string to an integer
```

 ```Python
 Examples:
 # Casting to Integer
num_str = "42"
num = int(num_str)  # Converts the string to an integer

# Casting to Float
pi_str = "3.14159"
pi = float(pi_str)  # Converts the string to a float

# Casting to String
x = 42
x_str = str(x)  # Converts the integer to a string

# Casting to Boolean
flag = 0
bool_flag = bool(flag)  # Converts the integer to a boolean (False in this case)

 ```
 ## String Format for Numbers

When working with strings representing numbers, the following rules apply:

- The string should only contain numbers.
- Other than numbers, the following are allowed:
  - Only one dot (.) character. This indicates that the decimal part starts after the dot (.) character.
  - A '+' or '−' character at the beginning of the string. This indicates that the number is either positive or negative.
