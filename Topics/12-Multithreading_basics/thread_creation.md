# Creating Threads in Java

Java provides two primary ways to create threads:
1. By **extending the `Thread` class**
2. By **implementing the `Runnable` interface**

Let’s understand both with real examples and their trade-offs.

---

## 🧵 Method 1: Extending the `Thread` Class

This approach involves creating a subclass of `Thread` and overriding its `run()` method.

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread running using Thread class.");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start(); // starts the thread
    }
}
```

✅ Pros:
- Simple and direct for quick threading.

- Easier to implement for basic tasks.

❌ Cons:
- You can't extend any other class since Java doesn’t support multiple inheritance.

### 🧵 Method 2: Implementing Runnable Interface
###### Here, you define a Runnable and pass it to a Thread object.

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread running using Runnable interface.");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread t1 = new Thread(new MyRunnable());
        t1.start();
    }
}
```

| Feature         | `Thread` Class             | `Runnable` Interface       |
| --------------- | -------------------------- | -------------------------- |
| Extensibility   | Can’t extend another class | Can extend other classes   |
| Reusability     | Less reusable              | More reusable and flexible |
| Best suited for | Simple threading           | Complex or thread pools    |

### 🧪 Anonymous Runnable Example (Modern Java):
```java
public class Main {
    public static void main(String[] args) {
        Thread t1 = new Thread(() -> {
            System.out.println("Thread running with lambda (Runnable).");
        });
        t1.start();
    }
}
```

## 📌 Summary
There are multiple ways to create threads in Java, and choosing the right one depends on flexibility and design. Prefer Runnable for cleaner separation and thread pool support.
