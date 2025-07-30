# InputStreamReader vs BufferedReader in Java

When handling input in Java, especially from the keyboard or files, two commonly used classes are `InputStreamReader` and `BufferedReader`. Though they often work together, they serve **different purposes** in the I/O stream hierarchy.


## 🎯 What is InputStreamReader?

The `InputStreamReader` class acts as a **bridge between byte streams and character streams**. It reads bytes from an input stream and decodes them into characters using a specified charset.

### ➤ Syntax:
```java
InputStreamReader isr = new InputStreamReader(System.in);
```


## 🎯 What is BufferedReader?

The `BufferedReader` class reads **text from a character input stream**, buffering characters to provide efficient reading of characters, arrays, and lines. It is faster than reading one character at a time.

### ➤ Syntax:
```java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
```

## ⚙️ Working Together

To get user input using `BufferedReader`, it is often wrapped around `InputStreamReader`.

```java
import java.io.*;

public class InputExample {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        System.out.print("Enter a line: ");
        String input = br.readLine();
        System.out.println("You entered: " + input);
    }
}
```


## 🔍 Comparison Table

| Feature               | InputStreamReader                | BufferedReader                        |
|------------------------|-----------------------------------|----------------------------------------|
| Purpose              | Converts byte stream to char stream | Buffers characters for efficient reading |
| Reads                | Characters                        | Characters, lines                     |
| Efficiency           | Less efficient                    | More efficient due to buffering       |
| Line Reading Support | Not directly                      | Has `readLine()` method               |
| Common Use           | Wrapping byte streams             | Wrapping around InputStreamReader     |


## ✅ When to Use What?

- Use `InputStreamReader` when:
  - You need to **convert byte streams** (e.g., reading from network sockets or `System.in`) to character streams.
  
- Use `BufferedReader` when:
  - You want **efficient reading** of lines or large blocks of text.
  - You use methods like `readLine()` or want better performance over multiple reads.


## 📌 Quick Tip

```java
// Full setup for reading a line from keyboard
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
String name = br.readLine();
```

⚠️ Don’t forget to handle `IOException` using `try-catch` or `throws`.


## 📝 Summary

- `InputStreamReader` converts **bytes to characters**.
- `BufferedReader` efficiently reads **characters, arrays, or lines**.
- Together, they allow smooth and fast input reading for Java applications.

