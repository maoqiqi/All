# shell

> 作者：March    
> 链接：[shell](https://github.com/maoqiqi/blog/blob/master/pages/os/shell.md)    
> 博客：http://blog.csdn.net/u011810138    
> 邮箱：fengqi.mao.march@gmail.com    
> 著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。    

## 简介

### 什么是 shell ？

shell 是操作系统（内核）与用户之间的桥梁，充当命令解释器的作用，将用户输入的命令翻译给系统执行。
Linux 中有多种 shell，Bash是许多Linux发行版的默认Shell。

### 什么是 Bash ？

ash（Bourne-Again SHell）是一个为GNU计划编写的 Unix shell。事实上，还有许多传统UNIX上用的Shell，
例如tcsh、csh、ash、bsh、ksh等等。

### bash shell 的优点

* 命令记忆能力（history）
* 命令和文件补全功能（[Tab]键的功能）
* 命令别名设置功能（alias）
* 作业控制、前台、后台控制（job control，foreground，background）
* 程序脚本（bash script）
* 通配符（Wildcard）

### bash shell 的内置命令：type


## shell 的变量功能

### 什么是变量？

变量就是以一组文字或符号等，来替代一些设置或者是一串保留的数据。

### 变量的作用

* 变量的可变性和方便性
* 影响bash环境操作的变量
* 脚本程序设计的好帮手

### 变量的显示与设置：echo，unset

```
echo $PATH
/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin::/usr/local/go/bin:/Users/mac/go//bin
echo $HOME
/Users/mac
echo $MAIL

echo $name
# 这里没有数据，因为变量尚未赋值。
name=march
echo $name
march
```

变量的设置规则

* 变量与变量内容以一个等号”=”连接。
  
  ```
  name=march
  ```
  
* 等号两边不能存在空格字符。
* 变量名称只能是英文字母或者数字，但是开头字符不能是数字。
* 变量内容若有空格符可使用双引号或者单引号将变量内容结合起来，但是双引号内的特殊字符如$等可以保持原有的特性，单引号内的特殊字符仅为一般字符（纯文本）。
  
  ```
  name="$LANG"
  echo $name
  zh_CN.UTF-8
  ```
  
  ```
  name='$LANG'
  echo $name
  $LANG
  ```
  
* 可以使用转义字符”\”将特殊符号（如[enter]、$、空格符、!等）变成一般字符。
  
  ```
  name="\$LANG"
  echo $name
  $LANG
  ```
  
* 在一串指令中，还需要通过其他的指令提供的信息，可以使用反单引号"\`命令\`"或"$（命令）"。特别注意，\`是键盘上方的数字键1左边的那个按键，而不是单引号。
  
  ```
  version=$(uname -r)
  echo $version
  15.6.0
  ```
  
  ```
  version=`uname -r`
  echo $version
  15.6.0
  ```
  
* 若该变量需要增加变量内容时，则可以使用"$变量名称"或${变量}累加内容。
  
  ```
  name="$name"_11
  echo $name
  march_11
  ```
  
* 若该变量需要在其他子程序使用，则需要以`export`来使变量成为环境变量。
  
  ```
  export name
  bash
  echo $name
  march_11
  exit
  ```
* 通体大写字符为系统预设的变量，自行设定的变量可以使用小写字符，方便判断。
* 取消变量的方法为:unset 变量名称。
  
  ```
  unset name
  ```
  

### 环境变量的功能

### 用env查看环境变量与常见环境变量说明

env 是 environment (环境) 的简写，上面的例子当中，是列出来所有的环境变量。当然，如果使用 export 也会是一样的内容，只不过，export 还有其他额外的功能就是了。

* HOME
  代表用户的家目录。还记得我们可以使用 cd ~ 去到自己的家目录吗？或者利用 cd 就可以直接回到用户家目录了。那就是取用这个变量，有很多程序都可能会取用到这个变量的值！
* SHELL
  告知我们，目前这个环境使用的 SHELL 是哪个程序？ Linux 默认使用 /bin/bash 的。
* HISTSIZE
  这个与"历史命令"有关，亦即是，我们曾经执行过的命令可以被系统记录下来，而记录的"笔数"则是由这个值来配置的。
* MAIL
  当我们使用 mail 这个命令在收信时，系统会去读取的邮件信箱文件 (mailbox)。
* PATH
  就是运行文件搜寻的路径，目录与目录中间以冒号(:)分隔，于文件的搜寻是依序由 PATH 的变量内的目录来查询，所以，目录的顺序也是重要的。
* LANG
  这个重要。就是语系数据，很多信息都会用到他。举例来说，当我们在启动某些 perl 的程序语言文件时，他会主动的去分析语系数据文件，
  如果发现有他无法解析的编码语系，可能会产生错误。一般来说，我们中文编码通常是 zh_TW.Big5 或者是 zh_TW.UTF-8，
  这两个编码偏偏不容易被解译出来，所以有的时候，可能需要修订一下语系数据。 
* RANDOM
  这是随机数的变量。目前大多数的 distributions 都会有随机数生成器，那就是 /dev/random 这个文件。
  我们可以通过这个随机数文件相关的变量 ($RANDOM) 来随机取得随机数值。在 BASH 的环境下，这个 RANDOM 变量的内容，
  介于 0~32767 之间，所以你只要 echo $RANDOM 时，系统就会主动的随机取出一个介于 0~32767 的数值。
  万一我想要使用 0~9 之间的数值呢？利用 declare 声明数值类型，然后这样做就可以了：
  
  ```
  number=$RANDOM * 10 / 32768 ;echo $number
  ```

### 用set查看所有变量(含环境变量与自定义变量)

一般来说，不论是否为环境变量，只要跟我们目前这个 shell 的操作接口有关的变量， 通常都会被配置为大写字符。
也就是说，基本上，在 Linux 默认的情况中，使用{大写的字母}来配置的变量一般为系统内定需要的变量。

* PS1：(提示字符的配置)
* $：(关于本 shell 的 PID)
* ?：(关于上个运行命令的回传值)


### export：自定义变量转成环境变量


### 影响显示结果的语系变量


### 变量的有效范围

### 变量键盘读取、数组与声明：read、array、declare

* read
  
  ```
  [root@www ~]# read [-pt] variable
  选项与参数：
  -p  ：后面可以接提示字符！
  -t  ：后面可以接等待的『秒数！』这个比较有趣～不会一直等待使用者啦！
  
  范例一：让用户由键盘输入一内容，将该内容变成名为 atest 的变量
  [root@www ~]# read atest
  This is a test        <==此时光标会等待你输入！请输入左侧文字看看
  [root@www ~]# echo $atest
  This is a test          <==你刚刚输入的数据已经变成一个变量内容！
  
  范例二：提示使用者 30 秒内输入自己的大名，将该输入字符串作为名为 named 的变量内容
  [root@www ~]# read -p "Please keyin your name: " -t 30 named
  Please keyin your name: VBird Tsai   <==注意看，会有提示字符喔！
  [root@www ~]# echo $named
  VBird Tsai        <==输入的数据又变成一个变量的内容了！
  ```
  
  read 之后不加任何参数，直接加上变量名称，那么下面就会主动出现一个空白行等待你的输入(如范例一)。 
  如果加上 -t 后面接秒数，例如上面的范例二，那么 30 秒之内没有任何操作时，该命令就会自动略过了，
  如果是加上 -p ，在输入的光标前就会有比较多可以用的提示字符给我们参考。在命令的下达里面，比较美观啦。
  
* declare / typeset

  ``` 
[root@www ~]# declare [-aixr] variable
选项与参数：
-a  ：将后面名为 variable 的变量定义成为数组 (array) 类型
-i  ：将后面名为 variable 的变量定义成为整数数字 (integer) 类型
-x  ：用法与 export 一样，就是将后面的 variable 变成环境变量；
-r  ：将变量配置成为 readonly 类型，该变量不可被更改内容，也不能 unset

范例一：让变量 sum 进行 100+300+50 的加总结果
[root@www ~]# sum=100+300+50
[root@www ~]# echo $sum
100+300+50  <==咦！怎么没有帮我计算加总？因为这是文字型态的变量属性啊！
[root@www ~]# declare -i sum=100+300+50
[root@www ~]# echo $sum
450         <==明白了吗？
  ```

  由于在默认的情况底下， bash 对于变量有几个基本的定义：
  
  * 

### 


## 命名别名与历史命令