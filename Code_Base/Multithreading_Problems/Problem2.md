# 🧩 Problem 2: Create a Blocked State Scenario Using Synchronized

## 📝 Objective: Simulate the BLOCKED state using synchronized block and show one thread waiting to acquire a lock held by another.

```java
public class BlockedStateDemo {

    public static void main(String[] args) throws InterruptedException {
        final Object lock = new Object();

        Thread t1 = new Thread(() -> {
            synchronized (lock) {
                try {
                    Thread.sleep(2000); // Holding lock for 2 seconds
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        });

        Thread t2 = new Thread(() -> {
            synchronized (lock) {
                System.out.println("Thread 2 acquired lock");
            }
        });

        t1.start();
        Thread.sleep(100); // Ensure t1 starts first and holds the lock
        t2.start();
        Thread.sleep(100); // Let t2 try acquiring lock

        System.out.println("Thread 1 state: " + t1.getState()); // TIMED_WAITING
        System.out.println("Thread 2 state: " + t2.getState()); // BLOCKED
    }
}
```

### ✅ Output:

```java
Thread 1 state: TIMED_WAITING
Thread 2 state: BLOCKED
```
