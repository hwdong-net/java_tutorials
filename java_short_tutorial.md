#### interface

interface关键字用来定义一个接口类型，接口是和类一样的引用类型，它是一组抽象方法(abstract methods)的集合,
接口是一个完全抽象的类型，表示实现这个接口的那些类的共同行为。

接口除了抽象方法，还可以包含constants（常量）, default methods, static methods, 和 nested types。 只有default methods 和static methods才能有方法体。

如果实现接口的方法不是抽象的，则接口的所有方法都必须在这个类中实现。

接口的*方法（methods）*默认是公开抽象（public和 abstract）的。

接口的*常数（constants）*默认是public, static and final的。

```java
interface Animal {
   public void eat();
   public void travel();
}
```

**实现接口**

一个类可以通过implements关键字实现一个接口。如：
```java
public class Mammal implements Animal {

   public void eat() {
      System.out.println("Mammal eats");
   }

   public void travel() {
      System.out.println("Mammal travels");
   } 

   public int noOfLegs() {
      return 0;
   }

   public static void main(String args[]) {
      Mammal m = new Mammal();
      m.eat();
      m.travel();
   }
} 
```
Mammal实现了接口Animal的所有方法。

一个类可以实现多个接口，但只能继承一个类。
```java
public interface A {
    default void m() {}
}

public interface B {
    default void m() {}
}

public class C implements A, B {
    @Override
    public void m() {}
}
```



[Introduction to Java programming - Tutorial](https://www.vogella.com/tutorials/JavaIntroduction/article.html#:~:text=Java%20is%20a%20programming%20language,1.0)%20was%20released%20in%201995.&text=Oracle%20has%20now%20the%20steermanship%20for%20Java.)
