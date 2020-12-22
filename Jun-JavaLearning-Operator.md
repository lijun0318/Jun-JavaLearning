##                                              运算符

#### Java中的运算符

【1】Java语言支持如下运算符：

+ 算术运算符

​        +，-，*，/，%，++（自增），--（自减）

+ 赋值运算符

​        =

+ 扩展赋值运算符

​        +=， -=， *=， /=

+ 关系运算符

 		> ，< ， >= ，<= ，== ， !=

+ 逻辑运算符

​          &&，|| , ! , &, |, ^

+ 位运算符

​          &，|，^, ~ ,>> , <<,     （了解！！！）

+ 条件运算符

​           ?   :

【2】 相关概念辨析

＋        运算符 操作符           Operator

5 + 6    表达式                       expression

5    6     操作数                       Operand

int m = 5 + 6;    语句             Sentence



### 算数运算符

####   /和%

【1】 /   除法运算符：表示两个数相除运算

​          %   取余运算符：用来求余数的

```java
public class TestOpe01{
	public static void main(String[] args){
		//打印结果：
		System.out.println(12/3);
		System.out.println(12%5);
		System.out.println(12/3.0);
		System.out.println(12%5.0);
	}
}
```

【2】练习：

```java
import java.util.Scanner;
public class TestOpe02{
	public static void main(String[] args){
		//实现功能：任意给出一个四位数，求出每位上的数字并输出
		
		//1.任意给出一个四位数：
		Scanner input = new Scanner(System.in);
		System.out.println("请录入一个四位数：");
		int num = input.nextInt();;
		
		//2.求出每位上的数字：
		//个位数：
		int num1 = num%10;
		//十位数：
		int num2 = num/10%10;//1234---》123----》3
		//百位数：
		int num3 = num/100%10;//1234---》12----》2
		//千位数：
		int num4 = num/1000;//1234----》1
		
		//3.输出每位上的数字：
		System.out.println("个位上的数为："+num1);
		System.out.println("十位上的数为："+num2);
		System.out.println("百位上的数为："+num3);
		System.out.println("千位上的数为："+num4);
	}
}
```



#### +

【1】+的作用：

（1）表示正数

（2）表示相加操作

（3）进行字符串的拼接

【2】代码练习：

```java
public class TestOpe03{
	public static void main(String[] args){
		//表示正数：
		System.out.println(+5);//5
		//相加操作：
		System.out.println(5+6);//11
		System.out.println(5+'6');//59
		//字符串的拼接：
		//规则： +左右两侧的任意一侧有字符串，那么这个加号就是字符串拼接的作用，结果一定是字符串
		int num = 56;
		System.out.println("num="+num);//"num=56" ---> num=56
		System.out.println(5+6+"7");//11+"7" ---> "117" ---> 117
		System.out.println(5+'6'+"7");//59 + "7" --->"597" ---> 597
		System.out.println("5"+6+"7");//"56"+"7" ---> "567" ---> 567
		System.out.println("5"+'6'+"7");// "56"+"7" ---> "567" ---> 567
		System.out.println("5"+'6'+'7');// "56" + '7' ---> "567" ---> 567
	}
}
```



#### ++

【1】++：

```java
public class TestOpe04{
	public static void main(String[] args){
		int a = 5;
		a++;//理解为：相当于 a=a+1 操作
		System.out.println(a);//6
		
		a = 5;
		++a;
		System.out.println(a);//6
		
		//总结：++单独使用的时候，无论放在前还是后，都是加1操作
		
		//将++参与到运算中：
		//规则：看++在前还是在后，如果++在后：先运算，后加1   如果++在前，先加1，后运算
		a =5;
		int m = a++ + 7;//先运算  m=a+7   再加1：  a = a+1
		System.out.println(m);//12
		System.out.println(a);//6
		
		a = 5;
		int n = ++a + 7;//先加1   a=a+1   再运算：  n = a+7
		System.out.println(n);//13
		System.out.println(a);//6
	}
}
```

无论这个变量是否参与到运算中去，只要用++运算符，这个变量本身就加1操作

只是说如果变量参与到运算中去的话，对运算结果是产生影响：

看++再前还是在后，如果++在后：先运算，后加1； 如果++在前，先加1，后运算



【2】练习：

代码：

```java
public class TestOpe05{
	public static void main(String[] args){
		int a = 5;
		//运算符的优先级问题： ++级别 > +
		System.out.println(a++ + a++);  
		//                  5  +   6 = 11      a = 7
		System.out.println(a++ + ++a);
		//                  7  +   9 = 16      a = 9
		System.out.println(++a + a++);
		//                  10  +  10= 20      a = 11
		System.out.println(++a + ++a);
		//                  12 +   13= 25      a = 13 
	}
}
```

运算过程：

![image-20201222181148982](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/%2B%2B%E8%BF%90%E7%AE%97%E4%BC%98%E5%85%88%E7%BA%A7?token=ANGHKQLAM5GF5KBWQPGHWB274HDLE)



