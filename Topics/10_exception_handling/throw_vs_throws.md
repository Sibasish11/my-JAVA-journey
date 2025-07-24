# throw vs throws in Java

Java provides two important keywords for exception handling: `throw` and `throws`. Though they sound similar, their **usage and purpose are different**.


## 🔹 `throw` Keyword

- Used to **explicitly throw an exception** (either built-in or user-defined).
- Can only **throw one exception** at a time.
- Usually used inside a method or a block of code.

### ✅ Syntax:
```java
throw new ExceptionType("Error Message");
```

### 💡 Example:
```java
public class Example {
    public static void main(String[] args) {
        throw new ArithmeticException("Division by zero not allowed");
    }
}
```

## 🔹 `throws` Keyword

- Used to **declare exceptions** in the method signature.
- Informs the caller method that an exception might be thrown.
- Can declare **multiple exceptions** using commas.

### ✅ Syntax:
```java
returnType methodName() throws ExceptionType1, ExceptionType2 {
    // method code
}
```

### 💡 Example:
```java
import java.io.*;

public class Example {
    public static void main(String[] args) throws IOException {
        readFile();
    }

    public static void readFile() throws IOException {
        FileReader file = new FileReader("data.txt");
    }
}
```


## 🆚 Difference Table

| Feature         | `throw`                          | `throws`                             |
|----------------|----------------------------------|--------------------------------------|
| Purpose         | Used to **throw** an exception   | Used to **declare** exceptions       |
| Position        | Inside the method                | In the method declaration            |
| Number of Exceptions | One at a time                  | Multiple exceptions (comma separated)|
| Object Required | Yes (e.g., `new ArithmeticException()`) | No                                   |
| Follows         | `throw` followed by an object    | `throws` followed by class names     |


## 🔁 Combined Example

```java
public class Example {
    static void validateAge(int age) throws IllegalArgumentException {
        if (age < 18) {
            throw new IllegalArgumentException("Not eligible to vote");
        } else {
            System.out.println("Eligible to vote");
        }
    }

    public static void main(String[] args) {
        validateAge(16);  // This will throw an exception
    }
}
```

