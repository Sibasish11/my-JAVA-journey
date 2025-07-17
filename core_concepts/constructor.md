# Constructors in Java

A **constructor** in Java is a special method used to initialize objects. It runs automatically when an object is created.


## 🔹 Features of Constructors:
- Same **name as the class**.
- **No return type**, not even `void`.
- Called **automatically** when an object is created.
- Used to **initialize fields** of a class.

## ✅ Syntax:
```java
class ClassName {
    // Constructor
    ClassName() {
        // Initialization code
    }
}
```

### 🔹 Types of Constructors in Java:

1. Default Constructor
 Provided by the compiler if no constructor is defined.

 Initializes fields with default values.

 Example:
 ```java
class Student {
    String name;
    int age;
}
public class Main {
    public static void main(String[] args) {
        Student s = new Student(); // Compiler adds default constructor
        System.out.println(s.name); // null
        System.out.println(s.age);  // 0
    }
}

```

### 2. No-Argument Constructor
 A constructor with no parameters defined by the programmer.

 Used to assign default values.

 Example:
```java
class Student {
    String name;
    int age;

    // No-argument constructor
    Student() {
        name = "Unknown";
        age = 18;
    }
}

```

### 3. Parameterized Constructor
 Accepts arguments to initialize fields with user-defined values.

 Example:
 ```java
class Student {
    String name;
    int age;

    // Parameterized constructor
    Student(String n, int a) {
        name = n;
        age = a;
    }
}
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Sibasish", 21);
        System.out.println(s1.name + " " + s1.age);
    }
}
```

### 🔸 Constructor Overloading
 Multiple constructors in a class with different parameter lists.

 Helps in flexible object initialization.

 Example:

 class Student {
    String name;
    int age;
 ```java
    Student() {
        name = "Unknown";
        age = 18;
    }

    Student(String n) {
        name = n;
        age = 18;
    }

    Student(String n, int a) {
        name = n;
        age = a;
    }
}
 ```

If you define any constructor, the compiler does NOT provide a default constructor.

Use this() to call another constructor in the same class.

Use super() to call the parent class constructor.

Example:
 ```java
Student() {
    this("Default Name", 0); // Calling another constructor
}

 ```

 
