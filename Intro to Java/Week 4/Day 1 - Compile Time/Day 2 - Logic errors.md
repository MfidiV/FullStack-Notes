## `LOGICAL ERRORS`


Logic errors, also known as bugs, occur when there is a flaw in the logical structure of a program. Unlike syntax errors, which prevent the program from compiling, logic errors may allow the program to compile successfully but cause unexpected behavior or incorrect results during runtime. 

examples:

```java
public class LogicalErrorExample {

    public static void main(String[] args) {
        int num1 = 10;
        int num2 = 20;

        // Incorrectly swapping values
        swapValues(num1, num2);

        System.out.println("After swapping: ");
        System.out.println("num1: " + num1); // Prints 10 (expected: 20)
        System.out.println("num2: " + num2); // Prints 20 (expected: 10)
    }

    // Incorrect method for swapping values
    public static void swapValues(int a, int b) {
        int temp = a;
        a = b;
        b = temp;
    }
}
// In this example, the swapValues method is intended to swap the values of two variables (num1 and num2). However, due to the way Java passes parameters (by value), the original values of num1 and num2 in the main method remain unchanged.

Output:
After swapping :
num1: 10
num2: 20

// This is incorrect because the swapValues method does not actually modify the values of num1 and num2 in the main method. To fix this logical error, you need to use a different approach, such as passing an array or using a class to hold the values.
```

## `DEBBUGING`
Debugging is a methodical process of finding and reducing the number of bugs(errors), or defects (malfunction pieces of code), in a computer program. All errors stem from a one basic premise: something thought to be right, was in fact wrong. Due to this simple principle, truly bizarre bugs can defy logic, making debugging a program or application challenging.

a debugging process can be divided into four main steps:
- Localising a bug
- Classifying a bug
- Understanding a bug
- Repairing a bug.

### `Localising a bug`

Inexperienced programmers often view error localisation as an easy task, leading to deception. All errors stem from a mistake, and it's crucial to locate the error source before attempting to fix it, as it can be challenging to identify and fix.


### `Classifying a bug`
Errors often have a common background, allowing for classification. Classifying them as compile, runtime, or logic errors can help fix them, but incorrect classification can be costly.

### `Understanding a bug`
Before attempting to fix an error, it's crucial to fully understand it to avoid further damage to the code.


 A check-list can help

- ensure a correct investigation,
- including avoiding confusion between observing symptoms and 
- finding the root cause, 
- and verifying the error is a programming error.

## `Repairing a bug.`
The final step in the debugging process is error fixing. Repairing an error is more than modifying code. Any fixes must be documented in the code properly. More important, learning from mistakes is an effective attitude: it is good practice filling a small file with detailed explanations about the way the bug was discovered and corrected.

**``General debugging``**

1. Exploitting compiler feature
2. The abused prinln() debugging technique
3. Logging
4. Defensive programming and assertions
5. ACI debugging technique
6. Reading the code through
7. The debugger
 
 ### Common errors in Java

 Java software development can lead to various errors, but most are avoidable. Some common errors include compiler errors, which occur when code is run through the compiler, and unclosed string literals, which end without quotation marks. The "illegal start of an expression" error occurs when the compiler expects an expression to be found, but it is often caused by bad code. The "cannot find symbol" error occurs when the compiler does not understand the meaning of an identifier, and there are several reasons for this error.

The "public class XXX should be in file" error occurs when the class and Java program filename do not match, and the code will only be compiled when the class and Java file are the same. The "incompatible types" error occurs when an assignment statement tries to pair a variable with an expression of types, and the developer may need to change what the code is expected to do. By addressing these common Java software errors, developers can improve their code and avoid potential issues.

The "Invalid Method Declaration; Return Type Required" error in Java software occurs when the return type of a method is not explicitly stated in the method signature. This error can occur due to forgetting to state the type or incorrect constructor names. The "missing return statement" error occurs when a method does not have a return statement, which is necessary for non-void types. The "possible loss of precision" error occurs when more information is assigned to a variable than it can hold, requiring the code to explicitly declare the variable as a new type. The "reached end of file while parsing" error occurs when the program is missing the closing curly brace ("}"), which can be fixed by placing it at the end of the code. Unreachable statements, variables might not have been initialized, operators cannot be applied to, inconvertible types, missing return value, cannot return a value from a void method, and non-static variables cannot be referenced from a static context can also trigger this error.

