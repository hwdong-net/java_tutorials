数据结构是研究如何存储表示同类型的一组元素并执行有效的数据操作的学科。常见的数据结构有数组Vector、链表List、树Tree、集合Set、散列表HashTable等。

Java 集合框架(The Java collections framework)提供了一种体系结构来存储和操作一组对象(Java的Collection是集合的意思，即同类型的一组数据元素的集合。)。 Java 集合框架提供了一组**接口interfaces**和**类classes** 来实现各种数据结构和算法（Algorithm），即包括：
- **Interfaces 接口**: 接口是指抽象数据类型。它们允许独立于其表示的细节来操作 Java 集合。此外，它们在面向对象的编程语言中形成了层次结构(即接口派生出子接口)。
- **Classes类**：类是接口的实现，同一个接口可以有不同的类实现。
- **Algorithm算法**：算法是指对实现了集合接口的对象进行查找、排序等操作的方法。算法本质上是多态的，因为可以使用相同的方法对不同的接口对象进行操作。


Java collections framework帮程序员实现了常用的典型数据结构，而不需要程序员自己去单独实现这些通用数据结构，可提高程序变量的效率和性能。例如，Java collections framework 提供的类**LinkedList**实现了**双向链表**数据结构。

Java Collections FrameWork 包含： 接口以及接口的实现（类）、算法。java.util 包含 Collection 框架的所有类和接口。

## Interface接口

Java 集合框架提供了各种接口。这些接口包括对集合执行不同操作的各种方法。
![Interfaces of Collections FrameWork](https://cdn.programiz.com/sites/tutorial2program/files/Java-Collections.png)

Interface接口主要分为2种： Collection和Map。

### Collection接口

  Collection接口是集合框架(Collections FrameWork)层次结构的根接口。Collection接口有add()方法向collection中添加一个元素或元素集合、有remove()方法删除一个元素或元素集合、有contains()方法用于搜索元素。例如，add ( Object obj)向Collection对象添加一个元素，而addAll ( Collection c)则添加一个Collection对象c。

Java不提供 Collection接口的直接实现，但提供其子接口（如 List、Set 和 Queue）的实现。Collection接口及其子接口和实现类的层次关系如下
  
  ![](https://static.javatpoint.com/images/java-collection-hierarchy.png)

### Iterable接口

Iterable 接口是所有Collection类的根接口.Collection 接口扩展了 Iterable 接口，因此 Collection 接口的所有子类也实现了 Iterable 接口。
 Iterable 接口只包含一个抽象方法：
 ```java
Iterator<T> iterator()  
 ```
 它返回 T类型元素的迭代器。


### List Interface（List列表接口）

List接口表示一个有序的集合（类似数据结构的线性表），允许我们像数组一样添加和删除元素。列表接口由类 ArrayList、LinkedList、Vector 和 Stack 实现。

要实例化 List 接口，我们必须使用：
```java
List <data-type> list1= new ArrayList();  
List <data-type> list2 = new LinkedList();  
List <data-type> list3 = new Vector();  
List <data-type> list4 = new Stack();  
```
List 接口中有多种方法可用于插入、删除和访问列表中的元素。

#### ArrayList类
ArrayList 类实现了 List 接口。它使用动态数组来存储不同数据类型的多个元素。 ArrayList 类维护插入顺序并且是非同步的。可以随机访问存储在 ArrayList 类中的元素。
```java
import java.util.*;  
class TestJavaCollection1{  
  public static void main(String args[]){  
     ArrayList<String> list=new ArrayList<String>();//Creating arraylist  
     list.add("Ravi");//Adding object in arraylist  
     list.add("Vijay");  
     list.add("Ravi");  
     list.add("Ajay");  
     //Traversing list through Iterator  
     Iterator itr=list.iterator();  
     while(itr.hasNext()){  
          System.out.println(itr.next());  
    }  
  }  
}  
```
输出：
```
Ravi
Vijay
Ravi
Ajay
```

#### LinkedList类
  LinkedList也实现了 List 和 Deque接口 。它在内部使用双向链表来存储元素。它维护插入顺序并且不同步。在 LinkedList 中，操作速度很快，因为不需要移动数据元素。
```java
import java.util.*;  
public class TestJavaCollection2{  
   public static void main(String args[]){  
       LinkedList<String> al=new LinkedList<String>();  
       al.add("Ravi");  
       al.add("Vijay");  
       al.add("Ravi");  
       al.add("Ajay");  
       Iterator<String> itr=al.iterator();  
       while(itr.hasNext()){  
         System.out.println(itr.next());  
       }  
   }  
}  
```
输出：
```
Ravi
Vijay
Ravi
Ajay
```

#### Vector类
Vector 使用动态数组来存储数据元素。它类似于 ArrayList。但是，它是同步的并且包含许多不属于 Collection 框架的方法。
```java
import java.util.*;  
public class TestJavaCollection3{  
   public static void main(String args[]){  
      Vector<String> v=new Vector<String>();  
      v.add("Ayush");  
      v.add("Amit");  
      v.add("Ashish");  
      v.add("Garima");  

      Iterator<String> itr=v.iterator();  
      while(itr.hasNext()){  
         System.out.println(itr.next());  
      }  
   }  
}  
```
输出：
```
Ayush
Amit
Ashish
Garima
```

**[Significant Differences between ArrayList and Vector](https://www.geeksforgeeks.org/vector-vs-arraylist-java/)**
 - **Synchronization**: Vector is synchronized, which means only one thread at a time can access the code, while ArrayList is not synchronized, which means multiple threads can work on ArrayList at the same time.
![](https://media.geeksforgeeks.org/wp-content/uploads/ArrayList-vs-Vector-Java.png)
- **Performance**: ArrayList is faster. Since it is non-synchronized, while vector operations give slower performance since they are synchronized (thread-safe), if one thread works on a vector, it has acquired a lock on it, which forces any other thread wanting to work on it to have to wait until the lock is released.
- **Traversal**: Vector can use both Enumeration and Iterator for traversing over vector elements, while ArrayList can only use Iterator for traversing.
- **Applications**: Most of the time, programmers prefer ArrayList over Vector because ArrayList can be synchronized explicitly using Collections.synchronizedList.

#### Stack 类
Stack（堆栈）是 Vector 的子类。它实现了**后进先出（ last-in-first-out）** 的数据结构，即堆栈。Stack类包含 Vector类的所有方法，还提供了它的方法，如 boolean push()、boolean peek()、boolean push(object o)，这些方法定义了它的属性。
```java
import java.util.*;  
public class TestJavaCollection4{  
   public static void main(String args[]){  
       Stack<String> stack = new Stack<String>();  
       stack.push("Ayush");  
       stack.push("Garvit");  
       stack.push("Amit");  
       stack.push("Ashish");  
       stack.push("Garima");  
       stack.pop();  
       Iterator<String> itr=stack.iterator();  
       while(itr.hasNext()){  
          System.out.println(itr.next());  
       }  
   }  
}  
```
输出：
```
Ayush
Garvit
Amit
Ashish
```

### Queue Interface(Queue队列接口)

Queue队列接口保持先进先出的顺序。它可以定义为一个保存将要处理的元素的**有序列表**。有各种类，如 PriorityQueue(优先队列)实现了 Queue，ArrayDeque接口实现了Deque接口的子接口Deque。Deque（双向队列接口）是Queue接口的子接口。
```java
import java.util.*;  
public class TestJavaCollection5{  
  public static void main(String args[]){  
     PriorityQueue<String> queue=new PriorityQueue<String>();  
     queue.add("Amit Sharma");  
     queue.add("Vijay Raj");  
     queue.add("JaiShankar");  
     queue.add("Raj");  
     System.out.println("head:"+queue.element());  
     System.out.println("head:"+queue.peek());  
     System.out.println("iterating the queue elements:");  
     Iterator itr=queue.iterator();  
     while(itr.hasNext()){  
        System.out.println(itr.next());  
     }  
     queue.remove();  
     queue.poll();  
     System.out.println("after removing two elements:");  
     Iterator<String> itr2=queue.iterator();  
     while(itr2.hasNext()){  
         System.out.println(itr2.next());  
     }  
  }  
}  
```
#### Deque 接口
Deque 接口扩展了 Queue 接口。在双端队列中，我们可以从两侧删除和添加元素。 Deque 代表双端队列，它使我们能够在两端执行操作。

#### ArrayDeque类
ArrayDeque 类实现了 Deque 接口。方便我们使用Deque。与队列不同，我们可以从两端添加或删除元素。
ArrayDeque 比 ArrayList 和 Stack 更快，并且没有容量限制。
```java
import java.util.*;  
public class TestJavaCollection6{  
  public static void main(String[] args) {  
     //Creating Deque and adding elements  
     Deque<String> deque = new ArrayDeque<String>();  
     deque.add("Gautam");  
     deque.add("Karan");  
     deque.add("Ajay");  
     //Traversing elements  
     for (String str : deque) {  
         System.out.println(str);  
     }  
  }  
}  
```
输出：
```
Gautam
Karan
Ajay
```

### Set Interface（Set集合接口）

Set 接口扩展了 Collection 接口。它表示不允许我们存储重复项的无序元素集。我们最多可以在 Set 中存储一个空值。 Set由HashSet、LinkedHashSet和TreeSet实现。
```java
Set<data-type> s1 = new HashSet<data-type>();  
Set<data-type> s2 = new LinkedHashSet<data-type>();  
Set<data-type> s3 = new TreeSet<data-type>();  
```

#### HashSet类
HashSet 类实现了Set 接口。它表示使用哈希表(散列表)进行存储的集合。不保证集合的元素具有某种次序。允许有空元素。
```java
import java.util.*;  
public class TestJavaCollection7{  
public static void main(String args[]){  
    //Creating HashSet and adding elements  
    HashSet<String> set=new HashSet<String>();  
    set.add("Ravi");  
    set.add("Vijay");  
    set.add("Ravi");  
    set.add("Ajay");  
    //Traversing elements  
    Iterator<String> itr=set.iterator();  
    while(itr.hasNext()){  
       System.out.println(itr.next());  
    }  
  }  
}  
```


### Map Interface（映射接口）

A Map is an object that maps keys to values, or is a collection of attribute-value pairs. It models the function abstraction in mathematics. The following picture illustrates a map:

一个Map(映射)是将键(keys)映射到值(values)的对象，或者是属性值对的集合。它模拟了数学中的函数抽象。下图说明了一个map：
![](https://www.codejava.net/images/articles/javacore/collections/map/Map_function_abstraction.png)

请注意，Map 不被视为真正的Collection，因为 Map 接口不扩展 Collection 接口。相反，它在 Java 集合框架中启动了一个独立的分支，如下图所示：
![](https://www.codejava.net/images/articles/javacore/collections/collections%20framework%20overview.png)


在 Map接口的继承树中，有多个实现，但只有 3 个主要的、通用的和通用的实现——它们是 HashMap 和 LinkedHashMap 以及 TreeMap。

- **HashMap**：此实现使用哈希表作为底层数据结构。它实现了所有 Map 操作并允许空值和一个空键。HashMap 不保证其键值元素的顺序。因此，当顺序无关紧要并且可以接受空值时，请考虑使用 HashMap。
- **LinkedHashMap**：该实现使用哈希表和链表作为底层数据结构，因此LinkedHashMap的顺序是可预测的，默认顺序为插入顺序。此实现还允许像 HashMap 这样的空值。因此，当您希望 Map 的键值对按插入顺序排序时，请考虑使用 LinkedHashMap。
- **TreeMap**：该实现使用红黑树作为底层数据结构。 TreeMap 根据其键的自然顺序或创建时提供的比较器进行排序。此实现不允许空值。因此，当您希望 Map 按键的自然顺序（例如字母顺序或数字顺序）或您指定的自定义顺序对其键值对进行排序时，请考虑使用 TreeMap。


```java
Map<Integer, String> mapHttpErrors = new HashMap<>();
 
mapHttpErrors.put(200, "OK");
mapHttpErrors.put(303, "See Other");
mapHttpErrors.put(404, "Not Found");
mapHttpErrors.put(500, "Internal Server Error");
 
System.out.println(mapHttpErrors);
```
输出：
```
{404=Not Found, 500=Internal Server Error, 200=OK, 303=See Other}
```
正如您在输出中看到的那样，HashMap 不会对其键值元素强加任何顺序。
您可以创建一个从现有map复制元素的新map。例如：
```java
Map<Integer, String> mapErrors = new HashMap<>(mapHttpErrors);
```
####  Iterator Interface（迭代器接口）
Iterator 接口提供了可用于访问集合元素的方法。迭代器类似于指向数组中元素的索引，通过迭代器可以遍历访问一个Collection对象的每个元素。

参考文献：
 - [Collections in Java] (https://www.javatpoint.com/collections-in-java)
 - [Java Map Collection Tutorial and Examples](https://www.codejava.net/java-core/collections/java-map-collection-tutorial-and-examples)
 - [The Java Collection Framework Part 1: JDK 5](https://www3.ntu.edu.sg/home/ehchua/programming/java/J5c_Collection.html)
 - [Java Collections Framework - Collections in Java With Examples](https://medium.com/edureka/java-collections-6d50b013aef8)
 - [Collections in Java with Example Programs](https://beginnersbook.com/java-collections-tutorials/)
