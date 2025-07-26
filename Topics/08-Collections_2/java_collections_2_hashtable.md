# Hashtable in Java

The **Hashtable** class in Java is a legacy class that implements the **Map interface**.  
It stores key-value pairs similar to `HashMap` but is **synchronized**, meaning it is **thread-safe** for concurrent access.


## 🔹 Key Features of Hashtable:
1. **Thread-Safe** – All methods are synchronized, making it suitable for multithreaded environments.
2. **No Null Keys/Values** – Unlike `HashMap`, `Hashtable` **does not allow `null` keys or null values**.
3. **Unordered** – Does not maintain insertion order or sorting.
4. **Performance** – Slower than `HashMap` due to synchronization overhead.


## 🔸 Common Methods:
- `put(K key, V value)` – Insert key-value pair.
- `get(Object key)` – Fetch value for a key.
- `remove(Object key)` – Remove entry.
- `containsKey(Object key)` – Check if key exists.
- `containsValue(Object value)` – Check if value exists.
- `keys()` – Returns an enumeration of keys.


## ✅ Example:
```java
import java.util.Hashtable;
import java.util.Map;

public class HashtableExample {
    public static void main(String[] args) {
        Hashtable<Integer, String> table = new Hashtable<>();

        // Adding elements
        table.put(1, "Apple");
        table.put(2, "Banana");
        table.put(3, "Cherry");

        // Accessing values
        System.out.println("Value for key 2: " + table.get(2));

        // Iterating through keys
        for (Map.Entry<Integer, String> entry : table.entrySet()) {
            System.out.println(entry.getKey() + " -> " + entry.getValue());
        }

        // Removing a key
        table.remove(3);
        System.out.println("After removing key 3: " + table);
    }
}
```
### 🔸 HashMap vs Hashtable:
| Feature         | HashMap          | Hashtable     |
| --------------- | ---------------- | ------------- |
| **Order**       | No order         | No order      |
| **Null Keys**   | 1 allowed        | Not allowed   |
| **Null Values** | Multiple allowed | Not allowed   |
| **Thread-Safe** | No               | Yes           |
| **Performance** | Faster (unsync)  | Slower (sync) |

### 🔸 Real-World Use Cases:
- Use Hashtable when you need thread-safe maps but don’t want to use ConcurrentHashMap (though ConcurrentHashMap is preferred today).

- Legacy systems where Hashtable is still in use.
