数据结构是研究如何存储表示同类型的一组元素并执行有效的数据操作的学科。常见的数据结构有数组Vector、链表List、树Tree、集合Set、散列表HashTable等。
Java集合框架(The Java collections framework)提供了一组**接口interfaces**和**类classes** 来实现各种数据结构和算法。Java的Collection是集合的意思，即同类型的一组数据元素的集合。
Java collections framework帮程序员实现了常用的典型数据结构，而不需要程序员自己去单独实现这些通用数据结构，可提高程序变量的效率和性能。例如，Java collections framework 提供的类**LinkedList**实现了**双向链表**数据结构。

Java Collections FrameWork 包含： 接口以及接口的实现（类）、算法。java.util 包包含 Collection 框架的所有类和接口。Collections FrameWork的层次接口如下：

![](https://static.javatpoint.com/images/java-collection-hierarchy.png)

### Interfaces of Collections FrameWork （Collection框架的接口）

Java 集合框架提供了各种接口。这些接口包括对集合执行不同操作的各种方法。
![Interfaces of Collections FrameWork](https://cdn.programiz.com/sites/tutorial2program/files/Java-Collections.png)

Collection 接口是集合框架层次结构的根接口。Java 不提供 Collection 接口的直接实现，但提供其子接口（如 List、Set 和 Queue）的实现。即Collection 接口包括由 Java 类实现的子接口。

#### List Interface（List列表接口）

List接口表示一个有序的集合（类似数据结构的线性表），允许我们像数组一样添加和删除元素。

#### Set Interface（Set集合接口）

Set 接口允许我们将元素存储在不同的集合中，类似于数学中的集合。它不能有重复的元素。

#### Queue Interface(Queue队列接口)

当我们想要以先进先出的方式存储和访问元素时，使用 Queue 接口。

#### Map Interface（映射接口）
在 Java 中，Map接口允许元素存储在键/值对中。键是可用于访问map中特定元素的唯一名称。而且，每个键都有一个与之关联的值。类似于通过单词查找单词的具体含义的字典。

####  Iterator Interface（迭代器接口）
Iterator 接口提供了可用于访问集合元素的方法。迭代器类似于指向数组中元素的索引，通过迭代器可以遍历访问一个Collection对象的每个元素。