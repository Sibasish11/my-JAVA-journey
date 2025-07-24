# Custom Exceptions in Java

In Java, apart from using built-in exceptions, we can also **create our own exceptions** to handle specific application scenarios. These are called **Custom Exceptions** or **User-defined Exceptions**.


## ✅ Why Use Custom Exceptions?

- To handle **domain-specific errors** (e.g., `InsufficientBalanceException`, `InvalidAgeException`).
- To provide **clear, meaningful error messages**.
- To **organize exception handling** based on specific cases.


## 🛠 How to Create a Custom Exception

1. Create a class that **extends** the `Exception` class (for checked exceptions)  
   or `RuntimeException` (for unchecked exceptions).
2. Define a constructor to accept a custom message.


## 🔹 Example 1: Custom Checked Exception

```java
class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message);
    }
}

public class VoterCheck {
    static void validateAge(int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("Age must be 18 or above.");
        } else {
            System.out.println("Valid voter.");
        }
    }

    public static void main(String[] args) {
        try {
            validateAge(15);
        } catch (InvalidAgeException e) {
            System.out.println("Caught Exception: " + e.getMessage());
        }
    }
}
```


## 🔹 Example 2: Custom Unchecked Exception

```java
class NegativeNumberException extends RuntimeException {
    public NegativeNumberException(String message) {
        super(message);
    }
}

public class Calculator {
    public static int squareRoot(int number) {
        if (number < 0) {
            throw new NegativeNumberException("Negative number not allowed.");
        }
        return (int)Math.sqrt(number);
    }

    public static void main(String[] args) {
        System.out.println(squareRoot(-9));
    }
}
```


## ✅ Notes

| Category          | Description                              |
|------------------|------------------------------------------|
| Base Class        | `Exception` (checked), `RuntimeException` (unchecked) |
| Use Case          | Custom business logic error handling     |
| Message           | Passed to `super()` in constructor       |


## 📌 Summary

- **Checked Exception**: Extend `Exception` → Must use `throws` and `try-catch`.
- **Unchecked Exception**: Extend `RuntimeException` → Optional handling.
- Use `super("message")` to define your own error message.

