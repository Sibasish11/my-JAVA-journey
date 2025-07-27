
## 🔸 Loop Structures in Java

Looping allows executing a block of code **multiple times** until a condition is met.

### ✅ `while` Loop Flow

```text
+-----------------------+
|  Evaluate Condition   |
+-----------+-----------+
            |
       +----v----+
       |  TRUE   |----------------------+
       +---------+                      |
            |                           |
            v                           |
   +---------------------+              |
   | Execute Statements  |              |
   +---------------------+              |
            |                           |
            +---------------------------+
            |
       +----v----+
       |  FALSE  |
       +---------+
            |
            v
+-------------------------+
| Exit the while loop     |
+-------------------------+
```


### ✅ do-while Loop Flow


```text
+------------------------+
|  Execute Statements    |
+-----------+------------+
            |
            v
+------------------------+
|  Evaluate Condition    |
+-----------+------------+
            |
       +----v----+
       |  TRUE   |-------------------+
       +---------+                   |
            |                        |
            +------------------------+
            |
       +----v----+
       |  FALSE  |
       +---------+
            |
            v
+--------------------------+
| Exit the do-while loop   |
+--------------------------+
```

### ✅ for Loop Flow


```text
+--------------------------+
| Initialization (int i=0) |
+-----------+--------------+
            |
            v
+--------------------------+
| Evaluate Condition (i<n) |
+-----------+--------------+
            |
       +----v----+
       |  TRUE   |------------------+
       +---------+                  |
            |                       |
            v                       |
+------------------------+          |
|  Execute Statements     |         |
+------------------------+          |
            |                       |
            v                       |
+------------------------+          |
| Increment/Decrement (i++)         |
+-----------+------------+          |
            |                       |
            +-----------------------+
            |
       +----v----+
       |  FALSE  |
       +---------+
            |
            v
+-------------------------+
| Exit the for loop       |
+-------------------------+
```


###### Break Statement

-Used to terminate the loop prematurely.
-Control jumps to the statement after the loop.

```text
for(int i = 0; i < 10; i++) {
    if(i == 5) break;
    System.out.println(i);
}
```

###### Continue Statement
- Used to skip the current iteration and proceed to the next.

```text
   for(int i = 0; i < 10; i++) {
    if(i == 5) continue;
    System.out.println(i);
}
```
