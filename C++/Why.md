编程（程序设计）实际上是一个对现实世界中的事物抽象，并由计算机语言实现的过程。一种优秀的编程语言，一定要对于计算这件事情实现一个`完整和自洽的抽象`。编程语言领域的竞争，除却实现质量外，基本上是在比拼抽象的设计。

C 语言之所以经久不衰，根本上在于它对现代计算机提供了一个底层的高级抽象，凡是比它低的抽象都过于简陋，比它高的抽象都可以用 C 语言构造出来。

C++ 是作为一种“高级的 C”而存在的，它始终可以看作是一种 C 语言的简写法，任何一句 C++ 都有着深刻的 C 语言背景，可以直接落实为 C 语言，进而落实为任何一种计算机最底层的机器吗。这一点，任何解释型语言做不到，因而效率上无法和 C++ 比拼。

另一方面，C++ 有着强大的抽象能力，它以奇妙的方式融合着 5 种编程范式（paradigm），即`面向过程、基于对象、面向对象、泛型和函数式`，将所有范型的优点提炼并发挥到极致的同时，又不拘泥于其中的任何一种。

# [面向过程](https://en.wikipedia.org/wiki/Procedural_programming)

面向过程的程序设计把计算机程序视为一系列的命令集合，即一组函数的顺序执行。为了简化程序设计，面向过程把函数继续切分为子函数，即把大块函数通过切割成小块函数来降低系统的复杂度。

面向过程编程以冯诺依曼计算机体系结构为背景。在这类语言中（经典的C语言），计算过程被看做是动作的序列，程序就是用语言提供的操作命令来书写一个具体的操作序列。

用过程式（命令式）程序设计语言编写程序，就是描述解题过程中每一步的过程，程序的运行过程就是问题的求解过程。机器语言及汇编语言是最早的过程式语言。

过程式语言最基本的语句通常包括：

1. 把某些数据放入变量中；
2. 从变量中获取数据；
3. 循环一个指令块直到满足了某些条件；
4. 如果某个命题为true，那么就进行某些操作。

# [基于对象](https://en.wikipedia.org/wiki/Abstract_data_type)

基于对象（也叫ADT, 抽象数据类型模型）是指采用对象封装技术，将数据和操作捆绑在一起，但是并没有使用多态、继承等面向对象技术进行软件设计。

C++ 支持基于对象的程序设计，例如 string class，一种非多态的数据类型。它提供了一个 public 接口和一个 private 具体实现，包括数据和算法，但是不支持类型的继承。

    string girl = "Anna";
    string daughter;
    ...
    // string::operator=();
    daughter = girl;
    ...
    // string::operator==();
    if(girl == daughter){
        take_to_disneyland(girl);
    }

一个 object-based（OB）设计可能会比一个对等的 OO 设计速度更快更紧凑。速度快是因为所有的函数调用操作都在编译时期解析完成，对象建构起来时不需要设置 virtual 机制；空间紧凑是因为每一个 class object 不需要负担传统上为了支持 virtual 机制而需要的额外负荷。但是，由于没有继承、多态机制，失去了部分弹性。

# [面向对象](https://en.wikipedia.org/wiki/Object-oriented_programming)

面向对象程序设计的核心思想是数据抽象（封装）、继承和多态（动态绑定）

* 数据抽象：把客观事物封装成抽象的类，同时将类的接口和实现分离。（优点：可以隐藏实现细节，使得代码模块化）
* 继承：定义相似的类型，并对其相似关系建模。（优点：可以扩展已存在的代码模块）
* 多态：一定程度上忽略相似类型的区别，以统一的方式使用它们的对象。

面向对象编程（Object Oriented Programming, OOP）把对象（object）作为程序的基本单元，一个对象包含了数据和操作数据的函数。同时把相同行为的对象归纳为类（class），通过类的`封装`隐藏内部细节，通过`继承`实现类的特化（specialization）／泛化（generalization），通过`多态`实现基于对象类型的动态分派。

面向对象的程序设计把计算机程序视为一组对象的集合，而每个对象都可以接收其他对象发过来的消息，并处理这些消息，计算机程序的执行就是一系列消息在各个对象之间传递。

面向对象设计的 5 大原则（SOLID）：

* SRP(The Single Responsibility Principle) 单一职责原则：一个类应该有且只有一个去改变它的理由，这意味着一个类应该只有一项工作。
* OCP(The Open Closed Principle) 开放封闭原则：对象或实体应该对扩展开放，对修改封闭，这就意味着一个类应该无需修改类本身但却容易扩展。
* LSP(The Liskov Substitution Principle) 里氏替换原则：每一个子类或派生类应该可以替换它们的基类或父类。
* ISP(The Interface Segregation Principle) 接口隔离原则：不应强迫客户端实现一个它用不上的接口，或是说客户端不应该被迫依赖它们不使用的方法。
* DIP(The Dependency Inversion Principle) 依赖倒置原则：实体必须依靠抽象而不是具体实现。它表示高层次的模块不应该依赖于低层次的模块，它们都应该依赖于抽象。

# [泛型](https://en.wikipedia.org/wiki/Generic_programming)

泛型编程（Generic Programming）最初提出时的动机很简单直接：发明一种语言机制，能够帮助实现一个通用的标准容器库。所谓通用的标准容器库，就是要能够做到，比如用一个List类存放所有可能类型的对象。

泛型编程最初诞生于C++中，目的是为了实现C++的STL（标准模板库）。其语言支持机制就是模板（Templates），模板的思想其实很简单：`参数化类型`。换句话说，把一个原本特定于某个类型的算法或类当中的类型信息抽掉，抽出来做成模板参数T。

比如qsort泛化之后就变成了：

    template<class RandomAccessIterator, class Compare>
    void sort(RandomAccessIterator first, RandomAccessIterator last,
             Compare comp);

泛型编程的核心活动是抽象：将一个特定于某些类型的算法中那些类型无关的共性抽象出来，比如，在STL的概念体系里面，管你是一个数组还是一个链表，反正都是一个区间，这就是一层抽象。管你是一个内建函数还是一个自定义类，反正都是一个Callable（可调用）的对象（在C++里面通过仿函数来表示），这就是一层抽象。泛型编程的过程就是一个不断将这些抽象提升出来的过程，最终的目的是形成一个最大程度上通用的算法或类。

相对于基于多态的面向对象抽象而言，使用模版更加高效。因为面向对象的多态引入了间接调用，需要在运行期查找真正调用的函数，而模板可以直接利用编译器的类型信息，避免了间接调用。

# [函数式编程](https://en.wikipedia.org/wiki/Functional_programming)

函数式编程的主要思想是把运算过程尽量写成一系列嵌套的函数调用，每一个函数调用不依赖于外部的数据，而且也不改变外部数据的值，而是返回一个新的值。

举例来说，现在有这样一个数学表达式：

    (1 + 2) * 3 - 4

传统的过程式编程，可能这样写：

    int a = 1 + 2;
    int b = a * 3;
    int c = b - 4;

函数式编程要求使用函数，我们可以把运算过程定义为不同的函数，然后写成下面这样：

    int result = subtract(multiply(add(1,2), 3), 4);

函数式编程具有五个鲜明的特点:

1. 函数是`第一等公民`。所谓"第一等公民"（first class），指的是函数与其他数据类型一样，处于平等地位，可以赋值给其他变量，也可以作为参数，传入另一个函数，或者作为别的函数的返回值。
2. 只用`表达式`，不用`语句`。表达式（expression）是一个单纯的运算过程，总是有返回值；语句（statement）是执行某种操作，没有返回值。函数式编程要求，只使用表达式，不使用语句。也就是说，每一步都是单纯的运算，而且都有返回值。
3. 没有`副作用`。函数式编程强调没有"副作用"，意味着函数要保持独立，所有功能就是返回一个新的值，没有其他行为（最典型的情况，就是修改全局变量的值）。
4. 不修改`参数`。函数参数是不可变的。
5. `引用透明`（Referential transparency）。函数的运行不依赖于外部变量，只依赖于输入的参数，任何时候只要参数相同，引用函数所得到的返回值总是相同的。

函数式编程的优点：

1. 代码简洁，开发快速。函数式编程大量使用函数，减少了代码的重复，因此程序比较短，开发速度较快。比如使用 map, reduce 来替代循环。
2. 更方便的代码管理。函数式编程不依赖、也不会改变外界的状态，只要给定输入参数，返回的结果必定相同。因此，每一个函数都可以被看做独立单元，很有利于进行单元测试（unit testing）和调试（debugging），以及模块化组合。
3. 易于"并发编程"。函数式编程不需要考虑"死锁"（deadlock），因为它不修改变量，所以根本不存在"锁"线程的问题。不必担心一个线程的数据，被另一个线程修改，所以可以很放心地把工作分摊到多个线程，部署"并发编程"（concurrency）。


# 更多阅读
《C++ Primer》  
《深入探索C++对象模型》  

[函数式编程初探](http://www.ruanyifeng.com/blog/2012/04/functional_programming.html)  
[酷壳：函数式编程](http://coolshell.cn/articles/10822.html)    
[如此理解面向对象编程](http://coolshell.cn/articles/8745.html)  
[泛型编程：源起、实现与意义](http://blog.csdn.net/pongba/article/details/2544894)  
[程序与证明](http://www.tuicool.com/articles/YRZvem)  
[逻辑和计算机](https://commondatastorage.googleapis.com/letscorp_archive/archives/75811)  
[S.O.L.I.D：面向对象设计的头 5 大原则](http://blog.jobbole.com/86267/)  

