# Method Overloading 
```java
class Casio{

public void add(int i, int j){
System.out.println(i+j);
}

public void add(int i, int j, int k){
System.out.println(i+j+k);
}

public void add(double i, double j){
System.out.println(i+j);
}

}


public class MethodOverloading{
public static void main(String[] args){

casio obj = new casio();
obj.add(4,5);
obj.add(6,7,8);
obj.add(3.2,6.4);
}
}
```

# Constructor Overloading
```java
class Casio{
int num1;
int num2;
String operation;

public casio(){
num1 = 0;
num2 = 0;
operation = "Nothing";
}

public casio(int i, int j){
num1 = i;
num2 = 0;
operation = "Nothing";

public casio(int i, int j){
num1 = i;
num2 = j;
operation = "Nothing";

public casio(int i, int j, String op){
num1 = i;
num2 = j;
operation = "op";

}
}
```

public class ConstructorOverloading{
public static void main(String[] args){
Casio.obj = new Casio(4,5,"Add");

}
}
