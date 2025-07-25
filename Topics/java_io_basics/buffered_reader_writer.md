# BufferedReader and BufferedWriter in Java

When dealing with **large text files** or **frequent I/O operations**, using `BufferedReader` and `BufferedWriter` is more efficient than directly using `FileReader` or `FileWriter`.

These classes add a **buffering layer** that reduces the number of I/O operations by reading or writing larger chunks of data at once.


## 💡 Why Use BufferedReader and BufferedWriter?

- They **improve performance** by buffering characters.
- Enable reading **lines of text** easily with `readLine()`.
- Preferred when reading or writing **multiple lines of text**.


## 🧱 Constructors

```java
BufferedReader br = new BufferedReader(new FileReader("input.txt"));
BufferedWriter bw = new BufferedWriter(new FileWriter("output.txt"));
```

You can also append content to a file:
```java
BufferedWriter bw = new BufferedWriter(new FileWriter("output.txt", true));
```

## 📌 Common Methods

| Method                   | Description                                      |
|--------------------------|--------------------------------------------------|
| `read()`                 | Reads a single character                         |
| `readLine()`             | Reads an entire line of text                     |
| `write(String str)`      | Writes a string                                  |
| `newLine()`              | Inserts a new line                               |
| `flush()`                | Flushes the buffer to the file                   |
| `close()`                | Closes the stream                                |


## 🧪 Example: Writing to a File

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class BufferedWriteDemo {
    public static void main(String[] args) {
        try {
            BufferedWriter bw = new BufferedWriter(new FileWriter("buffered_output.txt"));
            bw.write("Line 1: Java is powerful.");
            bw.newLine();
            bw.write("Line 2: BufferedWriter improves performance.");
            bw.close();
            System.out.println("Data written successfully.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```


## 🧪 Example: Reading from a File

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class BufferedReadDemo {
    public static void main(String[] args) {
        try {
            BufferedReader br = new BufferedReader(new FileReader("buffered_output.txt"));
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
            br.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```


## ⚠️ Tips and Best Practices

- Always use `close()` in a `finally` block or use **try-with-resources** to auto-close.
- Use `flush()` before closing `BufferedWriter` to ensure all data is written.
- `BufferedReader` is great for **line-by-line processing** like reading log files or CSVs.


## ✅ Summary

- `BufferedReader` and `BufferedWriter` are character stream classes with buffering capabilities.
- They are faster than unbuffered streams, especially for large or repetitive file I/O.
- Use them when efficiency and readability are key.



