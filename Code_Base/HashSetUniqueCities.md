# Problem Statement:
## Create a program that uses a HashSet to store city names.

- Add at least 5 city names with one duplicate.

- Display all unique cities.

## Solution:
```java
import java.util.HashSet;

public class HashSetUniqueCities {
    public static void main(String[] args) {
        HashSet<String> cities = new HashSet<>();
        cities.add("Delhi");
        cities.add("Mumbai");
        cities.add("Chennai");
        cities.add("Kolkata");
        cities.add("Delhi"); // Duplicate ignored

        System.out.println("Unique Cities:");
        for (String city : cities) {
            System.out.println(city);
        }
    }
}
```
