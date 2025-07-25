# Java Collections Framework (JCF)

The **Java Collections Framework** is a set of classes and interfaces that provide **data structures** (like lists, sets, queues, and maps) and **algorithms** to manipulate groups of objects efficiently.


## 🔹 Why Use Collections?
- **Dynamic Size**: Unlike arrays, collections can grow or shrink dynamically.
- **Built-in Algorithms**: Sorting, searching, shuffling, etc.
- **Unified Architecture**: All collection classes share common methods through interfaces.
- **Type Safety**: Generics allow collections to store specific data types.


## 🔸 Difference Between Arrays and Collections:

| Feature         | Arrays                           | Collections                        |
|-----------------|----------------------------------|------------------------------------|
| Size            | Fixed size                      | Dynamic size                       |
| Data Type       | Can store both primitives & objects | Only stores objects                |
| Performance     | Faster for fixed-size data       | Slightly slower due to flexibility |
| Algorithms      | No built-in methods (manual code)| Built-in utilities (e.g., sort)    |



## 🔹 Collection Framework Hierarchy:

```java
             +-------------------+
             |   Iterable        |
             +--------+----------+
                      |
     +----------------v----------------+
     |             Collection          |
     +--------+------------+-----------+
              |            |
    +---------v----+  +----v----------+
    |    List      |  |     Set       |
    +--------------+  +---------------+
       |   |   |        |       |
       |   |   |        |       |
    +-----------------------------------+
    |              Queue                |
    +-----------------------------------+
             |             |
      +------v------+ +----v--------+
      | PriorityQueue| | ArrayDeque  |
      +------v------+ +----v--------+    
```


---

## 🔸 Key Interfaces:
- **Iterable**: Root interface for all collections (`for-each` loop support).
- **Collection**: Base interface for most collections (List, Set, Queue).
- **List**: Ordered collection, allows duplicates (ArrayList, LinkedList, Vector).
- **Set**: Unordered collection, no duplicates (HashSet, LinkedHashSet, TreeSet).
- **Queue**: Holds elements in FIFO order (PriorityQueue, ArrayDeque).
- **Map**: (Not part of Collection) Stores key-value pairs (HashMap, TreeMap, etc.).



## 🔹 Utility Classes:
- **Collections Class**: Provides static methods (sort, reverse, shuffle, etc.).
- **Arrays Class**: Contains utility methods for arrays (e.g., `Arrays.sort()`).


## ✅ Example Code:
```java
import java.util.*;

public class CollectionsIntro {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Cherry");

        System.out.println("List Elements: " + list);

        Set<Integer> set = new HashSet<>();
        set.add(10);
        set.add(20);
        set.add(10); // Duplicate ignored

        System.out.println("Set Elements: " + set);
    }
}
