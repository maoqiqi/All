# Go语言基础

Go是一门类似C的编译型语言，但是它的编译速度非常快。这门语言的关键字总共也就二十五个，比英文字母还少一个。先让我们看一眼这些关键字都长什么样：

    break    default      func    interface    select
    case     defer        go      map          struct
    chan     else         goto    package      switch
    const    fallthrough  if      range        type
    continue for          import  return       var

    
## 目录

* [你好Go](#你好Go)
* Go基础
* 流程和函数
* struct
* 面向对象
* interface
* 并发
* 小结


## 你好Go

在开始编写应用之前，我们先从最基本的程序开始。就像你造房子之前不知道什么是地基一样，编写程序也不知道如何开始。因此，我们要学习用最基本的语法让Go程序运行起来。

这就像一个传统，在学习大部分语言之前，你先学会如何编写一个可以输出hello world的程序。

```
package main

import "fmt"

func main() {
	fmt.Printf("Hello, world or 你好，世界 or καλημ ́ρα κóσμ or こんにちはせかい\n")
}
```

输出如下：

```
Hello, world or 你好，世界 or καλημ ́ρα κóσμ or こんにちはせかい
```

* 首先我们要了解一个概念，Go程序是通过package来组织的
  * `package <pkgName>`(在我们的例子中是`package main`)这一行告诉我们当前文件属于哪个包，而包名`main`则告诉我们它是一个可独立运行的包，它在编译后会产生可执行文件。
  * 每一个可独立运行的Go程序，必定包含一个`package main`，在这个`main`包中必定包含一个入口函数`main`，而这个函数既没有参数，也没有返回值。
* 为了打印`Hello, world...`，我们调用了一个函数`Printf`，这个函数来自于`fmt`包，所以我们在第三行中导入了系统级别的`fmt`包：`import "fmt"`。
  * 包的概念和Python中的package类似，它们都有一些特别的好处：模块化(能够把你的程序分成多个模块)和可重用性(每个模块都能被其它应用程序反复使用)。
* 在第五行中，我们通过关键字`func`定义了一个`main`函数，函数体被放在`{}`(大括号)中，就像我们平时写C、C++或Java时一样。
* 第六行，我们调用了`fmt`包里面定义的函数`Printf`。大家可以看到，这个函数是通过`<pkgName>.<funcName>`的方式调用的，这一点和Python十分相似。
  * 包名和包所在的文件夹名可以是不同的，此处的`<pkgName>`即为通过`package <pkgName>`声明的包名，而非文件夹名。
* 最后大家可以看到我们输出的内容里面包含了很多非ASCII码字符。实际上，Go是天生支持UTF-8的，任何字符都可以直接输出，你甚至可以用UTF-8中的任何字符作为标识符。

> Go使用`package`(和Python的模块类似)来组织代码。`main.main()`函数(这个函数位于主包）是每一个独立的可运行程序的入口点。Go使用UTF-8字符串和标识符(因为UTF-8的发明者也就是Go的发明者之一)，所以它天生支持多语言。