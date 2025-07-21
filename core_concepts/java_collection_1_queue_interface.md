# Queue Interface in Java

The **Queue** interface is part of the Java Collections Framework and represents a **First-In-First-Out (FIFO)** data structure.  
- Elements are **added at the rear (tail)** and **removed from the front (head)**.  
- It is used for tasks like **scheduling**, **order processing**, and **buffer management**.



## 🔹 Key Features of Queue:
1. **FIFO Order** (first element added is the first to be removed).
2. **No random access** – elements are accessed in a specific order.
3. **Null elements** – Most queues (like `PriorityQueue`) don’t allow null elements.



## 🔸 Common Implementations:
1. **PriorityQueue** – Elements are ordered according to natural ordering or a custom comparator (not strictly FIFO).
2. **ArrayDeque** – A resizable array implementation of a double-ended queue (Deque), which can act as both **queue** and **stack**.


## ✅ Queue Interface Methods:
- `add(E e)` – Inserts the element (throws exception if full).
- `offer(E e)` – Inserts the element (returns `false` if full).
- `remove()` – Removes and returns the head (throws exception if empty).
- `poll()` – Removes and returns the head (returns `null` if empty).
- `peek()` – Returns head without removing (null if empty).
- `element()` – Returns head without removing (throws exception if empty).



## 🔹 Example with PriorityQueue:
```java
import java.util.*;

public class PriorityQueueExample {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.add(30);
        pq.add(10);
        pq.add(20);

        System.out.println("PriorityQueue: " + pq); // Elements in natural order

        System.out.println("Peek: " + pq.peek());  // Head element
        System.out.println("Removed: " + pq.poll()); // Removes head
        System.out.println("After Poll: " + pq);
    }
}
```

### 🔹 Example with ArrayDeque (Deque):
```java
import java.util.*;

public class ArrayDequeExample {
    public static void main(String[] args) {
        ArrayDeque<String> deque = new ArrayDeque<>();

        // Add elements
        deque.offer("A");
        deque.offer("B");
        deque.offer("C");

        System.out.println("Deque: " + deque);

        // Add elements at both ends
        deque.offerFirst("Start");
        deque.offerLast("End");

        System.out.println("After Adding Ends: " + deque);

        // Remove elements
        deque.pollFirst();  // Removes first
        deque.pollLast();   // Removes last

        System.out.println("After Removing Ends: " + deque);
    }
}
```
## 🔸 Queue vs Deque:


| Feature        | Queue (FIFO)                    | Deque (Double-Ended)          |
| -------------- | ------------------------------- | ----------------------------- |
| Access Points  | Insert at rear, remove at front | Insert/remove at both ends    |
| Implementation | PriorityQueue, LinkedList       | ArrayDeque, LinkedList        |
| Use Case       | Scheduling, Order Processing    | Stack + Queue functionalities |


## Ladder Visualization of Queue Types:
```text
+--------------+
|    Queue     |
+------+-------+
       |
+------v-------+
| PriorityQueue|
+--------------+
       |
+------v-------+
|    Deque     |
+------+-------+
       |
+------v-------+
|  ArrayDeque  |
+--------------+
```
