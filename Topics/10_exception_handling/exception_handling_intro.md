# Exception Handling in Java

Exception handling is a powerful mechanism in Java to handle **runtime errors**, allowing the program to continue normal flow even after an unexpected event.


## 🧠 What is an Exception?

An **exception** is an **event** that disrupts the normal flow of the program. It is an object that is thrown at runtime.

```java
int a = 10, b = 0;
int result = a / b;  // ArithmeticException: / by zero
```


## 🔍 Why Use Exception Handling?

- To gracefully handle unexpected errors
- To avoid abrupt termination of programs
- To separate error-handling code from normal logic
- To maintain normal application flow


## 🧰 Keywords Used in Exception Handling

| Keyword   | Description                                                        |
|-----------|--------------------------------------------------------------------|
| `try`     | Defines a block of code to be tested for errors                    |
| `catch`   | Defines a block of code to handle the error                        |
| `finally` | Defines a block of code, always executed (used for clean-up)      |
| `throw`   | Used to explicitly throw an exception                             |
| `throws`  | Declares exceptions thrown by a method                            |


## 🔸 Types of Exceptions

### ✅ Checked Exceptions
- Known to the compiler at compile-time
- Must be either caught or declared
- Example: `IOException`, `SQLException`

### ❌ Unchecked Exceptions
- Occur at runtime
- Compiler does **not** require them to be caught
- Example: `ArithmeticException`, `NullPointerException`


## 🔧 Basic try-catch Syntax

```java
try {
    // risky code
    int data = 100 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero!");
}
```


## 🚨 Common Exceptions in Java

| Exception Type           | Description                               |
|--------------------------|-------------------------------------------|
| `ArithmeticException`    | Division by zero, etc.                    |
| `NullPointerException`   | Accessing object with null reference      |
| `ArrayIndexOutOfBoundsException` | Invalid index access in arrays  |
| `ClassNotFoundException` | Class not found during runtime            |
| `IOException`            | Input/output failures                     |



## 🧱 Exception Hierarchy

```
java.lang.Object
   ↳ java.lang.Throwable
       ↳ java.lang.Exception
           ↳ Checked Exceptions
           ↳ Unchecked Exceptions (RuntimeException)
       ↳ java.lang.Error
```



## ✅ Summary

- Exception handling provides a **robust** way to deal with runtime issues.
- Java uses `try`, `catch`, `finally`, `throw`, and `throws`.
- Proper handling avoids program crashes and ensures better error management.


