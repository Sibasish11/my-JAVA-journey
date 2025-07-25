# Set Interface in Java

The **Set** interface is part of the Java Collections Framework and represents a collection of **unique elements**.  
- **No duplicate elements allowed.**  
- **No index-based access** (unlike `List`).  
- **Unordered** (except for some implementations).

---

## 🔹 Key Features of Set:
1. **Unique Elements**: Automatically removes duplicates.
2. **No Indexing**: Cannot access elements by position.
3. **Flexible Implementations**: Different implementations provide different orderings.

---

## 🔸 Common Implementations:
1. **HashSet** – Unordered, backed by a hash table.
2. **LinkedHashSet** – Maintains **insertion order**.
3. **TreeSet** – Stores elements in **sorted order** (natural ordering or custom comparator).

---

## ✅ Syntax:
```java
Set<Type> set = new HashSet<>();
OR
Set<Type> set = new LinkedHashSet<>();
OR
Set<Type> set = new TreeSet<>();
```

## 🔹 Example with HashSet:

```java
import java.util.*;

public class HashSetExample {
    public static void main(String[] args) {
        Set<String> cities = new HashSet<>();

        cities.add("Delhi");
        cities.add("Mumbai");
        cities.add("Kolkata");
        cities.add("Delhi"); // duplicate will be ignored

        System.out.println("Cities: " + cities);

        // Iterating
        for (String city : cities) {
            System.out.println(city);
        }
    }
}
```
## 🔹 Example with LinkedHashSet:
```java
import java.util.*;

public class LinkedHashSetExample {
    public static void main(String[] args) {
        Set<Integer> numbers = new LinkedHashSet<>();
        numbers.add(40);
        numbers.add(20);
        numbers.add(10);
        numbers.add(30);

        System.out.println("LinkedHashSet (Insertion Order): " + numbers);
    }
}
```

## 🔹 Example with TreeSet:
```java
import java.util.*;

public class TreeSetExample {
    public static void main(String[] args) {
        Set<String> fruits = new TreeSet<>();
        fruits.add("Apple");
        fruits.add("Mango");
        fruits.add("Banana");

        System.out.println("TreeSet (Sorted Order): " + fruits);
    }
}

```
## 🔸 Comparison: HashSet vs LinkedHashSet vs TreeSet

| Feature           | HashSet               | LinkedHashSet             | TreeSet                  |
| ----------------- | --------------------- | ------------------------- | ------------------------ |
| **Order**         | No ordering           | Maintains insertion order | Sorted (natural order)   |
| **Duplicates**    | Not allowed           | Not allowed               | Not allowed              |
| **Performance**   | O(1) for add, remove  | O(1) for add, remove      | O(log n) for add, remove |
| **Null Elements** | Allows one null value | Allows one null value     | Does NOT allow null      |

## Ladder Visualization of Set Types:
```java
+-----------+
|    Set    |
+-----+-----+
      |
+-----v--------+
|  HashSet     |
+--------------+
      |
+-----v------------+
| LinkedHashSet    |
+------------------+
      |
+-----v------------+
| TreeSet (Sorted) |
+------------------+
```

