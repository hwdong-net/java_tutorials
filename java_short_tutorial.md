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
**Functional interfaces(函数接口)**

只有一个方法的接口称为**函数接口**。 函数接口的好处是它们可以和lmabda表达式（lambda expression）一起使用，lambda expression的类型就是函数接口。

下面是一些常用的函数接口：
```
java.lang.Runnable

java.util.concurrent.Callable

java.io.FileFilter

java.util.Comparator

java.beans.PropertyChangeListener
```
java.util.function包里还包含了一些函数接口

#### @Override
@Override修饰一个方法，表示这个方法覆盖了父类或接口的相同签名方法。

```java
class MyBaseClass {

    public void hello() {
        System.out.println("Hello from MyBaseClass");
    }
}

```
从MyBaseClass定义一个派生类MyExtensionClass2，其中子类覆盖了父类的同签名方法hello():
```
class MyExtensionClass2 extends MyBaseClass {

    @Override
    public void hello() {
        System.out.println("Hello from MyExtensionClass2");
    }
}
```

#### 
原始数值类型有byte, int, long, double，如：
```
int i = 5000;
float gpa = 13.65f;
double mask = 125;
```
有些场合需要传递对象类型（Object）的引用而不是这些原始基本类型。例如如果想修改一个数值，直接传递原始基本类型是无法做到的（如交换2个整数变量）。
原始基本类型的**包裹类（wrapper classes）**都是从叫做Number的类派生出来的。
![](https://www.tutorialspoint.com/java/images/number_classes.jpg)

java1.5后编译器可以自动将一个原始基本类型转换为对应的包裹类型，这称为**Boxing**,反过来，也可以将一个包裹类型自动转化为对应的原始基本类型，这称为**unboxing**。

```java
public class Test {

   public static void main(String args[]) {
      Integer x = 5; // boxes int to an Integer object
      int y  =  x + 10;   // unboxes the Integer to a int     
      System.out.println(y);       
   }
}
```

包裹类还包含一些使用方法，而原始基本类型没有这些方法。如包裹类的方法parseX()可以将一个字符串解析为一个X类型的数值。如：
```java
public class Test { 

   public static void main(String args[]) {
      int x =Integer.parseInt("9");
      double c = Double.parseDouble("5");
      int b = Integer.parseInt("444",16); //16进制格式的字符串解析为整数

      System.out.println(x);
      System.out.println(c);
      System.out.println(b);
   }
}
```



[Introduction to Java programming - Tutorial](https://www.vogella.com/tutorials/JavaIntroduction/article.html#:~:text=Java%20is%20a%20programming%20language,1.0)%20was%20released%20in%201995.&text=Oracle%20has%20now%20the%20steermanship%20for%20Java.)
