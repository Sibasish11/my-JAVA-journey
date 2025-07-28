# Collections Class in Java

The **`Collections`** class (in `java.util`) is a **utility class** that provides **static methods** to operate on or return collections such as lists, sets, and maps.  
It includes algorithms for **sorting, searching, shuffling, reversing**, and **synchronizing collections**.


## 🔹 Difference: Collection vs Collections
- **Collection**:  
  - An **interface** (e.g., `List`, `Set`, `Queue`).  
  - Represents a group of objects.  
  - Example: `List<String> list = new ArrayList<>();`

- **Collections**:  
  - A **utility class** (final class with static methods).  
  - Contains methods for manipulating `Collection` objects (e.g., `Collections.sort(list)`).



## 🔸 Commonly Used Static Methods:
1. **Sorting** – `Collections.sort(List)`
2. **Searching** – `Collections.binarySearch(List, key)`
3. **Reversing** – `Collections.reverse(List)`
4. **Shuffling** – `Collections.shuffle(List)`
5. **Finding Min/Max** – `Collections.min(Collection)`, `Collections.max(Collection)`
6. **Synchronization** – `Collections.synchronizedList(List)`
7. **Frequency Count** – `Collections.frequency(Collection, element)`
8. **Unmodifiable Collection** – `Collections.unmodifiableList(List)`

---

## ✅ Basic Example:
```java
import java.util.*;

public class CollectionsIntro {
    public static void main(String[] args) {
        List<Integer> numbers = new ArrayList<>(Arrays.asList(5, 2, 8, 1, 9));

        // Sorting the list
        Collections.sort(numbers);
        System.out.println("Sorted List: " + numbers);

        // Reversing the list
        Collections.reverse(numbers);
        System.out.println("Reversed List: " + numbers);

        // Finding min and max
        System.out.println("Minimum: " + Collections.min(numbers));
        System.out.println("Maximum: " + Collections.max(numbers));
    }
}
```
### 🔸 Advantages of Collections Class:
Provides ready-made algorithms (sorting, searching) without writing extra code.

- Ensures thread-safety with synchronization wrappers.

- Simplifies operations on lists, sets, and maps.
