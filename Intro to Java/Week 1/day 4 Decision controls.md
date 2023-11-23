# INTRODUCTION TO DECISION CONTROL

When we need to execute a set of statements based on a condition then we need to use control flow statements.

Decision making structures have one or more conditions to be evaluated or tested by the program, along with a statement or statements that are to be executed if the condition is determined to be true, and optionally, other statements to be executed if the condition is determined to be false.

## The if statements
+ Use the *if* statement to specify a block of Java code to be executed if a condition is *true*.

example:
```java
if (20 > 18) {
  System.out.println("20 is greater than 18");
}

// We can also est variables
int x = 20;
int y = 18;
if (x > y) {
  System.out.println("x is greater than y");
}
```
## else statement
+ Use the else statement to specify a block of code to be executed if the condition is false
 ```java
 int time = 20;
    if (time < 18) {
        System.out.println("Good day.");
    } else {
         System.out.println("Good evening.");
    }
// Outputs "Good evening."
 ```
 ## else if statement

 + Use the else if statement to specify a new condition if the first condition is false

 ```java
 int time = 22;
if (time < 10) {
  System.out.println("Good morning.");
} else if (time < 18) {
  System.out.println("Good day.");
} else {
  System.out.println("Good evening.");
}
// Outputs "Good evening."
 ```
## Short hand if...else(Ternary operator)

There is also a short-hand if else, which is known as the ternary operator because it consists of three operands.
It can be used to replace multiple lines of code with a single line, and is most often used to replace simple if else statements:

Example:
```java
int time = 20;
if (time < 18) {
  System.out.println("Good day.");
} else {
  System.out.println("Good evening.");
}

// replace with - ternary

int time = 20;
String result = (time < 18) ? "Good day." : "Good evening.";
System.out.println(result);
```

## Switch statements

A switch statement allows a variable to be tested for equality against a list of values. Each value is called a case, and the variable being switched on is checked for each case.

Switch case statement is used when we have number of options (or choices) and we may need to perform a different task for each choice.
General rules to a switch statement are:

+ The variable used in a switch statement can only be integers, convertible integers (byte, short, char), strings and enums.
+ You can have any number of case statements within a switch. Each case is followed by the value to be compared to and a colon.
+ The value for a case must be the same data type as the variable in the switch and it must be a constant or a literal.
+ When the variable being switched on is equal to a case, the statements following that case will execute until a break statement is reached.
+ When a break statement is reached, the switch terminates, and the flow of control jumps to the next line following the switch statement.
+ Not every case needs to contain a break. If no break appears, the flow of control will fall through to subsequent cases until a break is reached.
+ A switch statement can have an optional default case, which must appear at the end of the switch. + The default case can be used for performing a task when none of the cases is true. No break is needed in the default case.

```java
int day = 4;
switch (day) {
  case 1:
    System.out.println("Monday");
    break;
  case 2:
    System.out.println("Tuesday");
    break;
  case 3:
    System.out.println("Wednesday");
    break;
  case 4:
    System.out.println("Thursday");
    break;
  case 5:
    System.out.println("Friday");
    break;
  case 6:
    System.out.println("Saturday");
    break;
  case 7:
    System.out.println("Sunday");
    break;
}
// Outputs "Thursday" (day 4)
```

## The Break Keyword
When Java reaches a break keyword, it breaks out of the switch block.

This will stop the execution of more code and case testing inside the block.

When a match is found, and the job is done, it's time for a break. There is no need for more testing.

*A break can save a lot of execution time because it "ignores" the execution of all the rest of the code in the switch block.*

## The default keyword
+ The default keyword specifies some code to run if there is no case match:

```java
int day = 4;
switch (day) {
  case 6:
    System.out.println("Today is Saturday");
    break;
  case 7:
    System.out.println("Today is Sunday");
    break;
  default:
    System.out.println("Looking forward to the Weekend");
}
// Outputs "Looking forward to the Weekend"
```
*Note that if the default statement is used as the last statement in a switch block, it does not need a break.*