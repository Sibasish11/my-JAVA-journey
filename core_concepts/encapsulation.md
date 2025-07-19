# Encapsulation in Java

**Encapsulation** is the process of wrapping **data (fields)** and **methods** into a single unit (class) and restricting direct access to the data.  
It is one of the **four pillars of OOP** (along with inheritance, polymorphism, and abstraction).

---

## 🔹 Key Points About Encapsulation:
- Data fields are declared **private**.
- Access to fields is given through **public getter and setter methods**.
- It ensures **data hiding** and controlled access.

---

## ✅ Syntax:
```java
class ClassName {
    private dataType variable;  // private data

    // Getter method
    public dataType getVariable() {
        return variable;
    }

    // Setter method
    public void setVariable(dataType value) {
        this.variable = value;
    }
}
```

## 🔸 Example of Encapsulation:

```java
class Student {
    // Private data members
    private String name;
    private int age;

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter for age
    public int getAge() {
        return age;
    }

    // Setter for age
    public void setAge(int age) {
        if (age > 0) {    // validation logic
            this.age = age;
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Student s = new Student();
        s.setName("Sibasish");
        s.setAge(21);

        System.out.println("Name: " + s.getName());
        System.out.println("Age: " + s.getAge());
    }
}
```

## 🔹 Benefits of Encapsulation:

• Data Hiding – Private fields prevent direct modification.

• Security – Control access to data using getters/setters.

• Flexibility – You can change implementation without affecting external code.

• Better Code Maintenance – Fields and methods are grouped in one place.

## 🔸 Real-Life Example:

Think of a bank account class:

• Balance is private.

• Deposits and withdrawals are controlled by public methods.

• This prevents unauthorized modification of balance.


### ✅ Difference Between Encapsulation and Abstraction:


| Aspect         | Encapsulation                               | Abstraction                                    |
| -------------- | ------------------------------------------- | ---------------------------------------------- |
| Definition     | Wrapping data and methods together          | Hiding implementation details                  |
| Focus          | Data hiding and access control              | Functionality hiding                           |
| Implementation | Achieved using classes and access modifiers | Achieved using abstract classes and interfaces |


### Ladder Visualization of Encapsulation:
```java
          +------------------------+
          |   Class (Blueprint)    |
          +------------------------+
                      |
               +------v-------+
               | Private Data |
               +--------------+
                      |
               +------v-------+
               |  Getters  &  |
               |   Setters    |
               +--------------+
                       |
               +------v-------+
               | External     |
               | Access (Main)|
               +--------------+
```
