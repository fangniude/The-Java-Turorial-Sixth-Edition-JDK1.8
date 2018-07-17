# The-Java-Turorial-Sixth-Edition-JDK1.8

Java 官方文档「The Java Tutorial, Sixth Edition」的中文翻译，本教程基于JDK1.8。

# 1. 准备开始

本章介绍了Java技术 和 安装Java开发软件开发环境，并创建一个简单的程序。

本章介绍了使用Java开始编程之前，你需要知道的所有事情。

## 1.1 Java技术

Java技术鸟瞰，讨论Java编程语言 和 Java平台，使用它能做什么，它是怎样使生活变得轻松的。

关于Java技术的讨论无处不在，但它空间是什么呢？以下各节解释了Java技术既是编程语言，又是一个平台，并概述了此技术可以为你做些什么。

### 1.1.1 关于Java技术

Java技术既是一种编程语言，又是一个平台。

#### 1.1.1.1 Java编程语言

Java编程语言是一种高级语言，可以用以下术语来描述

- 简单
- 面向对象
- 分布式
- 多线程
- 动态
- 体系结构中立
- 便携
- 高性能
- 稳定
- 安全

这些术语James Gosling 和 Henry McGilton写的白皮书「The Java Environment」中有展开的解释。

在Java语言中，首先，将所有源代码都写到以`.java`为扩展名的纯文本文件中，然后，这些源文件由`javac`编译器编译到`.class`文件中。`.class`文件不包含您的处理器本机代码，而是包含字节码----Java虚拟机(JVM)的机器语言。最后，`java`启动器工具在一个JVM实例中运行你的应用程序。

![getStarted-compiler](./getStarted-compiler.gif)

因为`JVM`在许多不同的操作系统上都可用，所以相同的`.class`文件可以在Windows、Solaris、Linux、macOS上运行。某些虚拟机（比如HotSport）在运行时会执行其他步骤，使应用程序的性能更好。这包括各种任务，如查找性能瓶颈 和 重新编译（本地机器码）经常使用的代码。

![getStarted-jvm](./getStarted-helloWorld.gif)

#### 1.1.1.2 Java平台

平台是程序运行的硬件或软件环境。我们已经提到了一些最受欢迎的平台，如Windows、Linux、Solaris和macOS。大多数平台可以被描述为操作系统和底层硬件的组合。Java平台与大多数其他平台不同，因为它是一个仅在其他基于硬件的平台之上运行的软件平台。

Java平台有两个组件：

- Java虚拟机
- Java应用程序接口(API)

刚刚介绍了Java虚拟机，它是Java平台的基础，并被移植到各种基于硬件的平台上。

API是大量现成的软件组件的集合，提供了许多有用的功能。根据相关性，将类和接口分组放到不同的包中。下一节「Java技术能做什么？」将重点展示API提供的功能。

![getStarted-jvm](./getStarted-jvm.gif)

作为独立于平台的环境，Java平台可能比本机代码稍微慢一些，但是编译器和虚拟机技术的进步，使性能接近于本地代码，而有很好的可移植性。

术语「Java虚拟机」和「JVM」指的是Java平台的虚拟机。

### 1.1.2 Java技术能做什么？

Java是一个强大的软件平台，它是以一般用途为目的的高级编程语言。Java平台的每个完全实现都提供了以下功能：

- **开发工具：**开发工具提供了应用程序所需的一切工具，包括编译、运行、监视、调度和文档等。作为一个新的开发人员，你将使用的主要工具是`javac`编译器、`java`启动器 和 `javadoc`文档工具。
- **应用程序编程接口(API)：**API提供了Java语言的核心功能。它提供了许多有用的类，供你在自己的代码中使用。API包括各个方面的内容，从基本对象，到网络 和 安全，再到XML生成 和 数据库访问 等。核心API非常大，要了解它所包含的内容，请参阅 [JavaSE文档](https://docs.oracle.com/javase/8/docs/index.html)。
- **部署技术：**JDK提供了标准机制，如Java Web Start 和 Java插件，用于将应用程序部署到最终用户。
- **用户界面工具包：**JavaFX、Swing和Java 2D工具包使你能够创建复杂的图形用户界面(GUI)。
- **集成库：**集成库，如Java IDL API、JDBC、JNDI、RMI、RMI-IIOP提供访问远程数据库 和 操作远程对象的能力。

### 1.1.3 Java技术将如何改变我的生活？

学习Java语言，我们并不能保证你将拥有名声、财富，甚至是一份工作。不过，它可能会使你的程序更好，并需要比其他语言更少的努力。我们相信Java技术将在以下方面给你带来帮助：

- **快速入门：**虽然Java语言是一种强大的面向对象语言，但它很容易学习，尤其是对于已经熟悉C或C++的程序员来说。
- **少写代码：**程序度量 (类计数、方法计数等) 的比较表明, 用 Java 编程语言编写的程序可以比用 C++ 编写的程序小四倍。
- **编写更好的代码：**Java 编程语言鼓励良好的编码习惯，自动垃圾回收有助于避免内存泄漏。它的面向对象、JavaBean组件架构 和 广泛的易于扩展的API 让你重用已有的、经过测试的代码，能够较少的引入Bug。
- **更快的开发程序：**Java语言比C++简单，在编写同样的程序时，可能只用其一半的时间。代码行数也会更少。
- **避免平台依赖性：**避免使用其他语言编写的库，可以使程序保持可移植性。
- **一次编写，到处运行：**因为Java语言编写的应用程序被编译成与机器无关的字节码，它们在任何Java平台上运行都是一致的。
- **更容易的分发软件：**使用Java Web Start软件，用户能够通过单击鼠标来启动应用程序。启动时自动检查版本可确保用户始终更新最新版本的软件。如果有可用的更新，Java Web Start软件将自动更新。

## 1.2 Hello World

下载、安装Java，并创建「Hello World！」应用程序。

主要在介绍NetBeans，不喜欢，不翻译了

## 1.3 Hello World详解

详细描述「Hello World！」代码的每一部分，包括注释、类字义 和 main方法。

现在你已经看到了「Hello World！」程序(也许已经编译并运行它了)，你可能会想知道它是如何工作的。这里再次贴出它的源码

```java
class HelloWorldApp {
    public static void main(String[] args) {
        System.out.println("Hello World!"); // Display the string.
    }
}
```

「Hello World！」程序由3个主要组件组成：注释、类定义 和 main方法。下面的解释将为你提供对代码的基本理解，更深层次的理解需要你阅读完本教程的其余部分才会显明。

### 1.3.1 注释

下面粗体文本定义了「Hello World！」的注释：

```java
/**
 * The HelloWorldApp class implements an application that
 * simply prints "Hello World!" to standard output.
 */
class HelloWorldApp {
    public static void main(String[] args) {
        System.out.println("Hello World!"); // Display the string.
    }
}
```

注释将被编译器忽略，但对其他程序员很有用。Java语言支持3种注释：

- /* text * / 编译器忽略从/ * 到*/的所有内容
- /** documentation */ 表示文档注释。编译器忽略此类注释，javadoc工具在生成文档时，会使用它们。有关javadoc更多的信息，请参考[Javadoc](https://docs.oracle.com/javase/8/docs/technotes/guides/javadoc/index.html)
- // text 编译器忽略从 // 到行末尾的所有内容

### 1.3.2 HelloWorldApp类定义

下面粗体文本开始了类字义块「Hello World！」应用程序：

```java
class HelloWorldApp
```

如上所示，类定义的最基本形式是：

class *name* {

​	. . . 

} 

关键字`class`用来定义一个类，`name`是这个类的名称，类的代码放在一对大括号中间。第2章概括介绍一般的类，第4章将会详细讨论类。现在，知道每个应用程序从类定义开始就足够了。

### 1.3.3 main方法

下面内容开始了main方法的定义

```java
public static void main(String[] args)
```

在Java语言中，每个应用程序都必须包含一个`main`方法，其签名为`public static void main(String[] args)`。

这些修饰符`public`和`static`可以按任意顺序编写，但该约定使用`public static`，如上所示。你可以为参数命名为其他你想要的内容，但是大多数程序员选择`args`。

main方法与C和C++中的main函数相似，它是应用程序的入口，在其中调用程序所需的其他方法。

main方法接受单个参数：String类型的数组。

此数组是运行时，系统将信息传递给应用程序的机制。例如：

```
java MyApp arg1 arg2
```

数组中的每个字符串称为`命令行参数`。命令行参数允许用户影响应用程序的操作，而无需重新编译它。例如，排序程序可能允许用户指定以降序对数据进行排序，并使用此命令行参数：

```
-descending
```

「Hello World！」程序忽略其命令行参数，但你应该了解此类参数确定存在的事实。

最后，行`System.out.println("Hello World!");`使用`System`类，从核心库打印`Hello World！`消息到标准输出。此库的部分（API）将在教程的其余部分中进行讨论。

## 1.4 问题和练习

### 1.4.1 问题

**问题1：** 编译用java语言编写的程序时，编译器将人可读的源文件转换为JVM可以理解的与平台无关的代码，这个与平台无关的代码叫什么？

**答案：** 字节码。

**问题2：** 下列哪项不是有效的注释？

- a. / ** comment */
- b. /* comment */
- c. /* comment
- d. // comment

**答案：** C

**问题3：** 如果在运行时看到以下错误，你应该检查的第一件事是：

```
Exception in thread "main" java.lang.NoClassDefFoundError:
HelloWorldApp.java.
```

**答案：** 检查类路径，找不到该类。

**问题 4:** `main`方法的正确签名是什么？

**答案：** public static void main(String[] args) 或 public static void main(String... args)

**问题 5**:  声明`main`方法时, 哪个修饰符必须先出现,`public`或`static`?

**答案：** 可以任意顺序，但大多数会是public static

**问题 6:** `main`方法定义了哪些参数？

**答案：** 一个String数组类型的参数，通常命名为args

### 1.4.2 练习

**练习 1:** 更改 HelloWorldApp 程序, 使其显示`Hola Mundo!`, 而不是`Hello World!`!.

**答案：** 修改 System.out.println("Hola Mundo!"); //Display the string.

**练习 2**:  下面是一个稍微修改过的HelloWorldApp版本: HelloWorldApp2.java

```
class HelloWorldApp2 {
    public static void main(String[] args) {
        System.out.println("Hello World!); // Display the string.
    }
}
```

程序有错误。修复错误, 以便程序成功编译和运行。错误是什么？

**答案：** 字条串后面缺少引号。

# 2. 学习Java语言

讲解Java语言的基本概念 和 基本功能。

# 3. 基本Java类

讲解异常、基本IO、并发、正则表达式 和 平台环境。

# 4. 集合

讲解Java集合框架的使用 和 扩展。

# 5. 日期时间

使用`java.time`包处理日期和时间。

# 6. 部署

Java应用程序 和 Applet 打成Jar包，并使用Java Web Start 和 Java 插件部署。

# 7. 准备JPLC

JPLC考试相关的资源。