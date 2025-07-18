# Polymorphism in Java

**Polymorphism** means "many forms". In Java, it allows a single entity (method, object) to behave differently based on the context.

---

## 🔹 Why Use Polymorphism?
- Improves **code reusability** and **readability**.
- Makes the system **flexible and scalable**.
- Supports **OOP principles** like abstraction.

---

## ✅ Types of Polymorphism in Java:

| Type                          | Description                             |
|------------------------------|-----------------------------------------|
| **Compile-Time (Static)**   | Achieved by **method overloading**     |
| **Run-Time (Dynamic)**      | Achieved by **method overriding**      |

---

## 🔸 1. Compile-Time Polymorphism (Method Overloading)
- Multiple methods with the **same name** but **different parameter lists** in the same class.
- Resolved by the **compiler** at compile time.

### ✅ Example:
```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator c = new Calculator();
        System.out.println(c.add(10, 20));       // 30
        System.out.println(c.add(10, 20, 30));   // 60
    }
}
```
### 🔸Run-Time Polymorphism (Method Overriding)
Occurs when a subclass provides its own implementation of a method defined in its parent class.

Resolved at runtime by the JVM.

Requires inheritance.

###### ✅ Example:
```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Dog(); // Reference of parent, object of child
        a.sound();  // Dog barks (runtime decision)
    }
}
```
### 🔹 Key Features:
Method Overloading → Same method name, different parameters, resolved at compile time.

Method Overriding → Same method name & parameters in parent and child class, resolved at runtime.


### ✅ Summary Table:
| Feature              | Compile-Time Polymorphism | Run-Time Polymorphism |
| -------------------- | ------------------------- | --------------------- |
| How Achieved         | Method Overloading        | Method Overriding     |
| Resolution Time      | Compile-Time              | Runtime               |
| Requires Inheritance | No                        | Yes                   |
