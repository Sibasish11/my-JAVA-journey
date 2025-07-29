# 🌀 Thread Lifecycle in Java

A thread in Java goes through multiple stages from creation to termination. The Java Thread Lifecycle includes:

```
NEW → RUNNABLE → RUNNING → BLOCKED/WAITING → TERMINATED
```


## 🔄 Thread States Explained

### 1. **NEW**
- A thread is in this state when it is instantiated using the `Thread` class but not yet started.
```java
Thread t = new Thread(); // NEW
```


### 2. **RUNNABLE**
- The thread is ready to run and is waiting for CPU scheduling.
```java
t.start(); // Thread moves to RUNNABLE
```


### 3. **RUNNING**
- The thread scheduler picks the thread from the RUNNABLE pool and executes its `run()` method.

⚠️ You **cannot control** when a thread goes from RUNNABLE to RUNNING — it's handled by the JVM scheduler.


### 4. **BLOCKED / WAITING / TIMED_WAITING**

- **BLOCKED**: Thread is waiting to acquire a lock.
- **WAITING**: Thread is waiting indefinitely for another thread to perform a particular action.
- **TIMED_WAITING**: Thread is waiting for a specified time (e.g., `sleep`, `join`, `wait` with timeout).

```java
Thread.sleep(1000); // TIMED_WAITING
```



### 5. **TERMINATED**
- The thread finishes execution or is forcefully stopped due to an exception.

```java
System.out.println("Thread has finished execution."); // TERMINATED
```


## 📊 Visual Summary

```
+----------+    start()   +-----------+    scheduler    +----------+
|  NEW     | -----------> | RUNNABLE  | --------------> | RUNNING  |
+----------+              +-----------+                 +----------+
                             |   ^                           |
                             v   |                           v
                      +-------------+                +--------------+
                      | BLOCKED /   | <------------- |   WAITING /  |
                      | TIMED_WAIT  |                | TIMED_WAITING|
                      +-------------+                +--------------+
                             |
                             v
                        +------------+
                        | TERMINATED |
                        +------------+
```



## 🧠 Pro Tip

Use `getState()` method to track the current state of a thread:
```java
System.out.println(t.getState());
```



➡️ **Next File:** `thread_methods.md` – Learn about useful thread methods like `sleep()`, `join()`, `yield()`, and more.
