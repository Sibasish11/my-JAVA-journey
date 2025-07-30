# FileInputStream and FileOutputStream in Java

When working with **binary data** (like images, videos, audio, etc.), Java provides `FileInputStream` and `FileOutputStream` classes from the `java.io` package.

These classes are part of the **byte stream** system and are suitable for reading/writing **raw bytes**.


## 📥 What is FileInputStream?

Used to read data in the form of bytes from a file.

### ➤ Syntax:
```java
FileInputStream fis = new FileInputStream("input.bin");
int i;
while ((i = fis.read()) != -1) {
    System.out.print((char) i);
}
fis.close();
```

> Even though we're casting to `char`, this class is best used for binary files.


## 📤 What is FileOutputStream?

Used to write raw bytes to a file.

### ➤ Syntax:
```java
FileOutputStream fos = new FileOutputStream("output.bin");
String data = "Java Byte Stream";
fos.write(data.getBytes());
fos.close();
```


## 🧠 Key Differences (vs. FileReader/FileWriter)

| Feature               | FileInputStream / FileOutputStream | FileReader / FileWriter |
|----------------------|-------------------------------------|--------------------------|
| Type of Stream        | Byte stream                        | Character stream         |
| Data Type             | Binary (images, PDFs, audio)       | Text (characters)        |
| Encoding Awareness    | No                                 | Yes                      |
| Performance (text)    | Slower for characters               | Faster for characters    |


## ⚙️ Example: Binary File Copy

```java
import java.io.*;

public class BinaryFileCopy {
    public static void main(String[] args) throws IOException {
        FileInputStream fis = new FileInputStream("image.png");
        FileOutputStream fos = new FileOutputStream("copy_image.png");

        int i;
        while ((i = fis.read()) != -1) {
            fos.write(i);
        }

        fis.close();
        fos.close();

        System.out.println("Binary file copied successfully.");
    }
}
```


## 📝 Summary

- `FileInputStream` and `FileOutputStream` are used for handling binary data.
- Always close streams after use to free up system resources.
- Suitable for files like `.png`, `.mp3`, `.mp4`, `.pdf`, etc.


