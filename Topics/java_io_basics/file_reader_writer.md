# FileReader and FileWriter in Java

When working with files in Java, `FileReader` and `FileWriter` are classes from the `java.io` package that help you perform **character-based** file input and output (I/O). They are designed to read and write text data.


## ✍️ Why Use FileReader and FileWriter?

- `FileReader` is used to read the content of a text file character-by-character.
- `FileWriter` is used to write characters into a text file.
- These are suitable when dealing with **textual content** (unlike `FileInputStream`/`FileOutputStream` which are for binary data).


## 🧱 Constructors

```java
FileReader fr = new FileReader("input.txt");
FileWriter fw = new FileWriter("output.txt");
```

You can also append to a file:
```java
FileWriter fw = new FileWriter("output.txt", true); // appends content
```


## 📌 Common Methods

| Method                | Description                                  |
|-----------------------|----------------------------------------------|
| `read()`              | Reads a single character                     |
| `read(char[] cbuf)`   | Reads characters into an array               |
| `write(int c)`        | Writes a single character                    |
| `write(String str)`   | Writes a string to the file                  |
| `close()`             | Closes the stream                            |
| `flush()`             | Forces any buffered output to be written    |


## 🧪 Example: Writing to a File

```java
import java.io.FileWriter;
import java.io.IOException;

public class WriteDemo {
    public static void main(String[] args) {
        try {
            FileWriter writer = new FileWriter("output.txt");
            writer.write("Hello, this is Java FileWriter example.");
            writer.close();
            System.out.println("Successfully written to the file.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```


## 🧪 Example: Reading from a File

```java
import java.io.FileReader;
import java.io.IOException;

public class ReadDemo {
    public static void main(String[] args) {
        try {
            FileReader reader = new FileReader("output.txt");
            int ch;
            while ((ch = reader.read()) != -1) {
                System.out.print((char) ch);
            }
            reader.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```


## ⚠️ Things to Remember

- Always close the streams using `close()` to prevent resource leaks.
- Use `try-catch` or `try-with-resources` to handle exceptions properly.
- For better performance, consider using `BufferedReader`/`BufferedWriter` (covered next).


## ✅ Summary

`FileReader` and `FileWriter` are ideal for reading and writing plain text files in Java. They're simple, efficient, and form the base of character stream operations.

➡️ Next up: We’ll explore `BufferedReader` and `BufferedWriter` for optimized reading and writing.

