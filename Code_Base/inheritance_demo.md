# // Example for Inheritance

```java
class Calculator{
public int add(int i,int j){
return i+j;
}
}

class CalcAdv extends Calculator{
public int sub(int i, int j){
return i-j;
}
}

class CalcVeryAdv extends CalcAdv{
public int multi(int i, int j){
return i*j;
}
}

public class InheritanceDemo{
public static void main(String[] args){

CalcVeryAdv c1 = new CalcVeryAdv();
int result1 = c1.add(6,5);
int result2 = c1.sub(39,8);
int result3 = c1.multi(3,3);

System.out.println(result1);
System.out.println(result2);
System.out.println(result3);


}
}

```
