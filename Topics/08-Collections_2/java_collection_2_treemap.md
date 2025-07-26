# TreeMap in Java

The **TreeMap** class in Java implements the **Map interface** and stores data in **sorted order of keys**.  
It uses a **Red-Black Tree** internally to maintain the natural or custom ordering of keys.


## 🔹 Key Features of TreeMap:
1. **Sorted Order** – Keys are sorted in **ascending order** by default.
2. **No Null Keys** – TreeMap does not allow `null` keys (throws `NullPointerException`).
3. **Multiple Null Values** – Allows multiple `null` values.
4. **Logarithmic Time** – Basic operations like `put()`, `get()` take O(log n) time.
5. **NavigableMap** – Provides extra methods like `firstKey()`, `lastKey()`, `higherKey()`.


## 🔸 Common Methods:
- `put(K key, V value)` – Add key-value pair.
- `get(Object key)` – Fetch value for the key.
- `remove(Object key)` – Remove entry.
- `firstKey()` / `lastKey()` – Get first and last keys.
- `subMap(K fromKey, K toKey)` – Get a sub-map of a range.


## ✅ Example:
```java
import java.util.TreeMap;

public class TreeMapExample {
    public static void main(String[] args) {
        TreeMap<Integer, String> map = new TreeMap<>();

        map.put(3, "Apple");
        map.put(1, "Banana");
        map.put(2, "Cherry");
        map.put(5, "Mango");
        map.put(4, "Orange");

        System.out.println("TreeMap (Sorted by Key): " + map);

        System.out.println("First Key: " + map.firstKey());
        System.out.println("Last Key: " + map.lastKey());

        // Sub-map
        System.out.println("SubMap (2 to 4): " + map.subMap(2, 5));
    }
}
```

### 🔹 TreeMap with Custom Comparator:

```java
import java.util.*;

public class CustomTreeMapExample {
    public static void main(String[] args) {
        TreeMap<String, Integer> map = new TreeMap<>(Collections.reverseOrder());

        map.put("A", 10);
        map.put("C", 30);
        map.put("B", 20);

        System.out.println("TreeMap (Reverse Order): " + map);
    }
}

```
### 🔸 HashMap vs TreeMap:

| Feature         | HashMap        | TreeMap                   |
| --------------- | -------------- | ------------------------- |
| **Order**       | No order       | Sorted by key (ascending) |
| **Null Keys**   | 1 allowed      | Not allowed               |
| **Time**        | O(1) (average) | O(log n)                  |
| **Thread-Safe** | No             | No                        |

### 🔸 Real-World Use Cases:
- Storing data that must be sorted by keys (e.g., dictionary).

- Implementing range-based queries (using subMap, headMap, tailMap).


