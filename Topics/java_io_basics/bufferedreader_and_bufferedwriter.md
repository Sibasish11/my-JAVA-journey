# BufferedReader and BufferedWriter in Java

When working with large text files, using `BufferedReader` and `BufferedWriter` can greatly improve efficiency. These classes provide **buffered I/O**, which means they reduce the number of I/O operations by using an internal memory buffer.


## 🧠 Why Use BufferedReader/Writer?

- Reading/writing character data one character at a time is inefficient.
- Buffered classes read/write **chunks of data at once** — improving speed.


## 📥 BufferedReader

Used to read text from a character-based input stream, efficiently.

### ➤ Syntax:
```java
BufferedReader br = new BufferedReader(new FileReader("input.txt"));
String line;
while ((line = br.readLine()) != null) {
    System.out.println(line);
}
br.close();
```

- `readLine()` reads a full line at a time.
- It wraps around `FileReader`.


## 📤 BufferedWriter

Used to write text to a character-based output stream, efficiently.

### ➤ Syntax:
```java
BufferedWriter bw = new BufferedWriter(new FileWriter("output.txt"));
bw.write("This is a buffered write operation.");
bw.newLine(); // adds a new line
bw.write("Java I/O is powerful.");
bw.close();
```


## ⚖️ BufferedReader vs Scanner

| Feature                 | BufferedReader           | Scanner                |
|------------------------|--------------------------|------------------------|
| Speed                  | Faster                   | Slightly slower        |
| Input Types            | Only Strings             | Supports primitive types |
| Used With              | Files / InputStreams     | Console / Files        |



## 🧪 Example: Reading and Writing Files

```java
import java.io.*;

public class BufferedFileCopy {
    public static void main(String[] args) throws IOException {
        BufferedReader reader = new BufferedReader(new FileReader("source.txt"));
        BufferedWriter writer = new BufferedWriter(new FileWriter("destination.txt"));

        String line;
        while ((line = reader.readLine()) != null) {
            writer.write(line);
            writer.newLine();
        }

        reader.close();
        writer.close();

        System.out.println("File copied using buffered streams.");
    }
}
```


## 📝 Summary

- `BufferedReader` improves read efficiency.
- `BufferedWriter` improves write efficiency.
- Always close both to prevent resource leaks.
- Great for handling large text-based files.
