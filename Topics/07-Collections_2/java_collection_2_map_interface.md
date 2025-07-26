# Map Interface in Java

The **Map** interface in Java is part of the **Java Collections Framework** but is **not a subtype of Collection**.  
A `Map` stores data in **key-value pairs**, where:
- **Each key is unique**.
- **Each key maps to exactly one value**.
- Values can be duplicated.


## 🔹 Key Features of Map:
1. **Unique Keys**: Duplicate keys are not allowed.
2. **Null Values**: Some implementations (like `HashMap`) allow `null` keys and `null` values.
3. **Key-Value Pair Operations**: You can store, retrieve, or remove data using keys.


## 🔸 Map Interface Methods:
- `put(K key, V value)` – Adds a key-value pair to the map.
- `get(Object key)` – Retrieves value associated with the key.
- `remove(Object key)` – Removes the key-value pair.
- `containsKey(Object key)` – Checks if key exists.
- `containsValue(Object value)` – Checks if value exists.
- `keySet()` – Returns a set of all keys.
- `values()` – Returns a collection of all values.
- `entrySet()` – Returns a set of key-value pairs.


## 🔹 Map Hierarchy:
```java
          +---------------------+
          |        Map          |
          +---------+-----------+
                    |
  +-----------------+-----------------+
  |         |              |          |
HashMap LinkedHashMap TreeMap Hashtable
```


## ✅ Example Code:
```java
import java.util.*;

public class MapIntro {
    public static void main(String[] args) {
        Map<Integer, String> map = new HashMap<>();

        // Adding key-value pairs
        map.put(1, "Apple");
        map.put(2, "Banana");
        map.put(3, "Cherry");

        // Accessing values
        System.out.println("Value for key 2: " + map.get(2));

        // Iterating through Map
        System.out.println("Key-Value Pairs:");
        for (Map.Entry<Integer, String> entry : map.entrySet()) {
            System.out.println(entry.getKey() + " -> " + entry.getValue());
        }
    }
}
```

### 🔸 Advantages of Map:
-Efficient data retrieval using keys (O(1) for HashMap in average cases).

-Useful for building dictionaries, caching, and key-based lookups.

