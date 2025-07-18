### Method Overriding:
```java
class A{
public void show(){
System.out.println("In A");
}

class B extends A(){

}
}


public class OverriddingDemo{
public static void main(String [] args){
B obj1 = new B;
obj1.show();
}  
}
```
### There is no show() component in childclass, the parentclass would override here and in the output we will get:

```java
In A
```

### However if you change the code to:

```java
class A{
public void show(){
System.out.println("In A");
}

class B extends A(){
public void show(){
System.out.println("In B");
}
}


public class OverriddingDemo{
public static void main(String [] args){
B obj1 = new B;
obj1.show();
}  
}
```
### Parent Class would not override the Child class:

```java
In B
```
