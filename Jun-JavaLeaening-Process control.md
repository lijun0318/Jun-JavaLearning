##                                                流程控制

#### 引入

【1】流程控制的作用：
流程控制语句是用来控制程序中各语句执行顺序的语句，可以把语句组合成能完成一定功能的小逻辑模块。
【2】控制语句的分类：
控制语句分为三类：顺序、选择和循环。
“顺序结构”代表“先执行a，再执行b”的逻辑。
“条件判断结构”代表“如果…，则…”的逻辑。
“循环结构”代表“如果…，则再继续…”的逻辑。
  三种流程控制语句就能表示所有的事情！不信，你可以试试拆分你遇到的各种事情。这三种基本逻辑结构是相互支撑的，它们共同构成了算法的基本结构，无论怎样复杂的逻辑结构，都可以通过它们来表达。所以任何一种高级语言都具备上述两种结构。
本章是大家真正进入编程界的“门票”。  
【3】流程控制的流程：

![image-20201224210228047](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/流程控制的流程?token=ANGHKQNBMTFH6EUHCQKR46C74SI2Y)



### 分支结构

#### if

##### 单分支

【1】语法结构:
if(布尔表达式){
    语句块
}
if语句对布尔表达式进行一次判定，若判定为真，则执行{}中的语句块，否则跳过该语句块。流程图如图所示：

![image-20201224214324893](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/%E5%8D%95%E5%88%86%E6%94%AF?token=ANGHKQPG24BV32ZBD5FRCIK74SNU4)

【2】代码：

```java
public class TestIf01{
        public static void main(String[] args){
                //实现一个功能：给出三个数（1-6），对三个数求和计算，根据和的大小来分配不同的奖品
                //1.给出三个数：
                int num1 = 6;
                int num2 = 2;
                int num3 = 3;
                //2.求和
                int sum = 0;
                sum += num1;
                sum += num2;
                sum += num3;
                System.out.println("和为："+sum);
                
                //3.根据和判断奖品：
                //如果和大于等于14，那么就是一等奖
                if(sum>=14){
                        System.out.println("一等奖");
                        System.out.println("恭喜你很幸运，中了一等奖");
                }
                
                if(sum>=10&&sum<14){
                        System.out.println("二等奖");
                }
                
                if(sum>=6&&sum<10){
                        System.out.println("三等奖");
                }
                
                if(sum<6){
                        System.out.println("四等奖");
                }
                
                /*
                if-单分支：
                （1）结构：
                        if(条件表达式，这个表达式的结果是布尔值：要么是false，要么是true){
                                //如果上面()中的表达式返回结果是true，那么执行{}中代码
                                //如果上面()中的表达式返回结果是false ，那么不执行{}中代码
                                //PS:{}中的代码是否执行，取决于()中表达式的返回结果
                        }
                （2）上面的代码中，我用四个单分支拼凑出四个选择，每个选择是独立的，依次判断执行的
                （3）if后面的()中的条件，要按照自己需求尽量完善
                （4）{}可以省略不写,但是一旦省略，这个if就只负责后面的一句话，所以我们不建议初学者省略
                */
        }
}
```



##### 多分支

【1】语法结构：
if(布尔表达式1) {
        语句块1;
} else if(布尔表达式2) {
        语句块2;
}……
else if(布尔表达式n){
        语句块n;
} else {
        语句块n+1;
}
当布尔表达式1为真时，执行语句块1；否则，判断布尔表达式2，当布尔表达式2为真时，执行语句块2；否则，继续判断布尔表达式3······；如果1~n个布尔表达式均判定为假时，则执行语句块n+1，也就是else部分。流程图如图所示：

![image-20201224214800376](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/%E6%95%B0%E8%BD%B4%E5%88%86%E6%9E%90%E5%A4%9A%E5%88%86%E6%94%AF?token=ANGHKQKNJSAHA7UAZPNDIUC74SOIW)

【2】
数轴分析：

![image-20201224214832939](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/%E6%95%B0%E8%BD%B4%E5%88%86%E6%9E%90%E5%A4%9A%E5%88%86%E6%94%AF?token=ANGHKQKNJSAHA7UAZPNDIUC74SOIW)

【3】代码：

```java
public class TestIf02{
        public static void main(String[] args){
                //实现一个功能：给出三个数（1-6），对三个数求和计算，根据和的大小来分配不同的奖品
                //1.给出三个数：
                int num1 = 6;
                int num2 = 4;
                int num3 = 2;
                //2.求和
                int sum = 0;
                sum += num1;
                sum += num2;
                sum += num3;
                System.out.println("和为："+sum);
                
                //3.根据和判断奖品：
                /*
                利用一个多分支
                【1】结构：
                if(){
                        
                }else if(){
                        
                }else if(){
                        
                }...
                else{
                        
                }
                【2】else:隐藏了一个条件，跟上面分支条件表达式相反的功能 (详见数轴分析)
                【3】多分支：好处：只要满足一个 分支以后，后面的分支就不需要判断了 --》效率高
                【4】我们写代码的时候，尽量保证else的存在--》else分支相当于“兜底”“备胎”的作用，别的分支都不走，就会走这个分支了
                */
                if(sum>=14){
                        System.out.println("一等奖");
                }else if(sum>=10){//隐藏了sum<14
                        System.out.println("二等奖");
                }else if(sum>=6){//隐藏了sum<10
                        System.out.println("三等奖");
                }else{//隐藏了sum<6
                        System.out.println("四等奖");
                }
                
                
                
        }
}
```



##### 双分支

【1】语法结构:
if(布尔表达式){
语句块1
}else{
      语句块2
}
当布尔表达式为真时，执行语句块1，否则，执行语句块2。也就是else部分。流程图如图所示：

![image-20201225201614188](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/%E5%8F%8C%E5%88%86%E6%94%AF?token=ANGHKQLHN4U6K6DT457UBLS74XMGE)



##### 随机数

随机数：这个数在生成之前我们不确定这个数是多少，不可知

在Java中依靠一个类：Math类帮助我们生成，这个类中有一个方法专门用来生成随机数：

![image-20201225210120946](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/random()?token=ANGHKQPAUH6LEMLOZLVIPM274XRO2)

Math.random() -------> [0.0,1.0)
Math.random()*6 ----->[0.0,6.0)
(int)(Math.random()*6)  ----->[0,5]
(int)(Math.random()*6) +1 ----->[1,6]

应用到程序中：

```java
int num1 = (int)(Math.random()*6) +1;
int num2 = (int)(Math.random()*6) +1;
int num3 = (int)(Math.random()*6) +1;
```



#### 分支的嵌套使用

##### 分支结构练习1

练习：
会员购物时，不同积分享受的折扣不同，规则如下：

| 会员积分X    | 折扣 |
| ------------ | ---- |
| x>=8000      | 6折  |
| 4000<=x<8000 | 7折  |
| 2000<=x<4000 | 8折  |
| x<2000       | 9折  |

计算会员购物时获得的折扣，效果如下：

![image-20201225214909824](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/%E5%88%86%E6%94%AF%E5%B5%8C%E5%A5%97%E7%B1%BB%E5%9E%8B1?token=ANGHKQOM2JV3H5KMFPIAQ4C74XXCE)

本题主要考的是 程序的优化：

```java
import java.util.Scanner;
public class TestIf04{
    public static void main(String[] args){
			//1.给出积分：
		Scanner sc = new Scanner(System.in);
		System.out.println("请录入你的积分：");
		
			//2.根据积分判断折扣：
		//判断是否为int类型：
		if(sc.hasNextInt()==true){
			int num = sc.nextInt();
			//判断这个数是否为正数
			if(num>=0){
				String discount = "";
				if(num>=8000){
					discount = "0.6";
				}else if(num>=4000){
					discount = "0.7";
				}else if(num>=2000){
					discount = "0.8";
				}else{
					discount = "0.9";
				}
				System.out.println("你的折扣是："+discount);
			}else{
			System.out.println("你输入不是正数！");
			}
	
		}else{
			System.out.println("你输入的不是整型！");
		}
	}
}
```



##### 分支结构练习2

练习：
小朋友搬桌子：
年龄大于7岁，可以搬桌子；
如果年龄大于5岁，性别是男，可以搬桌子；
否则不可以搬动桌子，提示：你还太小了

本题主要考的是：逻辑

方式1：性别用0或者1接收：

```java
import java.util.Scanner;
public class TestIf05{
        public static void main(String[] args){
                //1.录入小朋友的年龄：
                Scanner sc = new Scanner(System.in);
                System.out.println("请录入小朋友的年龄：");
                int age = sc.nextInt();
                
                //2.根据年龄判断：
                if(age>=7){
                        System.out.println("yes");
                }else if(age>=5){
                        //录入小朋友的性别；
                        System.out.println("请录入小朋友的性别：男：1  女 ：0");
                        int sex = sc.nextInt();
                        if(sex==1){//男生
                                System.out.println("yes");
                        }else{//女孩
                                System.out.println("no");
                        }
                }else{//age<5
                        System.out.println("no");
                }
        }
}
```

方式2：性别用男或者女接收：

```java
import java.util.Scanner;
public class TestIf06{
        public static void main(String[] args){
                //1.录入小朋友的年龄：
                Scanner sc = new Scanner(System.in);
                System.out.println("请录入小朋友的年龄：");
                int age = sc.nextInt();
                
                //2.根据年龄判断：
                if(age>=7){
                        System.out.println("yes");
                }else if(age>=5){
                        //录入小朋友的性别；
                        System.out.println("请录入小朋友的性别：");
                        String str = sc.next();
                        char sex = str.charAt(0);
                        if(sex=='男'){
                                System.out.println("yes");
                        }else{
                                System.out.println("no");
                        }
                }else{//age<5
                        System.out.println("no");
                }
        }
}
```



#### switch

【1】switch多分支结构(多值情况)
语法结构：
switch (表达式) {
    case 值1:
         语句序列1;
         [break];
    case 值2:
         语句序列2;
         [break];
        … … …      … …
    [default:默认语句;]
}

switch语句会根据表达式的值从相匹配的case标签处开始执行，一直执行到break语句处或者是switch语句的末尾。如果表达式的值与任一case值不匹配，则进入default语句（如果存在default语句的情况）。根据表达式值的不同可以执行许多不同的操作。switch语句中case标签在JDK1.5之前必须是整数（long类型除外）或者枚举，不能是字符串，在JDK1.7之后允许使用字符串(String)。大家要注意，当布尔表达式是等值判断的情况，可以使用if-else if-else多分支结构或者switch结构，如果布尔表达式区间判断的情况，则只能使用if-else if-else多分支结构。switch多分支结构的流程图如图所示：

![image-20201226105151116](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/switch%E5%A4%9A%E5%88%86%E6%94%AF%E6%B5%81%E7%A8%8B%E5%9B%BE?token=ANGHKQOPAT723ELXG4V6U7C742S22)

【2】练习

```java
public class TestSwitch{
        public static void main(String[] args){
                /*
                实现一个功能：
                根据给出的学生分数，判断学生的等级：
                >=90  -----A
                >=80  -----B
                >=70  -----C
                >=60  -----D
                <60   -----E
                
                用if分支：
                if(score>=90){
                        
                }else if(score>=80){
                        
                }
                */
                //1.给出学生的成绩：
                int score = 167;
                //2.根据成绩判断学生的等级：
                switch(score/10){
                        case 10 : 
                        case 9 : System.out.println("A级");break;
                        case 8 : System.out.println("B级");break;
                        case 7 : System.out.println("C级");break;
                        case 6 : System.out.println("D级");break;
                        default:System.out.println("成绩错误");break;
                        case 5 :  
                        case 4 :  
                        case 3 :  
                        case 2 :  
                        case 1 :  
                        case 0 : System.out.println("E级");break;
                        
                }
                /*
                【1】语法结构：
                switch(){
                        case * :
                        case * :
                        .......
                }
                【2】switch后面是一个()，()中表达式返回的结果是一个等值，这个等值的类型可以为：
                int,byte,short,char,String,枚举类型
                【3】这个()中的等值会依次跟case后面的值进行比较，如果匹配成功，就执行:后面的代码
                【4】为了防止代码的“穿透”效果：在每个分支后面加上一个关键词break，遇到break这个分支就结束了
                【5】类似else的“兜底”“备胎”的分支：default分支
                【6】default分支可以写在任意的位置上，但是如果没有在最后一行，后面必须加上break关键字，
                如果在最后一行的话，break可以省略
                【7】相邻分支逻辑是一样的，那么就可以只保留最后一个分支，上面的都可以省去不写了
                【8】switch分支和if分支区别：
                表达式是等值判断的话--》if ，switch都可以
                如果表达式是区间判断的情况---》if最好
                【9】switch应用场合：就是等值判断，等值的情况比较少的情况下
                */
        }
}
```



### 循环结构

#### while

【1】语法结构：
while (布尔表达式) {
            循环体;
}
在循环刚开始时，会计算一次“布尔表达式”的值，若条件为真，执行循环体。而对于后来每一次额外的循环，都会在开始前重新计算一次。
语句中应有使循环趋向于结束的语句，否则会出现无限循环–––"死"循环。
while循环结构流程图如图所示:

![image-20201226160520802](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/while%E5%BE%AA%E7%8E%AF%E7%BB%93%E6%9E%84%E6%B5%81%E7%A8%8B%E5%9B%BE?token=ANGHKQIHZOPUV2DRTLEPDGS743XQ4)

【2】练习：1+2+3+4+5

```java
public class TestWhile{
        public static void main(String[] args){
                //功能：1+2+3+4+5
                //1.定义变量：
                int num1 = 1;
                int num2 = 2;
                int num3 = 3;
                int num4 = 4;
                int num5 = 5;
                //2.定义一个求和变量，用来接收和：
                int sum = 0;
                sum += num1;
                sum += num2;
                sum += num3;
                sum += num4;
                sum += num5;
                
                //3.输出和
                System.out.println(sum);
        }
}
```

上述代码缺点：变量的定义个数太多了
解决：

```java
public class TestWhile{
        public static void main(String[] args){
                //功能：1+2+3+4+5
                //1.定义变量：
                int num = 1;
                //2.定义一个求和变量，用来接收和：
                int sum = 0;
                sum += num;
                num++;
                sum += num;
                num++;
                sum += num;
                num++;
                sum += num;
                num++;
                sum += num;
                num++;
                
                //3.输出和
                System.out.println(sum);
        }
}
```

上述代码缺点：重复写的代码太多了
解决：---》引入Java中循环结构：

```java
public class TestWhile{
        public static void main(String[] args){
                //功能：1+2+3+4+5
                //1.定义变量：
                int num = 1;[1]条件初始化
                //2.定义一个求和变量，用来接收和：
                int sum = 0;              
                while(num<=5){[2]条件判断
                        sum += num;[3]循环体
                        num++;[4]迭代
                }      
                //3.输出和
                System.out.println(sum);
        }
}
```

总结：
【1】循环作用：将部分代码重复执行。
                                循环只是提高了程序员编写代码的效率，但是底层执行的时候依然是重复执行。
【2】循环四要素：

![image-20201226160730243](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/%E5%BE%AA%E7%8E%AF%E5%9B%9B%E8%A6%81%E7%B4%A0?token=ANGHKQIWWVOKQ76WN3BZ4NC743XZI)

【1】条件初始化

【2】条件判断

【3】循环体

【4】迭代

初始化谁，就判断谁，判断谁，就迭代谁
执行过程：[1][2][3][4] [2][3][4] [2][3][4]。。。。

【3】循环的执行过程：

![image-20201226161016145](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/%E5%BE%AA%E7%8E%AF%E7%9A%84%E6%89%A7%E8%A1%8C%E8%BF%87%E7%A8%8B?token=ANGHKQLRIDJBOBF5PINIRAS743YDE)

【4】验证循环的执行过程：

![image-20201226161103753](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/%E9%AA%8C%E8%AF%81%E5%BE%AA%E7%8E%AF%E7%9A%84%E6%89%A7%E8%A1%8C%E8%BF%87%E7%A8%8B?token=ANGHKQJ3EI4PRJF4MU3LDUC743YGI)



#### do while

【1】语法结构：
do {
            循环体;
    } while(布尔表达式) ;
do-while循环结构会先执行循环体，然后再判断布尔表达式的值，若条件为真，执行循环体，当条件为假时结束循环。do-while循环的循环体至少执行一次。do-while循环结构流程图如图所示：

![image-20201229144714342](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/do-while%20%E5%BE%AA%E7%8E%AF%E7%BB%93%E6%9E%84?token=ANGHKQPN3GXW6HJMGDW5JOC75LIUU)

【2】代码：

```java
public class TestDoWhile{
        public static void main(String[] args){
                //1+2+3+4+...100
                //while方式:
                /*
                int i = 101;
                int sum = 0;
                while(i<=100){
                        sum += i;
                        i++;
                }
                System.out.println(i);//101
                System.out.println(sum);//0
                */
                //do-while方式：
                
                int i = 101;
                int sum = 0;
                do{
                        sum += i;
                        i++;
                }while(i<=100);//一定要注意写这个分号，否则编译出错
                System.out.println(i);//102
                System.out.println(sum);//101
                /*
                【1】while和do-while的区别:
                        while:先判断，再执行
                        do-while:先执行，再判断---》至少被执行一次，从第二次开始才进行判断
                【2】什么场合使用do-while:
                
                while(考试是否通过){
                        考试；
                }
                ---》不合适
                do{
                        考试；
                }while(考试是否通过);
                ---》合适
                */
                
        }
}
```



#### for

【1】语法结构：
for (初始表达式; 布尔表达式; 迭代因子) {
          循环体;
}
for循环语句是支持迭代的一种通用结构，是最有效、最灵活的循环结构。for循环在第一次反复之前要进行初始化，即执行初始表达式；随后，对布尔表达式进行判定，若判定结果为true，则执行循环体，否则，终止循环；最后在每一次反复的时候，进行某种形式的“步进”，即执行迭代因子。
初始化部分设置循环变量的初值
条件判断部分为任意布尔表达式
迭代因子控制循环变量的增减
for循环在执行条件判定后，先执行的循环体部分，再执行步进。
for循环结构的流程图如图所示：

![image-20201231000431123](https://raw.githubusercontent.com/lijun0318/PicGo/master/img/for%E7%9A%84%E5%BE%AA%E7%8E%AF%E7%BB%93%E6%9E%84?token=ANGHKQKHFAMMQKZ7IFSMVAC75SSWC)



【2】代码：

```java
public class TestFor01{
        public static void main(String[] args){
                //1+2+3+..+100
                //while:
                /*int i = 1;
                int sum = 0;
                while(i<=100){
                        sum += i;
                        i++;
                }
                System.out.println(sum);
                */
                
                //for:
                int sum = 0;
                int i;
                for(i = 1;i<=100;i++){
                        sum += i;
                }
                System.out.println(sum);
                System.out.println(i);
                
                /*
                【1】for的结构：
                for(条件初始化;条件判断;迭代){
                        循环体；
                }
                
                【2】i的作用域：作用范围：离变量最近{}  --->可以自己去控制
                【3】for循环格式特别灵活：格式虽然很灵活，但是我们自己写代码的时候不建议灵活着写。
                for(;;){}  -->死循环
                
                int i = 1;
                for(;i<=100;){
                        sum += i;
                        i++;
                }
                
                【4】死循环：
                for(;;){}
                
                while(true){}
                
                do{
                        
                }while(true);
                
                【5】循环分为两大类：
                第一类：当型   while(){}   for(;;){}
                第二类：直到型  do{}while();
                
                【6】以后常用：for循环 
                【7】do-while,while,for循环谁的效率高？  一样高 
                */
        }
}
```

