# Java Identifiers

Identifiers are the names of variables, methods, classes, packages and interfaces. Unlike literals they are not the things themselves, just ways of referring to them. In the HelloWorld program, HelloWorld,  args, main and println are identifiers.

Identifiers must be composed of letters, numbers, the underscore _ and the dollar sign $. Identifiers may only begin with a letter, the underscore or a dollar sign.

+ **Camel case consists** of compound words or phrases such that each word or abbreviation begins with a capital letter or first word with a lowercase letter, rest all with capital.

+ **Java Modifiers**
Modifiers are keywords that you add to those Identifiers to change their meanings. Java language has a wide variety of modifiers, including the following −

+ Java Access Modifiers
+ Non-Access Modifiers

## Java Access Modifiers
+ **Public** Accessible from other class
```java
public class MyClass {
    public void myMethod() {
        // Code here
    }
}
```

+ **Private** Accessible only within the same class

```java
public class MyClass {
    private int myAttribute;

    private void myMethod() {
        // Code here
    }
}

```

+ **Protected** Accessible within the same package and by subclasses (even if they are in different packages)

```java
package mypackage;

public class MyClass {
    protected void myMethod() {
        // Code here
    }
}

```

+ **Default (Package-Private, No Modifier):**
 Accessible within the same package. If no modifier is specified, it is considered package-private.
 ```java
 package mypackage;

class MyClass {
    // Code here
}
 ```

 ## Non-access modifiers for attribuutes and methods

 + **static:** The static keyword denotes that a member (attribute or method) belongs to the class rather than an instance of the class.

 ```java
 public class MyClass {
    public static int myStaticAttribute;
    public static void myStaticMethod() {
        // Code here
    }
}
```
+ **final:** A final attribute cannot be changed after it is initialized. A final method cannot be overridden by subclasses

```java
public class MyClass {
    public final int myFinalAttribute = 10;

    public final void myFinalMethod() {
        // Code here
    }
}
```
+ **abstract:** An abstract method is declared in an abstract class and has no implementation in the abstract class. It must be implemented by a concrete subclass.

```java
public abstract class AbstractClass {
    public abstract void myAbstractMethod();
}
```
+ **syncronized** A synchronized method is used to control the access of multiple threads to a method. Only one thread can execute a synchronized method at a time.
```java
public class MyClass {
    public synchronized void mySynchronizedMethod() {
        // Code here
    }
}
```


