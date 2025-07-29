# Vehicle Inheritance Model

###### Problem Statement:
Create a base class Vehicle with:

Fields: brand, speed

Method: displayInfo()

Create a subclass Car that:

Adds numberOfDoors.

Overrides displayInfo() to show car details.

### Answer:

```java
class Vehicle {
    String brand;
    int speed;

    Vehicle(String brand, int speed) {
        this.brand = brand;
        this.speed = speed;
    }

    void displayInfo() {
        System.out.println("Brand: " + brand + ", Speed: " + speed + " km/h");
    }
}

class Car extends Vehicle {
    int numberOfDoors;

    Car(String brand, int speed, int numberOfDoors) {
        super(brand, speed);
        this.numberOfDoors = numberOfDoors;
    }

    @Override
    void displayInfo() {
        System.out.println("Car Brand: " + brand + ", Speed: " + speed + " km/h, Doors: " + numberOfDoors);
    }

    public static void main(String[] args) {
        Car car = new Car("Toyota", 180, 4);
        car.displayInfo();
    }
}

```
