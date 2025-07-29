# Student Details Encapsulation

### Problem Statement:
-Create a class Student with:

-Private fields: name, rollNumber, marks.

-Getters and Setters for each field.

### Requirements:

-Use encapsulation to control data access.

-Create at least 2 student objects and print their details.

### Answer:

```java
class Student {
    private String name;
    private int rollNumber;
    private double marks;

    // Getter and Setter for Name
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }

    // Getter and Setter for Roll Number
    public int getRollNumber() {
        return rollNumber;
    }
    public void setRollNumber(int rollNumber) {
        this.rollNumber = rollNumber;
    }

    // Getter and Setter for Marks
    public double getMarks() {
        return marks;
    }
    public void setMarks(double marks) {
        this.marks = marks;
    }
}

public class StudentEncapsulation {
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.setName("Sibasish");
        s1.setRollNumber(101);
        s1.setMarks(89.5);

        System.out.println("Name: " + s1.getName() + ", Roll No: " + s1.getRollNumber() + ", Marks: " + s1.getMarks());

        Student s2 = new Student();
        s2.setName("John");
        s2.setRollNumber(102);
        s2.setMarks(92);

        System.out.println("Name: " + s2.getName() + ", Roll No: " + s2.getRollNumber() + ", Marks: " + s2.getMarks());
    }
}

```
