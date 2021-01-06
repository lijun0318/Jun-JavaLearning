### 数组

【1】习题引入：

```java
import java.util.Scanner;
public class TestArray01{
    public static void main(String[] args){
                //功能：键盘录入十个学生的成绩，求和，求平均数：
                //定义一个求和的变量：
                int sum = 0;
                Scanner sc = new Scanner(System.in);
                for(int i=1;i<=10;i++){//i:控制循环次数
                        System.out.print("请录入第"+i+"个学生的成绩：");
                        int score = sc.nextInt();
                        sum += score;
                }
                
                System.out.println("十个学生的成绩之和为："+sum);
                System.out.println("十个学生的成绩平均数为："+sum/10);
                
                //本题的缺点：
                //求第6个学生的成绩：？？？？？---》不能
                
        }
}
```

缺点：就是不能求每个学生的成绩具体是多少

解决：将成绩进行存储  ----》 引入 ： 数组 

感受到数组的作用：数组用来存储数据的，在程序设计中，为了处理方便，数组用来将相同类型的若干数据组织起来。
这个若干数据的集合我们称之为数组。



### 数值的学习

【1】数组的定义
数组是相同类型数据的有序集合。数组描述的是相同类型的若干个数据，按照一定的先后次序排列组合而成。其中，每一个数据称作一个元素，每个元素可以通过一个索引（下标）来访问它们。
数组的四个基本特点：
1.长度是确定的。数组一旦被创建，它的大小就是不可以改变的。
2.其元素的类型必须是相同类型，不允许出现混合类型。
3.数组类型可以是任何数据类型，包括基本类型和引用类型。
4.数组有索引的：索引从0开始，到 数组.length-1 结束 
5.数组变量属于引用类型，数组也是对象。
PS:数组变量属于引用类型，数组也是对象，数组中的每个元素相当于该对象的成员变量。数组本身就是对象，Java中对象是在堆中的，因此数组无论保存原始类型还是其他对象类型，数组对象本身是在堆中存储的。

【2】数组的学习：

```java
public class TestArray02{
    public static void main(String[] args){
                //数组的作用：用来存储相同类型的数据
                //以int类型数据为案例：数组用来存储int类型数据
                //1.声明(定义数组)
                int[] arr; //定义一个int类型的数组，名字叫arr
                //int arr2[];
                //如果数组只声明，没有后续操作，那么这个数组相当于没定义
                //int[] arr3 = null;//空 辨别：数组赋值为null和什么都没有赋值  不一样的效果 
                
                //2.创建
                arr = new int[4];//给数组开辟了一个长度为4的空间
                //编译期声明和创建会被合为一句话: int[] arr = new int[4];
                
                //3.赋值
                arr[0] = 12;
                arr[3] = 47;
                arr[2] = 98;
                arr[1] = 56;
                arr[2] = 66;
                /*
                arr[4] = 93;
                出现异常：Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 4
                Array 数组
                Index 索引
                OutOf 超出
                Bounds 界限
                Exception 异常
                ---》数组索引越界异常  
                */
        
                //4.使用
                System.out.println(arr[2]);
                System.out.println(arr[0]+100);
                //通过数组一个属性来获取  length 长度
                System.out.println("数组的长度是："+arr.length);
        }
}
```



#### 完善引入的习题_数组的遍历

【1】代码：

```java
import java.util.Scanner;
public class TestArray03{
    public static void main(String[] args){
                //功能：键盘录入十个学生的成绩，求和，求平均数：
                //定义一个int类型的数组，长度为10 ：
                int[] scores = new int[10];
                //定义一个求和的变量：
                int sum = 0;
                Scanner sc = new Scanner(System.in);
                for(int i=1;i<=10;i++){//i:控制循环次数
                        System.out.print("请录入第"+i+"个学生的成绩：");
                        int score = sc.nextInt();
                        scores[i-1] = score;
                        sum += score;
                }
                
                System.out.println("十个学生的成绩之和为："+sum);
                System.out.println("十个学生的成绩平均数为："+sum/10);
                
                 
                //求第6个学生的成绩： 
                //System.out.println(scores[5]);
                /*
                System.out.println(scores[0]);
                System.out.println(scores[1]);
                System.out.println(scores[2]);
                System.out.println(scores[3]);
                //....
                System.out.println(scores[9]);
                */
                //将数组中的每个元素进行查看--》数组的遍历：
                //方式1：普通for循环---》正向遍历：
                for(int i=0;i<=9;i++){
                        System.out.println("第"+(i+1)+"个学生的成绩为："+scores[i]);
                }
                
                //方式2：增强for循环:
                //对scores数组进行遍历，遍历出来每个元素都用int类型的num接收：
                int count = 0;
                for(int num:scores){
                        count++;
                        //每次都将num在控制台输出
                        System.out.println("第"+count+"个学生的成绩为："+num);
                }
                
                /*
                增强for循环：
                优点：代码简单
                缺点：单纯的增强for循环不能涉及跟索引相关的操作
                */
                
                //方式3：利用普通for循环： 逆向遍历：
                for(int i=9;i>=0;i--){
                        System.out.println("第"+(i+1)+"个学生的成绩为："+scores[i]);
                }
                
        }
}
```



【2】用IDEA验证数组的确将数据进行存储了：

![image.png](https://ae04.alicdn.com/kf/He87c03c188104e09b0e85ed078b073d2p.png)



#### 数组的三种初始化方式

数组的初始化方式总共有三种：静态初始化、动态初始化、默认初始化。

静态初始化
除了用new关键字来产生数组以外，还可以直接在定义数组的同时就为数组元素分配空间并赋值。

eg:
int[] arr = {12,23,45};
int[] arr = new int[]{12,23,45};
注意：
1.new int[3]{12,23,45};-->错误
2.int[] arr ;
   arr = {12,23,45};  --->错误

动态初始化
数组定义与为数组元素分配空间并赋值的操作分开进行。

eg:
int[] arr ;
arr = new int[3]
arr[0] = 12;
arr[1] = 23;
arr[2] = 45;
默认初始化
数组是引用类型，它的元素相当于类的实例变量，因此数组一经分配空间，其中的每个元素也被按照实例变量同样的方式被隐式初始化。

int[] arr = new int[3];   ---> 数组有默认的初始化值

![image.png](https://ae02.alicdn.com/kf/H3de499f3ca4840fd95e6cf9c8c0c4b39D.png)