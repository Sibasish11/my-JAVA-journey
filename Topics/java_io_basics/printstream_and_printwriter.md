# PrintStream and PrintWriter in Java

While `BufferedWriter` is great for writing characters efficiently, Java also provides **`PrintStream`** and **`PrintWriter`** to simplify formatted output to files or other output streams.

These classes are primarily used when you want **easy text output** similar to how `System.out.print()` works.



## 🧠 Why Use PrintStream or PrintWriter?

- Both allow **printing formatted text** (strings, numbers, etc.).
- Support methods like `.print()` and `.println()` — just like `System.out`.
- They are convenient for **writing human-readable data**.



## 📤 PrintStream

A subclass of `OutputStream`, it automatically handles conversion of data to bytes and supports auto flushing.

### ➤ Syntax:
```java
PrintStream ps = new PrintStream("output.txt");
ps.println("Hello from PrintStream!");
ps.println(123);
ps.close();
```

- Often used to **redirect console output** to files:
```java
System.setOut(new PrintStream("log.txt"));
System.out.println("Redirected output");
```


## ✍️ PrintWriter

More flexible than `PrintStream` as it works with **character-based output** and supports **auto flushing** and **internationalization**.

### ➤ Syntax:
```java
PrintWriter pw = new PrintWriter("output.txt");
pw.println("Hello from PrintWriter!");
pw.printf("You scored %d marks in %s", 95, "Math");
pw.close();
```

- You can wrap it around a `BufferedWriter` or `FileWriter` for better performance.


## 🆚 PrintStream vs PrintWriter

| Feature              | PrintStream          | PrintWriter         |
|---------------------|----------------------|---------------------|
| Based On            | Byte Stream          | Character Stream    |
| AutoFlush Support   | Yes (optional)       | Yes (optional)      |
| Format Support      | Basic                | Better (printf, format) |
| Encoding Handling   | Poor                 | Better              |


## ✅ Example: Writing with PrintWriter

```java
import java.io.*;

public class ReportCard {
    public static void main(String[] args) throws IOException {
        PrintWriter pw = new PrintWriter("report.txt");
        pw.println("Name: Ravi Kumar");
        pw.println("Subject: Computer Science");
        pw.printf("Score: %d/100\n", 92);
        pw.close();

        System.out.println("Report generated successfully.");
    }
}
```


## 📝 Summary

- Use `PrintStream` when working with byte-based output or redirecting `System.out`.
- Use `PrintWriter` for **text formatting** and character-based file writing.
- Both support `.print()`, `.println()`, and `.printf()` methods.

