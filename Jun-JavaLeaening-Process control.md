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

