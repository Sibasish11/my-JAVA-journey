# Finding Minimum and Maximum with Collections Class

The **`Collections`** class provides utility methods to find the **minimum** and **maximum** elements in a collection.

---

## 🔹 Methods:
1. `Collections.min(Collection<? extends T> coll)`  
   - Returns the **smallest element** based on natural ordering (Comparable).

2. `Collections.min(Collection<? extends T> coll, Comparator<? super T> comp)`  
   - Returns the minimum element using a **custom comparator**.

3. `Collections.max(Collection<? extends T> coll)`  
   - Returns the **largest element** based on natural ordering.

4. `Collections.max(Collection<? extends T> coll, Comparator<? super T> comp)`  
   - Returns the maximum element using a **custom comparator**.

---

## ✅ Example 1: Min and Max of Integers:
```java
import java.util.*;

public class MinMaxExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(10, 50, 30, 20, 40);

        int min = Collections.min(numbers);
        int max = Collections.max(numbers);

        System.out.println("Numbers: " + numbers);
        System.out.println("Minimum: " + min);
        System.out.println("Maximum: " + max);
    }
}
```
## ✅ Example 2: Min and Max of Strings:
```java
import java.util.*;

public class MinMaxStrings {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("Alice", "David", "Charlie", "Bob");

        String min = Collections.min(names);
        String max = Collections.max(names);

        System.out.println("Names: " + names);
        System.out.println("Alphabetically Min: " + min);
        System.out.println("Alphabetically Max: " + max);
    }
}
```

## ✅ Example 3: Custom Comparator for Objects:
```java
import java.util.*;

class Student {
    String name;
    int marks;

    Student(String name, int marks) {
        this.name = name;
        this.marks = marks;
    }

    @Override
    public String toString() {
        return name + " (" + marks + ")";
    }
}

public class MinMaxCustom {
    public static void main(String[] args) {
        List<Student> students = new ArrayList<>();
        students.add(new Student("John", 85));
        students.add(new Student("Alice", 95));
        students.add(new Student("Bob", 90));

        Student topStudent = Collections.max(students, Comparator.comparingInt(s -> s.marks));
        Student lowestStudent = Collections.min(students, Comparator.comparingInt(s -> s.marks));

        System.out.println("Students: " + students);
        System.out.println("Topper: " + topStudent);
        System.out.println("Lowest Scorer: " + lowestStudent);
    }
}
```

## 🔸 Use Cases:

Finding the highest/lowest marks in a list of students.

- Identifying minimum and maximum prices in a product catalog.

- Determining smallest and largest values in datasets.
