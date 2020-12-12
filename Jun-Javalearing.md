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

![image-20201212103020630](https://i.loli.net/2020/12/12/I4fNehxj1tUBA5V.png)

（2）变量如果没有进行赋值的话，那么使用的时候会出错，告诉你：尚未初始化变量：

![image-20201212103141024](https://i.loli.net/2020/12/12/LKx29vGOogWzje7.png)

【3】变量的赋值

![image-20201211235855341](https://i.loli.net/2020/12/12/wIH3JAL7PxedSFu.png)

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

![image-20201212105419711](https://i.loli.net/2020/12/12/B5xVmhyzCvsw8Ya.png)

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

![image-20201212104926803](https://i.loli.net/2020/12/12/HxO1VsQD9KGvf8d.png)

![image-20201212104523435](https://i.loli.net/2020/12/12/VU14JiKGjlmqIXw.png)

【5】变量的内存

![image-20201212105626100](https://i.loli.net/2020/12/12/kjq6LclozJrXW5g.png)

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

![image-20201212110423993](https://i.loli.net/2020/12/12/UlokMP2gnapcxjf.png)

结果：

![image-20201212110618585](https://i.loli.net/2020/12/12/te2K1x5wO4QIbkA.png)



