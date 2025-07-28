# Shuffling and Reversing with Collections Class

The **`Collections`** class provides methods to **shuffle** elements (randomize order) and **reverse** elements (reverse order) in a list.


## 🔹 Methods:
1. `Collections.shuffle(List<?> list)`  
   - Randomly permutes the elements of the list using a default random source.

2. `Collections.shuffle(List<?> list, Random rnd)`  
   - Shuffles elements using a custom `Random` object.

3. `Collections.reverse(List<?> list)`  
   - Reverses the order of elements in the list.


## ✅ Example 1: Shuffle a List:
```java
import java.util.*;

public class ShuffleExample {
    public static void main(String[] args) {
        List<String> cards = new ArrayList<>(Arrays.asList("Ace", "King", "Queen", "Jack", "10"));

        System.out.println("Original List: " + cards);

        Collections.shuffle(cards);
        System.out.println("Shuffled List: " + cards);

        // Shuffle with custom Random seed
        Collections.shuffle(cards, new Random(42));
        System.out.println("Shuffled (with seed 42): " + cards);
    }
}
```

## ✅ Example 2: Reverse a List:
```java
import java.util.*;

public class ReverseExample {
    public static void main(String[] args) {
        List<Integer> numbers = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));

        System.out.println("Original List: " + numbers);

        Collections.reverse(numbers);
        System.out.println("Reversed List: " + numbers);
    }
}
```

## ✅ Example 3: Combining Sort, Reverse, and Shuffle:
```java
import java.util.*;

public class SortReverseShuffle {
    public static void main(String[] args) {
        List<Integer> list = new ArrayList<>(Arrays.asList(5, 3, 8, 1, 2));

        // Sort
        Collections.sort(list);
        System.out.println("Sorted List: " + list);

        // Reverse
        Collections.reverse(list);
        System.out.println("Reversed List: " + list);

        // Shuffle
        Collections.shuffle(list);
        System.out.println("Shuffled List: " + list);
    }
}
```

##  🔸 Use Cases:
- Shuffling is useful in games (e.g., shuffling cards).

- Reversing is used when you need the elements in reverse order after sorting.
