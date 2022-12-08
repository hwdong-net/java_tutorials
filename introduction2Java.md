**学编程、认准hwdong （[https://hwdong.net](https://hwdong.net)）**

## 1.1 java介绍

### 1.1.1 Java技术（Java Technology）

Java技术既是一种编程语言又是一个平台(Java technology is both a programming language and a platform.)。

#### Java 编程语言 （The Java Programming Language）

编程语言可分为机器语言、汇编语言、高级语言。Java 编程语言是一种高级语言。

##### 机器语言

　是直接对硬件操作的语言，由多个0、1构成对底层硬件操作的机器指令。从编程效率、可读性等角度，机器语言是最低级的编程语言。 
  - 不同机器的指令集是不同的，程序员必须记忆针对特定机器的大量二进制（0，1串）指令集。
  - 机器语言程序缺少移植性：针对一种型号的机器语言程序无法在其他类型型号机器上运行。
  - 机器语言程序不但编程效率低、调式困难、也难以阅读理解。
  
##### 汇编语言

汇编语言是机器语言的符号化表示，将二进制指令和数据用简短的英文字母组合表示。除了比机器语言具有较好的阅读性外，具有机器语言同样的特点（缺点）
- 汇编语言同机器语言一样直接对硬件操作。
- 具有汇编语言同样的缺点如缺乏移植性、编程效率低等。虽然相比机器语言，其编程效率、可读性有了一定的提高。

#### 高级语言

Java语言和C语言、C++语言等高级编程语言一样，具有可读性好、编程效率高、移植性好等优点。此外，由于Java语言程序是在**Java虚拟机**（称为**安全沙盒**）上运行的，具有更好的安全性。

Java软件开发过程如图所示：

![An overview of the software development process.](https://docs.oracle.com/javase/tutorial/figures/getStarted/getStarted-compiler.gif)

Java语言的 **源程序** 是以后缀 **.java** 结尾的文本文件，经过Java编译器(**Javac**)编译为 **.class** 的**字节码（bytecodes）** 文件，字节码是**Java虚拟机**（**Java Virtual Machine** 简称 **Java VM**）的机器语言。**Java**装载器将java字节码程序装载到Java虚拟机中运行。

因为不同的操作系统上都有相应的**Java VM**，因此，同样的 **.class** 字节码程序可以运行在不同的操作系统（如Microsoft Windows, the Solaris™ Operating System (Solaris OS), Linux, or Mac OS.）上。 使得Java程序“**编写一次、处处运行**(write once run anywhere)”。

![ 通过Java VM，同样程序可运行在任何操作系统上](https://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif)

#### java平台（Java Platform）

   平台是程序运行的硬件或软件环境。如Microsoft Windows, Linux, Solaris OS, 和 Mac OS等曹祖哟系统平台。大多数平台可以描述为操作系统和底层硬件的组合。不同于大多数其他平台，Java平台是一个运行在其他基于硬件的平台（如Microsoft Windows）之上的纯软件平台。
   
   Java 平台有两个组件：
   - Java 虚拟机
   - Java 应用程序编程接口 (API)
   
API 是大量现成软件组件的集合，可提供许多有用的功能。它被分组为相关**类**（classes）和**接口**（interfaces）的库；这些库被称为**包**（*packages*）。

![The API and Java Virtual Machine insulate the program from the underlying hardware.](https://docs.oracle.com/javase/tutorial/figures/getStarted/getStarted-jvm.gif)
   
因为Java程序是运行在Java VM这个虚拟机软件上，所以Java程序的速度要比直接操纵硬件的程序如C/C++等低。
   
### Java JDK, JRE and JVM
   
**JVM**是Java VM的缩写。**JRE**（Java Runtime Environment）（**Java运行环境**）是一个软件包，它提供了 Java 类库、Java 虚拟机 (JVM) 以及运行 Java 应用程序所需的其他组件。要运行java软件，你的操作系统上必须有JRE环境。
    
![Java Runtime Environment](https://cdn.programiz.com/sites/tutorial2program/files/java-realtime-enviornment_0.jpg)
    
JDK（Java Development Kit）（**Java开发工具包**）是用Java开发应用程序所需的软件开发工具包，其中除了JRE，还包含了开发Java程序的开发工具如Java编译器Javac、字节码装载器Java、java文档工具JavaDoc等。当您下载 JDK 时，JRE 也会随之下载。要开发java软件，就需要下载安装JDK。

![](https://cdn.programiz.com/sites/tutorial2program/files/jdk-jre-jvm.jpg)

#### JDK能做啥？

- 开发工具： 开发工具提供了编译、运行、监控、调试和记录应用程序所需的一切。作为一名新开发人员，您将使用的主要工具是 javac 编译器、java 启动器和 javadoc 文档工具。
- Application Programming Interface (API): API 提供 Java 编程语言的核心功能。它提供了大量有用的类，可以在您自己的应用程序中使用。它涵盖了从基本对象到网络和安全，再到 XML 生成和数据库访问等方方面面。
- 部署技术：JDK 软件提供标准机制，例如 Java Web Start 软件和 Java Plug-In 软件，用于将您的应用程序部署到最终用户。
- 用户界面工具包：JavaFX、Swing 和 Java 2D 工具包使创建复杂的图形用户界面 (GUI) 成为可能。

### 1.1.2 Java的应用
 Java 用于开发移动应用程序、Web 应用程序、桌面应用程序、游戏等等。
 
### 1.1.3 “Hello World！”程序

下面的java程序在屏幕上显示“Hello World！”。
```java
/**
 * The HelloWorld class implements an application that
 * simply prints "Hello World!" to standard output.
 */
class HelloWorld{
    public static void main(String[] args) {
        System.out.println("Hello World!"); // 显示字符串 “Hello World!”
    }
}
```

### 1.1.4 编译和运行“HelloWorld”程序

####  Microsoft Windows


- 下载安装[JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html)。注意将jdk的bin文件夹路径添加到系统或当前用户的path环境变量中。

- 用一个文本编辑器如Notepad编写上述的HelloWorld程序代码，并将文本保存为.java后缀的文件（如HelloWorld.java）。

- 编译和运行
  - 打开windows的命令行窗口
  - 进入HelloWorld.java文件所在的文件夹
  - 执行编译命令： javac HelloWorld.java
  - 在同一目录下，执行dir，可以发现多出了一个HelloWorld.class文件。这是刚才编译HelloWorld.java产生的字节码文件
  - 在同一目录下，通过执行命令“java -cp . HelloWorld”运行HelloWorld.class。


### 1.1.5 理解“HelloWorld”程序

这个java程序由三个部分组成：注释（comments）、HelloWorld类定义和main方法。注释是对程序代码进行解释，注释不是代码，编译器会忽略注释，但注释增加了代码的可读性，注释有助于其他程序员或自己今后阅读代码。

#### 注释

Java编程语言支持三种注释：

- `/* 文本 */`
   
   ```编译器忽略从 /* 到 */ 的所有内容。```

- `/** 文档 */`
  
   ```这表示文档注释（简称doc comment）。编译器会忽略这种注释，就像它会忽略使用 /* 和 */ 的注释一样。 javadoc 工具在准备自动生成的文档时使用文档注释。```
   
-  // 文本

    编译器忽略从 // 到行尾的所有内容。
   
 #### 定义类
 
     每个应用程序都以类定义开始,定义一个类的一般格式是：
```java
 a class definition is:

class name {
    . . .
}
```
其中class是用于定义类的关键字，而name是这个类的名字。

上述的Hello World程序中，用关键字clas定义了一个名字为HelloWorld的类。
```java
class HelloWorld {
     ... .. ...
}
```
当然，一个程序可以定义多个不同的类。
#### main 方法

在 Java 编程语言中，每个应用程序都必须包含一个 main 方法，其签名为：
```java
public static void main(String[] args)
```

修饰符 public 和 static 可以按任意顺序编写（public static 或 static public）。main方法类似于C和C++中的main函数；它是您的应用程序的入口点，应用程序执行的是main方法中的代码，main方法中的代码可能调用其他类的方法。

main 方法接受一个参数args,args是一个包含多个元素的数组，每个元素的类型是String（String是一个表示字符串的类型），即每个元素是一个字符串。
```cpp
public static void main(String[] args)
```

该数组是运行时系统将信息传递给您的应用程序的机制。例如：
```
java MyApp arg1 arg2
```
运行MyAPP程序时，传递给它2个字符串arg1和arg2。

main()方法中的语句:
```cpp
System.out.println("Hello World!");
```
使用核心库中的System类来打印“Hello World！”消息到标准输出。
   
#### Reference:
   - [https://docs.oracle.com/javase/tutorial/getStarted/intro/definition.html](https://docs.oracle.com/javase/tutorial/getStarted/intro/definition.html)
   - [https://www.programiz.com/java-programming/jvm-jre-jdk](https://www.programiz.com/java-programming/jvm-jre-jdk)
