//write a program to find first 15 fibonacci numbers.

```java
class fibonacci{
  public static void main(String [] args){
   int n = 10;
   int first = 0, second = 1;
   System.out.println("Fibonacci series upto " + n + " terms:");
   for (int i = 1; i<=n ; i++){
   System.out.println(first + "");
   int next = first + second;
    first = second;
    second = next;
  }
  }
}
```

###### OUTPUT
```java
Fibonacci series upto 10 terms:
0
1
1
2
3
5
8
13
21
34
```
  
