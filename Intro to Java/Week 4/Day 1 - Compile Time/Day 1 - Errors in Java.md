# `ERRORS IN JAVA`

In java errors occurs when your program fails to compile or program crashes when executing or the program doesn’t produce the desired results. You can encounter all or some these scenarios as a programmer/ developer, and your ability to fix or rectify errors is one of the most important skills you can possess as a programmer.

- Complier Errors
- Runtime Errors 
- Logic Errors

## `Compiler Errors/Syntax Error`

**Compile errors** or **syntax errors** occur when a code is written that the compiler cannot understand or translate into Java byte code. These errors are caused by breaking the language's rules, such as forgetting semicolons or misspelled variables, or violating Java's rules, such as using a non-static variable from a static function.

Example:
```java
public class Example {
    public static void main(String[] args) {
        System.out.println("Hello, World!")
    }
}
// In this example, there is a missing semicolon at the end of the System.out.println statement, causing a syntax error.
```
## `Runtime Errors`

Runtime errors occur during program execution, disrupting normal flow and causing abnormal termination,also refered to as exceptions. 


They can occur due:
- A user has entered an invalid data. 
- A file that needs to be opened cannot be found. 
- A network connection has been lost in the middle of communications 
- or the JVM has run out of memory. 

Caused by user, programmer, or physical resource failures, runtime errors are not picked by the compiler and only occur during program execution.

Example:
```java
public class Example {
    public static void main(String[] args) {
        int x = 5;
        int y = 0;
        int z = x / y; 
        // This will result in an ArithmeticException at runtime
    }
}
```
# Exception Handling in Java

In Java, you can handle exceptions using the `try`, `catch`, and `finally` blocks. Here's a brief explanation of how these blocks work together to handle exceptions:

## 1. try Block:

The `try` block contains the code that might throw an exception. It encloses the statements that are expected to cause an exception. If an exception occurs within the `try` block, the control is transferred to the corresponding `catch` block.

```java
try {
    // code that may throw an exception
} catch (ExceptionType1 e1) {
    // handle exception of type ExceptionType1
} catch (ExceptionType2 e2) {
    // handle exception of type ExceptionType2
} finally {
    // optional: code that always executes, whether an exception occurred or not
}


