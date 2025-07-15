# Java Data Types

In Java, data types define the type of data a variable can hold. They are mainly divided into:

- **Primitive Data Types**
- **Non-Primitive (Reference) Data Types**

---

## 🔹 Primitive Data Types

Java has **8 primitive data types**, classified as:

| **Category**       | **Data Type** | **Size**       | **Description**                      |
|--------------------|---------------|----------------|--------------------------------------|
| Integer Types      | `byte`        | 1 byte         | Whole numbers from -128 to 127       |
|                    | `short`       | 2 bytes        | Whole numbers from -32,768 to 32,767 |
|                    | `int`         | 4 bytes        | Default integer type                 |
|                    | `long`        | 8 bytes        | For very large integers              |
| Floating Point     | `float`       | 4 bytes        | Single-precision decimal numbers     |
|                    | `double`      | 8 bytes        | Double-precision decimal numbers     |
| Character Type     | `char`        | 2 bytes        | A single 16-bit Unicode character    |
| Boolean Type       | `boolean`     | ~1 bit (JVM)   | Holds `true` or `false`              |

---

## 🔸 Classification Overview

| **Integral Types**     | **Floating Point Types** | **Other Types**    |
|------------------------|--------------------------|--------------------|
| `byte`, `short`, `int`, `long` | `float`, `double`           | `char`, `boolean`     |

---

## 🔹 Non-Primitive Data Types

Non-primitive types (also called reference types) include:

- **String**
- **Arrays**
- **Classes**
- **Interfaces**

They refer to objects, have methods, and don't store the value directly — they store a reference to the memory location.

---

> 🧠 **Tip:** Prefer `int` for whole numbers and `double` for decimals unless you have memory constraints.
