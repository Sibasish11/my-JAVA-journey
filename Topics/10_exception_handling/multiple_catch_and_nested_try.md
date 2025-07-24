# Multiple `catch` Blocks and Nested `try` in Java

In Java, exception handling can be extended to cover complex scenarios using **multiple `catch` blocks** and **nested `try` blocks**. These are useful when your code can throw more than one type of exception or when you want localized exception handling inside a broader exception management structure.


## ✅ Multiple `catch` Blocks

You can use multiple `catch` blocks to handle different exception types that might occur within a `try` block. Java checks the exceptions **in order** from top to bottom.

```java
try {
    int[] arr = new int[3];
    arr[4] = 10;  // ArrayIndexOutOfBoundsException
    int result = 10 / 0;  // ArithmeticException
} catch (ArithmeticException e) {
    System.out.println("Arithmetic Exception occurred.");
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Array Index Out of Bounds.");
} catch (Exception e) {
    System.out.println("Some other exception occurred.");
}
```

### 🔍 Key Points:
- More specific exceptions must be **written before** general exceptions (like `Exception`).
- If the order is incorrect, it results in a **compile-time error**.


## ✅ Nested `try` Blocks

You can write one `try` block inside another `try` block. This is called **nested try**. It allows handling specific errors at a more localized level before escalating them.

```java
try {
    System.out.println("Outer try block");

    try {
        int num = 10 / 0;
    } catch (ArithmeticException e) {
        System.out.println("Handled ArithmeticException in inner try.");
    }

    int[] arr = new int[2];
    arr[5] = 100;  // Will be handled by outer catch
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Handled ArrayIndexOutOfBoundsException in outer try.");
}
```

## 🧠 When to Use?

| Situation                                | Strategy                       |
|-----------------------------------------|--------------------------------|
| Multiple known exception types possible | Use multiple `catch` blocks    |
| Need localized exception control        | Use nested `try` blocks        |


## 🧪 Output Sample

For the above code:
```
Outer try block
Handled ArithmeticException in inner try.
Handled ArrayIndexOutOfBoundsException in outer try.
```


## 🧵 Summary

- Use multiple `catch` blocks for different exception types.
- Order matters: more specific exceptions first.
- Use nested `try` blocks when you want to handle inner exceptions separately before proceeding with the rest of the code.

