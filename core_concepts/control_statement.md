# Control Statements in Java

In Java, **control statements** determine the flow of execution of a program. Normally, statements execute sequentially, but using control structures, we can **alter the flow**, allowing decisions, loops, and exceptions.

Java supports the following groups of control statements:

---

## 🔸 Categories of Control Statements

| **Group**                    | **Examples**                                 | **Purpose**                             |
|-----------------------------|----------------------------------------------|-----------------------------------------|
| Decision-making             | `if`, `if-else`, `switch-case`               | Select between options                  |
| Looping                     | `while`, `do-while`, `for`                   | Execute code repeatedly                 |
| Branching                   | `break`, `continue`, `return`, `label:`      | Alter normal flow                       |
| Exception Handling          | `try-catch-finally`, `throw`                 | Handle unexpected runtime errors        |

---

## 🔹 1. Simple `if` Statement

Used when we want to execute a statement **only if a condition is true**.

### ✅ Syntax:

```java
if (condition) 
    statement;
```


✅ Key Points:


Condition must return a boolean.

If condition is true, the statement runs.

Curly braces {} can group multiple statements.



🧠 Example:

```java
int marks = 80;
if (marks > 50) 
    System.out.println("Pass");
```


🔹 2. if-else Statement
Allows us to define an alternate path when the condition fails.

✅ Syntax:

```java
if (condition)
    statement1;
else
    statement2;
```

✅ Key Points:


Runs statement1 if the condition is true.

Otherwise, executes statement2.

🧠 Example:

```java
int marks = 40;
if (marks >= 50)
    System.out.println("Pass");
else
    System.out.println("Fail");
```

🔹 3. switch-case Statement

Used when we need to compare a variable with multiple values.

✅ Syntax:

```java
switch (n) {
    case 1: statement_1; break;
    case 2: statement_2; break;
    case 3: statement_3; break;
    default: statement_default;
}
```


✅ Key Points:

Matches the value of n with a case.

Executes the matching case block.

break stops further case checks.

default runs when no case matches.

🧠 Example:

```java
int day = 2;
switch (day) {
    case 1: System.out.println("Sunday"); break;
    case 2: System.out.println("Monday"); break;
    default: System.out.println("Another day");
}
```


######  🔸 Summary Flow


### ✅ `if` Statement Flow

```text
+------------------+
|  if (condition)  |
+--------+---------+
         |
   +-----v-----+
   |  TRUE     |--------------------+
   +-----------+                    |
         |                          |
         v                          |
+------------------+                |
| Execute Statement |               |
+------------------+                |
                                    |
   +-----------+                    |
   |  FALSE     |-------------------+
   +-----------+
         |
         v
+---------------------+
| Skip the statement  |
+---------------------+
```


### ✅ Switch Statement Flow


```text
+-----------------+
| switch (n)      |
+--------+--------+
         |
   +-----v-----+
   | case 1?   |------------------+
   +-----------+                  |
         | YES                    |
         v                        |
+-----------------+               |
| Statement_1     |               |
+-----------------+               |
                                  |
   +-----------+                  |
   | case 2?   |------------------+
   +-----------+
         |
         v
+-----------------+
| Statement_2     |
+-----------------+

   ... and so on ...

   +-----------+
   | default   |
   +-----------+
         |
         v
+---------------------+
| Default Statement   |
+---------------------+
```
