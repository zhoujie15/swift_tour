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
NOTE
为了最好的学习体验，在Xcode中打开这章节内容的一个playground，它会让你能够编写代码同时立即看到执行结果。
```
[下载Playground](https://developer.apple.com/library/prerelease/ios/documentation/Swift/Conceptual/Swift_Programming_Language/GuidedTour.playground.zip)

----------------------------------------------

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

```
EXPERIMENT
创建一个一个常量，拥有显式类型Float和初始值4。
```
声明的值并不会隐式地转换成其它类型，如果你需要将一个值转换成其它类型，显式地创建一个想要的类型的实例。

```
let label = "The width is"
let width = 94
let widthLabel = label + String(width)
```

```
EXPERIMENT
删除最后一行的String类型转换，你会得到什么样的错误？
```
有一种更简单地在字符串中使用数值的方法：将值写在括号中，在括号前写一个反斜线。例如：
```
let apples = 3
let oranges = 5
let appleSummary = "I have \(apples) apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
```
```
EXPERIMENT
使用\()在字符串中包含一个浮点数计算以及在一句问候语中包含一个人的名字。
```
使用中括号([])创建列表和字典，通过写出它们的索引或者键值来访问它们的元素。允许在最后一个元素后面有一个逗号。

```
var shoppingList = ["catfish", "water", "tulips", "blue paint"]
shoppingList[1] = "bottle of water"
 
var occupations = [
    "Malcolm": "Captain",
    "Kaylee": "Mechanic",
]
occupations["Jayne"] = "Public Relations"
```
用初始化的语法创建一个空的数组或者字典。
```
let emptyArray = [String]()
let emptyDictionary = [String: Float]()
```
如果类型信息能够被推断出来，你一个将一个空数组写成[]将一个空字典写成[:]。例如在当你为一个变量赋一个值或者给函数传递参数的时候。
```
shoppingList = []
occupations = [:]
```

----------------------------------------------

### Control Flow

使用if和switch做条件句，使用for-in，for，while和repeat－while做循环。条件和循环变量外是否有括号是可选的，条件或者循环体外的大括号是必要的。
```
let individualScores = [75, 43, 103, 87, 12]
var teamScore = 0
for score in individualScores{
	if score > 50 {
		teamScore += 3
	} else{
		teamScore += 1
	}
}
print(teamScore)
```
在if语句中，选择条件必须是一个布尔表达式，这意味着像是```if score{...}```的代码会出错，而不会隐性地和0相比较。


































