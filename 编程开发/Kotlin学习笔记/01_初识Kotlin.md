### Kotlin简介

​        Kotlin（科特林）是由JetBrains开发的针对JVM、Android和浏览器的静态编程语言，目前在Apache组织的许可下已经开源。

​        之所以开发Kotlin，是因为JetBrains 的工程师们在使用Java开发应用程序的过程中，发现了大量的问题。为了提升开发效率以及解决使用Java开发带来的问题，在借鉴了Scala、Groovy等语言后，开发出一款致力于解决Java问题的编程语言。

​        Kotlin来源于一个岛屿的名字，全称是Kotlin Island，是英语“科特林岛”之意，这个小岛位于俄罗斯的圣彼得堡附近。之所以要命名为Kotlin，是因为Kotlin的主要开发工作就是由位于圣彼得堡分公司团队完成的。

​        Kotlin可以编译成[Java字节码]()，也可以编译成[JavaScript]()，方便在没有JVM的设备上运行。除此之外Kotlin还可以编译成[二进制代码]()直接运行在机器上（例如嵌入式设备或iOS），因此开发者可以很方便地开发移动Android应用、服务器程序和JavaScript程序。

​        Kotlin已正式成为Android官方支持开发语言。

### Kotlin优势

##### 1、跨平台开发能力

​        因为Kotlin是基于JVM开发的，所以它同时具备了Android 开发、Web浏览器开发、原生Native开发的能力。在原生Native开发方面，目前Kotlin官方在Github上开源了Native的源码(Github地址：https://github.com/JetBrains/kotlin-native)。在Web开发方面，Kotlin可以结合Spring框架使用，也可以编译生成JavaScript模块，方便在一些JavaScript的虚拟机上编译运行。

##### 2、开源

​        众人拾柴火焰高，对于一门新技术、新语言，开源可以更快速地发现Bug，从而利用开源的力量更快的推动新技术的发展。在开源领域方面，Java就是一个好例子，从语言标准，到Core API、虚拟机、开发者工具，这些都能找到开放的影子。

##### 3、100%兼容Java

​       Kotlin能够和Java达到100%互通，也就是说，使用Kotlin可以调用 Java已有的代码或库，也可以同时使用Java和Kotlin来混合编写代码。而且JetBrains提供的开发工具可以很简单的实现Java代码到Kotlin的转换。

##### 4、空指针安全

​        针对空指针问题，Kotlin有专门的语法来避免空指针问题。

##### 5、语言简洁，学习成本低

​        Kotlin语法简洁直观，看上去非常像Scala，但更简单易学。同时，Kotlin使用了大量的语法糖，使得代码更加简洁。Kotlin并不遵循特定的编程规范，它借鉴了函数式风格和面向对象风格的诸多优点。

##### 6、支持Lambda表达式

​        函数式编程是软件技术的发展方向，而Lambda是函数式编程最基础的内容。引入Lambda，最直观的一个改进是，不用再写大量的匿名内部类，并且集合操作也得到了极大的改善。事实上，还有更多由于函数式编程本身特性带来的性能。比如，代码的可读性会更好、高阶函数引入了函数组合的概念等。

​        然而使用Lambda表达式并非只有好处没有坏处，正如C#之父Anders Hejlsberg在《编程语言大趋势》一文中所说，未来的编程语言将逐渐融合各自的特性，而不会只存在单纯的声明式语言或者单纯的函数编程语言。

##### 7、类型推断

​        使用Kotlin编程，开发人员不必为每个变量明确指定类型，编译器可以在编译的时候推导出某个参数的数据类型，从而使得代码更为简洁。

##### 8、支持自定义的DSL

​        DSL(Domain-Specific Language)，全称领域特定语言，指的是专注于特定问题领域的计算机语言。不同于通用的计算机语言(GPL)，领域特定语言只用在某些特定的领域。

​        DSL语言能让开发者以一种更优雅、更简洁的方式来表达和解决领域问题。例如，gradle就是一种用groovy定义的dsl。Kotlin的lambda系统使其成为创建DSL的理想选择。

##### 9、IDE环境的支持

​        作为JetBrains旗下的产品，JetBrains旗下众多的IDE可以为Kotlin开发提供无缝支持，并相互协作，协同发展。

### Kotlin开发初体验

​        IntelliJ IDEA 是一套Kotlin 集成开发环境。JetBrains 公司创建了Kotlin 语言并打造出了这套开发工具。访问JetBrains 公司网站https://www.jetbrains.com/idea/download，下载IntelliJ IDEA 社区开发版软件。

