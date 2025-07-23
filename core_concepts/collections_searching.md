# Searching with Collections Class

The **`Collections`** class provides the `binarySearch()` method to search for elements in a **sorted list**.  
It uses the **binary search algorithm**, which runs in O(log n) time.


## 🔹 Methods for Searching:
1. `Collections.binarySearch(List<? extends Comparable<? super T>> list, T key)`  
   - Searches for `key` in the list (which must be sorted in natural order).
   
2. `Collections.binarySearch(List<T> list, T key, Comparator<? super T> c)`  
   - Searches using a custom comparator (when the list is sorted with a comparator).


## ✅ Example 1: Natural Order Search
```java
import java.util.*;

public class BinarySearchExample {
    public static void main(String[] args) {
        List<Integer> numbers = new ArrayList<>(Arrays.asList(10, 20, 30, 40, 50));

        // List must be sorted
        Collections.sort(numbers);

        int index = Collections.binarySearch(numbers, 30);
        System.out.println("Element 30 found at index: " + index);
    }
}
```

## ✅ Example 2: Searching Strings
```java
import java.util.*;

public class BinarySearchStrings {
    public static void main(String[] args) {
        List<String> names = new ArrayList<>(Arrays.asList("Alice", "Bob", "Charlie", "David"));

        // Sort the list first
        Collections.sort(names);

        int index = Collections.binarySearch(names, "Charlie");
        System.out.println("Charlie found at index: " + index);
    }
}

```

## ✅ Example 3: Custom Comparator Search:
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

class MarksComparator implements Comparator<Student> {
    public int compare(Student s1, Student s2) {
        return s1.marks - s2.marks;
    }
}

public class BinarySearchCustom {
    public static void main(String[] args) {
        List<Student> students = new ArrayList<>();
        students.add(new Student("Alice", 85));
        students.add(new Student("Bob", 90));
        students.add(new Student("Charlie", 95));

        // Sort with custom comparator
        MarksComparator comp = new MarksComparator();
        Collections.sort(students, comp);

        // Search for a student with 90 marks
        int index = Collections.binarySearch(students, new Student("X", 90), comp);
        System.out.println("Student with 90 marks found at index: " + index);
    }
}

```

## 🔸 Key Notes:
The list must be sorted before using binarySearch().

- If the element is not found, the method returns (−insertion_point − 1).

- The behavior is undefined if the list is not sorted.
