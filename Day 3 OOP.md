# What os OOP?

Object-oriented programming System (OOPs) is a programming paradigm based on the concept of “objects” that contain data and methods. The primary purpose of object-oriented programming is to increase the flexibility and maintainability of programs. Object oriented programming brings together data and its behaviour(methods) in a single location(object) makes it easier to understand how a program works. Java is mature OOP language.

# Fundamentals of OOP

**1. Classes and Objects:**

+ In Java, a class is a blueprint or a template for creating objects. It defines the properties (attributes) and behaviors (methods) that objects of the class will have.. 

```java
class Car:
   public class Car {
    // Attributes
    String brand;
    String model;
    int year;

    // Methods
    void start() {
        System.out.println("The car is starting.");
    }

    void drive() {
        System.out.println("The car is in motion.");
    }
}
```
+ **An object** is an instance of a class. It is a concrete realization of the properties and behaviors defined by its class
```java
public class Main {
    public static void main(String[] args) {
        // Creating an object of the Car class
        Car myCar = new Car();

        // Setting values for object properties
        myCar.brand = "Toyota";
        myCar.model = "Camry";
        myCar.year = 2022;

        // Calling methods on the object
        myCar.start();
        myCar.drive();
    }
}
```
## Features of OOP – Core features

The four main features of OOP are:

1. **Encapsulation**
+ Encapsulation n Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as data hiding.

### To achieve encapsulation in Java −

+ Declare the variables of a class as private.
+ Provide public setter and getter methods to modify and view the variables values.

```java
    public class BankAccount {
    // Private attributes
    private String accountNumber;
    private double balance;

    // Public methods for accessing and modifying data
    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        balance += amount;
    }

    public void withdraw(double amount) {
        if (amount <= balance) {
            balance -= amount;
        } else {
            System.out.println("Insufficient funds");
        }
    }
}
```

2. **Abstraction**
+ Abstraction is a process of hiding the implementation details from the user, only the functionality will be provided to the user. In other words, the user will have the information on what the object does instead of how it does it. In Java, abstraction is achieved using Abstract classes and interfaces.
```java
// Abstract class representing a shape
abstract class Shape {
    // Abstract method to calculate area
    abstract double calculateArea();
    
    // Concrete method
    void displayArea() {
        System.out.println("Area: " + calculateArea());
    }
}

// Concrete subclass representing a rectangle
class Rectangle extends Shape {
    // Attributes
    double length;
    double width;

    // Constructor
    Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    // Implementation of abstract method
    @Override
    double calculateArea() {
        return length * width;
    }
}

// Concrete subclass representing a circle
class Circle extends Shape {
    // Attribute
    double radius;

    // Constructor
    Circle(double radius) {
        this.radius = radius;
    }

    // Implementation of abstract method
    @Override
    double calculateArea() {
        return Math.PI * radius * radius;
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating objects of concrete subclasses
        Rectangle rectangle = new Rectangle(5, 10);
        Circle circle = new Circle(7);

        // Using the abstract class reference to access common behavior
        Shape shape1 = rectangle;
        Shape shape2 = circle;

        // Calling methods without knowing the specific subclass implementation
        shape1.displayArea(); // Output: Area: 50.0
        shape2.displayArea(); // Output: Area: 153.93804002589985
    }
}
Results:
// In this example, the Shape class is an abstract class with an abstract method calculateArea(). Concrete subclasses (Rectangle and Circle) provide their own implementations of the calculateArea() method. The displayArea() method is a concrete method in the abstract class, demonstrating that abstract classes can have both abstract and concrete methods. The Main class demonstrates abstraction by creating objects of the concrete subclasses and using the abstract class reference to access common behavior without knowing the specific implementation details of each subclass.
```
3. **Inheritance**
+ Inheritance can be defined as the process where one class acquires the properties (methods and fields) of another. With the use of inheritance, the information is made manageable in a hierarchical order.

The class which inherits the properties of other is known as subclass (derived class, child class) and the class whose properties are inherited is known as superclass (base class, parent class).

**extends** is the keyword used to inherit the properties of a class. In the example below class **Sub** inherits some of the properties from class **Super**.

```java
public class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

public class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}
```

4. **Polymorphism**

+ Polymorphism means to process objects differently based on their data type. In other words, it means, one method with multiple implementations, for a certain class of action. And which implementation to be used is decided at runtime depending upon the situation (i.e., data type of the object)

This can be implemented by designing a generic interface, which provides generic methods for a certain class of action and there can be multiple classes, which provides the implementation of these generic methods.

polymorphism can be implemented in two ways:

+ **Overloading** in simple words means more than one method having the same method name that behaves differently based on the arguments passed while calling the method. This called static because, which method to be invoked is decided at the time of compilation.
+ **Overriding** means a derived class is implementing a method of its super class. The call to overriden method is resolved at runtime, thus called runtime polymorphism.

## Other features of OOP

1. **Coupling:**

+ **Definition:** Coupling refers to the degree of dependence between different modules or classes in a system. Low coupling is desirable as it indicates that changes in one part of the system are less likely to affect other parts.
+ **Example:** If class A depends on class B, changes in the implementation of class B should not require changes in class A. Loose coupling is achieved by minimizing dependencies between classes.

2. **Cohesion:**

+ **Definition**: Cohesion measures how closely the methods and attributes within a single module or class are related to each other. High cohesion is desirable as it indicates that the class or module has a single, well-defined responsibility.
+ **Example:** A class that only handles file I/O operations and nothing else exhibits high cohesion. On the other hand, a class that handles file I/O, user input, and data processing may have lower cohesion.
3. **Association:**

+ **Definition:** Association represents a relationship between two or more classes. It can be a simple association, one-way association, or two-way association, and it can be either a composition or an aggregation.
+ **Example:** In a class diagram, a line connecting two classes with an arrow indicates an association. For example, a **Student** class may be associated with a **Course** class in a university system.
4. **Aggregation:**

+ **Definition:** Aggregation is a special form of association where one class contains another class, but the contained class can exist independently. It represents a "has-a" relationship.
+ **Example:** If a **University** class has a collection of **Departments**, it's an aggregation. The **Department** objects can exist independently of the **University**.
5. **Composition:**

+ **Definition:** Composition is a stronger form of aggregation where the lifetime of the contained object is dependent on the containing object. If the containing object is destroyed, the contained object is also destroyed.
+ **Example:** If a **Car** class is composed of Engine and Wheels classes, the **Engine** and **Wheels** are part of the **Car**, and if the **Car** is destroyed, the **Engine** and **Wheels** are also destroyed.