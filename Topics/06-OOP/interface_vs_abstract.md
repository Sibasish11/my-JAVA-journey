# Interface vs Abstract Class in Java

In Java, **abstract classes** and **interfaces** are used to achieve **abstraction**, but they are used in different scenarios and have distinct features.

---

## 🔹 Abstract Class
- A class declared with the `abstract` keyword.
- Can have **abstract (without body)** and **concrete (with body)** methods.
- Used when classes share a **common base with default functionality**.

### ✅ Example:
```java
abstract class Animal {
    abstract void sound(); // abstract method
    void sleep() {
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}
```

### 🔹 Interface
-A completely abstract type that specifies what a class must do but not how.

-All methods are public and abstract by default (before Java 8).

-Can have default and static methods (from Java 8 onwards).

### ✅ Example:
```java
interface Animal {
    void sound();  // public & abstract by default
}

class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }
}
```
### 🔸 Key Differences Between Abstract Class and Interface:
| Feature                  | Abstract Class                                | Interface                                 |
| ------------------------ | --------------------------------------------- | ----------------------------------------- |
| **Keyword**              | `abstract`                                    | `interface`                               |
| **Methods**              | Can have abstract & concrete methods          | All methods abstract (default)            |
| **Fields**               | Can have variables (with any access modifier) | Only public, static, final constants      |
| **Multiple Inheritance** | Not supported                                 | A class can implement multiple interfaces |
| **Constructor**          | Can have constructors                         | Cannot have constructors                  |
| **Access Modifiers**     | Abstract methods can have any access modifier | Methods are always `public` by default    |


### 🔹 When to Use What?
-Use abstract classes when:

-You need default behavior that can be shared.

-You have non-static fields to maintain state.

###### Use interfaces when:

-You need to define capabilities or contracts.

-You need multiple inheritance.

##### Ladder Visualization of Key Difference:


```java
+-----------------------------------+
|        Abstract Class             |
+-----------------------------------+
| - Can have both abstract &        |
|   concrete methods                |
| - Supports single inheritance     |
| - Can define fields & constructors|
+-----------------------------------+

+-----------------------------------+
|            Interface              |
+-----------------------------------+
| - All methods are abstract        |
| - No constructors or fields       |
| - Supports multiple inheritance   |
+-----------------------------------+
```
