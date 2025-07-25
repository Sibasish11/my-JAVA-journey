# The `File` Class in Java

The `File` class in Java, part of the `java.io` package, is used to represent file and directory pathnames in an abstract manner. It doesn’t perform file I/O itself, but is used to get metadata and manage files or directories.


## 🧱 What Does the `File` Class Do?

The `File` class helps you:
- Create new files or directories
- Delete existing files or directories
- Check file properties like size, existence, readability, etc.
- Rename or move files
- List contents of directories


## 📌 Important Constructor

```java
File f = new File("path/to/file.txt");
```

You can also create it using absolute or relative paths.


## 📦 Common Methods of `File` Class

| Method                     | Description                                  |
|----------------------------|----------------------------------------------|
| `createNewFile()`         | Creates a new empty file                     |
| `mkdir()`                 | Creates a new directory                      |
| `exists()`                | Checks if file or directory exists          |
| `delete()`                | Deletes the file or directory               |
| `getName()`               | Returns the name of the file                |
| `getAbsolutePath()`       | Returns the absolute pathname               |
| `length()`                | Returns the length (in bytes) of the file   |
| `list()` / `listFiles()`  | Lists contents of a directory               |


## 🧪 Example Usage

```java
import java.io.File;
import java.io.IOException;

public class FileDemo {
    public static void main(String[] args) {
        try {
            File myFile = new File("demo.txt");
            
            if (myFile.createNewFile()) {
                System.out.println("File created: " + myFile.getName());
            } else {
                System.out.println("File already exists.");
            }

            System.out.println("Absolute Path: " + myFile.getAbsolutePath());
            System.out.println("Writable: " + myFile.canWrite());
            System.out.println("Readable: " + myFile.canRead());
            System.out.println("File Size: " + myFile.length() + " bytes");

        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```


## ✅ Summary

The `File` class is the **first step** when dealing with file handling in Java. It allows you to **create**, **delete**, **inspect**, and **navigate** files and directories — all without actually reading or writing data yet.

Up next, we’ll cover how to read and write data using `FileReader` and `FileWriter`.

