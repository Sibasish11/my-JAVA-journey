# 🧵 Creating Threads in Java

Multithreading in Java begins with the ability to **create and start threads**. Java provides two main ways to define and run a thread:


## 🔹 1. By Extending the `Thread` Class

You can create a thread by extending the `Thread` class and overriding its `run()` method.

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running using Thread class");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();  
        t1.start();  // starts the thread
    }
}
```

> ✅ Use `start()` to initiate the new thread. It internally calls `run()`.


## 🔸 2. By Implementing the `Runnable` Interface

A more flexible approach—especially when you need to extend other classes—is implementing `Runnable`.

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread is running using Runnable");
    }
}

public class Main {
    public static void main(String[] args) {
        MyRunnable obj = new MyRunnable();
        Thread t1 = new Thread(obj);  
        t1.start();  
    }
}
```

> ⚠️ In this method, you **pass the `Runnable` object** to the `Thread` constructor.


## ✅ Runnable vs Thread Class

| Feature                   | `Thread` Class             | `Runnable` Interface        |
|---------------------------|----------------------------|-----------------------------|
| Inheritance Limitation    | Cannot extend another class| Can extend other classes    |
| Object sharing            | Difficult                  | Easy                        |
| Recommended?              | No                         | ✅ Yes                      |


## 🔍 Using Anonymous Classes

For short tasks, you can use anonymous classes or lambda expressions (Java 8+):

```java
Thread t = new Thread(() -> {
    System.out.println("Thread using lambda expression");
});
t.start();
```


## 🚀 Quick Tip

If you're not overriding `run()` properly or not using `start()`, your thread will behave like a normal method call.


