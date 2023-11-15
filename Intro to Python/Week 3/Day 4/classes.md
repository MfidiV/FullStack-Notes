# Python Classes Notes

## Classes

In Python, a class is a blueprint for creating objects. Objects are instances of a class and can have attributes (characteristics) and methods (functions) associated with them. Classes provide a way to bundle data and functionality together.

## Names and Objects

- Everything in Python is an object.
- Objects have an identity, a type, and a value.
- Names refer to objects, and multiple names can refer to the same object.

## Python Scopes and Namespaces

- A namespace is a container for a set of identifiers (names) to avoid naming conflicts.
- Scopes define the region of a program where a namespace is directly accessible.
- Python has local, enclosing, global, and built-in scopes.

## Class Definition Syntax

The basic syntax for defining a class in Python is:

```python
class ClassName:
    # class body
```
## Class Objects:

- A class itself is an object in Python. It is an instance of the metaclass.


- Class objects support attribute reference and instantiation.

## Instance Objects:

- An instance is an individual object created from a class.
- Instances have attributes and can invoke methods defined in the class.


## Method Objects:

- In Python, methods are functions defined within a class.


- Method objects are created on-the-fly and contain both the function and the instance it is bound to.
 
## Class and Instance Variables:

- Class variables are shared by all instances of a class. They are defined within the class but outside any methods.
- Instance variables are specific to each instance of a class. They are usually defined in the constructor (__init__ method).

## Random Remarks:

This might refer to miscellaneous points about classes in Python.
Python supports multiple inheritance, allowing a class to inherit from more than one base class.
Class methods are marked with the @classmethod decorator, and instance methods take self as the first parameter.
