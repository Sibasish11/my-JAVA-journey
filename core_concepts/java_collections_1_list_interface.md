# List Interface in Java

The **List** interface in Java is a **child interface of Collection** that represents an **ordered collection of elements**.  
- **Allows duplicate elements**.  
- Elements can be accessed using **index** (like arrays).


## 🔹 Key Features of List:
1. **Index-based access** (0-based index).
2. **Allows duplicate elements**.
3. Maintains **insertion order**.
4. Can store `null` elements (depending on implementation).


## 🔸 Common Implementations:
1. **ArrayList** – Dynamic array, faster for retrieval.
2. **LinkedList** – Doubly linked list, faster for insertion/deletion.
3. **Vector** – Synchronized version of ArrayList.
4. **Stack** – Subclass of Vector, LIFO (Last In, First Out).


## ✅ Syntax:
```java
List<Type> list = new ArrayList<>();

OR

List<Type> list = new LinkedList<>();
```

### 🔹 Example with ArrayList:
```java
import java.util.*;

public class ListExample {
    public static void main(String[] args) {
        List<String> fruits = new ArrayList<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");
        fruits.add("Banana"); // duplicates allowed

        System.out.println("Fruits List: " + fruits);

        // Accessing by index
        System.out.println("First Fruit: " + fruits.get(0));

        // Iterating
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

### 🔹 LinkedList Example:

```java
import java.util.*;

public class LinkedListExample {
    public static void main(String[] args) {
        List<Integer> numbers = new LinkedList<>();
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);

        System.out.println("Numbers: " + numbers);
    }
}

```

### 🔹 Vector Example:
```java
import java.util.*;

public class VectorExample {
    public static void main(String[] args) {
        Vector<String> vector = new Vector<>();
        vector.add("Red");
        vector.add("Blue");
        vector.add("Green");

        System.out.println("Vector Elements: " + vector);
    }
}

```

### 🔹 Stack Example:
```java
import java.util.*;

public class StackExample {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(10);
        stack.push(20);
        stack.push(30);

        System.out.println("Stack: " + stack);
        System.out.println("Popped Element: " + stack.pop());
        System.out.println("Top Element: " + stack.peek());
    }
}

```

### 🔸 Comparison: ArrayList vs LinkedList vs Vector
| Feature         | ArrayList                  | LinkedList              | Vector                |
| --------------- | -------------------------- | ----------------------- | --------------------- |
| **Structure**   | Dynamic Array              | Doubly Linked List      | Dynamic Array         |
| **Insertion**   | Slower (shifting required) | Faster (no shifting)    | Slower (synchronized) |
| **Access**      | Faster (index-based)       | Slower (traverse nodes) | Faster (index-based)  |
| **Thread-Safe** | No                         | No                      | Yes (Synchronized)    |

### Ladder Visualization of List Types:
```text
+-------------------+
|       List        |
+---------+---------+
          |
   +------+------+
   |             |
ArrayList    LinkedList
   |             |
   +------+ +----+
           |
         Vector
           |
         Stack
```

