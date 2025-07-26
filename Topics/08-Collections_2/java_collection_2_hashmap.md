# HashMap in Java

The **HashMap** class in Java is a part of the **Map interface** and stores data in **key-value pairs**.  
It uses **hashing** for efficient storage and retrieval (average time complexity is O(1) for basic operations).


## 🔹 Key Features of HashMap:
1. **No Duplicate Keys** – Each key must be unique.
2. **Allows Null** – One `null` key and multiple `null` values are allowed.
3. **Unordered** – The order of keys and values is not guaranteed.
4. **Non-Synchronized** – Not thread-safe by default (use `Collections.synchronizedMap()` if needed).
5. **Fast Lookup** – Uses hash codes to retrieve values quickly.


## 🔸 Common Methods:
- `put(K key, V value)` – Insert key-value pair.
- `get(Object key)` – Fetch value for given key.
- `remove(Object key)` – Remove mapping for key.
- `containsKey(Object key)` – Check if key exists.
- `containsValue(Object value)` – Check if value exists.
- `size()` – Number of key-value pairs.
- `entrySet()`, `keySet()`, `values()` – Get keys, values, or entries.


## ✅ Example:
```java
import java.util.HashMap;
import java.util.Map;

public class HashMapExample {
    public static void main(String[] args) {
        HashMap<Integer, String> map = new HashMap<>();

        // Adding elements
        map.put(1, "Apple");
        map.put(2, "Banana");
        map.put(3, "Cherry");
        map.put(4, "Mango");

        // Accessing values
        System.out.println("Value for key 2: " + map.get(2));

        // Iterating
        for (Map.Entry<Integer, String> entry : map.entrySet()) {
            System.out.println(entry.getKey() + " -> " + entry.getValue());
        }

        // Removing
        map.remove(3);
        System.out.println("After removing key 3: " + map);
    }
}
```
### 🔹 Internal Working of HashMap:
HashMap uses an array of buckets (hash table) to store key-value pairs.

-Each key is converted to a hash code (via hashCode() method).

-Hash code is used to find the bucket index.

-If multiple keys hash to the same bucket, a LinkedList or Tree (since Java 8) is used for collision resolution.

## Hashing Formula:
```java
index = hashCode(key) & (capacity - 1)
```

## 🔸 Real-World Use Cases:
-Implementing caches (key = data id, value = data).

-Storing configuration settings (key = setting name).

-Counting word frequencies (key = word, value = frequency).

## 🔸 HashMap vs Hashtable vs TreeMap:

| Feature         | HashMap            | Hashtable    | TreeMap           |
| --------------- | ------------------ | ------------ | ----------------- |
| **Order**       | No order           | No order     | Sorted (by key)   |
| **Nulls**       | 1 null key allowed | No null keys | No null keys      |
| **Thread-Safe** | No                 | Yes          | No                |
| **Performance** | Faster (no sync)   | Slower       | O(log n) (sorted) |
