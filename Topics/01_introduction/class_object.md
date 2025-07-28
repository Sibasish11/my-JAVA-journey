# Classes and Objects in Java

Java is an **Object-Oriented Programming Language**, which means the main building blocks of any Java program are **classes** and **objects**.


### 🔹 What is a Class?
- A **class** is a blueprint or template from which objects are created.
- It defines **attributes** (fields) and **behaviors** (methods) for objects.

### ✅ Syntax:
```java
class ClassName {
    // fields (attributes)
    // methods (behavior)
}
```

### ✅ Example:
```java
class Student {
    // Fields
    String name;
    int age;

    // Method
    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}
```
### 🔹 What is an Object?
-An object is an instance of a class.

-Objects have state (values of attributes) and behavior (methods).

-Created using the new keyword.

```java
ClassName obj = new ClassName();
```

###### Example:
```java
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();  // Create object
        s1.name = "Sibasish";
        s1.age = 21;
        s1.display();
    }
}
```
### 🔸 Key Points:

Class = Definition (Blueprint)

Object = Implementation (Instance)

Multiple objects can be created from a single class.

### 🔹 Characteristics of Objects:

Identity → Name/Reference

State → Values of fields

Behavior → Methods that operate on data

### 🔸 Memory Allocation:

Class: Loaded once in the Method Area.

Objects: Stored in the Heap memory.

References: Stored in the Stack.


