# Map Implementations Comparison

Java provides multiple **Map** implementations with different characteristics, such as ordering, performance, and thread safety.  
The three primary implementations are **HashMap**, **TreeMap**, and **Hashtable**.

---

## 🔹 Key Differences:

| Feature          | HashMap                  | TreeMap                     | Hashtable                 |
|------------------|--------------------------|-----------------------------|---------------------------|
| **Ordering**     | No ordering              | Sorted by keys (ascending)  | No ordering               |
| **Null Keys**    | 1 `null` key allowed     | No `null` keys allowed      | No `null` keys allowed    |
| **Null Values**  | Multiple `null` values   | Multiple `null` values      | No `null` values allowed  |
| **Thread-Safe**  | No                       | No                          | Yes (synchronized)        |
| **Performance**  | O(1) average operations  | O(log n) due to tree        | Slower due to sync        |
| **Use Cases**    | Fast lookups, caching    | Sorted data or range queries| Multi-threaded legacy apps|

---

## 🔸 Which One to Use?
1. **Use HashMap** for most cases when ordering is not important (best performance).
2. **Use TreeMap** when you need keys to be stored in **sorted order** or when performing range queries (`subMap`, `headMap`, etc.).
3. **Use Hashtable** only when **thread-safety** is required and you’re working with **legacy code**.  
   - For new multi-threaded applications, prefer **ConcurrentHashMap** instead.

---

## ✅ Example Demonstrating Differences:
```java
import java.util.*;

public class MapComparisonExample {
    public static void main(String[] args) {
        // HashMap (unordered)
        Map<Integer, String> hashMap = new HashMap<>();
        hashMap.put(2, "B");
        hashMap.put(1, "A");
        hashMap.put(3, "C");
        System.out.println("HashMap: " + hashMap);

        // TreeMap (sorted by key)
        Map<Integer, String> treeMap = new TreeMap<>();
        treeMap.put(2, "B");
        treeMap.put(1, "A");
        treeMap.put(3, "C");
        System.out.println("TreeMap: " + treeMap);

        // Hashtable (unordered, thread-safe)
        Map<Integer, String> hashtable = new Hashtable<>();
        hashtable.put(2, "B");
        hashtable.put(1, "A");
        hashtable.put(3, "C");
        System.out.println("Hashtable: " + hashtable);
    }
}
```
