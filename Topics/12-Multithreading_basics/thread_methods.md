# 🛠️ Common Thread Methods in Java

Java provides several useful methods in the `Thread` class to manage thread execution. These methods allow developers to control and coordinate how threads behave.


## 🔧 Frequently Used Thread Methods

### 1. `start()`
- **Purpose**: Begins the execution of a thread by calling its `run()` method.
```java
Thread t = new MyThread();
t.start();  // Enters RUNNABLE state
```


### 2. `run()`
- **Purpose**: Defines the actual task that a thread will execute.
```java
public void run() {
    System.out.println("Running in a thread");
}
```
> ⚠️ Do **not** call `run()` directly. Use `start()` to begin a thread.


### 3. `sleep(milliseconds)`
- **Purpose**: Pauses the thread for a specific time.
- **Checked exception**: Throws `InterruptedException`.

```java
try {
    Thread.sleep(1000); // Sleep for 1 second
} catch (InterruptedException e) {
    e.printStackTrace();
}
```



### 4. `join()`
- **Purpose**: Waits for another thread to complete.
```java
t1.start();
t1.join();  // Main thread waits for t1 to finish
```



### 5. `yield()`
- **Purpose**: Hints the scheduler that the current thread is willing to pause.
```java
Thread.yield();  // Gives chance to other threads of equal priority
```


### 6. `interrupt()`
- **Purpose**: Interrupts a thread in sleeping or waiting state.
```java
t1.interrupt(); // Throws InterruptedException if sleeping or waiting
```


### 7. `isAlive()`
- **Purpose**: Checks if a thread is still running.
```java
if(t1.isAlive()) {
    System.out.println("Thread is alive");
}
```


## 🧠 Quick Tip

Always wrap `sleep()` and `join()` in a try-catch block to handle `InterruptedException`.


## ✅ Summary Table

| Method       | Description                          |
|--------------|--------------------------------------|
| `start()`    | Begins thread execution              |
| `run()`      | Defines the thread's task            |
| `sleep()`    | Pauses thread temporarily            |
| `join()`     | Waits for another thread to finish   |
| `yield()`    | Suggests CPU handoff to other thread |
| `interrupt()`| Interrupts sleeping/waiting thread   |
| `isAlive()`  | Checks if thread is still active     |

