# Iterator and ListIterator in Java

The **Iterator** and **ListIterator** interfaces in Java are used to **traverse collections** safely. They are part of the **java.util** package and provide a standard way to iterate over elements.


## 🔹 What is an Iterator?
- `Iterator` is a **universal cursor** for traversing collections (e.g., List, Set).
- Allows **forward-only** traversal.
- Provides methods to **remove elements** during iteration (unlike `for-each` loop).



## ✅ Iterator Interface Methods:
- `boolean hasNext()` – Checks if there is a next element.
- `E next()` – Returns the next element.
- `void remove()` – Removes the current element (optional operation).

### Example:
```java
import java.util.*;

public class IteratorExample {
    public static void main(String[] args) {
        List<String> names = new ArrayList<>();
        names.add("John");
        names.add("Jane");
        names.add("Tom");

        Iterator<String> it = names.iterator();
        while (it.hasNext()) {
            String name = it.next();
            System.out.println(name);
            if (name.equals("Jane")) {
                it.remove(); // remove element during iteration
            }
        }
        System.out.println("After Removal: " + names);
    }
}
```
## 🔹 What is a ListIterator?
-ListIterator is a bidirectional iterator (only for List types).

-Allows traversal in both forward and backward directions.

-Can modify elements during iteration (add, set).

## ✅ ListIterator Interface Methods:

-boolean hasNext() – Checks if there is a next element.

-E next() – Returns the next element.

-boolean hasPrevious() – Checks if there is a previous element.

-E previous() – Returns the previous element.

-void add(E e) – Inserts element during iteration.

-void set(E e) – Replaces the last element returned.

## Example:

```java
import java.util.*;

public class ListIteratorExample {
    public static void main(String[] args) {
        List<String> colors = new ArrayList<>();
        colors.add("Red");
        colors.add("Green");
        colors.add("Blue");

        ListIterator<String> listIt = colors.listIterator();
        System.out.println("Forward Traversal:");
        while (listIt.hasNext()) {
            System.out.println(listIt.next());
        }

        System.out.println("\nBackward Traversal:");
        while (listIt.hasPrevious()) {
            System.out.println(listIt.previous());
        }
    }
}
```
### 🔸 Difference: Iterator vs ListIterator


| Feature           | Iterator                          | ListIterator                                                           |
| ----------------- | --------------------------------- | ---------------------------------------------------------------------- |
| **Traversal**     | Forward only                      | Forward and backward                                                   |
| **Modification**  | Can remove elements               | Can add, set, and remove                                               |
| **Applicable To** | All collection classes            | Only for List implementations                                          |
| **Methods**       | `hasNext()`, `next()`, `remove()` | `hasNext()`, `next()`, `hasPrevious()`, `previous()`, `add()`, `set()` |

### Ladder Visualization:

```text
+-----------------+
|   Iterator      |
+-----------------+
        |
+-------v---------+
|  ListIterator   |
+-----------------+
|   Adds          |
|   Backward      |
|   Traversal     |
+-----------------+

```
