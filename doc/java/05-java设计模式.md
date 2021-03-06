# 设计模式

## 概述

- 设计模式是人们在面对同类型软件工程设计问题所总结出的一些有用经验。模式不是代码，而是某类问题的通用设计解决方案
- 拥有设计模式词汇，在沟通时就能用更少的词汇来讨论，并且不需要了解底层细节。
- 设计模式可以分为创建型、行为型、结构型
![](https://raw.githubusercontent.com/Jiang-xs/jiangxs/master/assets/9.png)

## 创建型设计模式

### 一、单例模式

单例模式，它的定义就是确保某一个类只有一个实例，并且提供一个全局访问点。

单例模式具备典型的3个特点：1、只有一个实例。 2、自我实例化。 3、提供全局访问点。

因此当系统中只需要一个实例对象或者系统中只允许一个公共访问点，除了这个公共访问点外，不能通过其他访问点访问该实例时，可以使用单例模式。

单例模式的主要优点就是节约系统资源、提高了系统效率，同时也能够严格控制客户对它的访问。也许就是因为系统中只有一个实例，这样就导致了单例类的职责过重，违背了“单一职责原则”，同时也没有抽象类，所以扩展起来有一定的困难。其UML结构图非常简单，就只有一个类，如下图：
![](https://raw.githubusercontent.com/Jiang-xs/jiangxs/master/assets/10.png)

#### 实现方式

- **饿汉方式(线程安全)**
	- JVM在加载这个类时就马上创建此唯一的单例实例，不管你用不用，先创建了再说，如果一直没有被使用，便浪费了空间，典型的空间换时间，每次调用的时候，就不需要再判断，节省了运行时间。
- **懒汉式（非线程安全和synchronized关键字线程安全版本 ）**
	- 单例实例在第一次被使用时构建，而不是在JVM在加载这个类时就马上创建此唯一的单例实例。
	- 这种方式很明显是线程不安全的，如果多个线程同时访问getInstance()方法时就会出现问题。如果想要保证线程安全，一种比较常见的方式就是在getInstance() 方法前加上synchronized关键字，如下：


- **懒汉式(双重检查加锁版本)**
	- 利用双重检查加锁（double-checked locking），首先检查是否实例已经创建，如果尚未创建，“才”进行同步。这样以来，只有一次同步，这正是我们想要的效果。
	- 这种方式相比于使用synchronized关键字的方法，可以大大减少getInstance() 的时间消费

- **懒汉式（登记式/静态内部类方式）**
	- 静态内部实现的单例是懒加载的且线程安全。
	- 只有通过显式调用 getInstance 方法时，才会显式装载 SingletonHolder 类，从而实例化 instance（只有第一次使用这个单例的实例的时候才加载，同时不会有线程安全问题）。

-  **饿汉式（枚举方式）**
	-   它更简洁，自动支持序列化机制，绝对防止多次实例化

### 二、简单工厂

- 简单工厂模式并不是23种常用的设计模式之一，它只算工厂模式的一个特殊实现。简单工厂模式在实际中的应用相对于其他2个工厂模式用的还是相对少得多，因为它只适应很多简单的情况
	- （1）需要创建的对象较少。
	- （2）客户端不关心对象的创建过程。





### 三、工厂方法

### 四、抽象工厂

### 五、原型模式

### 六、建造者模式


## 行为型设计模式

### 一、访问者模式

### 二、模板模式

### 三、策略模式

### 四、状态模式

### 五、观察者模式

### 六、备忘录模式

### 七、中介者模式

### 八、迭代器模式

### 九、解释器模式

### 十、命令模式

### 十一、责任链模式

## 结构型设计模式

### 一、适配器模式

### 二、桥接模式

### 三、组合模式

### 四、装饰模式

### 五、外观模式

### 六、享元模式

### 七、代理模式


