### //Super method in inheritance
```java
class A{
public A(){
System.out.println("in A");
}
public A(int i){
System.out.println(In A int)
}
}

class B extends A{
public B{
System.out.println("in B");
}
public B(int i){
super(i);
System.out.println("In B int")
}

public class SuperDemo{
public static void main(String[] args){
B obj1 = new B(5)
}
}

}
```

### Output:
```java
In A int
In B int
```
### // Due to the super(i) in the public B(int i) it will call : public A(int i) & public B(int i)

