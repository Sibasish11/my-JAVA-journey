# try-catch-finally in Java

Java provides a robust mechanism to handle exceptions using `try`, `catch`, and `finally` blocks. These help manage runtime errors and ensure the application continues running or shuts down gracefully.

---

## 🔹 try Block

- Used to wrap the **risky code** that might throw an exception.
- Must be followed by at least one `catch` or `finally`.

```java
try {
    int result = 10 / 0;  // risky code
}
```

---

## 🔹 catch Block

- Handles the specific exception thrown in the `try` block.
- Multiple `catch` blocks can be used to handle different types of exceptions.

```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Division by zero error!");
}
```

### 🔁 Multiple Catch Example

```java
try {
    int[] arr = new int[3];
    arr[5] = 100;
} catch (ArithmeticException e) {
    System.out.println("Arithmetic Error");
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Array Index Error");
} catch (Exception e) {
    System.out.println("General Error");
}
```

---

## 🔹 finally Block

- **Always executed**, whether an exception is thrown or not.
- Typically used for cleanup operations (e.g., closing files, releasing resources).

```java
try {
    int data = 25 / 5;
    System.out.println("Result: " + data);
} catch (NullPointerException e) {
    System.out.println("Null Pointer Exception");
} finally {
    System.out.println("Finally block executed");
}
```

---

## 🔍 Flow of try-catch-finally

```plaintext
+------------+        +-----------+        +------------+
|   try {}   | -----> | catch {}  | -----> | finally {} |
+------------+        +-----------+        +------------+
       |                   |
       |<-- if error       |
```

---

## 💡 Notes

- You can use **try with multiple catch** blocks.
- **finally** executes regardless of whether an exception occurs or not.
- You **cannot** write only `try` without a `catch` or `finally`.

---

## ✅ Summary

| Block     | Purpose                                   |
|-----------|-------------------------------------------|
| try       | Wraps risky code                          |
| catch     | Catches and handles exceptions            |
| finally   | Executes cleanup code (always runs)       |

---

