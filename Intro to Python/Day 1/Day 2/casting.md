## Casting in Python

Casting, also known as type casting or type conversion, is the process of explicitly assigning a data type to a variable or converting a value from one data type to another. In Python, you can use casting functions to change the data type of a variable or value.

### Casting to Integer

You can use the `int()` function to convert a value to an integer data type.

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