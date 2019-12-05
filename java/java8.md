# Java8 新特性

> 作者：March    
> 链接：[Java8 新特性](https://github.com/maoqiqi/blog/blob/master/pages/mock.md)    
> 博客：http://blog.csdn.net/u011810138    
> 邮箱：fengqi.mao.march@gmail.com    
> 著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。    

* 速度更快
* 代码更少（增加了新的语法 Lambda 表达式）
* 强大的 Stream API
* 便于并行
* 最大化减少空指针异常 Optional

## 一、Lambda 表达式

* 定义

  Lambda 是一个匿名函数,我们可以把 Lambda 表达式理解为是一段可以传递的代码(将代码像数据一样进行传递)。
  可以写出更简洁、更灵活的代码。作为一种更紧凑的代码风格,使 Java 的语言表达能力得到了提升。
  
* 从匿名类到 Lambda 的转换

    ```java
    public class LambdaTest {
    
        @org.junit.Test
        public void test() {
            // 匿名内部类
            Runnable r1 = new Runnable() {
                @Override
                public void run() {
                    System.out.println("Hello World!");
                }
            };
            r1.run();
    
            // Lambda 表达式
            Runnable r2 = () -> System.out.println("Hello World!");
            r2.run();
        }
    }
    ```

* Lambda 表达式语法

  Lambda 表达式在 Java 语言中引入了一个新的语法元素和操作符。
  这个操作符为 “->” , 该操作符被称为 Lambda 操作符或剪头操作符。
  它将 Lambda 分为两个部分:
  
  左侧:指定了 Lambda 表达式需要的所有参数。
  
  右侧:指定了 Lambda 体,即 Lambda 表达式要执行的功能。

* 类型推断

  Lambda 表达式中的参数类型都是由编译器推断得出的。
  Lambda 表达式中无需指定类型,程序依然可以编译,这是因为 javac 根据程序的上下文,在后台推断出了参数的类型。
  Lambda 表达式的类型依赖于上下文环境,是由编译器推断出来的。
  这就是所谓的 “类型推断”。


## 二、函数式接口

* 定义

  * 只包含一个抽象方法的接口,称为函数式接口。
  * 你可以通过 Lambda 表达式来创建该接口的对象。
  (若 Lambda 表达式抛出一个受检异常,那么该异常需要在目标接口的抽象方法上进行声明)。
  * 我们可以在任意函数式接口上使用 @FunctionalInterface 注解,
    这样做可以检查它是否是一个函数式接口,同时 javadoc 也会包含一条声明,说明这个接口是一个函数式接口。

* 自定义函数式接口

    ```java
    // 函数式接口中使用泛型
    @FunctionalInterface
    public interface MyFunc<T> {
    
        T getValue(T t);
    }
    ```

* 作为参数传递 Lambda 表达式

    ```java
    public class LambdaTest {
    
        public String getValue(String string, MyFunc<String> func) {
            return func.getValue(string);
        }
    
        @org.junit.Test
        public void test() {
            // 匿名内部类
            String str1 = getValue("hello", new MyFunc<String>() {
                @Override
                public String getValue(String s) {
                    return s.toUpperCase();
                }
            });
            System.out.println(str1);
    
            // 作为参数传递 Lambda 表达式:
            String str2 = getValue("hello", (s) -> s.toUpperCase());
            System.out.println(str2);
        }
    }
    ```

  **注意**
  
  作为参数传递 Lambda 表达式:为了将 Lambda 表达式作为参数传递,
  接收Lambda 表达式的参数类型必须是与该 Lambda 表达式兼容的函数式接口的类型。
  
*  Java 内置四大核心函数式接口

    | 函数式接口 | 参数类型 | 返回类型 | 用途 |
    | :------: | :----: | :-----: | --- |
    | Consumer\<T><br>消费型接口 | T | void | 对类型为T的对象应用操作。包含方法: void accept(T t); |
    | Supplier\<T><br>供给型接口 | 无 | T | 返回类型为T的对象。包含方法:T get(); |
    | Function<T,R><br>函数型接口 | T | R | 对类型为T的对象应用操作,并返回结果。结果是R类型的对象。包含方法:R apply(T t); |
    | Predicate\<T><br>断定型接口 | T | boolean | 确定类型为T的对象是否满足某约束,并返回 boolean 值。包含方法：boolean test(T t); |


## 三、方法引用与构造器引用

#### 方法引用

* 定义

  当要传递给Lambda体的操作,已经有实现的方法了,可以使用方法引用!
  
  (实现抽象方法的参数列表,必须与方法引用方法的参数列表保持一致!)
  
  方法引用:使用操作符 “::” 将方法名和对象或类的名字分隔开来。
  
  如下三种主要使用情况:
  
  * 对象::实例方法
  * 类::静态方法
  * 类::实例方法
  
  **注意**
  
  当需要引用方法的第一个参数是调用对象,并且第二个参数是需要引用方法的第二个参数(或无参数)时：ClassName::methodName

* 

#### 构造器引用

#### 数组引用

## 四、Stream API

* 介绍
  
  Stream 是 Java8 中处理集合的关键抽象概念,它可以指定你希望对集合进行的操作,可以执行非常复杂的查找、过滤和映射数据等操作。
  使用 Stream API 对集合数据进行操作,就类似于使用 SQL 执行的数据库查询。也可以使用 Stream API 来并行执行操作。
  简而言之, Stream API 提供了一种高效且易于使用的处理数据的方式。
  
* 定义
  
  **流(Stream) 到底是什么呢?**
  
  是数据渠道,用于操作数据源(集合、数组等)所生成的元素序列。“集合讲的是数据,流讲的是计算!”
  
  **注意**
  
  * Stream 自己不会存储元素。
  * Stream 不会改变源对象。相反,他们会返回一个持有结果的新Stream。
  * Stream 操作是延迟执行的。这意味着他们会等到需要结果的时候才执行。
  
* Stream 的操作三个步骤

  * 1.创建 Stream
  
    一个数据源(如:集合、数组),获取一个流
    
    * 由数组创建流
    
    * 由值创建流
    
    * 由函数创建流:创建无限流
    
  * 2.中间操作
    
    一个中间操作链,对数据源的数据进行处理
    
    * 筛选与切片
    
    * 映射
    
    * 排序
    
  * 3.终止操作（终端操作）
    
    一个终止操作,执行中间操作链,并产生结果
    
    * 查找与匹配
    
    * 归约
    
    * 收集

*  并行流与串行流

## 五、接口中的默认方法与静态方法

## 六、新时间日期 API

## 七、其它新特性

1. 111

    (1). 111
      
    (2). 222
  
2. 222
3. 333

* 1
  * 1
  * 2
* 2
  * 1
  * 2
* 3
  * 1
  * 2
  
一、 a

  a. 1
  
    a. 1
    b. b
    c. c
    
  b. 2
  c. 3
  
二、 2

  1. 1
    
    1. 1
    2. 2
    3. 3
    
  2. 2
  3. 3

三、 2

  1. 1
    
    a. 1
    
      dddddddd
      
      ```java
      public
      ```
      
      ojvgofjop
    
    b. 2
    c. 3
    
  2. 2
  3. 3