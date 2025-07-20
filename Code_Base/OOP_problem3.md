# Shape Polymorphism

### Problem Statement:
Create a class Shape with a method area().
Create subclasses:

-Circle with radius.

-Rectangle with length and breadth.

-Override area() in each subclass to calculate their area.

### Requirements:

-Use runtime polymorphism with Shape s = new Circle() and Shape s = new Rectangle().

-Demonstrate method overriding.

### Answer:

```java
class Shape {
    void area() {
        System.out.println("Calculating area...");
    }
}

class Circle extends Shape {
    double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    @Override
    void area() {
        double result = Math.PI * radius * radius;
        System.out.println("Circle Area: " + result);
    }
}

class Rectangle extends Shape {
    double length, breadth;

    Rectangle(double length, double breadth) {
        this.length = length;
        this.breadth = breadth;
    }

    @Override
    void area() {
        double result = length * breadth;
        System.out.println("Rectangle Area: " + result);
    }
}

public class ShapePolymorphism {
    public static void main(String[] args) {
        Shape s;

        s = new Circle(7);
        s.area();

        s = new Rectangle(5, 10);
        s.area();
    }
}
```
