### Java技术（Java Technology）

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

