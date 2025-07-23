# Sorting with Collections Class

The **`Collections`** class provides the `sort()` method to sort elements of a list.  
Sorting can be done in **natural order** (default) or with a **custom comparator**.


## 🔹 Methods for Sorting:
1. `Collections.sort(List<T> list)`  
   Sorts the list into natural ascending order (for `Comparable` objects).
   
2. `Collections.sort(List<T> list, Comparator<? super T> c)`  
   Sorts the list based on the provided **Comparator**.


## ✅ Example 1: Natural Order (Ascending)
```java
import java.util.*;

public class NaturalSortingExample {
    public static void main(String[] args) {
        List<Integer> numbers = new ArrayList<>(Arrays.asList(5, 2, 8, 1, 9));

        // Sort in ascending order
        Collections.sort(numbers);
        System.out.println("Sorted (Ascending): " + numbers);
    }
}
```

## ✅ Example 2: Reverse Order:
```java
import java.util.*;

public class ReverseSortingExample {
    public static void main(String[] args) {
        List<String> names = new ArrayList<>(Arrays.asList("John", "Alice", "Bob"));

        // Sort in reverse order
        Collections.sort(names, Collections.reverseOrder());
        System.out.println("Sorted (Descending): " + names);
    }
}
```

## ✅ Example 3: Sorting Custom Objects (Using Comparator):
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

public class CustomSortingExample {
    public static void main(String[] args) {
        List<Student> students = new ArrayList<>();
        students.add(new Student("John", 85));
        students.add(new Student("Alice", 95));
        students.add(new Student("Bob", 90));

        // Sort by marks in ascending order
        Collections.sort(students, new Comparator<Student>() {
            public int compare(Student s1, Student s2) {
                return s1.marks - s2.marks;
            }
        });

        System.out.println("Students sorted by marks: " + students);
    }
}
```

## 🔸 Key Notes:
Objects in a list must be Comparable or a Comparator must be provided.

- Use Collections.reverseOrder() for quick reverse sorting.

- Sorting a list of custom objects requires implementing Comparable or passing a Comparator.
