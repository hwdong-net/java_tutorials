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

#### 原始基本类型的包裹类型：Number、Integer、Long、Double

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

包裹类的toString()将一个数值类型转化为一个字符串：
```java
public class Test { 

   public static void main(String args[]) {
      Integer x = 5;

      System.out.println(x.toString());  
      System.out.println(Integer.toString(12)); 
      System.out.println(Double.toString(11.0));
      System.out.println(Long.toString(123213123));
      System.out.println(Boolean.toString(false));
   }
}
```

 Valueof(arg)将参数值arg转化为相应的Number包裹类对象，如：
 ```java
 ublic class Test { 

   public static void main(String args[]) {
      Integer x =Integer.valueOf(9);
      Double c = Double.valueOf(5);
      Float a = Float.valueOf("80");               
      Integer b = Integer.valueOf("444",16);

      System.out.println(x); 
      System.out.println(c);
      System.out.println(a);
      System.out.println(b);
   }
}
 ```
 类似的，String的Valueof()方法也可以将参数值转化为String类型对象:
 ```java
 import java.io.*;
public class Test {

   public static void main(String args[]) {
      double d = 102939939.939;
      boolean b = true;
      long l = 1232874;
      char[] arr = {'a', 'b', 'c', 'd', 'e', 'f','g' };

      System.out.println("Return Value : " + String.valueOf(d) );
      System.out.println("Return Value : " + String.valueOf(b) );
      System.out.println("Return Value : " + String.valueOf(l) );
      System.out.println("Return Value : " + String.valueOf(arr) );
   }
}
 ```

Number还有equals()、compareTo()用来比较2个对象的内容是否相等，而==是比较2个对象的引用是不是引用的是同一个对象。


[Number的一些方法](https://www.tutorialspoint.com/java/java_numbers.htm#:~:text=All%20the%20wrapper%20classes%20(Integer,taken%20care%20by%20the%20compiler.)


#### String
创建String类对象有2种方法：通过赋值一个文字量、通过new创建。

```java
String str1 = "Welcome";
String str2 = new String("Welcome");
```
例子：
```java
public class Example{  
   public static void main(String args[]){  
	//creating a string by java string literal 
	String str = "Beginnersbook"; 
	char arrch[]={'h','e','l','l','o'}; 
	//converting char array arrch[] to string str2
	String str2 = new String(arrch); 
		
	//creating another java string str3 by using new keyword 
	String str3 = new String("Java String Example"); 
		
	//Displaying all the three strings
	System.out.println(str);  
	System.out.println(str2);  
	System.out.println(str3);  
   }
}
```
常用方法有：

+ **char charAt(int index)**: It returns the character at the specified index. Specified index value should be between 0 to length() -1 both inclusive. It throws IndexOutOfBoundsException if index<0||>= length of String.
+ **boolean equals(Object obj)**: Compares the string with the specified string and returns true if both matches else false.
+ **boolean equalsIgnoreCase(String string)**: It works same as equals method but it doesn’t consider the case while comparing strings. It does a case insensitive comparison.
+ int compareTo(String string): This method compares the two strings based on the Unicode value of each character in the strings.
+ **int compareToIgnoreCase(String string)**: Same as CompareTo method however it ignores the case during comparison.
+ **boolean startsWith(String prefix, int offset)**: It checks whether the substring (starting from the specified offset index) is having the specified prefix or not.
+ **boolean startsWith(String prefix)**: It tests whether the string is having specified prefix, if yes then it returns true else false.
+ boolean endsWith(String suffix): Checks whether the string ends with the specified suffix.
+ int hashCode(): It returns the hash code of the string.
+ int indexOf(int ch): Returns the index of first occurrence of the specified character ch in the string.
+ **int indexOf(int ch, int fromIndex)**: Same as indexOf method however it starts searching in the string from the specified fromIndex.
+ int lastIndexOf(int ch): It returns the last occurrence of the character ch in the string.
+ **int lastIndexOf(int ch, int fromIndex)**: Same as lastIndexOf(int ch) method, it starts search from fromIndex.
+ **int indexOf(String str)**: This method returns the index of first occurrence of specified substring str.
+ int lastindexOf(String str): Returns the index of last occurrence of string str.
+ **String substring(int beginIndex)**: It returns the substring of the string. The substring starts with the character at the specified index.
+ **String substring(int beginIndex, int endIndex)**: Returns the substring. The substring starts with character at beginIndex and ends with the character at endIndex.
+ **String concat(String str)**: Concatenates the specified string “str” at the end of the string.
+ **String replace(char oldChar, char newChar)**: It returns the new updated string after changing all the occurrences of oldChar with the newChar.
+ **boolean contains(CharSequence s)**: It checks whether the string contains the specified sequence of char values. If yes then it returns true else false. It throws NullPointerException of ‘s’ is null.
+ String toUpperCase(Locale locale): Converts the string to upper case string using the rules defined by specified locale.
String toUpperCase(): Equivalent to toUpperCase(Locale.getDefault()).
+ public String intern(): This method searches the specified string in the memory pool and if it is found then it returns the reference of it, else it allocates the memory space to the specified string and assign the reference to it.
+ **public boolean isEmpty()**: This method returns true if the given string has 0 length. If the length of the specified Java String is non-zero then it returns false.
+ public static String join(): This method joins the given strings using the specified delimiter and returns the concatenated Java String
+ **String replaceFirst(String regex, String replacement)**: It replaces the first occurrence of substring that fits the given regular expression “regex” with the specified replacement string.
+ String replaceAll(String regex, String replacement): It replaces all the occurrences of substrings that fits the regular expression regex with the replacement string.
+ **String[] split(String regex, int limit)**: It splits the string and returns the array of substrings that matches the given regular expression. limit is a result threshold here.
+ **String[] split(String regex)**: Same as split(String regex, int limit) method however it does not have any threshold limit.
+ String toLowerCase(Locale locale): It converts the string to lower case string using the rules defined by given locale.
+ public static String format(): This method returns a formatted java String
+ **String toLowerCase()**: Equivalent to toLowerCase(Locale. getDefault()).
+ **String trim()**: Returns the substring after omitting leading and trailing white spaces from the original string.
+ char[] toCharArray(): Converts the string to a character array.
+ static String copyValueOf(char[] data): It returns a string that contains the characters of the specified character array.
+ static String copyValueOf(char[] data, int offset, int count): Same as above method with two extra arguments – initial offset of subarray and length of subarray.
+ void getChars(int srcBegin, int srcEnd, char[] dest, int destBegin): It copies the characters of src array to the dest array. Only the specified range is being copied(srcBegin to srcEnd) to the dest subarray(starting fromdestBegin).
+ **static String valueOf()**: This method returns a string representation of passed arguments such as int, long, float, double, char and char array.
+ boolean contentEquals(StringBuffer sb): It compares the string to the specified string buffer.
+ boolean regionMatches(int srcoffset, String dest, int destoffset, int len): It compares the substring of input to the substring of specified string.
+ boolean regionMatches(boolean ignoreCase, int srcoffset, String dest, int destoffset, int len): Another variation of regionMatches method with the extra boolean argument to specify whether the comparison is case sensitive or case insensitive.
+ **byte[] getBytes(String charsetName)**: It converts the String into sequence of bytes using the specified charset encoding and returns the array of resulted bytes.
+ **byte[] getBytes()**: This method is similar to the above method it just uses the default charset encoding for converting the string into sequence of bytes.
+ int length(): It returns the length of a String.
+ boolean matches(String regex): It checks whether the String is matching with the specified regular expression regex.
+ int codePointAt(int index):It is similar to the charAt method however it returns the Unicode code point value of specified index rather than the character itself.

常用方法有：**charAt()、equals()、subString()、trim()、split()、+、 length()、indexOf()、lastIndexOf()**等。


用**equals()**方法比较字符串是否相等:
```java
String name = "Java"; //1st String object
String name_1 = "Java"; //same object referenced by name variable
String name_2 = new String("Java") //different String object

if(name.equals(name_1)){
System.out.println("name and name_1 are equal String by equals method");
}

//this will return false
if(name==name_2){
System.out.println("name_1 and name_2 are equal String by equals method");
}

```

用**indexOf()**和 **lastIndexOf()** 或用**matches(String regex)**方法在一个字符串中搜索：

```java
String str = "Java is best programming language";

if(str.indexOf("Java") != -1){
     System.out.println("String contains Java at index :" + str.indexOf("Java"));
}

if(str.matches("J.*")){
     System.out.println("String Starts with J");
}

str ="Do you like Java ME or Java EE";

if(str.lastIndexOf("Java") != -1){
      System.out.println("String contains Java lastly at: " + str.lastIndexOf("Java"));
}
```
split(String regex, int limit)用正则表达式regex分割字符串，limit是最大分割的字符串个数。
```
Public String [ ] split ( String regex, int limit )
```
如：
```java
String string = "004-034556-42";
String[] parts = string.split("-", 2);
String part1 = parts[0]; // 004
String part2 = parts[1]; // 034556-42
```

[Introduction to Java programming - Tutorial](https://www.vogella.com/tutorials/JavaIntroduction/article.html#:~:text=Java%20is%20a%20programming%20language,1.0)%20was%20released%20in%201995.&text=Oracle%20has%20now%20the%20steermanship%20for%20Java.)
