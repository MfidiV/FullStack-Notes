# Inheritance in Python

One of the core concepts in object-oriented programming (OOP) languages is **inheritance**. 

It is a mechanism that allows you to create a hierarchy of classes that share a set of properties and methods by deriving a class from another class. 

Inheritance is the capability of one class to derive or inherit the properties from another class.

## Benefits of Inheritance:

Inheritance allows you to inherit the properties of a class, i.e., base class to another, i.e., derived class. The benefits of Inheritance in Python are as follows:

1. It represents real-world relationships well.
2. It provides the reusability of code, allowing the addition of features to a class without modifying it.
3. It is transitive in nature, meaning if class B inherits from class A, then all subclasses of B would automatically inherit from class A.
4. Inheritance offers a simple, understandable model structure.
5. It results in less development and maintenance expenses.

## Python Inheritance Syntax:

The syntax for simple inheritance in Python is as follows:

```python
class BaseClass:
    {Body}

class DerivedClass(BaseClass):
    {Body}
```

## Creating a Parent Class:

A parent class is a class whose properties are inherited by the child class. Let's create a parent class called **Person** with a **Display** method to display the person’s information.

```python


# A Python program to demonstrate inheritance
class Person(object):
    def __init__(self, name, id):
        self.name = name
        self.id = id

    def Display(self):
        print(self.name, self.id)

Output:
Satyam 102
```

## Creating a Child Class:

A child class is a class that derives properties from its parent class. Here, Emp is another class that inherits the properties of the Person class (base class).

```python
Copy code
class Emp(Person):
    def Print(self):
        print("Emp class called")

Emp_details = Emp("Mayank", 103)
Emp_details.Display()  # calling parent class function
Emp_details.Print()    # calling child class function

Output:

Mayank 103
Emp class called

```

## Subclassing (Calling constructor of parent class):
A child class needs to identify its parent class by mentioning the parent class name in the definition of the child class.

```python
Copy code
class A:
    def __init__(self, n='Rahul'):
        self.name = n

class B(A):
    def __init__(self, roll):
        self.roll = roll

object = B(23)
print(object.name)  # Produces an error
```
## The super() Function:
The **super()** function returns objects that represent the parent class, allowing access to the parent class’s methods and attributes in the child class.

```python
class Person():
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print(self.name, self.age)

class Student(Person):
    def __init__(self, name, age):
        self.sName = name
        self.sAge = age
        super().__init__("Rahul", age)

    def displayInfo(self):
        print(self.sName, self.sAge)

obj = Student("Mayank", 23)
obj.display()
obj.displayInfo()
```

## Adding Properties:
Inheritance allows adding new properties to the child class. Here, we add a new property, 'dob' (date of birth), to the **Student** class.

```python
class Person():
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print(self.name, self.age)

class Student(Person):
    def __init__(self, name, age, dob):
        self.sName = name
        self.sAge = age
        self.dob = dob
        super().__init__("Rahul", age)

    def displayInfo(self):
        print(self.sName, self.sAge, self.dob)

obj = Student("Mayank", 23, "16-03-2000")
obj.display()
obj.displayInfo()

Output:
#Here we can see that we added a new property to the child class, i.e., date of birth (dob).

Rahul 23
Mayank 23 16-03-2000
```
## Different types of Python Inheritance:
1. **Single Inheritance:** When a child class inherits from only one parent class.
2. **Multiple Inheritances:**
 When a child class inherits from multiple parent classes.

```python
# Python example to show the working of multiple
# inheritance
 
class Base1(object):
    def __init__(self):
        self.str1 = "Geek1"
        print("Base1")
 
 
class Base2(object):
    def __init__(self):
        self.str2 = "Geek2"
        print("Base2")
 
 
class Derived(Base1, Base2):
    def __init__(self):
 
        # Calling constructors of Base1
        # and Base2 classes
        Base1.__init__(self)
        Base2.__init__(self)
        print("Derived")
 
    def printStrs(self):
        print(self.str1, self.str2)
 
 
ob = Derived()
ob.printStrs()


Output: 
Base1
Base2
Derived
Geek1 Geek2
```

3. **Multilevel Inheritance:** When a child class inherits from a parent, and another class inherits from this child.
4. **Hierarchical Inheritance:** More than one derived class can be created from a single base.
5. **Hybrid Inheritance:** A blend of more than one type of inheritance.

## Private Members of the Parent Class:
Private instance variables of the parent class can be made inaccessible to the child class by adding double underscores before their names.
```python
class C(object):
    def __init__(self):
        self.c = 21
        self.__d = 42

class D(C):
    def __init__(self):
        self.e = 84
        C.__init__(self)

object1 = D()
print(object1.c)   # 21
print(object1.__d)  # Error

# Output : 
# Here we can see that when we tried to print the variable ‘c’, its value 21 is printed on the console. Whereas when we tried to print ‘d’, it generated the error. This is because the variable ‘d’ is made private by using the underscores. It is not available to the child class ‘D’ and hence the error.

21
  File "/home/993bb61c3e76cda5bb67bd9ea05956a1.py", line 16, in 
    print (object1.d)                     
AttributeError: type object 'D' has no attribute 'd'

```