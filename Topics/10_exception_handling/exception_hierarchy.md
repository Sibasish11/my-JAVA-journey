# Exception Hierarchy in Java

Java uses an object-oriented exception handling model where **all exceptions are objects** derived from the `Throwable` class.


## 🔰 Top of the Hierarchy

```
                     Throwable
                     /      \
              Exception   Error
```


## ✅ `Throwable`

- The **root class** for all errors and exceptions.
- It has two major subclasses: `Exception` and `Error`.


## ✅ `Exception` (Checked & Unchecked)

### 1. **Checked Exceptions**  
These are **checked at compile time**. If not handled or declared, code will not compile.

Examples:
- `IOException`
- `SQLException`
- `ParseException`

### 2. **Unchecked Exceptions (RuntimeException and its subclasses)**  
These are **not checked at compile time**. Program compiles but may crash at runtime.

Examples:
- `NullPointerException`
- `ArrayIndexOutOfBoundsException`
- `ArithmeticException`

```
                Exception
                   |
       ------------------------
      |                        |
Checked Exceptions      RuntimeException
                             |
          ----------------------------------
         |          |           |          |
  NullPointer   Arithmetic   ArrayIndex   ...
```


## ❌ `Error`

Errors indicate **serious problems** that applications should not try to handle.

Examples:
- `StackOverflowError`
- `OutOfMemoryError`
- `VirtualMachineError`


## 📋 Summary Table

| Type                | Subclass Of | Checked/Unchecked | Example                          |
|---------------------|-------------|-------------------|----------------------------------|
| IOException         | Exception   | Checked           | File not found                   |
| SQLException        | Exception   | Checked           | DB query fails                   |
| NullPointerException| RuntimeException | Unchecked   | Accessing null object            |
| ArithmeticException | RuntimeException | Unchecked   | Division by zero                 |
| StackOverflowError  | Error       | Unchecked         | Infinite recursion               |


## 📌 Conclusion

- All exceptions inherit from `Throwable`.
- `Exception` is used for conditions applications might catch.
- `Error` represents serious problems the application shouldn't handle.
- **Only classes under `Exception` (not `Error`) are meant to be caught.**

