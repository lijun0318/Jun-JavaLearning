##                                          数据类型

#### 标识符

【1】标识符 ： 读音 biao zhi fu

【2】什么是标识符？

 包，类，变量，方法.....等等，就是要起名字的地方，那个名字就是标识符

【3】标识符定义规则：

1.四个可以（组成部分）：数字，字母，下划线_，美元符号$

注意：字母的概念比较宽泛，指的是英文字母，汉字，日语，俄语.....

但是我们一般起名字尽量用英文字母

2.两个不可以：不可以以数字开头，不可以使用Java中的关键字

3.见名知意：增加可读性

4.大小写敏感：int a ；int A;

5.遵照驼峰命名：

​	类名：首字母大写，其余遵循驼峰命名

​	方法名，变量名：首字母小写，其余遵循驼峰命名

​	包名：全部小写，不遵循驼峰命名

6.长度无限制，但是不建议太长 



#### 关键字

关键字：被Java语言赋予了特殊含义，用作专门用途的单词

特点：Java中所有的关键字都为小写

官网：[https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html)

| `abstract`  | `continue` | `for`        | `new`        | `switch`       |
| ----------- | ---------- | ------------ | ------------ | -------------- |
| `assert`*** | `default`  | `goto`*      | `package`    | `synchronized` |
| `boolean`   | `do`       | `if`         | `private`    | `this`         |
| `break`     | `double`   | `implements` | `protected`  | `throw`        |
| `byte`      | `else`     | `import`     | `public`     | `throws`       |
| `case`      | `enum`**** | `instanceof` | `return`     | `transient`    |
| `catch`     | `extends`  | `int`        | `short`      | `try`          |
| `char`      | `final`    | `interface`  | `static`     | `void`         |
| `class`     | `finally`  | `long`       | `strictfp`** | `volatile`     |
| `const`*    | `float`    | `native`     | `super`      | `while`        |

| *    |      | not used     |
| ---- | ---- | ------------ |
| **   |      | added in 1.2 |
| ***  |      | added in 1.4 |
| **** |      | added in 5.0 |



###                                                           变量和常量

#### 字面常量

常量分为两种：

常量通常指的是一个固定的值，例如：1，2，3，'a','b',true,false,"hello-World"等.....

在Java语言中，主要是利用关键字final来定义一个常量。常量一旦被初始化后不能再更改其值。

为了更好的区分和表述，一般将1，2，3，'a','b',true,false,"hello-World"等称为字面常量，而使用final修饰的PI等称为符号常量（字符常量）。



字面常量的类型：

​	整形常量 123 88

​	实型常量 3.1415926

​	字符常量  'a'

​	逻辑常量 true false

​	字符串常量 “hello-world”



注意：逻辑常量就两个值，一个是true，一个是false



#### 变量

变量本质上就是代表一个“可操作的储存空间”，空间位置是确定的，但是里面放置什么值不确定。我们可通过变量名来访问“对应的储存空间”，从而操作这个“储存空间”储存的值。Java是一种强类型语言，每个变量都必须声明其数据类型。变量的数据类型决定了变量占据储存空间的大小。比如： int a =  3; 表示a变量的空间大小为4个字节。变量作为程序中最基本的储存单元，其要素包括变量，变量类型和作用域。变量在使用前必须对其声明，只有在变量声明以后，才能为其分配相应长度的储存空间。



【1】变量声明格式：

type varName;    数据类型 变量名； 如： int age;

type varName = value;  数据类型 变量名 = 初始值； 如：int age = 66;

type varName,varName2;  数据类型 变量名，变量名2 ；如：int age, age2;

type varName = value,varName2 = value2;  数据类型 变量名 = 初始值，变量名2 = 初始值;   如：int age =19,age2= 99;

【2】变量声明：

（1）如果你只定义一个变量，没有给变量进行赋值的话，那么其实这个变量相当于没有定义：（反编译查看）

![image-20201213161955576](https://i.loli.net/2020/12/13/kxOmubqFKUdInj8.png)

（2）变量如果没有进行赋值的话，那么使用的时候会出错，告诉你：尚未初始化变量：

![image-20201213162051623](https://i.loli.net/2020/12/13/4y2Wcdixa36RlLI.png)

【3】变量的赋值

![image-20201213162147368](https://i.loli.net/2020/12/13/Cd2H4wl17vQbuyj.png)

我们自己定义的时候直接可以用一句话定义：

int age = 10；

变量的值可以更改：

```java
public class TestVar01{
	public static void main(String[] args){
		    //变量的声明（定义变量）  （以年龄为案例见解）
			//Java是一个强类型的语言，只要声明变量就必须定义类型：定义整形类型
			int age;  //定义一个整型类型的变量，变量名字为age
			//对变量进行赋值操作：
			age = 10; //变量名为age，具体的值为10
			age = 12;
			age = 20;
			age = age + 4;
			age = 9;
			System.out.println(age);  //结果输出为9
	}
}
```

变量不可重复定义：

![image-20201213163045082](https://i.loli.net/2020/12/13/lXjn3bPS1KowVrg.png)

【4】变量的使用：

```java
public class TestVar01{
	public static void main(String[] args){
		    //变量的声明（定义变量）  （以年龄为案例见解）
			//Java是一个强类型的语言，只要声明变量就必须定义类型：定义整形类型
			int age;  //定义一个整型类型的变量，变量名字为age
			//对变量进行赋值操作：
			age = 10; //变量名为age，具体的值为10
			age = 12;
			age = 20;
			age = age + 4;
			age = 9;
			System.out.println(age);  //9
			//变量的使用
			System.out.println(age-2);  //7
			System.out.println(age+10);  //19
			int num = age - 66;  
			System.out.println(num);  //-57
	}
}
```

扩展：

```java
public class TestVar02{
	public static void main(String[] args){
		int a = 10;
		int b = 20;
		int c = a + b;
	}
}
```

现在对上述代码进行“反编译过程” “反汇编过程” （javap -v TestVar02.class）

![image-20201213162510824](https://i.loli.net/2020/12/13/8Q34zZ2PJGYqgs7.png)

![image-20201213162606319](https://i.loli.net/2020/12/13/OI5WyF3bdG6Dzh4.png)

【5】变量的内存

![image-20201213162713909](https://i.loli.net/2020/12/13/RGq3v7OSUhjlows.png)

【6】习题

```java
public class TestVar03{
	public static void main(String[] args){
		int num1 = 10;
		int num2 = 20;
		num1 = num2;
		num2 = num2 + 10;
		num1 = num2 + 10;
		num2 = num1;
		System.out.println("num1="+num1);
		System.out.println("num2="+num2);
	}
}
```

内存分析：

![image-20201213162802404](https://i.loli.net/2020/12/13/kGVEcKU9NDqHsgn.png)

结果：

![image-20201213162840409](https://i.loli.net/2020/12/13/o2zPFsN4b8RHATO.png)



【7】变量的作用域：

作用域指的就是作用范围，变量在什么范围中有效

作用范围就是离它最近的{}

备注：一会我们写的代码，不要去运行，会出错

```java
	/*
	局部变量： 定义在方法中
	成员变量：定义在类中，方法外
	*/
public class TestVar04{
	int b = 20;//成员变量
	public static void main(String[] args){
		System.out.println(a);//no
		int a = 10;//局部变量
		System.out.println(a);//yes
		System.out.println(b);//yes
		{
			int c = 40;
			System.ot.println(c);//yes
			int a = 50;//属于变量的重复定义
		}
		System.ot.println(c);//no
	}
	
	public void eat(){
		System.out.println(b);//yes
		System.out.println(a);//no
		int a = 30;//不是变量的重复定义
		System.out.println(a);//yes
	}
}
```



### 数据类型

Java是一种强类型语言，每个变量都必须声明其数据类型。

Java的数据类型可分为两大类：基本数据类型（primitive data type）和引用数据类型（reference data type）。

![image-20201213163139498](https://i.loli.net/2020/12/13/Y29CJcXFlHrqByh.png)

PS：巧妙记忆：除了基本数据类型以外的所有数据类型都属于引用数据类型，本章重点：基本数据类型

#### 整数类型

十进制整数，如：99，-500，0

八进制整数，要求以0开头，如：015

十六进制整数，要求0x或0X开头，如：0x15

二进制：要求0b或者0B开头，如：0b11



几进制：就是逢几进1的问题：

平时实际生活中用的最多的是：十进制

计算机用二进制最多

![image-20201213163203765](https://i.loli.net/2020/12/13/Bi8KS7xIyNqn5Hl.png)



##### 整数类型常量

【1】二进制转换为十进制：

二进制： 1101

  	1 x2^3   +     1 x*2^2   +   0 x2^1   +    1 x2^0 

=            8     +        4          +       0       +        1

=    13



【2】十进制转换为二进制：

十进制： 13

![image-20201213164916006](https://i.loli.net/2020/12/13/NAYBqSL1dOW2y5w.png)



【3】八进制装换为十进制：
八进制： 16

​        1 x8^1     +     6 x8^0

=         8       +       6

14



【4】十进制转换为八进制：

十进制： 14

![image-20201213165814848](https://i.loli.net/2020/12/13/X7W3kpomMz85Q16.png)



【5】八进制转换为十六进制：

把十进制当成一个中转站：

八进制----》十进制----》十六进制



实际上根本不用自己转换这么麻烦： 我们可以直接用系统中提供给我们的程序员计算器：

![image-20201213170522477](https://i.loli.net/2020/12/13/2kfq1cPz4FenNWY.png)



##### 整数类型变量

整型数据类型：

| 类型  | 占用存储空间 |                    表数范围                     |
| :---: | :----------: | :---------------------------------------------: |
| byte  |      1       |            -2^7 ~ 2^7-1（-128~127）             |
| short |      2       |         -2^15 ~ 2^15-1 （-32768~32767）         |
|  int  |      4       | -2^31 ~ 2^31-1 （-2147483648~2147483647）约21亿 |
| long  |      8       |                 -2^63 ~ 2^63-1                  |

比如：byte的右侧表数范围127怎么算出来的？

byte：1字节 = 8位

二进制：01111111

   1x2^6   + 1x2^5   + 1x2^4   + 1x2^3   + 1x2^2   + 1x2^1   + 1x2^0

=      64     +  32       +      16      +   8          +    4        +       2      +      1

=      127 

代码：

```java
public class TestVar05{
	public static void main(String[] args){
		//定义整数类型的变量：
		//给变量赋值的时候，值可以为不同进制的：
		int num1 = 12;//默认情况下赋值就是十进制的情况
		System.out.println(num1);
		int num2 = 012;//前面加上0， 这个值就是八进制的
		System.out.println(num2);
		int num3 = 0x12;//前面加上0x或者0X，这个值就是十六进制的
		System.out.println(num3);
		int num4 = 0b10;//前面加上0b或者0B，这个值就是二进制的
		System.out.println(num4);
		
		//定义byte类型的变量：
		byte b = 126;//定义了一个byte类型的变量，名字叫b，赋值为126
		System.out.println(b);
		//注意：超范围的赋值会报错。
		short s = 30000;
		System.out.println(s);
		int i = 1234;  //int i = 12345678910; 报错
		System.out.println(i);
		//整数类型默认就是int类型的，所以12345678910是一个int类型的数，对于int类型来说，它超出范围了
		//要想把一个数给long类型变量，那么后面加上L（推荐）或者l就可以了
		long l = 12345678910L;  //long l = 12345678910;  报错
		System.out.println(l);
		//注意： 只有这个数超出int类型的范围了后面才需要加上L， 否则无需加L也可以赋值给long类型；
		long num5 =12;
		System.out.println(num5);
	}
}
```



#### 浮点类型

##### 浮点类型常量

（1）十进制数形式，例如：

3.14   314.0    0.314

（2）科学计数法形式，如：

314e2     314E2（e的大小写没有区分）   314E-2

double f = 314E2;    //314*10^2     -->31400.0

double f2 = 314E-2;   //314*10^(-2)      -->3.14



##### 浮点类型变量

float类型又被称作单精度类型，尾数可以精确到7位有效数字，在很多情况下，float类型的精度很难满足需求。

而double表示这种类型的数值精度约是float类型的两倍，又被称作为双精度类型，绝大部分应用程序都常用double类型。

float类型的数值有一个后缀F或者f，没有后缀F/f的浮点数值默认为double类型。

也可以在浮点数值后添加后缀D或者d，以明确其为double类型。

|  类型  | 占用存储空间 |                          表数范围                           |
| :----: | :----------: | :---------------------------------------------------------: |
| float  |    4字节     |       大约±3.402 823 47E+38F （有效位数为6-7位左右）        |
| double |    8字节     | 大约±1.797 693 134 862 315 70E+308（有效位数为15-16位左右） |

PS： 有效数字指的是从左开始第一个不为0的数到最后一个数

同样的int与float都是4字节的，但两者的表数范围不一样。是因为浮点型的存储更为复杂。



代码：

```java
public class TestVar06{
	public static void main(String[] args){
		//浮点类型的常量有两种形式：
		//十进制形式：
		double num1 = 3.14;
		System.out.println(num1);
		//科学计数法形式：
		double num2 = 314E-2;
		System.out.println(num2);
		
		//浮点类型的变量：
		//注意： 浮点型默认是double类型的，要想将一个double的数赋给float类型，必须后面加上F或者f
		float f1 = 3.14159263654584F;  //float f1 = 3.14159263654584; 报错
		System.out.println(f1);
		//注意：double类型后面可以加D或者d，但是一般我们都省略不写
		double d1 = 3.14159263654584D;
		System.out.println(d1);
		
		//注意：我们最好不要进行浮点类型的比较：
		float f2 = 0.3F;
		double d2 = 0.3;
		System.out.println(f2==d2);
		/*
		区别：
		= 赋值运算： 将等号右侧的值赋给等号左侧
		== 判断==左右两侧的值是否相等  ： 结果要么相等 要么不相等
		==运算符的结果就是要么是true，要么是false
		*/
	}
}
```

