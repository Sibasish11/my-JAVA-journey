# Scanner Class in Java

The `Scanner` class in Java is part of the `java.util` package and is widely used to **read input** from various sources — like keyboard, files, and streams. It is an **easy-to-use** utility especially for beginners.


## 🔍 What is the Scanner Class?

The Scanner class helps in parsing **primitive types** and **strings** using regular expressions. It breaks input into tokens and provides methods to read different types of data.


## 📦 Import Statement

```java
import java.util.Scanner;
```


## 🧱 Creating Scanner Objects

| Source      | Code Example                             |
|-------------|-------------------------------------------|
| Keyboard    | `Scanner sc = new Scanner(System.in);`    |
| File Input  | `Scanner sc = new Scanner(new File("input.txt"));` |
| String      | `Scanner sc = new Scanner("Java 101");`   |


## 🧪 Example: Reading from Keyboard

```java
import java.util.Scanner;

public class ScannerExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String name = sc.nextLine();
        System.out.print("Enter your age: ");
        int age = sc.nextInt();
        System.out.println("Hello " + name + ", you are " + age + " years old.");
        sc.close();
    }
}
```


## 🧪 Example: Reading from a File

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class ReadFromFile {
    public static void main(String[] args) {
        try {
            Scanner sc = new Scanner(new File("sample.txt"));
            while (sc.hasNextLine()) {
                System.out.println(sc.nextLine());
            }
            sc.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found!");
        }
    }
}
```


## 📌 Common Scanner Methods

| Method         | Description                    |
|----------------|--------------------------------|
| `next()`       | Reads a single word            |
| `nextLine()`   | Reads the entire line          |
| `nextInt()`    | Reads an integer               |
| `nextDouble()` | Reads a double                 |
| `nextBoolean()`| Reads a boolean                |
| `hasNext()`    | Checks if there's another token|
| `hasNextInt()` | Checks if next token is int    |


## ✅ Best Practices

- **Always close** the Scanner using `sc.close()` to free up resources.
- When switching from `nextInt()` to `nextLine()`, use an extra `nextLine()` to consume the newline.
- Ideal for **user input**, **file scanning**, or **parsing data** from strings.


## 📝 Summary

- Scanner is a **convenient and flexible** class for input.
- Can read from **keyboard**, **files**, and **strings**.
- Supports various data types and is commonly used in **competitive programming**, **beginner apps**, and **text parsing**.

