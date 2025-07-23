# Synchronizing Collections in Java

The **`Collections`** class provides utility methods to make collections **thread-safe**.  
Thread-safe collections prevent data inconsistencies when accessed by multiple threads simultaneously.

---

## 🔹 Methods for Synchronization:
1. `Collections.synchronizedList(List<T> list)`  
   - Returns a thread-safe **List**.
2. `Collections.synchronizedSet(Set<T> set)`  
   - Returns a thread-safe **Set**.
3. `Collections.synchronizedMap(Map<K, V> map)`  
   - Returns a thread-safe **Map**.

---

## ✅ Example 1: Synchronized List
```java
import java.util.*;

public class SynchronizedListExample {
    public static void main(String[] args) {
        List<Integer> list = Collections.synchronizedList(new ArrayList<>());

        // Adding elements
        list.add(1);
        list.add(2);
        list.add(3);

        // Iterating safely
        synchronized (list) {
            for (int num : list) {
                System.out.println(num);
            }
        }
    }
}
```
## ✅ Example 2: Synchronized Set:
```java
import java.util.*;

public class SynchronizedSetExample {
    public static void main(String[] args) {
        Set<String> set = Collections.synchronizedSet(new HashSet<>());

        set.add("A");
        set.add("B");
        set.add("C");

        synchronized (set) {
            for (String s : set) {
                System.out.println(s);
            }
        }
    }
}
```
## ✅ Example 3: Synchronized Map:
```java
import java.util.*;

public class SynchronizedMapExample {
    public static void main(String[] args) {
        Map<Integer, String> map = Collections.synchronizedMap(new HashMap<>());

        map.put(1, "Apple");
        map.put(2, "Banana");

        synchronized (map) {
            for (Map.Entry<Integer, String> entry : map.entrySet()) {
                System.out.println(entry.getKey() + " -> " + entry.getValue());
            }
        }
    }
}
```

## 🔸 Why Use Synchronization?
- To prevent ConcurrentModificationException when multiple threads modify a collection.

- Ensures atomic operations like add/remove in multi-threaded environments.

