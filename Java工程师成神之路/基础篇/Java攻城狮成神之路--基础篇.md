
Table of Contents
=================

   * [Java攻城狮成神之路(基础篇)](#java攻城狮成神之路基础篇)
   * [面向对象](#面向对象)
      * [1、什么是面向对象、面向过程？](#1什么是面向对象面向过程)
      * [2、面向对象的三大特征、五大基本原则](#2面向对象的三大特征五大基本原则)
         * [单一职责原则SRP(Single Responsibility Principle)](#单一职责原则srpsingle-responsibility-principle)
         * [开放封闭原则OCP(Open－Close Principle)](#开放封闭原则ocpopenclose-principle)
         * [里式替换原则LSP(the Liskov Substitution Principle LSP)](#里式替换原则lspthe-liskov-substitution-principle-lsp)
         * [依赖倒置原则DIP(the Dependency Inversion Principle DIP)](#依赖倒置原则dipthe-dependency-inversion-principle-dip)
         * [接口分离原则ISP(the Interface Segregation Principle ISP)](#接口分离原则ispthe-interface-segregation-principle-isp)
      * [2、平台无关性](#2平台无关性)
         * [1、Java如何实现平台无关](#1java如何实现平台无关)
      * [3、值传递](#3值传递)
         * [1、值传递与引用传递](#1值传递与引用传递)
         * [2、值传递与引用传递的详解](#2值传递与引用传递的详解)
      * [4、类变量、成员变量、局部变量](#4类变量成员变量局部变量)
         * [成员变量和局部变量的区别](#成员变量和局部变量的区别)
         * [类(静态)变量](#类静态变量)
         * [成员变量和类(静态)变量的区别](#成员变量和类静态变量的区别)
         * [static关键字](#static关键字)
   * [Java基础知识](#java基础知识)
      * [1、数据类型](#1数据类型)
         * [1、Java的8中基本数据类型](#1java的8中基本数据类型)
         * [2、单精度和双精度](#2单精度和双精度)
      * [2、自动拆箱装箱](#2自动拆箱装箱)
         * [1、基本数据类型和包装类型](#1基本数据类型和包装类型)
         * [2、自动装箱和自动拆箱](#2自动装箱和自动拆箱)
         * [3、自动装箱和自动拆箱的实现](#3自动装箱和自动拆箱的实现)
         * [4、相关问题补充](#4相关问题补充)
      * [3、String](#3string)
         * [1、字符串的不可变性](#1字符串的不可变性)
         * [2、java中replace、replaceFirst和replaceAll区别](#2java中replacereplacefirst和replaceall区别)
         * [3、String对” “的重载](#3string对的重载)
         * [4、字符串的拼接方式与区别](#4字符串的拼接方式与区别)
         * [5、String valueOf()和<code>toString()</code>的区别](#5string-valueof和tostring的区别)
         * [6、switch中对String的支持](#6switch中对string的支持)
         * [7、==和equals()方法的区别](#7和equals方法的区别)
         * [8、字符串常量池](#8字符串常量池)
                     * [补充：字符串常量池是什么？](#补充字符串常量池是什么)
            * [补充：字符串常量池里放什么？](#补充字符串常量池里放什么)
         * [9、Class常量池](#9class常量池)
            * [补充：什么是字面量和符号引用？](#补充什么是字面量和符号引用)
         * [10、运行时常量池](#10运行时常量池)
      * [集合类](#集合类)
         * [1、常用集合类的使用总结](#1常用集合类的使用总结)
            * [1、集合体系结构图](#1集合体系结构图)
            * [2、Collection中的常用功能](#2collection中的常用功能)
            * [3、迭代器](#3迭代器)
            * [4、泛型](#4泛型)
            * [5、List序列](#5list序列)
               * [1、List特有方法](#1list特有方法)
               * [2、List的常用子类](#2list的常用子类)
               * [3、Set集合及其常用子类](#3set集合及其常用子类)
               * [4、Map集合及其子类](#4map集合及其子类)
      * [2、集合间的区别与总结](#2集合间的区别与总结)
      * [3、Collections工具类](#3collections工具类)
         * [1、Collection与Collections的区别](#1collection与collections的区别)
# Java攻城狮成神之路(基础篇)

# 面向对象

## 1、什么是面向对象、面向过程？

- 面向对象

  > 把数据及对数据的操作方法放在一起，作为一个相互依存的整体——对象。对同类对象抽象出其共性，形成类。类中的大多数数据，只能用本类的方法进行处理。类通过一个简单的外部接口与外界发生关系，对象与对象之间通过消息进行通信。程序流程由用户在使用中决定。

- 面向过程

  > 自顶向下顺序执行，逐步求精；其程序结构是按功能划分为若干个基本模块，这些模块形成一个树状结构；各模块之间的关系尽可能简单，在功能上相对独立；每一模块内部均是由顺序、选择和循环三种基本结构组成；其模块化实现的具体方法是使用子程序。程序流程在写程序时就已决定。

  转自——[Hi_PAUL](https://blog.csdn.net/u013220032)

## 2、面向对象的三大特征、五大基本原则

- 三大基本特征

  1. 封装

     > 封装是面向对象的特征之一，是对象和类概念的主要特性。
     >
     > 封装，也就是把客观事物封装成抽象的类，并且类可以把自己的数据和方法只让可信的类或者对象操作，对不可信的进行信息隐藏。

  2. 继承

     > 继承，指可以让某个类型的对象获得另一个类型的对象的属性的方法。简单说，多个类有共同的成员，将这些成员抽取到另外一个类中(父类、基类)，再让多个类继承父类，多个类便有了父类的成员。

     - 继承的特点:
       1. Java中只支持单一多层继承
       2. 可以调用父类，及父类的父类的成员
       3. 就近原则: 当父类和子类拥有相同成员时，若没有方法重写，子类成员方法优先调用子类自己的成员变量。
     - 继承中成员变量的特点:
       1. 子类只能获取父类的非私有成员
       2. 子父类中，成员的调用遵循就近原则
     - 继承中成员方法的特点:
       1. **方法重写(@Override)**: 当子父类中有完全相同的方法时，调用子类对象，会调用子类中的该方法 
       2. **方法重载(@Overload)**: 同一个类中，有多个方法名相同但参数不同的方法。与返回值无关。参数个数，位置，类型不同。
     - 继承中构造方法的的执行顺序
       1. 子类构造方法第一行没有调用父类构造，默认调用父类无参构造
       2. 构造方法调用构造方法只能位于构造方法的第一行
       3. 肯定会先调用父类构造方法，因为要为父类的变量初始化。
     - 继承的实现方式
       1. 实现继承：指直接使用 基类的属性和方法而无需额外编码的能力
       2. 接口继承: 是指仅使用属性和方法的名称、但是子类必须提供实现的能力。

  3. 多态

     > 多态，是指一个类实例的相同方法在不同情形有不同表现形式。

     - 多态的特点
       1. 必须有继承关系
       2. 必须有方法的重写(子类实现父类接口也可)
       3. 父类的引用指向子类对象
       4. 动态绑定: 运行期间调用的方法，是根据子类/右边类型决定。
     - 成员特点
       - 成员变量：编译和运行都是根据左边父类
       - 成员方法: 
         - 编译时根据左边父类，若父类缺少该方法，编译无法通过。
         - 运行时根据右边子类，若子类没有方法重写，调用父类方法。

- 五大基本原则

  - ### 单一职责原则SRP(Single Responsibility Principle)

    > 是指一个类的功能要单一，不能包罗万象。如同一个人一样，分配的工作不能太多，否则一天到晚虽然忙忙碌碌的，但效率却高不起来。

  - ### 开放封闭原则OCP(Open－Close Principle)

    > 一个模块在扩展性方面应该是开放的而在更改性方面应该是封闭的。比如：一个网络模块，原来只服务端功能，而现在要加入客户端功能，那么应当在不用修改服务端功能代码的前提下，就能够增加客户端功能的实现代码，这要求在设计之初，就应当将服务端和客户端分开，公共部分抽象出来。

  - ### 里式替换原则LSP(the Liskov Substitution Principle LSP)

    > 子类应当可以替换父类并出现在父类能够出现的任何地方。比如：公司搞年度晚会，所有员工可以参加抽奖，那么不管是老员工还是新员工，也不管是总部员工还是外派员工，都应当可以参加抽奖，否则这公司就不和谐了。

  - ### 依赖倒置原则DIP(the Dependency Inversion Principle DIP)

    > 具体依赖抽象，上层依赖下层。假设B是较A低的模块，但B需要使用到A的功能，这个时候，B不应当直接使用A中的具体类： 而应当由B定义一抽象接口，并由A来实现这个抽象接口，B只使用这个抽象接口：这样就达到了依赖倒置的目的，B也解除了对A的依赖，反过来是A依赖于B定义的抽象接口。通过上层模块难以避免依赖下层模块，假如B也直接依赖A的实现，那么就可能 造成循环依赖。一个常见的问题就是编译A模块时需要直接包含到B模块的cpp文件，而编译B时同样要直接包含到A的cpp文件。

  - ### 接口分离原则ISP(the Interface Segregation Principle ISP)

    > 模块间要通过抽象接口隔离开，而不是通过具体的类强耦合起来

《五大基本原则》转自——[woshihaiyong168](https://blog.csdn.net/woshihaiyong168)

## 2、平台无关性

### 1、Java如何实现平台无关

- Java如何支持平台无关性
  1. Java平台扮演Java程序和所在的硬件与操作系统之间的缓冲角色。这样Java程序只需要与Java平台打交道，而不用管具体的操作系统。
  2. Java语言保证了基本数据类型的值域和行为都是由语言自己定义的。而C/C++中，基本数据类是由它的占位宽度决定的，占位宽度由所在平台决定的。不同平台编译同一个C++程序会出现不同的行为。通过保证基本数据类型在所有平台的一致性，Java语言为平台无关性提供强有力的支持。
  3. Java class文件。Java程序最终会被编译成二进制class文件。class文件可以在任何平台创建，也可以被任何平台的Java虚拟机装载运行。它的格式有着严格的定义，是平台无关的。
  4. 可伸缩性。Sun通过改变API的方式得到三个基础API集合，表现为Java平台不同的伸缩性：J2EE,J2SE,J2ME。
- 实现平台无关性的7大步骤
  1. 选择程序运行的主机和设备集合（目标宿主机）
  2. 在目标宿主机中选择Java平台版本。
  3. 对于每个目标宿主机，选择程序将要运行的Java平台实现（目标运行时环境）
  4. 编写程序，调用Java API标准运行库（不调用本地方法，或者专门开发商专门调用本地方法的库）
  5. 编写程序，不依赖于垃圾收集器收集垃圾时间，不依赖线程的优先级
  6. 努力设计用户界面，在所有的目标宿主机都能正常工作
  7. 在所有目标运行时环境和所有目标宿主机进行测试

转自——[箫筱沐羽](https://blog.csdn.net/lincolnmi)

## 3、值传递

### 1、值传递与引用传递

> Java中方法参数传递方式是按值传递
>
> - 如果参数是基本类型，传递的是基本类型的字面量值的拷贝。
> - 如果参数是引用类型，传递的是该参量所引用的对象在堆中地址值的拷贝。

转自——[祖春雷](https://www.zhihu.com/people/zu-chun-lei)

### 2、值传递与引用传递的详解

**1、搞清楚 基本类型 和 引用类型的不同之处**

```java
int num = 10;
String str = "hello";
```

![1](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/1.png)

> 如图所示，num是基本类型，值就直接保存在变量中。而str是引用类型，变量中保存的只是实际对象的地址。一般称这种变量为"引用"，引用指向实际对象，实际对象中保存着内容。

**2、搞清楚赋值运算符（=）的作用**

```java
num = 20;
str = "java";
```

> 对于基本类型 num ，赋值运算符会直接改变变量的值，原来的值被覆盖掉。
> 对于引用类型 str，赋值运算符会改变引用中所保存的地址，原来的地址被覆盖掉。但是原来的对象不会被改变（重要）。
> 如上图所示，"hello" 字符串对象没有被改变。（没有被任何引用所指向的对象是垃圾，会被垃圾回收器回收）

![2](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/2.png)

**3、调用方法时发生了什么？参数传递基本上就是赋值操作。**

```java
//第一个例子：基本类型
void foo(int value) {
    value = 100;
}
foo(num); // num 没有被改变

//第二个例子：没有提供改变自身方法的引用类型
void foo(String text) {
    text = "windows";
}
foo(str); // str 也没有被改变

//第三个例子：提供了改变自身方法的引用类型
StringBuilder sb = new StringBuilder("iphone");
void foo(StringBuilder builder) {
    builder.append("4");
}
foo(sb); // sb 被改变了，变成了"iphone4"。

//第四个例子：提供了改变自身方法的引用类型，但是不使用，而是使用赋值运算符。
StringBuilder sb = new StringBuilder("iphone");
void foo(StringBuilder builder) {
    builder = new StringBuilder("ipad");
}
foo(sb); // sb 没有被改变，还是 "iphone"。
```

重点理解为什么，第三个例子和第四个例子结果不同？

下面是第三个例子的图解：

![3](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/3.png)

builder.append("4")之后

![4](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/4.png)

下面是第四个例子的图解：

![5](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/5.png)

builder = new StringBuilder("ipad"); 之后

![6](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/6.png)

转自——[Intopass](https://www.zhihu.com/people/intopass)

## 4、类变量、成员变量、局部变量

### 成员变量和局部变量的区别

- 成员变量

  1. 成员变量定义在类中，在整个类中都可以被访问。
  2. 成员变量随着对象的建立而建立，随着对象的消失而消失，存在于对象所在的堆内存中。
  3. 成员变量有默认初始化值。

- 局部变量

  1. 局部变量只定义在局部范围内，如：函数内，语句内等，只在所属的区域有效。
  2. 局部变量存在于栈内存中，作用的范围结束，变量空间会自动释放。
  3. 局部变量没有默认初始化值 

- 在使用变量时需要遵循的原则为：就近原则

  首先在局部范围找，有就使用；接着在成员位置找。

### 类(静态)变量

- 类(静态)变量

  1. 由static修饰的变量称为静态变量，其实质上就是一个全局变量。

     > 如果某个内容是被所有对象所共享，那么该内容就应该用静态修饰；没有被静态修饰的内容，其实是属于对象的特殊描述。

  2. 不同的对象的实例变量将被分配不同的内存空间， 如果类中的成员变量有类变量，那么所有对象的这个类变量都分配给相同的一处内存，改变其中一个对象的这个类变量会影响其他对象的这个类变量，也就是说对象共享类变量。

### 成员变量和类(静态)变量的区别

1. 生命周期不同
   - 成员变量随着对象的创建而存在，随着对象的回收而释放。
   - 静态变量随着类的加载而存在，随着类的消失而消失。
2. 调用方式不同
   - 成员变量只能被对象调用。
   - 静态变量可以被对象调用，还可以被类名调用。
3. 别名不同
   - 成员变量也称为实例变量。
   - 静态变量也称为类变量。
4. 数据存储位置不同
   - 成员变量存储在堆内存的对象中，所以也叫对象的特有数据。
   - 静态变量数据存储在方法区（共享数据区）的静态区，所以也叫对象的共享数据。

### static关键字

> 是一个修饰符，用于修饰成员(成员变量和成员函数)

特点：

- 想要实现对象中的共性数据的对象共享。可以将这个数据进行静态修饰。
- 被静态修饰的成员，可以直接被类名所调用。也就是说，静态的成员多了一种调用方式。类名.静态方式。
- 静态随着类的加载而加载。而且优先于对象存在。

转自——[cy扯淡](https://www.cnblogs.com/cy19/)

# Java基础知识

## 1、数据类型

### 1、Java的8中基本数据类型

| 序号 |    数据类型     | 位数 | 默认值 |          取值范围          | 举例说明           |
| :--: | :-------------: | :--: | :----: | :------------------------: | :----------------- |
|  1   |    byte(位)     |  8   |   0    |   $$ (-2^7) - (2^7-1)$$    | `byte b = 10`      |
|  2   |  short(短整数)  |  16  |   0    | $$(-2^{15}) - (2^{15}-1)$$ | `short s = 10;`    |
|  3   |    int(整数)    |  32  |   0    |  $$(-2^{31})-(2^{31}-1)$$  | `int i = 10;`      |
|  4   |  long(长整数)   |  64  |   0    | $$(-2^{63}) - (2^{63}-1)$$ | `long l = 10L`     |
|  5   |  float(单精度)  |  32  |  0.0   | $$(-2^{31}) - (2^{31}-1)$$ | `float f = 10.0f`  |
|  6   | double(双精度)  |  64  |  0.0   |  $$(-2^{63})-(2^{63}-1)$$  | `double d = 10.0d` |
|  7   |   char(字符)    |  16  |   空   |      $$0-(2^{16}-1)$$      | `char c = ‘c’`     |
|  8   | boolean(布尔值) |  8   | false  |         true,false         | `boolean b = true` |

### 2、单精度和双精度

- 单精度

  > 1位符号位，8位指数，23位小数

![单精度](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/Java%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86/1%E3%80%81%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B/2%E3%80%81%E5%8D%95%E7%B2%BE%E5%BA%A6%E5%92%8C%E5%8F%8C%E7%B2%BE%E5%BA%A6/%E5%8D%95%E7%B2%BE%E5%BA%A6.jpg)

- 双精度

  > 1位符号位，11位指数，52位小数

![双精度](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/Java%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86/1%E3%80%81%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B/2%E3%80%81%E5%8D%95%E7%B2%BE%E5%BA%A6%E5%92%8C%E5%8F%8C%E7%B2%BE%E5%BA%A6/%E5%8F%8C%E7%B2%BE%E5%BA%A6.jpg)



## 2、自动拆箱装箱

### 1、基本数据类型和包装类型

- 基本数据类型及其所对应的包装类

| 基本数据类型 |  包装类   |
| :----------: | :-------: |
|     byte     |   Byte    |
|    short     |   Short   |
|     int      |  Integer  |
|     long     |   Long    |
|    float     |   Float   |
|    double    |  Double   |
|     char     | Character |
|   boolean    |  Boolean  |

- 包装类的主要作用

  > 进行基本数据类型和字符串之间的转换

- 基本数据类型转换为字符串的三种方式

  1. 基本数据类型包装类的中的方法: `static String toString(基本类型)`
  2. String类中的方法: `static String valueOf(基本类型)`
  3. 基本数据类型+“”;

- 字符串到基本数据类型的转换

  基本数据类型 变量名 = 基本数据类型.parseXxx(XxxString);

### 2、自动装箱和自动拆箱

- 自动装箱: 自动将基本数据类型转换为包装器类型
- 自动拆箱: 自动将包装器类型转换为基本数据类型

### 3、自动装箱和自动拆箱的实现

- 自动装箱: 是通过调用包装器的`valueOf()`方法实现的
- 自动拆箱: 是通过调用包装器的`XxxValue()`方法实现的

### 4、相关问题补充

1. 下面这段代码输出结果是什么？

```java
public class Main {
    public static void main(String[] args) {
         
        Integer i1 = 100;
        Integer i2 = 100;
        Integer i3 = 200;
        Integer i4 = 200;
         
        System.out.println(i1==i2);	//true
        System.out.println(i3==i4);	//false
    }
}
```

- Integer赋值的实现过程: 

```java
public static Integer valueOf(int i) {
        if(i >= -128 && i <= IntegerCache.high)
            return IntegerCache.cache[i + 128];
        else
            return new Integer(i);
}
```

- IntegerCache类源码:

```java
private static class IntegerCache {
        static final int high;
        static final Integer cache[];

        static {
            final int low = -128;

            // high value may be configured by property
            int h = 127;
            if (integerCacheHighPropValue != null) {
                // Use Long.decode here to avoid invoking methods that
                // require Integer's autoboxing cache to be initialized
                int i = Long.decode(integerCacheHighPropValue).intValue();
                i = Math.max(i, 127);
                // Maximum array size is Integer.MAX_VALUE
                h = Math.min(i, Integer.MAX_VALUE - -low);
            }
            high = h;

            cache = new Integer[(high - low) + 1];
            int j = low;
            for(int k = 0; k < cache.length; k++)
                cache[k] = new Integer(j++);
        }

        private IntegerCache() {}
}
```

- 解释: Integer的缓存机制(常量池)

  > 在通过valueOf方法创建Integer对象的时候，如果数值在[-128,127]之间，便返回指向IntegerCache.cache中已经存在的对象的引用；否则创建一个新的Integer对象。
  >
  > 上面的代码中i1和i2的数值为100，因此会直接从cache中取已经存在的对象，所以i1和i2指向的是同一个对象，而i3和i4则是分别指向不同的对象。

2. 下面这段代码输出结果是什么?

```java
public class Main {
    public static void main(String[] args) {
         
        Double i1 = 100.0;
        Double i2 = 100.0;
        Double i3 = 200.0;
        Double i4 = 200.0;
         
        System.out.println(i1==i2); //false
        System.out.println(i3==i4); //false
    }
}
```

- 解释:

  > 在某个范围内的整型数值的个数是有限的，而浮点数却不是。
  >
  > Integer、Short、Byte、Character、Long这几个类的valueOf方法的实现是类似的。Double、Float的valueOf方法的实现是类似的。

3. 下面这段代码输出结果是什么？

```java
public class Main {
    public static void main(String[] args) {
         
        Boolean i1 = false;
        Boolean i2 = false;
        Boolean i3 = true;
        Boolean i4 = true;
         
        System.out.println(i1==i2); //true
        System.out.println(i3==i4); //true
    }
}
```

- Boolean valueOf()源码

  ```java
  public static Boolean valueOf(boolean b) {
          return (b ? TRUE : FALSE);
  }
  
  public static final Boolean TRUE = new Boolean(true);
  public static final Boolean FALSE = new Boolean(false);
  ```

4. `Integer i = new Integer(xx);`和`Integer i = xx;`的区别
   - 第一种方式不会触发自动装箱的过程；而第二种方式会触发；
   - 在执行效率和资源占用上的区别。第二种方式的执行效率和资源占用在一般性情况下要优于第一种情况（注意这并不是绝对的）。
5. 下面这段代码输出结果是什么？

```java
public class Main {
    public static void main(String[] args) {
         
        Integer a = 1;
        Integer b = 2;
        Integer c = 3;
        Integer d = 3;
        Integer e = 321;
        Integer f = 321;
        Long g = 3L;
        Long h = 2L;
         
        System.out.println(c==d); //true
        System.out.println(e==f); //false
        System.out.println(c==(a+b)); //true
        System.out.println(c.equals(a+b)); //false❌ 
        System.out.println(g==(a+b)); //false❌
        System.out.println(g.equals(a+b)); //false
        System.out.println(g.equals(a+h)); //true
    }
}
```

- 解释:

  > - 当 "=="运算符的两个操作数都是 包装器类型的引用，则是比较指向的是否是同一个对象
  > - 而如果其中有一个操作数是表达式（即包含算术运算）则比较的是数值（即会触发自动拆箱的过程）
  > - 对于包装器类型，equals方法并不会进行类型转换

转自——[海子](http://www.cnblogs.com/dolphin0520/)

## 3、String

### 1、字符串的不可变性

> String类中每一个看似修改String的方法,实际上都创建了一个新的String对象,而最初的String对象则丝毫未动。因为其底层源码**为final修饰**的`char[]`数组
>
> java传递参数的时候,传递的是引用的一个拷贝,调用时,都会复制一份引用,而引用所指向的对象,一直呆在某一单一物理位置,从未变动过.

转自——[唐丶莱布尼茨](https://blog.csdn.net/Dextrad_ihacker)

图解:

- 声明一个字符串：`String s = “abcd”;`

  ![1](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/Java%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86/3%E3%80%81String/1.jpeg)

- 将一个字符串变量分配给另一个字符串变量：`String s2 = s;` 

  > s2储存了一个相同的引用值，因为它是同一个字符串对象。

  ![2](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/Java%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86/3%E3%80%81String/2.jpeg)

- 合并字符串”ef“到s: `s = s.concat("ef");`

  ![3](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/Java%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86/3%E3%80%81String/3.jpeg)

总结:

- 一旦在内存（堆）中创建了一个字符串，它就不能被改变。所有字符串的方法都没有去改变字符串自己，而是返回了一个新对象。
- 如果我们需要一个可以修改的字符串，我们将需要使用**StringBuffer** 或 **StringBuilder**. 否则，垃圾收集会浪费大量时间，因为每次创建一个新的字符串。

转自——[在下贼溜](https://blog.csdn.net/weixin_37668042)

### 2、java中replace、replaceFirst和replaceAll区别

- `replace()`的参数是char和CharSequence,即可以支持字符的替换,也支持字符串的替换(CharSequence即字符串序列的意思,说白了也就是字符串);
- `replaceAll()`的参数是regex,即基于规则表达式的替换,比如,可以通过`replaceAll("\\d", "*")`把一个字符串所有的数字字符都换成星号;
- `replaceFirst()`这个方法也是基于规则表达式的替换,但与`replaceAll()`不同的是,只替换第一次出现的字符串;
- 如果`replaceAll()`和`replaceFirst()`所用的参数据不是基于规则表达式的,则与`replace()`替换字符串的效果是一样的,即这两者也支持字符串的操作;

### 3、String对”+“的重载

> 每调用一次“+”，编译器都会创建一个新的`StringBuilder`对象，并调用其中的`append()`方法进行字符串的拼接，然后再调用`toString()`方法返回拼接的字符串。
>
> 因此，为了更加高效应该先使用`StringBuilder`进行拼接后，调用`toString()`方法转换为字符串。

```java
public class StringTest {
    public static void main(String[] args) {

        String apple = "Apple,";
        String fruit = apple + "Pear," + "Orange";

        System.out.println(fruit); //输出：Apple,Pear,Orange
    }
}
```

> 编译器在执行上述代码的时候会的自动引入 java.lang.StringBuilder 类，因为更加高效。
>
> 编译器会创建一个 StringBuilder 对象，用来构造最终要生成的 String，并为每一个字符串调用一次 StringBuilder 中的 append() 方法，因此上述代码一共执行了三次 append() 方法。最后调用 toString 生成最终的结果，并保存为 fruit。

转自——[留兰香丶](https://blog.csdn.net/codejas)

### 4、字符串的拼接方式与区别

- `StringBuilder append();`
- `String +`
- `String format();`

> 不论是通过String的”+“，还是`String format()`底层实现都是基于`StringBuilder append();`**在使用大量字符串拼接的时候优先使用StringBuilder.**

### 5、`String valueOf()`和`toString()`的区别

- 将对象转换为String类型的的方法：

  - (String)[对象]

    > 这是标准的类型转换，将对象强制转换为String类型，前提是**该对象必须能保证转成String类型**，**否则将抛出ClassCastException异常**

  - toString

    > 此方法返回对象本身，在java.lang.Object类中也有toString()方法，所以Java对象都可以调用此方法，但使用的时候**必须保证要转换的对象不为null**，**否则将抛出NullPointerException异常**

  - String.valueOf()

    > 从上面源码可以看出，我们不用担心Object为null，但使用的时候也要小心，**当Object为null时，它的返回值是“null”，而不是null**，是有区别的。

转自——[麦田](https://blog.csdn.net/itmyhome)

### 6、switch中对String的支持

> 底层使用了`equals();`方法对字符串进行比较

### 7、==和equals()方法的区别

| 比较 |               ==               |                  equals()                  |
| :--: | :----------------------------: | :----------------------------------------: |
| 层次 | 操作符==是进行的浅层次的比较。 | equals方法被认为是对象的值进行深层次的比较 |
| 类型 |   对象的地址值和基本类型的值   |                 对象的内容                 |
| 对象 |     对象引用地址相同，为真     |          两个对象内容相同时，为真          |
|  值  |          值相同，为真          |                                            |

### 8、字符串常量池

> 减少了字符串分配时耗费的时间和空间，从而提高了性能，减少了开销。

- 每当代码创建字符串常量时，JVM会首先检查字符串常量池
  - 如果字符串已经存在池中，就返回池中的实例引用
  - 如果字符串不在池中，就会实例化一个字符串并放到池中
- **通过new操作符创建的字符串对象不指向字符串池中的任何对象**，但是可以通过使用字符串的intern()方法来指向其中的某一个。
- 为了优化空间，运行时实例创建的全局字符串常量池中有一个表，总是为池中每个唯一的字符串对象维护一个引用。这就意味着它们一直引用着字符串常量池中的对象，所以，**在常量池中的这些字符串不会被垃圾收集器回收**。

原文链接： [xyzws](http://www.xyzws.com/Javafaq/what-is-string-literal-pool/3) 翻译： [ImportNew.com ](http://www.importnew.com/)- [lumeng689](http://www.importnew.com/author/lumeng689)
译文链接： <http://www.importnew.com/10756.html>

#### 补充：字符串常量池是什么？

- 在HotSpot VM里实现的string pool功能的是一个StringTable类，它是一个Hash表，默认值大小长度是1009；这个StringTable在每个HotSpot VM的实例只有一份，被所有的类共享。字符串常量由一个一个字符组成，放在了StringTable上。
- 在JDK6.0中，StringTable的长度是固定的，长度就是1009，因此如果放入String Pool中的String非常多，就会造成hash冲突，导致链表过长，当调用String#intern()时会需要到链表上一个一个找，从而导致性能大幅度下降
- 在JDK7.0中，StringTable的长度可以通过参数指定：

```java
-XX:StringTableSize=66666
```

#### 补充：字符串常量池里放什么？

- 在JDK6.0及之前版本中，String Pool里放的都是字符串常量；
- 在JDK7.0中，由于String#intern()发生了改变，因此String Pool中也可以存放放于堆内的字符串对象的引用。
- 字符串常量池中的字符串只存在一份！ 

转自——[zhuminChosen](https://blog.csdn.net/zm13007310400)

原文链接：https://blog.csdn.net/zm13007310400/article/details/77534349

### 9、Class常量池

- 我们写的每一个Java类被编译后，就会形成一份class文件；class文件中除了包含类的版本、字段、方法、接口等描述信息外，还有一项信息就是常量池(constant pool table)，用于存放编译器生成的各种字面量(Literal)和符号引用(Symbolic References)；
  每个class文件都有一个class常量池。

#### 补充：什么是字面量和符号引用？

- 字面量包括：1.文本字符串 2.八种基本类型的值 3.被声明为final的常量等;
- 符号引用包括：1.类和方法的全限定名 2.字段的名称和描述符 3.方法的名称和描述符。

转自——[zhuminChosen](https://blog.csdn.net/zm13007310400)

原文链接：https://blog.csdn.net/zm13007310400/article/details/77534349

### 10、运行时常量池

- 运行时常量池存在于内存中，也就是class常量池被加载到内存之后的版本，不同之处是：它的字面量可以动态的添加(String#intern()),符号引用可以被解析为直接引用
- VM在执行某个类的时候，必须经过加载、连接、初始化，而连接又包括验证、准备、解析三个阶段。而当类加载到内存中后，jvm就会将class常量池中的内容存放到运行时常量池中，由此可知，运行时常量池也是每个类都有一个。在解析阶段，会把符号引用替换为直接引用，解析的过程会去查询字符串常量池，也就是我们上面所说的StringTable，以保证运行时常量池所引用的字符串与字符串常量池中是一致的。

转自——[zhuminChosen](https://blog.csdn.net/zm13007310400)

原文链接：https://blog.csdn.net/zm13007310400/article/details/77534349

## 集合类

### 1、常用集合类的使用总结

#### 1、集合体系结构图

![1、常用集合类的使用总结——集合体系结构图](https://github.com/GooderYan/toBeTopJavaer/blob/master/Java%E5%B7%A5%E7%A8%8B%E5%B8%88%E6%88%90%E7%A5%9E%E4%B9%8B%E8%B7%AF/%E5%9F%BA%E7%A1%80%E7%AF%87/%E7%9B%B8%E5%85%B3%E5%9B%BE%E7%89%87/%E9%9B%86%E5%90%88%E7%B1%BB/1%E3%80%81%E5%B8%B8%E7%94%A8%E9%9B%86%E5%90%88%E7%B1%BB%E7%9A%84%E4%BD%BF%E7%94%A8%E6%80%BB%E7%BB%93%E2%80%94%E2%80%94%E9%9B%86%E5%90%88%E4%BD%93%E7%B3%BB%E7%BB%93%E6%9E%84%E5%9B%BE.png)

#### 2、Collection中的常用功能

| 返回值   | 方法                | 解释                                         |
| -------- | :------------------ | :------------------------------------------- |
| boolean  | add(Object e);      | 向集合中添加元素                             |
| void     | clear();            | 清空集合中的所有元素                         |
| boolean  | contains(Object o); | 判断集合中是否包含某元素                     |
| boolean  | isEmpty();          | 判断集合中的元素是否为空                     |
| boolean  | remove(Object o);   | 根据元素的内容来删除某个元素。               |
| Object[] | toArray();          | 将集合转换成数组并把集合中的元素存储到数组中 |
| int      | size();             | 获取集合的长度。                             |

#### 3、迭代器

> Collection集合元素的通用获取方式：在取元素之前先要判断集合中有没有元素，如果有，就把这个元素取出来，继续在判断，如果还有就再取出出来。一直把集合中的所有元素全部取出。这种取出方式专业术语称为迭代。

1. Iterator接口的常用方法

   | 返回值  | 方法       | 解释                                             |
   | ------- | ---------- | ------------------------------------------------ |
   | E       | next();    | 用来返回迭代的下一个元素，并把指针向后移动一位。 |
   | boolean | hasNext(); | 判断集合中是否有元素可以迭代                     |

2. 并发修改异常

   > java.util.ConcurrentModificationExcepiton
   >
   > 迭代器是依赖于集合的，相当于集合的一个副本，当迭代器在操作的时候，如果发现和集合不一样，则抛出异常。

   解决方案：

   1. 不使用迭代器遍历集合
   2. 依然使用迭代器遍历,那么就需要使用Iterator的子接口ListIterator来实现向集合中添加

#### 4、泛型

> 使用集合存储自定义对象并遍历，由于集合可以存储任意类型的对象，当我们存储了不同类型的对象，就有可能在转换的时候出现类型转换异常。
>
> 所以java为了解决这个问题，给我们提供了一种机制，叫做泛型。

#### 5、List序列

> List接口：**有序(存储和读取的顺序是一致的), 有整数索引，允许重复**

##### 1、List特有方法

| 返回值 | 方法                                      | 解释                                                         |
| ------ | ----------------------------------------- | ------------------------------------------------------------ |
| void   | add(int index, E element);                | 将元素添加到index索引位置上。                                |
| void   | addAll(int index, Collection collection); | 在指定位置增加给定集合中的所有元素，若省略位置参数，则在当前集合的后面依次添加元素 |
|        | indexOf(e);                               | 通过指定元素获取其在集合中的位置                             |
|        | subList(int from,int to);                 | 获取从from到to位置上的元素                                   |
| E      | get(int index);                           | 根据index索引获取元素。                                      |
| E      | remove(int index);                        | 根据index索引删除元素。                                      |
| E      | set(int index, E element);                | 将index索引位置的的元素设置为element。                       |

##### 2、List的常用子类

1. ArrayList：

   - 底层由数组实现

   - 在列表尾部插入或删除数据非常有效

   - 适合查找和更新元素

   - 元素可以为null

   - 访问元素的`get()`方法时间复杂度为常数，因为是直接根据下标索引来访问的

   - 添加元素的`add()`方法时间复杂度为O(n), 因为需要移动元素，将新元素插入到合适的位置。

   - 非线程安全

   - 自动扩容(动态增长)机制：Arraylist是用Object数组实现的，扩容是生成新的数组，再把原来的数组复制过来

     > 1. 得到当前的ArrayList的容量(oldCapacity)。
     > 2. 计算除扩容后的新容量(newCapacity)，其值$$(oldCapacity + (oldCapacity >>1))$$**约是oldCapacity 的1.5倍**。(这里采用的是移位运算。为什么采用这种方法呢？应该是出于效率的考虑)
     > 3. 当newCapacity小于所需最小容量，那么将所需最小容量赋值给newCapacity。
     > 4. newCapacity大于ArrayList的所允许的最大容量,处理。进行数据的复制，完成向ArrayList实例添加元素操作。
     >
     > 转自：[gyl-coder](https://www.zhihu.com/people/xian-yu-16-13-50)
     >
     > 链接：https://zhuanlan.zhihu.com/p/37500957

2. LinkedList：

   - 其内部实现是使用**双向链表**来保存元素，因此插入与删除元素的性能较好
   - 提供了操作头部、尾部的方法，因此可以模拟栈、队列、双向队列
   - 由于是使用链表保存元素的，所以随机访问元素的时候速度会比较慢(需要遍历链表找到目标元素)
   - 非线程安全
   - LinkedList特有方法:

   

   JDK1.6之前：

   | 返回值 | 方法          | 解释                                                         |
   | ------ | ------------- | :----------------------------------------------------------- |
   | void   | addFirst(E e) | 向链表的头部添加元素                                         |
   | void   | addLast(E e)  | 向链表的尾部添加元素                                         |
   | E      | getFirst()    | 获取链头的元素, 若集合中没有元素，则抛出NoSuchElementException |
   | E      | getLast()     | 获取链尾的元素, 若集合中没有元素，则抛出NoSuchElementException |
   | E      | removeFirst() | 返回链头的元素并删除链头的元素, 若集合中没有元素，则抛出NoSuchElementException |
   | E      | removeLast()  | 返回链尾的元素并删除链尾的元素, 若集合中没有元素，则抛出NoSuchElementException |

   JDK1.6之后的替代方法：

   | 返回值 | 方法            | 解释                                                         |
   | ------ | --------------- | :----------------------------------------------------------- |
   | void   | offerFirst(E e) | 向链表的头部添加元素                                         |
   | void   | offerLast(E e)  | 向链表的尾部添加元素                                         |
   | E      | peekFirst()     | 获取链头的元素, 若集合中没有元素，则返回null                 |
   | E      | peekLast()      | 获取链尾的元素, 若集合中没有元素，则返回null                 |
   | E      | pollFirst()     | 返回链头的元素并删除链头的元素, 若集合中没有元素，则返回null |
   | E      | pollLast()      | 返回链尾的元素并删除链尾的元素, 若集合中没有元素，则返回null |

##### 3、Set集合及其常用子类

1. Set

   > - 可以且只包含一个null元素
   >
   > - 无序：存入集合的顺序和取出集合的顺序不一致
   > - 没有索引
   > - 不可重复：存入集合的元素没有重复

2. HashSet

   > - 实现了Set接口，内部采用HashMap实现
   > - 所添加的元素最好重写hasCode() 和 equals()方法
   > - HashSet元素添加的规则
   >   - 相等对象，hashCode一定相等。
   >   - 不等对象，hashCode不一定不相等。
   >   - 两个对象的hashCode相同，不一定相等。
   >   - 两个对象的hashCode不同，一定不相等。

   补充：HashSet元素唯一性的原理

   > 通过元素的两个方法hasCode和equals方法来完成的。
   >
   > - 如果元素的hashCode的值相同，才会判断equals是否为true。
   > - 如果元素的hashCode值不相同，就不会调用equals方法。

   补充: hashCode的优化

   > 可以让成员变量的不同对象，hash值也不同，可以减少一部分`equals()`方法的比较。因此，可以让`hascode()`方法的返回值与对象的成员变量相关联。

3. TreeSet

   > 1. 底层的数据结构为二叉树(红黑树)结构
   > 2. 实现了Comparable接口，该接口强制让增加到集合中的对象进行了比较。因此，可以对Set集合中的元素进行排序。排序需要重写`compareTo()`方法。

   补充：TreeSet元素唯一性的原理

   > 实现的compareTo方法的返回值，是正整数、负整数或零，则两个对象较大、较小或相同。相等时则不会存入。

##### 4、Map集合及其子类

1. Map接口

> Map<K,V>集合是一个接口，和List集合及Set集合不同的是，它是双列集合，并且可以给对象加上名字，即键（Key）

- Map集合的特点
  - 该集合存储键值对，一对一对往里存
  - 键唯一，值可重复
  - 用于处理对应关系的数据
- 常用方法

| 返回值               | 方法                        | 解释                                                         |
| -------------------- | --------------------------- | ------------------------------------------------------------ |
| V                    | put(K key, V value);        | 将key映射到value。若key存在, 返回原value,并覆盖；若key不存在，返回null, 并映射。 |
| void                 | clear()                     | 清空所有映射关系                                             |
| boolean              | containsKey(Object key);    | 包含键                                                       |
| boolean              | cotainsValue(Object value); | 包含值                                                       |
| boolean              | isEmpty();                  | 判断是否为空                                                 |
| V                    | remove(Object key);         | 根据指定的key删除其对应关系，并返回value。**失败返回null**   |
| int                  | size();                     | 获取map中的映射个数                                          |
| V                    | get(Object key)             | 根据指定的key获取对应的value，**失败返回null**               |
| Set<K>               | keySet();                   | 获取Map中所有映射关系的key                                   |
| Collection<V>        | values();                   | 获取Map中所有映射关系的value                                 |
| Set<Map.Entry<K, V>> | entrySet();                 | 返回一个Set集合，泛型为Map中的内部类Entry                    |

2. HashTable

   > - 底层是哈希表数据结构
   > - 不可存入null键和null值
   > - 该集合是线程同步的，效率较低

3. HashMap

   > -  底层是哈希表数据结构
   > - 允许使用null值和null键
   > - 该集合是线程同步的，效率较高

4. TreeMap

   > - 底层是二叉树数据结构，线程不同步
   > - 可以用于给Map集合中的键值进行排序，和Set很像，其实，Set集合的底层就是使用了Map集合

## 2、集合间的区别与总结

1. List接口
   - List接口对Collection进行了简单的扩充，它的具体实现类常用的有ArrayList和LinkedList。
   - 可以将任何东西放到一个List容器中，并在需要时从中取出
   - ArrayList是一种类似数组的形式进行存储，因此它的随机访问速度极快
   - LinkedList的内部实现是链表，它适合于在链表中间需要频繁进行插入和删除操作
2. Set接口
   - 与List不同的是，在Set中的对象元素不能重复
   - 常用具体实现有HashSet和TreeSet类
     - HashSet能快速定位一个元素，但存储到HashSet中的对象需要实现hashCode()方法
     - TreeSet则将放入其中的元素按序存放，这就要求存入其中的对象是可排序的，这就用到了集合框架提供的另外两个实用类Comparable和Comparator
3. Map接口
   - Map是一种把键对象和值对象进行关联的容器，而一个值对象又可以是一个Map，依次类推，这样就可形成一个多级映射。
   - Map容器中的**键对象不允许重复**，这是为了保持查找结果的一致性
   - 在使用过程中，某个键所对应的值对象可能会发生变化，这时**会按照最后一次修改的值对象与键对应**
   - 常用具体实现有HashMap和TreeMap类
     - HashMap也用到了哈希码的算法，以便快速查找一个键
     - TreeMap则是对键按序存放，因此它便有一些扩展的方法，比如firstKey(),lastKey()等

转自：[玉圣](https://www.jianshu.com/u/65e19270f991)

原文链接：https://www.jianshu.com/p/ab6a0d17822d

## 3、Collections工具类

### 1、Collection与Collections的区别

- Collection是集合体系的最顶层接口，包含了集合体系所有的共性
- Collections是一个工具类，构造方法私有，其中所有的方法均为静态方法。主要用于服务Collection。

2、Collections的常用方法

| 返回值 | 方法                                 | 解释                                                         |
| ------ | ------------------------------------ | ------------------------------------------------------------ |
| void   | swap(List list, int i, int j);       | 将制定列表中的两个元素交换                                   |
| void   | sort(List list);                     | 将列表元素按自然顺序排序                                     |
| void   | shuffle(List list);                  | 将列表中的元素随机交换                                       |
| void   | reverse(List list);                  | 将列表翻转                                                   |
| void   | fill(List list, Object obj);         | 使用指定的obj对象，将指定的list列表中的元素替换。**注：替换对象必须与列表的泛型一致，且列表中有元素** |
| void   | copy(List dest, List src);           | 把源列表(src)中的元素覆盖到目标列表(dest)。注：两个列表泛型需一致，dest表的长度需大于src表 |
| int    | binarySearch(List list, Object key); | 查找指定元素key在list中的位置                                |

## 









































