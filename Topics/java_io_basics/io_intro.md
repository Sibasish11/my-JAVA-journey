# Java I/O Introduction

Java provides a rich set of input and output (I/O) classes to handle reading from and writing to various data sources such as files, memory, or network connections. These are part of the `java.io` and `java.nio` packages.

I/O operations in Java are mainly divided into two types:

- **Byte-based I/O** (for handling binary data like images, audio, video, etc.)
- **Character-based I/O** (for handling textual data)

Understanding the flow of data — from source to destination — is crucial to mastering Java I/O.


## 📊 Java I/O Stream Classification

```
                            +---------------------+
                            |     Java I/O        |
                            +----------+----------+
                                       |
                 +---------------------+----------------------+
                 |                                            |
        +--------v--------+                        +----------v----------+
        |  Byte Streams   |                        |  Character Streams  |
        +--------+--------+                        +----------+----------+
                 |                                            |
      +----------+----------+                    +------------+-----------+
      | InputStream (read)  |                    |  Reader (read)         |
      | OutputStream (write)|                    |  Writer (write)        |
      +---------------------+                    +------------------------+
```


## 🔄 Byte vs Character Streams

| Feature            | Byte Streams                          | Character Streams                          |
|--------------------|----------------------------------------|--------------------------------------------|
| Base Classes       | `InputStream`, `OutputStream`         | `Reader`, `Writer`                         |
| Data Type Handled  | Binary data (bytes)                   | Text data (characters)                     |
| Common Use Cases   | Images, audio, video, binary files    | Text files, character data                 |
| Example Classes    | `FileInputStream`, `BufferedOutputStream` | `FileReader`, `BufferedWriter`        |


## 🧠 Why Two Types of Streams?

- Java I/O is designed to support **internationalization**.
- Character streams handle **encoding/decoding** automatically.
- Byte streams give **lower-level control** for non-text data.


## ✅ Summary

Java I/O allows you to interact with files, memory, or the network by abstracting input/output operations into stream-based models. Understanding whether your data is **binary** or **textual** helps determine which stream type to use.

Next, we’ll explore how to work with the `File` class to perform file-related operations.

