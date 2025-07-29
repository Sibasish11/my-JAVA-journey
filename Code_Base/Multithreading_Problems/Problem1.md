# 🧩 Problem 1: Demonstrate All Major Thread States

## 📝 Objective: Create a program that moves a thread through NEW → RUNNABLE → TIMED_WAITING → TERMINATED states and prints the state at each step.

```java
public class ThreadStateDemo {

    public static void main(String[] args) throws InterruptedException {
        Thread t = new Thread(() -> {
            try {
                Thread.sleep(500); // Goes to TIMED_WAITING
                System.out.println("Thread inside run: " + Thread.currentThread().getState());
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        });

        System.out.println("Before start: " + t.getState()); // NEW
        t.start();
        System.out.println("After start: " + t.getState()); // RUNNABLE

        Thread.sleep(100); // Give some time for thread to enter sleep
        System.out.println("While sleeping: " + t.getState()); // TIMED_WAITING

        t.join(); // Wait for thread to finish
        System.out.println("After termination: " + t.getState()); // TERMINATED
    }
}

```
### ✅ Output:

```java
Before start: NEW
After start: RUNNABLE
While sleeping: TIMED_WAITING
Thread inside run: TIMED_WAITING
After termination: TERMINATED
```

