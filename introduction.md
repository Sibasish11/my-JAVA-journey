###### INTRODUCTION TO JAVA PROGRAMMING LANGUAGE

### 🧠 Introduction to Java

#### 📖 What is Java?

Java is a high-level, class-based, object-oriented programming language designed to have as few implementation dependencies as possible. It is platform-independent thanks to the concept of the Java Virtual Machine (JVM), which allows compiled code to run on any system.

✅ Motto: Write Once, Run Anywhere (WORA)

### 🕰️ A Brief History of Java

Developed by: James Gosling and team at Sun Microsystems

Released in: 1995

Acquired by: Oracle Corporation in 2010

Initially created for embedded devices but later evolved into one of the most popular programming languages in the world.

### ⭐ Key Characteristics of Java

Object-Oriented – Everything is treated as an object.

Platform-Independent – Java bytecode can run on any machine with a JVM.

Simple and Secure – Easy to learn and includes security features like bytecode verification.

Multithreaded – Supports multithreaded programming for better performance.

Robust and Reliable – Includes strong memory management and exception handling.

Distributed – Supports networking and remote method invocation (RMI).

### 🧰 Java Development Kit (JDK)

The JDK is a software development environment used to develop Java applications. It includes:

JRE (Java Runtime Environment): Runs Java programs.

JVM (Java Virtual Machine): Executes Java bytecode.

Java Compiler (javac): Converts .java files into bytecode (.class files).

Development Tools: Debugger, documentation generator, etc.

### 🧱 Core Concepts of Java

1. Classes and Objects
Java is based on OOP (Object-Oriented Programming). Every Java program is a collection of classes and objects.

2. Inheritance
Allows a class to acquire properties and behaviors (methods) of another class.

3. Polymorphism
Enables one interface to be used for a general class of actions.

4. Encapsulation
Wrapping of data and methods into a single unit (class).

5. Abstraction
Hiding the internal details and showing only the functionality to the user.

### 📌 Simple Java Program

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
### 🔍 Code Explanation

public class HelloWorld: This defines a class named HelloWorld.
In Java, every program must have at least one class, and the class name should match the filename (HelloWorld.java).

-public static void main(String[] args): This is the main method, which acts as the entry point of the program.

-public means it can be accessed from anywhere.

-static means it belongs to the class, not a specific object.

-void means it doesn’t return any value.

-String[] args allows the program to accept command-line arguments.

-System.out.println("Hello, World!");: This line prints the text Hello, World! to the console.

-System.out is used to output data.

-println() prints the message followed by a newline.

# Java Program Execution Flow

Here's how a Java program runs through various layers:

```text
+---------------------+
|    Java Program     |
|     (.java file)    |
+---------------------+
         ||
         \/
+---------------------+
| Java Virtual Machine|
|        (JVM)        |
+---------------------+
         ||
         \/
+---------------------+
|  Operating System   |
+---------------------+
         ||
         \/
+---------------------+
|      Hardware       |
+---------------------+


### Explanation:
- **Java Program**: You write code in `.java` files.
- **JVM**: The Java Virtual Machine converts bytecode (`.class`) into machine code.
- **Operating System**: Manages resources and interacts with hardware.
- **Hardware**: Executes the final machine instructions.

> JVM acts as a bridge between the Java code and the underlying system.

