# Problem Statement:
## Create an ArrayList of integers and use a for-each loop to:

-Print all elements.

-Calculate and print the sum of all elements.

### Solution:
```java
import java.util.ArrayList;

public class ForEachExample {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(5);
        numbers.add(10);
        numbers.add(15);
        numbers.add(20);

        int sum = 0;
        System.out.println("Numbers:");
        for (int num : numbers) {
            System.out.println(num);
            sum += num;
        }

        System.out.println("Sum of Elements: " + sum);
    }
}

```
