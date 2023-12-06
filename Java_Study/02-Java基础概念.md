# 02-Java基础概念

##### 注释

注释是对代码的解释和说明文字

Java中的注释分为三种：

* 单行注释：

  ```java
  // 这是单行注释文字
  ```
* 多行注释：

  ```java
  /*
  这是多行注释文字
  这是多行注释文字
  这是多行注释文字
  */
  注意：多行注释不能嵌套使用。
  ```
* 文档注释：

  ```java
  /**
  这是多行注释文字
  这是多行注释文字
  这是多行注释文字
  */
  ```

##### 关键字

被Java赋予了特定含义的英文单词。

当我们在代码中写了关键字之后，程序在运行的时候，就知道要做什么事情了。

![image](assets/image-20230812104119-1mxwnem.png)

第一个关键字class

* 表示定义一个类。创建一个类。

类：Java项目最基本的组成单元，一个完整的Java项目有可能会有成千上万个类来组成的。

class后面跟随的就是这个类的名字，简称：类名。

在类名后面会有一对大括号，表示这个类的内容。

```java
public class HelloWorld{
  
}
```

##### 字面量

作用：告诉程序员，数据在程序中的书写格式。

![image](assets/image-20230812105019-x3l0j48.png)

```java
public class Demo {
    public static void main(String[] args) {
        System.out.println(10); // 输出一个整数
        System.out.println(5.5); // 输出一个小数
        System.out.println('a'); // 输出一个字符
        System.out.println(true); // 输出boolean值true
        System.out.println("欢迎来到黑马程序员"); // 输出字符串
	System.out.println("null"); // 输出null
    }
}
```

注意：如果要打印null，那么只能用字符串的形式进行打印

技巧：

1. 不带小数点的数字都是整数类型的字面量。
2. 只要带了小数点，那么就是小数类型的字面量。
3. 只要用双引号引起来的，不管里面的内容是什么，不管里面有没有内容，都是字符串类型的字面量。
4. 字符类型的字面量必须用单引号引起来，不管内容是什么，但是个数有且只能有一个。
5. 字符类型的字面量只有两个值，true、false。
6. 空类型的字面量只有一个值，null。

特殊字符

* \t：制表符

  在打印时，把前面字符串的长度补齐到8，或者8的整数倍，最少补1个空格，最多补8个空格

  ```java
  public class Demo {
      public static void main(String[] args) {
          System.out.println("abc"+'\t'); //会打印出5个空格
      }
  }
  ```

##### 变量

###### 什么是变量？

* 变量就在程序中临时存储数据的容器。但是这个容器中只能存一个值。

###### 变量的定义格式

* 数据类型 变量名 = 数据值；

  * 数据类型：限定了变量当中能存储什么类型的数据。如果要存10，那么数据类型就需要写整数类型。如果要存10.0，那么数据类型就需要写小数类型。

  * 变量名：其实就是这个容器的名字。当以后想要使用变量里面的数据时，直接使用变量名就可以了。

  * 数据值：真正存储在容器中的数据。

  * 分号：表示语句的结束，就跟以前写作文时候的句号是一样的。

###### 常用的数据类型

* 整数：int
* 小数：double（浮点数）

```java
public class VariableDemo{
	public static void main(String[] args){
		//定义一个整数类型的变量
		//数据类型 变量名 = 数据值;
		int a = 16;
		System.out.println(a);//16
	
		//定义一个小数类型的变量
		double b = 10.1;
		System.out.println(b);//10.1
	}
}
```

###### 变量的使用方式

* 输出打印
* 参与计算
* 修改记录的值

###### 变量的注意事项

* 变量名不能重复。
* 在一条语句中，可以定义多个变量。但是这种方式影响代码的阅读，所以了解一下即可。
* 变量在使用之前必须要赋值。

```java
public class VariableDemo2{
	public static void main(String[] args){
		//1.变量名不允许重复
		//int a = 10;
		//int a = 20;
		//System.out.println(a);
	
		//2.一条语句可以定义多个变量
		//了解。
		//int a = 10, b = 20, c = 20,d = 20;
		//System.out.println(a);//?
		//System.out.println(b);//?
	
	
		//3.变量在使用之前必须要赋值
		int a = 30;
		System.out.println(a);
	}
}
```

###### 变量的练习

需求：说出公交车到终点站之后，车上一共有多少乘客？  
 一开始没有乘客。  
第一站：上去一位乘客，没有下来乘客。  
第二站：上去两位乘客，下来一位乘客。  
第三站：上去两位乘客，下来一位乘客。  
第四站：没有上去乘客，下来一位乘客。  
第五站：上去一位乘客，没有下来乘客。  
问：到了终点站之后，车上一共多少乘客？

```java
public class VariableTest1{
	//主入口
	public static void main(String[] args){
		//一开始没有乘客。
		int count = 0;
		//第一站：上去一位乘客
		//在原有的基础上 + 1
		count = count + 1;
		//System.out.println(count);
		//第二站：上去两位乘客，下来一位乘客
		count = count + 2 - 1; 
		//第三站：上去两位乘客，下来一位乘客
		count = count + 2 - 1;
		//第四站：下来一位乘客
		count = count - 1;
		//第五站：上去一位乘客
		count = count + 1;
		//请问：到了终点站，车上一共几位乘客。
		System.out.println(count);//3
	}
}
```

##### 计算机的存储规则(扩展)

在计算机中，任意数据都是以二进制的形式来存储的

![3c54178ce1269547b4b99c4027fa309](assets/3c54178ce1269547b4b99c4027fa309-20230812120922-x2gdjhk.jpg)

###### 常见的进制

* 二进制：由0和1组成

  代码中以0b开头
* 十进制：由0~9组成

  前面不需要加任何前缀
* 八进制：由0~7组成

  代码中以0开头
* 十六进制：由0~9和a~f组成

  代码中以0x开头

注：JDK7的特性

###### 进制转换

==其他进制转十进制==

![8a05133c0edd90095ec1c48c75460d3](assets/8a05133c0edd90095ec1c48c75460d3-20230812114618-htowcy7.jpg)

![a62affd2140d5fee7838c2228d4360f](assets/a62affd2140d5fee7838c2228d4360f-20230812114634-8qbw40c.jpg)

![92a2eefa2b2f7978ad27edc01d37089](assets/92a2eefa2b2f7978ad27edc01d37089-20230812114646-snprz7m.jpg)

![2235a5e0f3c1fb04b415b782b332c08](assets/2235a5e0f3c1fb04b415b782b332c08-20230812114700-us6d8n7.jpg)

==十进制转其他进制==

![1188261201adb6c3f2bad737762e2dd](assets/1188261201adb6c3f2bad737762e2dd-20230812114718-p1snkfg.jpg)

==ASCII码表==

![bab6bd348a39e08a886d09e7f6b169d](assets/bab6bd348a39e08a886d09e7f6b169d-20230812114833-quclc0a.jpg)

==中文汉字码表==

![dfb5f5c3f75ee2c13a0888872ced467](assets/dfb5f5c3f75ee2c13a0888872ced467-20230812120637-piu9o21.jpg)

![0bc15a08bfb92ab5cfbd64de4a9f684](assets/0bc15a08bfb92ab5cfbd64de4a9f684-20230812120722-td6hk50.jpg)

![a6155b2c55a0cbf6a2e069d06c3d0e7](assets/a6155b2c55a0cbf6a2e069d06c3d0e7-20230812120840-vt1e5mb.jpg)

![45d5f37626ade73a477b7a880cae434](assets/45d5f37626ade73a477b7a880cae434-20230812120946-06zy136.jpg)

![e0384f86fa28b78f6361ca87665cc69](assets/e0384f86fa28b78f6361ca87665cc69-20230812121008-qghpdhv.jpg)

注：2k、4k是指屏幕的最大分辨率

![c232dc21e732654e6c8926b966feb0b](assets/c232dc21e732654e6c8926b966feb0b-20230812121112-ut85z70.jpg)

注：小方块就是像素点

![1f3a22cf46881b7cb566187fa342762](assets/1f3a22cf46881b7cb566187fa342762-20230812121148-0vocow9.jpg)

![95e08b637cbf6b8c5c84d17e215071b](assets/95e08b637cbf6b8c5c84d17e215071b-20230812121209-94n8ydw.jpg)

![a025c15fe7463a2473ed2ed0051bbda](assets/a025c15fe7463a2473ed2ed0051bbda-20230812121227-rpd4j1w.jpg)

注：美学三原色-红黄蓝

![48fafd7ceb753a697062cc12d6a9e9b](assets/48fafd7ceb753a697062cc12d6a9e9b-20230812121302-ybvt9oy.jpg)

注：光学三原色-红绿蓝

![58132ae6b1d59349dfad48d0f258628](assets/58132ae6b1d59349dfad48d0f258628-20230812121336-y1gfddg.jpg)

![b0745e687d5d45ea7771b4576da3ba3](assets/b0745e687d5d45ea7771b4576da3ba3-20230812121350-vd3ie0j.jpg)

![3df5c2b5c6860256893ddf9adaa2c7b](assets/3df5c2b5c6860256893ddf9adaa2c7b-20230812121407-egbiex0.jpg)

![552a6e3107bf9f32e53392964a79535](assets/552a6e3107bf9f32e53392964a79535-20230812121423-0andw10.jpg)

![90901f585f48990cffa005a8e32bd98](assets/90901f585f48990cffa005a8e32bd98-20230812121437-i57r6vg.jpg)

##### 数据类型

###### Java语言数据类型的分类

* 基本数据类型
* 引用数据类型（面向对象的时候再深入学习）

###### 基本数据类型的四类八种

![image](assets/image-20230812121717-4cyoqud.png)

说明：

* e+38表示是乘以10的38次方，同样，e-45表示乘以10的负45次方。
* 在java中整数默认是int类型，浮点数默认是double类型。

需要记忆以下几点

* byte类型的取值范围：-128 ~ 127

* int类型的大概取值范围：-21亿多  ~ 21亿多

* 整数类型和小数类型的取值范围大小关系：double > float > long > int > short > byte

* 最为常用的数据类型选择：

  * 在定义变量的时候，要根据实际的情况来选择不同类型的变量。比如：人的年龄，可以选择byte类型。比如：地球的年龄，可以选择long类型。
  * 如果整数类型中，不太确定范围，那么默认使用int类型。
  * 如果小数类型中，不太确定范围，那么默认使用double类型。
  * 如果要定义字符类型的变量，那么使用char
  * 如果要定义布尔类型的变量，那么使用boolean

```java
public class VariableDemo3{
    public static void main(String[] args){
        //1.定义byte类型的变量
        //数据类型 变量名 = 数据值;
        byte a = 10;
        System.out.println(a);

        //2.定义short类型的变量
        short b = 20;
        System.out.println(b);

        //3.定义int类型的变量
        int c = 30;
        System.out.println(c);

        //4.定义long类型的变量
        long d = 123456789123456789L;
        System.out.println(d);

        //5.定义float类型的变量
        float e = 10.1F;
        System.out.println(e);

        //6.定义double类型的变量
        double f = 20.3;
        System.out.println(f);

        //7.定义char类型的变量
        char g = 'a';
        System.out.println(g);

        //8.定义boolean类型的变量
        boolean h = true;
        System.out.println(h);

    }
}
```

注意点：

* 如果要定义 一个整数类型的变量，不知道选择哪种数据类型了，默认使用int。
* 如果要定义 一个小数类型的变量，不知道选择哪种数据类型了，默认使用double。
* 如果要定义一个long类型的变量，那么在数据值的后面需要加上L后缀。（大小写都可以，建议大写）
* 如果要定义一个float类型的变量，那么在数据值的后面需要加上F后缀。（大小写都可以）

###### **练习1**

需求：定义5个变量记录老师的信息并打印

```java
public class VariableTest1{
	public static void main(String[] args){
		//1.定义字符串类型的变量记录老师的姓名
		String name = "黑马谢广坤";
		//2.定义整数类型的变量记录老师的年龄
		int age = 18;
		//3.定义字符类型的变量记录老师的性别
		char gender = '男';
		//4.定义小数类型的变量记录老师的身高
		double height = 180.1;
		//5.定义布尔类型的变量记录老师的婚姻状况
		boolean flag = true;
	
		//输出5个变量的值
		System.out.println(name);
		System.out.println(age);
		System.out.println(gender);
		System.out.println(height);
		System.out.println(flag);
	
	}
}
```

###### **练习2**

需求：将（电影名称，主演，年份，评分）四个信息选择不同类型的变量，随后打印出来。

```java
public class VariableTest2{
	public static void main(String[] args){
		//1.定义字符串变量记录电影的名称
		String movie = "送初恋回家";
		//2.定义三个变量记录主演的名字
		String name1 = "刘鑫";
		String name2 = "张雨提";
		String name3 = "高媛";
		//3. 定义整数类型的变量记录年份
		int year = 2020;
		//4.定义小数类型的变量记录电影的评分
		double score = 9.0;

		//打印变量的信息
		System.out.println(movie);
		System.out.println(name1);
		System.out.println(name2);
		System.out.println(name3);
		System.out.println(year);
		System.out.println(score);

	}
}
```

###### **练习3**

需求：选择其中一部手机，将（手机价格，手机品牌）两个信息选择不同类型的变量，随后打印出来。

```java
public class VariableTest3{
	public static void main(String[] args){
		//1.定义小数类型的变量记录手机的价格
		double price = 5299.0;
	
		//2.定义字符串类型的变量记录手机的品牌
		String brand = "华为";
	
		//输出变量记录的值
		System.out.println(price);
		System.out.println(brand);
	}
}
```

##### 标识符

标识符就是给类，方法，变量等起的名字。

业内大多数程序员都在遵守阿里巴巴的命名规则。

###### 硬性要求

必须要这么做，否则代码会报错。

* 必须由数字、字母、下划线(_)、美元符号($)组成
* 不能以数字开头
* 不能是关键字
* 区分大小写

###### 软件建议

如果不这么做，代码不会报错，但是会让代码显得比较low。

* 小驼峰命名法：适用于变量名和方法名

  * 如果是一个单词，那么全部小写，比如：name
  * ​如果是多个单词，那么从第二个单词开始，首字母大写，比如：firstName、maxAge
* 大驼峰命名法：适用于类名

  * 如果是一个单词，那么首字母大写。比如：Demo、Test
  * 如果是多个单词，那么每一个单词首字母都需要大写。比如：HelloWorld

说明：不管起什么名字，都要做到见名知意。

###### 阿里巴巴命名规范细节

1. 尽量不要用拼音。但是一些国际通用的拼音可视为英文单词。

    正确：alibaba、hangzhou、nanjing 错误：jiage、dazhe
2. 平时在给变量名、方法名、类名起名字的时候，不要使用下划线或美元符号。

    错误：_name 正确：name

##### 键盘录入

键盘录入的实际功能Java已经帮我们写好了，不需要我们自己再实现了，而Java写好的功能都放在了Scanner这个类中，所以，我们只要直接使用Scanner这个类就可以了。

使用步骤：

* 导包：其实就是表示先找到Scanner这个类在哪
* 创建对象：其实就表示申明一下，我准备开始用Scanner这个类了
* 接收数据：也是真正干活的代码

```java
//导包，其实就是先找到Scanner这个类在哪
import java.util.Scanner;
public class ScannerDemo1{
	public static void main(String[] args){
		//2.创建对象，其实就是申明一下，我准备开始用Scanner这个类了。
		Scanner sc = new Scanner(System.in);
		//3.接收数据
		//当程序运行之后，我们在键盘输入的数据就会被变量i给接收了
		System.out.println("请输入一个数字");
		int i = sc.nextInt();
		System.out.println(i);
	}
}
```

##### IDEA

###### IDEA概述

IDEA全称IntelliJ IDEA，是用于Java语言开发的集成环境，它是业界公认的目前用于Java程序开发最好的工具。

集成环境：把代码编写，编译，执行，调试等多种功能综合到一起的开发工具。

###### IDEA中层级结构介绍

结构分类

* project（项目、工程）
* module（模块）
* package（包）
* class（类）

结构介绍

* project（项目、工程）

  淘宝、京东、黑马程序员网站都属于一个个项目，IDEA中就是一个个的Project。
* module（模块）

  在一个项目中，可以存放多个模块，不同的模块可以存放项目中不同的业务功能代码。在黑马程序员的官方网站中，至少包含了论坛模块和报名、咨询模块，为了更好的管理代码，我们会把代码分别放在两个模块中存放。
* package（包）

  一个模块中又有很多的业务，以黑马程序员官方网站的论坛模块为例，至少包含了发帖和评论的业务。为了把这些业务区分的更加清楚，就会用包来管理这些不同的业务。
* class（类）

  就是真正写代码的地方。

###### IDEA相关设置

==字体和字体大小设置==

![image](assets/image-20230812131638-m17a76z.png)

==注释颜色设置==

![image](assets/image-20230812131907-9zpku3g.png)

==自动导包设置==

![image](assets/image-20230812132019-yzum29b.png)

==忽略大小写设置==

![image](assets/image-20230812132122-ycbdzk7.png)

‍
