# Java常用API

## 概述
API(Application Programming Interface) : 应用程序编程接口

编写一个机器人程序去控制机器人踢足球，程序就需要向机器人发出向前跑、向后跑、射门、抢球等各种命令，没有编过程序的人很难想象这样的程序如何编写。但是对于有经验的开发人员来说，知道机器人厂商一定会提供一些用于控制机器人的Java类，这些类中定义好了操作机器人各种动作的方法。其实，这些Java类就是机器人厂商提供给应用程序编程的接口，大家把这些类称为API。本章涉及的Java API指的就是JDK中提供的各种功能的Java类

## java基础API

### java.lang.Math

提供sin, cos, tan, exp, log, log10 等类方法，PI和E等类字段

### java.lang.String（StringBuilder线程不安全，StringBuffer线程安全）

 <table border="1" width="800" cellspacing="1" cellpadding="1" style="font-size:18px;"><tbody><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">char charAt(int index)<br></span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回给定位置的代码单元<br></span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">boolean equals(Object other)<br>
boolean equalsIngoreCase(String other)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">如果字符串与other相等，返回true<br>
忽略大小写</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">int length()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回字符串的长度</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">String substring(int beginIndex)<br>
String substring(int beginIndex, int endIndex)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回一个新字符串，包含原始字符串从beginIndex到串尾或到endIndex-1的所有代码单元</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">String toLowerCase()<br><span style="font-family:'Microsoft YaHei';font-size:18px;">String toUpperCase()</span><br></span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回小写字符串<br><span style="font-family:'Microsoft YaHei';font-size:18px;">返回大</span><span style="font-family:'Microsoft YaHei';font-size:18px;">写字符串</span><br></span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">int indexOf(String str[, int fromIndex])<br>
int lastIndexOF(String str[, int fromIndex])</span></td>
<td><span style="font-size:18px;">返回第一个/最后一个子串的位置,从起始位置或者fromIndex开始</span></td>
</tr></tbody></table>

### java.util.Scanner
  <table border="1" width="900" cellspacing="1" cellpadding="1" style="font-weight:bold;font-size:24px;"><tbody><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;font-weight:normal;">Scanner(InputStream in)<br>
Scanner(File f)<br>
Scanner(String data)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;font-weight:normal;">用给定的输入流创建一个Scanner对象<br>
例子：Scanner in = new Scanner(System.in)</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;font-weight:normal;">String nextLine()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;font-weight:normal;">读取输入的下一行内容</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;font-weight:normal;">String next()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;font-weight:normal;">读取输入的下一个单词（以空格作为间隔）</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;font-weight:normal;">int nextInt()<br>
double nextDouble()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;font-weight:normal;">读取并转换下一个表示整数或浮点数的字符序列</span></td>
</tr></tbody></table>

### for each循环
for(variable : collection) statement
collection这一集合表达式必须是一个数组或者是一个实现了Iterable接口的类对象

### java.util.Arrays

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">static String toString(type[] a)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回包含a中数据元素的字符串</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">static void sort(type[] a)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">采用优化的快速排序算法对数组进行排序</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">static void binarySearch(type[] a, type v)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">使用二分搜索算法查找值v</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">static Boolean equals(type[] a, type[] b)</span></td>
<td><span style="font-size:18px;">如果两个数字相同，返回true</span></td>
</tr></tbody></table>

### java.util.Radom

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-size:18px;">Random()</span></td>
<td><span style="font-size:18px;">构建一个新的随机数生成器</span></td>
</tr><tr><td><span style="font-size:18px;">int nextInt(int n)</span></td>
<td><span style="font-size:18px;">返回一个 0 ~ n-1之间的随机数</span></td>
</tr></tbody></table>

### java.lang.Object

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">String toString()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回描述该对象值的字符串。在自定义类中应覆盖这个方法</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">boolean equals(Object otherObject)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">比较两个对象是否相等。在自定义类中应覆盖这个方法</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">Class getClass()<br><span style="font-family:'Microsoft YaHei';font-size:18px;">int hashCode()</span><br></span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回包含对象信息的类对象<br><span style="font-family:'Microsoft YaHei';font-size:18px;">返回对象的散列码</span><br></span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">static wait()<br>
static notify()<br>
static notifyAll()</span></td>
<td>&nbsp;</td>
</tr></tbody></table>

### java.lang.Class

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">String getName()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回这个类的名字</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">static Class forName(String className)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回描述类名为className的Class对象</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">Object newInstance()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回这个类的一个新实例</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">Field[] getFields()<br>
Field[] getDeclareFields()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">getFields()返回一个包含Field对象的数组，这些对象记录了这个类或其超类的公有域<br>
getDeclareFields()返回的Field对象记录了这个类的全部域<br></span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">Method[] getMethods()<br>
Method[] getDeclareMethods()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">getMethods()返回一个包含Method对象的数组，这些对象记录了这个类或其超类的公用方法<br>
getDeclareMethods()返回的Field对象记录了这个类的全部方法<br></span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">Constructor[] getConstructors()<br>
Constructor[] getDeclareConstructors()<br></span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">getConstructors()返回一个包含Constructor对象的数组，这些对象记录了这个类的公有构造器<br>
getDeclareConstructors()返回的Constructor对象记录了这个类的全部构造器</span></td>
</tr></tbody></table>

## JAVA集合框架
Java集合类库将接口和实现分离。当程序使用集合时，一旦构建了集合就不需要知道究竟使用了哪种实现。因此，只有在构建集合对象时，使用具体的类才有意义。可以使用接口类型存放集合的引用。利用这种方法，一旦改变想法，可以轻松使用另外一种不同的实现，只需在对象创建处修改即可。

### java.util.Collection<E>

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">Iterator&lt;E&gt; iterator()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回一个用于访问集合中每个元素的迭代器</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">int size()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回当前存储在集合中的元素个数</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">boolean isEmpty()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">如果集合中没有元素，返回true</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">boolean contains(Object obj)<br>
boolean containAll(Collection&lt;? extend E&gt; other)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">如果集合中包含相等对象，返回true</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">boolean add<span style="font-family:'Microsoft YaHei';font-size:18px;">(Object element)<br>
boolean addAll(Collection&lt;? extend E&gt; other)<br></span></span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">将一个元素添加到集合中，集合改变返回true</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">boolean remove(Object element)<br>
boolean removeAll(Collection&lt;?&gt; other)<br></span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">删除相等元素，成功删除返回true</span></td>
</tr></tbody></table>

### java.util.Iterator<E>

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">boolean hasNext()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">如果存在可访问的元素，返回true</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">E next()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回将要访问的下一个对象</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">void remove()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">删除上次访问的元素</span></td>
</tr></tbody></table>

### Java库中具体集合


<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-size:18px;">ArrayList</span></td>
<td><span style="font-size:18px;">一种可以动态增长和缩减的索引序列</span></td>
</tr><tr><td><span style="font-size:18px;">LinkedList</span></td>
<td><span style="font-size:18px;">一种可以在任何位置进行高效插入和删除操作的有序序列</span></td>
</tr><tr><td><span style="font-size:18px;">ArrayDeque</span></td>
<td><span style="font-size:18px;">一种用循环数组实现的双端队列</span></td>
</tr><tr><td><span style="font-size:18px;">HashSet</span></td>
<td><span style="font-size:18px;">一种没有重复元素的无序集合</span></td>
</tr><tr><td><span style="font-size:18px;">TreeSet</span></td>
<td><span style="font-size:18px;">一种有序集</span></td>
</tr><tr><td><span style="font-size:18px;">EnumSet</span></td>
<td><span style="font-size:18px;">一种包含枚举类型值的集合</span></td>
</tr><tr><td><span style="font-size:18px;">LinkedHashSet</span></td>
<td><span style="font-size:18px;">一种可以记住元素插入次序的集</span></td>
</tr><tr><td><span style="font-size:18px;">PriorityQueue</span></td>
<td><span style="font-size:18px;">一种允许高效删除最小元素的集合</span></td>
</tr><tr><td><span style="font-size:18px;">HashMap<span> </span></span></td>
<td><span style="font-size:18px;">一种存储键/值关联的数据结构</span></td>
</tr><tr><td><span style="font-size:18px;">TreeMap</span></td>
<td><span style="font-size:18px;">一种键值有序排列的映射表</span></td>
</tr><tr><td><span style="font-size:18px;">EnumMap<span> </span></span></td>
<td><span style="font-size:18px;">一种键值属于枚举类型的映射表</span></td>
</tr><tr><td><span style="font-size:18px;">LinkedHashMap</span></td>
<td><span style="font-size:18px;">一种可以记住键/值项添加次序的映射表</span></td>
</tr><tr><td><span style="font-size:18px;">WeakHashMap</span></td>
<td><span style="font-size:18px;">一种其值无用武之地后可以被垃圾回收期回收的映射表</span></td>
</tr><tr><td><span style="font-size:18px;">IdentityHashMap</span></td>
<td><span style="font-size:18px;">一种用==而不是用equals比较键值的映射表</span></td>
</tr></tbody></table>

	一、List
List接口扩展自Collection，它可以定义一个允许重复的有序集合，从List接口中的方法来看，List接口主要是增加了面向位置的操作，允许在指定位置上操作元素，同时增加了一个能够双向遍历线性表的新列表迭代器ListIterator。List接口有动态数组（ArrayList类）和双端链表（LinkedList类）两种实现方式。

### java.util.List<E>

<table border="1" width="900" cellspacing="1" cellpadding="1" style="font-size:18px;"><tbody><tr><td><span style="font-size:18px;">ListIterator&lt;E&gt; listIterator()<br>
ListIterator&lt;E&gt; listIterator(int index)<br></span></td>
<td><span style="font-size:18px;">返回一个列表迭代器<br>
迭代器第一次调用next返回给定位置元素</span></td>
</tr><tr><td><span style="font-size:18px;">void add(int i, E element)<br>
void addAll(int i, Colletion&lt;? extend E&gt; elements)</span></td>
<td><span style="font-size:18px;">向集合指定位置添加元素</span></td>
</tr><tr><td><span style="font-size:18px;">E remove(int i)</span></td>
<td><span style="font-size:18px;">删除给定位置元素并返回</span></td>
</tr><tr><td><span style="font-size:18px;">E get(int i)</span></td>
<td><span style="font-size:18px;"><span style="font-size:18px;">获得给定位置元素并返回</span><br></span></td>
</tr><tr><td><span style="font-size:18px;"><span style="font-size:18px;">E set(int i, E element)</span><br></span></td>
<td><span style="font-size:18px;">设置给定位置元素并返回原来的元素</span></td>
</tr><tr><td><span style="font-size:18px;">int indexOf(Object element)<br>
int lastIndexOf(Object element)</span></td>
<td><span style="font-size:18px;">返回与指定元素相等元素在列表中第一次出现的位置<br><span style="font-size:18px;">返回与指定元素相等元素在列表中最后一次出现的位置</span><br></span></td>
</tr></tbody></table>

### java.util.ListIterator<E>

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">void add(E Element)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">在当前位置添加一个元素</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">void set(E Element)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">用新元素代替next或previous上次访问的元素</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">boolean havaPrevious()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">反向迭代列表时是否还有可供访问的值</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">E previous()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回前一个对象</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">int nextIndex()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回下一次调用next时返回的元素索引</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">int previousIndex()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回下一次调用previous时返回的元素索引</span></td>
</tr></tbody></table>

### java.util.ArrayList<E>

<table border="1" width="900" cellspacing="1" cellpadding="1" style="font-size:18px;"><tbody><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">ArrayList&lt;E&gt;()<br></span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">构造一个空数组列表</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">boolean add(E obj)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">在数组列表尾端添加一个元素，永远返回true</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">int size()</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">返回存储在数组中的<span style="color:#ff0000;">当前元素数量</span></span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">void set(int index, E obj)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">设置数组列表指定位置的值</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">E get(int index)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">获的指定位置的元素值</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">void add(int index, E obj)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">向后移动元素，插入元素</span></td>
</tr><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">E remove(int index)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">删除一个元素，并将后面元素前移</span></td>
</tr></tbody></table>

### java.util.LinkedList<E>

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-size:18px;">LinkedList()<br>
LinkedList(Colletion&lt;? extend E&gt; elements)</span></td>
<td><span style="font-size:18px;">构造一个链表</span></td>
</tr><tr><td><span style="font-size:18px;">void addFirst(E element)<br>
void addLast(E element)</span></td>
<td><span style="font-size:18px;">添加元素到表头或表尾</span></td>
</tr><tr><td><span style="font-size:18px;">E getFirst()<br>
E getLast()</span></td>
<td><span style="font-size:18px;"><span style="font-size:18px;">返回表头或表尾的元素</span><br></span></td>
</tr><tr><td><span style="font-size:18px;">E removeFirst()<br>
E removeLast()</span></td>
<td><span style="font-size:18px;">删除表头或表尾的元素并返回</span></td>
</tr></tbody></table>

	二、Set
Set接口扩展自Collection，它与List的不同之处在于，规定Set的实例不包含重复的元素。在一个规则集内，一定不存在两个相等的元素。AbstractSet是一个实现Set接口的抽象类，Set接口有三个具体实现类，分别是散列集HashSet、链式散列集LinkedHashSet和树形集TreeSet。

### java.util.HashSet<E>

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-family:'Microsoft YaHei';font-size:18px;">HashSet()<br><span style="font-size:18px;">HashSet(</span><span style="font-size:18px;">Colletion&lt;? extend E&gt; elements</span><span style="font-size:18px;">)<br></span>HashSet(int initialCapacity)</span></td>
<td><span style="font-family:'Microsoft YaHei';font-size:18px;">构造散列表</span></td>
</tr></tbody></table>

### java.util.LinkedHashSet<E>
LinkedHashSet是用一个链表实现来扩展HashSet类，它支持对规则集内的元素排序。HashSet中的元素是没有被排序的，而LinkedHashSet中的元素可以按照它们插入规则集的顺序提取。

### java.util.TreeSet<E>
TreeSet扩展自AbstractSet，并实现了NavigableSet，AbstractSet扩展自AbstractCollection，树形集是一个有序的Set，其底层是一颗树,用红黑树实现，这样就能从Set里面提取一个有序序列了。在实例化TreeSet时，我们可以给TreeSet指定一个比较器Comparator来指定树形集中的元素顺序。树形集中提供了很多便捷的方法。

	三、队列

### java.util.Queue<E>(接口)

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-size:18px;">boolean add(E element)<br>
boolean offer<span style="font-size:18px;">(E element)</span></span></td>
<td><span style="font-size:18px;">如果队列没有满，将元素添加到队列尾部</span></td>
</tr><tr><td><span style="font-size:18px;">E remove()<br>
E poll()</span></td>
<td><span style="font-size:18px;">如果队列不为空，删除并返回这个队列头部元素</span></td>
</tr><tr><td><span style="font-size:18px;">E element()<br>
E peek()</span></td>
<td><span style="font-size:18px;">如果队列不为空，返回这个队列头部元素</span></td>
</tr></tbody></table>

### java.util.Deque<E>
接口Deque，是一个扩展自Queue的双端队列，它支持在两端插入和删除元素，Deque接口由ArrayDeque和LinkedList这两个类实现，所以通常我们可以使用LinkedList来创建一个队列。PriorityQueue类实现了一个优先队列，优先队列中元素被赋予优先级，拥有高优先级的先被删除。

### java.util.ProrityQueue<E>

优先级队列中的元素可以按任意顺序插入，却总是按照排序的顺序进行检索。优先级队列由堆实现。堆是一个可以自我调整的二叉树，对树执行添加和删除操作，可以让最小元素移动到根（最小堆），而不必花费时间对元素进行排序

	四、Map接口
Map，图，是一种存储键值对映射的容器类，在Map中键可以是任意类型的对象，但不能有重复的键，每个键都对应一个值，真正存储在图中的是键值构成的条目。

###java.util.Map<K,V>

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-size:18px;">V get(Object key)<br></span></td>
<td><span style="font-size:18px;">获得与键对应的值</span></td>
</tr><tr><td><span style="font-size:18px;">V put(K key, V value)<br>
V putAll(Map&lt;? extends K, ? extends V&gt; entries)</span></td>
<td><span style="font-size:18px;">将键与对应的值关系插入到映射中</span></td>
</tr><tr><td><span style="font-size:18px;">boolean containKey(Object key)<br>
boolean containValue(Object value)</span></td>
<td><span style="font-size:18px;">查询</span></td>
</tr></tbody></table> 

### java.util.HashMap<K,V>
HashMap是基于哈希表的Map接口的非同步实现，继承自AbstractMap，AbstractMap是部分实现Map接口的抽象类。在之前的版本中，HashMap采用数组+链表实现，即使用链表处理冲突，同一hash值的链表都存储在一个链表里。但是当链表中的元素较多，即hash值相等的元素较多时，通过key值依次查找的效率较低。而JDK1.8中，HashMap采用数组+链表+红黑树实现，当链表长度超过阈值（8）时，将链表转换为红黑树，这样大大减少了查找时间。

### java.util.LinkedHashMap<K,V>

LinkedHashMap继承自HashMap，它主要是用链表实现来扩展HashMap类，HashMap中条目是没有顺序的，但是在LinkedHashMap中元素既可以按照它们插入图的顺序排序，也可以按它们最后一次被访问的顺序排序。


### java.util.TreeHashMap<K,V>

TreeMap基于红黑树数据结构的实现，键值可以使用Comparable或Comparator接口来排序。TreeMap继承自AbstractMap，同时实现了接口NavigableMap，而接口NavigableMap则继承自SortedMap。SortedMap是Map的子接口，使用它可以确保图中的条目是排好序的。在实际使用中，如果更新图时不需要保持图中元素的顺序，就使用HashMap，如果需要保持图中元素的插入顺序或者访问顺序，就使用LinkedHashMap，如果需要使图按照键值排序，就使用TreeMap。

	五、其他集合类
下面主要介绍一下其它几个特殊的集合类，Vector、Stack、HashTable、ConcurrentHashMap以及CopyOnWriteArrayList。

###java.util.Vector<E>

用法上，Vector与ArrayList基本一致，不同之处在于Vector使用了关键字synchronized将访问和修改向量的方法都变成同步的了，所以对于不需要同步的应用程序来说，类ArrayList比类Vector更高效。

###java.util.Stack<E>

Stack，栈类，是Java2之前引入的，继承自类Vector。

###java.util.HashTable

HashTable和前面介绍的HashMap很类似，它也是一个散列表，存储的内容是键值对映射，不同之处在于，HashTable是继承自Dictionary的，HashTable中的函数都是同步的，这意味着它也是线程安全的，另外，HashTable中key和value都不可以为null。

###java.util.ConcurrentHashMap

ConcurrentHashMap是HashMap的线程安全版。同HashMap相比，ConcurrentHashMap不仅保证了访问的线程安全性，而且在效率上与HashTable相比，也有较大的提高。

###java.util.CopyOnWriteArrayList

CopyOnWriteArrayList，是一个线程安全的List接口的实现，它使用了ReentrantLock锁来保证在并发情况下提供高性能的并发读取。


###java.util.CopyOnWriteArraySet

CopyOnWriteArraySet，是一个线程安全的set接口的实现，它使用了ReentrantLock锁来保证在并发情况下提供高性能的并发读取。


ConcurrentLinkedQuerue是一个先进先出的队列。它是非阻塞队列。

ConcurrentSkipListMap可以在高效并发中替代SoredMap（例如用Collections.synchronzedMap包装的TreeMap）。

ConcurrentSkipListSet可以在高效并发中替代SoredSet（例如用Collections.synchronzedSet包装的TreeMap）。

## 并发部分API

### java.lang.Runnable

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-size:18px;">void run()</span></td>
<td><span style="font-size:18px;">必须覆盖这个方法</span></td>
</tr></tbody></table>

### java.lang.Thread

<table border="1" width="900" cellspacing="1" cellpadding="1"><tbody><tr><td><span style="font-size:18px;">Thread()<br>
Thread(Runnable target)</span></td>
<td><span style="font-size:18px;">构造器</span></td>
</tr><tr><td><span style="font-size:18px;">void start()</span></td>
<td><span style="font-size:18px;">启动线程</span></td>
</tr><tr><td><span style="font-size:18px;">void run()</span></td>
<td><span style="font-size:18px;">如果没有重写，调用关联Runnable的run方法</span></td>
</tr><tr><td><span style="font-size:18px;">void interupt()</span></td>
<td><span style="font-size:18px;">中断线程（中止阻塞状态，对运行线程无作用）</span></td>
</tr><tr><td><span style="font-size:18px;">void setPriority(int newPriority)</span></td>
<td><span style="font-size:18px;">设置优先级（1-10，默认5）</span></td>
</tr><tr><td><span style="font-size:18px;">static&nbsp;void yield()<br>
static void sleep(long millis)</span></td>
<td><span style="font-size:18px;">使当前线程处于让步状态（让步于同优先级或高优先级线程）<br>
休眠</span></td>
</tr><tr><td><span style="font-size:18px;">void setDaemon()</span></td>
<td><span style="font-size:18px;">设置为守护线程</span></td>
</tr><tr><td><span style="font-size:18px;">Thread.State getState()</span></td>
<td><span style="font-size:18px;">获得线程当前状态</span></td>
</tr></tbody></table>

### java.lang.ThreadLocal<T>
将内存共享变量变为线程拷贝变量

> [郭大侠-JAVA常用API整理](https://blog.csdn.net/u013547284/article/details/71158100 "郭大侠-JAVA常用API整理")
