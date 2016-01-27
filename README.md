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

你可以同时使用if和let来处理那些可能丢失的值。这些值为可选内容。一个可选的值要么会有一个实际的值，要么是一个nil表示当前该值的缺失。在值的类型后面写一个问号(?)来表示当前的值是可选的。

```
var optionalString: String? = "Hello"
print(optionalString == nil)
 
var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
```
```
EXPERIMENT
将optionalName的值变为nil。你会得到什么问候语？加一句else为optionalName为nil的情况设置一个不同的问候语。
```
如果可选的值为nil，那么条件选择会是false，大括号中的代码将会被跳过。否则，可选择的值会被去包裹并且在let语句中被赋给常量，这会让这种去包裹的值在下面的代码块中可用。

另一种处理可选择的值的方法是使用??运算符提供一个默认值。如果可选的值丢失，那么会用默认值代替。
```
let nickName: String? = nil
let fullName: String = "John Appleseed"
let informalGreeting = "Hi \(nickName ?? fullName)"
```
Switch语句支持各种类型的数据和各种方式的比较操作，不会局限于整数并且会平等的被检测。
```
let vegetable = "red pepper"
switch vegetable {
case "celery":
    print("Add some raisins and make ants on a log.")
case "cucumber", "watercress":
    print("That would make a good tea sandwich.")
case let x where x.hasSuffix("pepper"):
    print("Is it a spicy \(x)?")
default:
    print("Everything tastes good in soup.")
}
```
```
EXPERIMENT
尝试去掉default部分，你会得到什么错误？
```
注意上面的let是如何使用的，它被用来把匹配一个固定模式的值赋给一个常量。

在运行完一个匹配的case中的语句后，程序会从switch语句退出，不会运行到下一个case，所以不需要在每一个case的最后加上break语句。

使用for-in语句提供一对变量名来迭代取出字典中的每个键值对。字典是无序的集合，所以它们的键和值在迭代中是随机顺序的。
```
let interestingNumbers = [
    "Prime": [2, 3, 5, 7, 11, 13],
    "Fibonacci": [1, 1, 2, 3, 5, 8],
    "Square": [1, 4, 9, 16, 25],
]
var largest = 0
for (kind, numbers) in interestingNumbers {
    for number in numbers {
        if number > largest {
            largest = number
        }
    }
}
print(largest)
```
```
EXPERIMENT
使用另一个变量来记录哪种类型的数是最大的，同时记录最大的数是什么。
```
使用while重复运行一段代码直到某个条件改变。循环的条件也可以在循环体的末尾，确保循环被运行至少一遍。
```
var n = 2
while n < 100 {
    n = n * 2
}
print(n)
 
var m = 2
repeat {
    m = m * 2
} while m < 100
print(m)
```
你可以通过使用..<在循环中制造一个区间的索引。
```
var firstForLoop = 0
for i in 0..<4 {
    firstForLoop += i
}
print(firstForLoop)
```
用..<创造一个区间会忽视它的上界，用...创造的区间会包含上下界。



























