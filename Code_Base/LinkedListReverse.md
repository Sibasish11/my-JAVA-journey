# Problem Statement:

### Create a LinkedList of integers.

-Add 5 integers.

-Print the elements in reverse order using ListIterator.

## Answer:

```java
import java.util.LinkedList;
import java.util.ListIterator;

public class LinkedListReverse {
    public static void main(String[] args) {
        LinkedList<Integer> numbers = new LinkedList<>();
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);
        numbers.add(40);
        numbers.add(50);

        // Print in reverse order
        ListIterator<Integer> it = numbers.listIterator(numbers.size());
        System.out.println("LinkedList in Reverse Order:");
        while (it.hasPrevious()) {
            System.out.println(it.previous());
        }
    }
}
```


