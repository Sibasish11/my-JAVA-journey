### VARIABLES IN JAVA

In Java, **variables** are abstraction of memory to store data.
Each variable has a **data type**, **name**, and optionally an **initial value**.



## 🔹 Syntax

```java
dataType variableName = value;
int age = 25;
double pi = 3.14;
String name = "Sibasish";
```

| **Type**              | **Declared In**                                | **Scope**                     | **Lifetime**                             |
| --------------------- | ---------------------------------------------- | ----------------------------- | ---------------------------------------- |
| **Local Variable**    | Inside a method or block                       | Only within that method/block | Created and destroyed during method call |
| **Instance Variable** | Inside a class (outside methods), *non-static* | Throughout the object         | Exists as long as the object exists      |
| **Static Variable**   | Inside a class, marked with `static`           | Shared across all objects     | Exists for the life of the program       |





🔹 Examples of Each
```java
public class Example {
    
    int instanceVar = 10;      // Instance Variable
    static int staticVar = 20; // Static Variable

    void method() {
        int localVar = 30;     // Local Variable
        System.out.println(localVar);
    }
}
```



 
 Rules for Naming Variables
Must start with a letter, _, or $ (cannot start with a digit)

Cannot use Java keywords (e.g., class, int, public)


Are case-sensitive (score and Score are different)

✅ Valid: myName, _score, $amount


❌ Invalid: 2value, int, my-name





🔹 Default Values (for class-level variables)
| **Data Type**          | **Default Value** |
| ---------------------- | ----------------- |
| int, short, byte, long | 0                 |
| float, double          | 0.0               |
| char                   | `'\u0000'`        |
| boolean                | `false`           |
| Object references      | `null`            |




💡  Remember
Use meaningful names (count, studentName) to improve readability.

Prefer camelCase for naming (userAge, totalPrice).

Use final to make variables constant.
```java
final double PI = 3.14159;
```
