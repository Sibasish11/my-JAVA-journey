# Built-in Exceptions in Java

In Java, exceptions are broadly categorized into **checked** and **unchecked** exceptions. The Java API provides a rich set of built-in exceptions to help programmers gracefully handle unexpected situations at runtime.

These exceptions are part of the `java.lang` package and are automatically available without any explicit import.


## ✅ Classification of Built-in Exceptions

Java exceptions are mainly divided into two types:

```
                        +------------------------+
                        |      Exception         |
                        +------------------------+
                                   |
             +---------------------+----------------------+
             |                                            |
   +--------------------+                    +------------------------+
   | Checked Exceptions |                    | Unchecked Exceptions   |
   +--------------------+                    +------------------------+
             |                                            |
+-------------------------+        +----------------------------------------+
| IOException             |        | ArithmeticException                    |
| SQLException            |        | ArrayIndexOutOfBoundsException         |
| FileNotFoundException   |        | NullPointerException                   |
| ClassNotFoundException  |        | NumberFormatException                  |
+-------------------------+        +----------------------------------------+
```


## ✅ Checked Exceptions

These are exceptions that are **checked at compile-time**. If your code can potentially throw one, you **must handle it using try-catch** or declare it with `throws`.

### Example: FileNotFoundException

```java
import java.io.FileReader;
import java.io.FileNotFoundException;

public class Demo {
    public static void main(String[] args) {
        try {
            FileReader file = new FileReader("input.txt");
        } catch (FileNotFoundException e) {
            System.out.println("File not found.");
        }
    }
}
```

### Common Checked Exceptions:
- `IOException`
- `SQLException`
- `FileNotFoundException`
- `ClassNotFoundException`


## ✅ Unchecked Exceptions

These are **not checked at compile-time**. They occur due to programming errors and extend the `RuntimeException` class.

### Example: ArithmeticException

```java
public class Demo {
    public static void main(String[] args) {
        int a = 10 / 0;  // ArithmeticException
    }
}
```

### Common Unchecked Exceptions:
- `ArithmeticException`
- `ArrayIndexOutOfBoundsException`
- `NullPointerException`
- `IllegalArgumentException`
- `NumberFormatException`



## 📌 Quick Comparison Table

| Feature                  | Checked Exceptions          | Unchecked Exceptions              |
|--------------------------|-----------------------------|-----------------------------------|
| Checked at compile-time? | Yes                         | No                                |
| Must handle in code?     | Yes (try-catch / throws)    | No, but recommended               |
| Inherits from            | `Exception`                 | `RuntimeException`                |


## 🧵 Summary

- Java offers many built-in exceptions categorized into checked and unchecked.
- Checked exceptions ensure robust I/O and database operations.
- Unchecked exceptions deal with logic and programming errors.
- Understanding these is key to writing error-resilient code.

