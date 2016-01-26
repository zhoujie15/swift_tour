# Swift Tour
[Swift Tour](https://developer.apple.com/library/prerelease/ios/documentation/Swift/Conceptual/Swift_Programming_Language/GuidedTour.html#//apple_ref/doc/uid/TP40014097-CH2-XID_1)的个人中文翻译

Author: Jayz

Blog: [清夏的荷塘](http://www.tsingxia.com)

----------------------------------------------

一般情况下，学习用一门新的语言编写的第一个程序都是使用程序在屏幕上打印出“Hello world”。在Swift中，这可以用下面这一行代码完成：

```
print("Hello, world!")
```
如果你曾经写过C或着Objective-C，你会很熟悉这种语法，在Swift中，这简单的一行代码就是一个完整的程序。你不需要引入一个单独的库来引入像是输入输出或者字符串处理的功能。在全局范围内书写的代码会作为程序的入口点，所以你不需要一个main()函数。你也不需要在每一句话后面写分号。

这份教程会通过向你展示如何完成功能各异的编程任务，从而为你开始学习用Swift写程序提供充实的内容。如果你有什么不理解，请不要担心，这篇教程中介绍的所有内容都会在本书的其余部分提供更加详细的介绍。

```
Note
为了最好的学习体验，在Xcode中打开这章节内容的一个playground，它会让你能够编写代码同时立即看到执行结果。
```
[下载Playground](https://developer.apple.com/library/prerelease/ios/documentation/Swift/Conceptual/Swift_Programming_Language/GuidedTour.playground.zip)

### Simple Values

用let声明一个常量，用var声明一个变量。常量的值并不需要在编译时获知，但是你只能给它赋值一次。这意味着你可以用常量为一个特定的值命名，并且在很多其他地方使用。

```
var myVariable = 42
myVariable = 50
let myConstant = 42
```
常量或者变量必须和你想赋给它们的值拥有同样的类型。然而你并不需要显式地指定类型。在创建常量或者变量时提供给它们一个值，然后让编译器推断它的类型。在上面的例子中，编译器推断myVariable是一个整数因为它的初始值就是一个整型。

如果初始值并没有提供充足的信息（或者没有初始值），你可以在变量之后写明它的类型，用一个冒号分隔。

```
let implicitInteger = 70
let implicitDouble = 70.0
let explicitDouble: Double = 70
```






































