# Problem Statement:
Create a program that stores a list of student names using an ArrayList.

-Add at least 5 names.

-Remove one name.

-Display all names using a for-each loop.

### Solution:
```java
import java.util.ArrayList;

public class ArrayListStudentManagement {
    public static void main(String[] args) {
        ArrayList<String> students = new ArrayList<>();

        // Adding names
        students.add("John");
        students.add("Alice");
        students.add("Bob");
        students.add("Emma");
        students.add("Mike");

        // Remove a name
        students.remove("Bob");

        // Display all names using for-each
        System.out.println("Student List:");
        for (String name : students) {
            System.out.println(name);
        }
    }
}

```
