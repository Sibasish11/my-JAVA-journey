# Inheritance in Java

**Inheritance** is an Object-Oriented Programming (OOP) concept where one class acquires the properties (fields) and behaviors (methods) of another class.


## 🔹 Why Use Inheritance?
- Code **reusability**.
- Improves **maintainability**.
- Provides a way to achieve **polymorphism**.

---

## ✅ Syntax:
```java
class ParentClass {
    // fields and methods
}

class ChildClass extends ParentClass {
    // additional fields and methods
}
```

### 🔸 Key Terms:
Superclass (Parent Class) → The class whose members are inherited.

Subclass (Child Class) → The class that inherits from another class.

extends → Keyword used for inheritance.

### 🔹 Example:
```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();  // inherited method
        d.bark(); // child class method
    }
}
```
### 🔸 Types of Inheritance in Java:
| Type             | Description                                    | Supported in Java?     |
| ---------------- | ---------------------------------------------- | ---------------------- |
| **Single**       | One class inherits another                     | ✅ Yes                  |
| **Multilevel**   | A class inherits from another class, and so on | ✅ Yes                  |
| **Hierarchical** | Multiple classes inherit one class             | ✅ Yes                  |
| **Multiple**     | One class inherits from multiple classes       | ❌ No (Use interfaces)  |
| **Hybrid**       | Combination of two or more types               | ✅ Yes (via interfaces) |

### ✅ Single Inheritance Example:
```java
class A {
    void displayA() {
        System.out.println("Class A");
    }
}

class B extends A {
    void displayB() {
        System.out.println("Class B");
    }
}
```
### ✅ Multilevel Inheritance Example:
```java
class A {
    void displayA() {
        System.out.println("Class A");
    }
}

class B extends A {
    void displayB() {
        System.out.println("Class B");
    }
}

class C extends B {
    void displayC() {
        System.out.println("Class C");
    }
}
```

### ✅ Hierarchical Inheritance Example:
```java
class A {
    void displayA() {
        System.out.println("Class A");
    }
}

class B extends A {
    void displayB() {
        System.out.println("Class B");
    }
}

class C extends A {
    void displayC() {
        System.out.println("Class C");
    }
}
```

### 🔹 super Keyword in Inheritance:
-Used to call the parent class constructor.

-Used to access parent class methods and fields.
```java
class Parent {
    Parent() {
        System.out.println("Parent constructor");
    }
}

class Child extends Parent {
    Child() {
        super(); // calls Parent constructor
        System.out.println("Child constructor");
    }
}
```

### 🔸 Method Overriding in Inheritance:
When a subclass provides its own implementation of a method declared in the parent class.

```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}
```
### ✅ Summary Table:
| Feature              | Inheritance                    |
| -------------------- | ------------------------------ |
| Keyword              | `extends`                      |
| Purpose              | Reuse code and achieve OOP     |
| Access               | Public and protected members   |
| Multiple Inheritance | Not supported (use interfaces) |
