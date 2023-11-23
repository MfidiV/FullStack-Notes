# What is Java?
Java is a popular programming language, created in 1995.

It is owned by Oracle, and more than 3 billion devices run Java.

It is used for:

+ Mobile applications (specially Android apps)
+ Desktop applications
+ Web applications
+ Web servers and application servers
Games
+ Database connection
And much, much more!

# Why Use Java?
+ Java works on different platforms (Windows, Mac, Linux, Raspberry Pi, etc.)
+ It is one of the most popular programming language in the world
+ t has a large demand in the current job market
+ It is easy to learn and simple to use
+ It is open-source and free
+ It is secure, fast and powerful
+ It has a huge community support (tens of millions of developers)
+ Java is an object oriented language which gives a clear structure to programs and allows code to be reused, lowering development costs
+ As Java is close to C++ and C#, it makes it easy for programmers to switch to Java or vice versa

# Typical Structure of a Java program

**1.Package Declaration:**

+ Defines the package to which the Java class belongs.
+ Helps in organizing classes and avoiding naming conflicts.

**2. Import Statements:**

+ Used to bring in classes from other packages.
+ Multiple import statements can be used in a program.
+ Reduces the need for fully qualified class names.

**3. Comments:**


+ Provide information about variables, methods, classes, or any code statement.
+ Single-line comments start with //.
+ Multi-line comments are enclosed between /* and */.

**4. Class Definition:**

Includes the name given to the Java class.
The name is used when creating objects of the class in other classes or programs.

**5.Main Method:**

+ The entry point for a Java program.
+ Execution of a Java application starts from the main method.
+ All Java programs must have a main method.

**6. Methods/Behaviors:**

+ A set of instructions forming a purposeful functionality.
+ Enclosed in a method to avoid repeating the same instructions.
+ Methods can take parameters, allowing them to be more flexible and reusable.

```python
package com.cititraining.edu.firstjava; <-  package statement

import System.io. *; <-  import statement

 

public class HelloWorld {<- Class definition

 

   /* This is my first java program. <- Multiline comment

    * This will print 'Hello World' as the output

    */

   public static void main (String [] args) {<- main Method

      printHelloWorld();

   }

   public void printHelloWorld () {//Method

           System.out.println("Hello World"); // This prints Hello World <- Singleline comment

}

}
```