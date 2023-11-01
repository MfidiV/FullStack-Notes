# Module / library

A module in programming refers to a self-contained unit of code that typically contains functions, classes, and variables related to a specific purpose. 

Modules are used to organize and manage code in a structured manner, enabling code reusability, maintainability, and collaboration among developers.

# Examples of Modules

1.The os module provides functions for interacting with the operating system. It can be used for tasks like file and directory manipulation.

```python
import os

# Get the current working directory
current_directory = os.getcwd()
print("Current Directory:", current_directory)

# List files and directories in a directory
files_and_dirs = os.listdir(current_directory)
print("Files and Directories:", files_and_dirs)

# Create a new directory
new_directory = "my_new_directory"
os.mkdir(new_directory)

# Check if a path exists and is a directory
if os.path.exists(new_directory) and os.path.isdir(new_directory):
    print(f"{new_directory} exists and is a directory.")

```

2.The random module allows you to generate random numbers and make random selections.
```python
import random

# Generate a random integer between 1 and 10
random_number = random.randint(1, 10)
print("Random Number:", random_number)

# Select a random item from a list
my_list = ["apple", "banana", "cherry", "date"]
random_fruit = random.choice(my_list)
print("Random Fruit:", random_fruit)

```

3.The math module provides mathematical functions and constants.
```python
import math

# Calculate the square root of a number
sqrt_value = math.sqrt(25)
print("Square Root:", sqrt_value)

# Calculate the value of pi
pi_value = math.pi
print("Pi:", pi_value)

```

4.datetime Module:
The datetime module allows you to work with date and time values.
```python
import datetime

# Get the current date and time
current_datetime = datetime.datetime.now()
print("Current Date and Time:", current_datetime)

# Format a date as a string
formatted_date = current_datetime.strftime("%Y-%m-%d %H:%M:%S")
print("Formatted Date:", formatted_date)

```

# Mechanism of Python modules
The moment a module is imported through a program, Python Interpreter fetches the module from either of the following locations:

 + 1.Program directory -  Default directory(directory on pythhonpath variable)

 + 2.Listing of Modules - >>> help(“module”) 

# Importing modules

## Importing modules from Python Standard path
```python
import math
```
## Importing Modules from other Sources
```python
python -m pip3 install numpy
```
+ 

# Difference between a module and a package in Pyton
Python modules and Python packages are both mechanisms for organizing and structuring code in a Python program, but they serve different purposes and operate at different levels of code organization.

## Modules
Modules are single files or scripts that contain Python code, including functions, classes, and variables.

## Packages
Packages are directories that contain one or more Python modules. They provide a way to organize and group related modules into a hierarchical structure.

