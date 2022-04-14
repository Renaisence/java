#   1. windows中的CMD常用命令

D:                 切换D盘

dir				查看目录（ls）

cls				clean screen

exit				

JShell			JAVA的轻量级使用脚本（Japyter）

# 2. JDK_JRE_JVM

## 2.1 JAVA虚拟机--JVM (Java Virtual Machine)

编写的JAVA代码，都运行在JVM上。



## 2.2 JRE  (Java Runtime Environment)

Java程序运行环境，包含JVM和运行时需要的核心库。



## 2.3 JDK (Java Development Kit)

Java程序开发工具包，包含JRE和开发人员使用的工具。



# 3. HelloWorld

## 3.1 编写

```java
/*
第一行的第三个单词必须与文件名完全一样
public class后面代表定义一个类的名称，类是Java中所有源代码的基本组织单位
*/
public class HelloWorld {
    //第二行的内容是万年固定写法，代表main方法
    //代表程序执行的起点
    public static void main(String[] args){
        //第三行代表打印输出语句格式
        System.out.println("Hello, World!"); //println自带换行
    }		
}
```



## 3.2 编译

使用Javac.exe

在CMD中执行命令 

```
DIR: javac HelloWorld.java
```

生成 HelloWorld.class 文件



## 3.3 运行

使用java.exe

在CMD中执行命令

```
DIR: java HelloWorld
```

**PS.**代码更改后需要重新编译再运行。



# 4. 关键字_标识符

**Example：**

@是电子邮箱当中有特殊含义的、被保留的、不能随意使用的字符。



## 4.1 JAVA关键字

1.完全小写的字母。

2.IDE中带颜色的。



## 4.2 标识符

在程序中，我们自定义的内容。如：类的名字、方法的名字、变量的名字等等，都是标识符。

### 4.2.1 标识符命名要求：

1.标识符可以包含**英文大小写**、**0-9数字**、**$** 和 **_** 

2.标识符不能以**数字**开头。

3.标识符不能是**关键字**。

### 4.2.2 标识符命名规范：

类名：首字母大写，后面每个单词首字母大写。

变量：首字母小写，后面每个单词首字母大写。

方法：同变量名。



# 5. 常量_变量

## 5.1 常量

1.字符串常量：**双引号**引起来的部分。如："ABC"、"123"

2.字符常量：**单引号**引起来的**单个**字符，且必须要有。如：'A'、'4'、'中'、' '

3.浮点数常量：直接写上数字，有小数点。如：2.2、-3.14、0.0

4.整数常量：直接写上的数字，没有小数点。如：123、0、-200

5.布尔常量：只有两种取值。TURE、FALSE

6.空常量：null   //代表没有任何数据，不能直接用`System.out.println(null)`显示。



## 5.2 数据类型

### 5.2.1 基本数据类型

**整数型：**

`byte（1个字节）	short（2）	int（4）默认	long（8）`  

**浮点型：**

`float（4）	double（8）默认`

**ps.**long数字后要加L**（`long i = 9000000000L;`）**，

float数字后要加F**（`float i = 3.14F`）**,

注意取值范围。

**字符型：**

`char（2）`

**布尔型：**

`boolean（1）`



### 5.2.2 引用数据类型

字符串(String)、数组( [] )、类、接口、Lambda



## 5.3 变量（Variable）

程序运行期间，内容可以发生改变的量。

**例：**`int 标识符;`

### 5.3.1 变量使用注意事项

1.没有进行赋值的变量，不能直接使用；一定要赋值之后，才能使用。

2.变量使用不能超过作用域（大括号{}）的范围。

3.如果使用byte或者short类型的变量，那么右侧的数据值不能超过左侧类型的范围。

4.可以通过一个语句创建多个变量。（不推荐这么写）

5.多个变量之间名称不可以重复。

6.对于float和long类型，要加F和L。



## 5.4 自动类型转换（隐式）

**例：**`long num1 = 100;`

​		`double num2 = 2.5F;`

​		`float num3 = 30L;`

1.特点：代码不需要进行特殊处理，自动完成。

2.规则：数据范围从小到大。( int -> long; float -> double; long -> float;)



## 5.5 强制类型转换

1.特点：代码需要进行特殊的格式处理，不能自动完成。

2.格式：范围小的类型，范围小的变量名 = (范围小的类型) 原本范围大的数据；

**例：** `int num = (int) 100L;`

**ps.**如果转换后的类型装不下该数据，会发生精度损失、数据溢出。

3.byte/short/char 这三种类型都可以发生数学运算,在运算的时候，会被提升为int类型，然后计算。

**例：**

```java
char I = 'A';

System.our.println(i + 1);		//66
```

```java
byte num1 = 40;

byte num2 = 50;

int result1 = num1 + num2;		//应该用int类型接收  

System.out.println(result1);	//90 (int)
```

4.boolean类型不能发生任何数据类型转换。

<u><!--2021年10月30日22:06:07--></u>



# 6. ASCII编码表

**em.**		`char zifu = 'A'` 对应的数字是65

**查看方法：**

```JAVA
public class DemoTypeChar{
    public static void main(String[] args){
        char zifu1 = '1';
        System.out.println(zifu1 + 0);   //49  自动类型转换
        /*
        48 - '0'
        65 - 'A'
        97 - 'a'
        */
        
        int num = zifu1;	 // char -> int  从小到大
        
        char zifu2 = '中'
            System.out.println(zifu2 + 0)  //20013
    }
}
```

**ASCII码表：**American Standard Code for Information Interchange， 美国信息交换标准代码。

**Unicode码表：**万国码，开头0-127和ASCII完全一样，从128开始包含更多，包含emoji。



# 7. 算数运算符

## 7.1 四则与取模运算_加法的多种用法

**四则：**+ - * /

`System.out.println(20 + 50);   //先运算，再打印输出`

**取模：**%     //取余数

**ps.**只有对于整数的除法，取模才有意义。

**注意事项：**

1.一旦运算当中有不同类型的数据，那么结果将会是数据类型范围大的那种。



**加号的常见三种用法：**

1.对于数值来说，那就是加法。

2.对于字符char类型来说，在计算之前，char会被提升成为int，然后计算。

对照关系表：ASCII、Unicode

3.对于字符串String（首字母大写，并不是关键字）来说，加号代表字符串连接操作。

任何数据类型和字符串进行连接时，结果都会变成字符串。

**em.**	`System.out.println("Hello" + "World")`

**ps.优先级问题：**

`char str = Java`

`System.out.println(str + 20 + 30);  //Java2030`

*String + int + int  =*  

*String		  + int  =*

*String* 

`System.out.println(str + (20 + 30));  //Java50`

<!--2021年11月8日13:26:02-->



## 7.2 自增自减运算符

**自增：**++、num++、++num

**自减：**--、  num--、  --num

**ps.** 只有**变量**可以使用自增自减运算符，**常量**不可使用。



**使用方式：**

1.单独使用：不和其他任何操作混合，自己独立成为一个步骤。

2.混合使用：和其他操作回合，例如与赋值混合，或者与打印操作混合，等。

**使用区别：**

1.在单独使用的时候，先++和后++没有任何区别。

**em.** 	`int num = 9;`

​			`num++;		//单独使用`		

​			`System.out.println(num);  //10`

2.在混合的时候，有重大区别：

​	A.如果是 ++num ，那么变量num先+1，然后拿着结果进行使用。  		**先加后用**

​	B.如果是 num++，那么首先使用变量num本来的数值，然后再让变量+1。**先用后加**

**em.**		 `int num1 = 10;`

​				`int num2 = 10;`

​				`System.out.println(++num1);   //21`

​				`System.out.println(num2++);	 //20`

​				`System.out.println(num2);   //21`



## 7.3 赋值运算符

**等于号： **=

**加等于： **+=

**减等于：** -+

**乘等于：** *=

**除等于：** /=

**取模等：** %=

**em.**  a += 3 相当于 a = a + 3

**ps.** 常量不能进行赋值，不能写在赋值运算符左边，此乃错误写法！

<!--2021年11月9日13:22:37-->



## 7.4 比较运算符

**等于：==**

**小于：<**

**大于：>**

**小于等于：<=**

**大于等于：>=**

**不等于：!=**

满足比较条件则返回True，否则返回False。

不可以连写，比如 println(1 <  x < 3)，会报错。



## 7.5 逻辑运算符

**与（并且、and）：&&**

**或（或者、or）：||**

**非（取反、not）：！**

逻辑运算符是用来连接多个boolean值的，且只能用于boolean值。

**em.**   `1 < x < 3  -->  1 < x && x < 3`

**ps.**  &&和||，具有短路效果：如果根据左边已经可以判断得到最终结果，那么右边的代码将不再执行，从而节省一定的性能。

**em.**  `System.out.println(3 < 4 || ++b)   //变量b不会自增`



## 7.6 三元运算符

**一元运算符：**只需要一个数据就可以进行操作的运算符。例如：取反！、自增++、自减--

**二元运算符：**需要两个数据才可以进行操作的运算符。例如：加法+、赋值=

**三元运算符：**需要三个数据才可以进行操作的运算符。



**格式：**

数据类型 变量名称 = 条件判断 ？ 表达式A ：表达式B;



**流程：**

首先判断条件是否成立：

​		如果成立为true，那么将表达式A的值赋值给左侧的变量;

​		如果不成立为false，那么将表达式B的值赋值给左侧变量;

二者选其一。

**em.**

```java
public class Demo10Operator{
    public static main(String[] args){
        int a = 10;
        int b = 20;
        int max = a > b ? a : b;   
        System.out.println("最大值：" + max);	//20
    }
}
```

**注意事项：**

1.必须同时保证表达式A和表达式B都符合左侧数据类型的要求。

2.三元运算符的结果必须被使用，即要么赋值，要么打印，不能空写。

<!--2021年11月10日13:26:48-->



# 7.5 jshell_javac编译器优化

## 1.jshell

**JDK9**之后才加入的工具

**CMD**中的**Java**脚本命令

**退出命令：**/exit



## 2.两个优化

1.编译器常量优化：常量与常量相加会直接在编译步骤完成输出。——> byte a = 8 + 8;

2.编译器自动强制转换：如果右侧赋值的数值没有超过范围，那么javac编译器自动补上（byte）、（char）、（short）等强制转换符号。



# 8. 流程控制

## 8.1 顺序结构

*开始 --> 步骤A --> 步骤B --> 步骤C --> 结束*



## 8.2 选择结构

### 8.2.1 if语句

```java
if(关系表达式){
    语句体;
}
```

关系表达式要保证的到一个boolean值。



### 8.2.2 if-else语句

**标准if-else语句：**

```java
if(关系表达式){
    语句体1;
}else{
    语句体2;
}
```

**扩展if-else语句：**

```java
if(判断条件1){
    执行语句1;
}else if(判断条件2){
    执行语句2;
...
}else if(判断条件n){
    执行语句n;
}else{
    执行语句n+1;
}
```

**if-else语句可以替代三元运算符。** -->  int max = a > b ? a : b 

### 8.2.3 switch语句

```java
switch(表达式){	
    case 常量值1:
        语句体1;
        break;
    case 常量值2:	  //case条件不能重复
        语句体2;		
        break;
    ...
    default:
        语句体n;
        break;		//可以省略，但没必要。
}
```

default兜底，相当于else。

**注：switch**后面小括号只能是一下数据类型：

1. 基本数据类型：byte/short/char/int

2. 引用数据类型：String字符串、enum枚举。

   如果没有**break**，程序会继续执行下一个case。

**ps. **与C语言的switch语句相同。



## 8.3 循环结构

### 8.3.1 for循环

```java
for(初始表达式①; 布尔表达式②； 步进表达式④;){
    循环体③;
}
```

①②③④**-->**②③④**-->**②③④...②不满足(false)为止。

①负责完成循环变量初始化；

②负责判断是否满足循环条件，不满足则跳出循环；

③具体执行语句；

④循环后，循环条件所涉及变量的变化情况。



### 8.3.2 while循环

```java
while(bool条件判断){	//先判断
    循环体;
}
```

### 8.3.3 do-while循环

```java
do{
    循环体;
}while(bool条件判断);   //后判断
```

**注：** 三种循环的区别：

1. 如果条件判断从来没有满足过，那么**for循环和while循环**将会执行**0次**，而**do-while循环**会执行**至少1次**。

2. for循环的变量在小括号当中定义，只有循环内部才可以使用；而while循环和do-while循环初始化语句本来就在外面，所以出来循环之后还可以继续使用。

   **em.**

   ```java
   for(int i=0; i==0; i++){ //变量i在for循环中定义
       return 0;
   }
   System.out.println(i);  //变量i报错
   ```

### 8.3.4 break_continue语句

**break;** -----------跳出

**continue;**-------跳出当次循环，进入下次循环。



# 9.方法

## 9.1 方法的定义

**定义一个方法的格式：**

```java
public static 返回值类型 方法名称(参数类型 参数名称, ...){
    方法体;
    return 返回值;
}
```

1.方法名称的命名规则和变量一样，使用小驼峰。（第一个单词首字母小写）

2.方法体：也就是大括号当中可以包含任意条语句。



**注意事项：**

1.方法定义的先后顺序无所谓。

2.方法的定义不能产生嵌套包含关系。

3.方法定义号了之后，不会执行的。如果要想执行，一定要进行方法的**调用**。



## 9.2 方法的调用

**em.**

```java
public class Demo11Method{
    public static main(String[] args){
        方法名称1();
        方法名称2();
        方法名称3();
    }
    public static void 方法名称1(){
    方法体1
	}
    public static void 方法名称2(){
    方法体2
	}
    public static void 方法名称3(){
    方法体3
	}
}
```



## 9.3 方法的重载（Overload）

**拟解决问题：**对于功能类似的方法来说，因为参数列表不一样，却需要记住多种不同的方法名称，太麻烦。

**方法的重载（Overload）：**多个方法的名称一样，但是参数列表不一样。

```java
public class MethodOverload{
    public static void main(String[] args){
        System.out.println(sum(a: 10,b: 20));  
        //30
        System.out.println(sum(a: 10,b: 20, c: 30));	
        //60
        System.out.println(sum(a: 10,b: 20, c: 30, d: 40));		
        //100
        System.out.println(sum(a: 10,b: 20, c: 30, d: 40, e: 50));
        //error，没有方法与之匹配。
    }
    
    public static int sum(int a, int b){
        return a + b;
    }
    
    public static int sum(int a, int b, int c){
        return a + b + c;
    }
    
    public static int sum(int a, int b, int c, int d){
        return a + b + c + d;
    }
}
```

**方法重载与下列因素有关：**

1.参数个数不同是可以的；

2.参数类型不同是可以的；

3.参数的多类型顺序不同是可以的； em. 先double后int，先int后double。



**方法重载与下列因素无关：**

1.与方法的名称无关；

2.与方法的返回值类型无关。



# 9.5 IDEA

**Project -> Model -> Package(cn.address.1.2.3) -> Java Class**

**src文件夹**是源码文件夹。

**out文件夹**内生成编译后的文件。

**src**在**Model** 中，**Project**中可以有多个**Model**。



# 10.数组

**数组：**是一个容器，可以同时存放多个数据值。

**数组的特点：**

1.数组是一种引用数据类型；

2.数组中的多个数据类型必须统一；

3.数组长度在程序运行期间不可改变。



## 10.1 数组的初始化

两种常见的初始化方式：

1.**动态初始化**（指定长度）

```java
数据类型[] 数组名称 = new 数据类型[数组长度];
```

**解析含义：**

左侧数据类型：数组中数据的统一类型，=左右需已知、

左侧中括号：代表这是一个数组。

左侧数组名称：数组的名字。

右侧new：代表创建数组的动作。

右侧数组长度：填入数组当中可以保存多少数据，是一个int数字。



2.**静态初始化**（指定内容）

```java
标准格式：
数据类型[] 数组名称 = new 数据类型[]{元素1, 元素2, ...};

省略格式：
数据类型[] 数组名称 = {元素1, 元素2, ...};
```

**与动态的区别：**

数组中有多少个数据以及数据内容已经被安排了。



**ps. ** 除了静态省略格式外，其他初始化格式都可以写成两行。



## 10.2 访问数组元素

**直接**打印数组名称，输出的是数组的**内存地址值**。

`System.out.println(数组名称);    // [I@75412c2f`

[ ------ 代表这是一个数组

i ------ 代表里面全是int

@之后是十六进制地址



**访问数组元素格式：**

```java
System.out.println(数组名称[int数字]);
```



**数组元素赋值：**

动态初始化数组的时候，其中的元素**默认值**如下：

整数类型：0

浮点类型：0.0

字符类型：'\u0000'

布尔类型：false

引用类型：null

```java
数组名称[指定下标] = 123;
```

<!--2022年1月27日00:41:10-->



## 10.3 数组的长度-遍历-最值-元素反转

**长度：**`int n = array.length;`

**遍历：**

```java
public static void arrayTraversal(){
    int[] array = {15, 20, 25, 30};
    for(int i=0; i<array.length; i++){
        System.out.println(array[i]);
    }
}
```

**最大值：**

```java
public static int arrayMax(int[] array){
	int max = array[0];
    for(int i=1; i<array.length; i++){
        if(array[i] > max){
            max = array[i];
        }
    }
    return max;
}
```

**最小值：**

```java
public static int arrayMin(int[] array){
    int min = array[0];
    for(int i=1; i<array.length; i++){
        if(array[i] < min){
            min = array[i];
        }
    }
    return min;
}
```

**反转：**

```java
public static void arrayReverse(int[] array){
    int tmp;
    for(int i=0; i<(array.length / 2); i++){
        tmp = array[i];
        array[i] = array[array.length - i];
        array[array.length - i] = tmp;
    }
}
```



## 10.4 数组传递地址-返回地址

**传递地址：**	

**em.** `public static void arrayReverse(int[] array)`

**arrayReverse**方法收到的参数是数组的地址。

**返回地址：**

就是普通的返回一个数组：`return array;`



# 11. Java中的内存划分

**Java中的内存需要划分成5个部分：**

**1.栈（Stack）**：存放的都是方法中的局部变量。**方法的运行一定要在栈当中。**

​		局部变量：方法的参数，或者方法{}内部的变量。

​						作用域：一旦超出作用域，立刻从栈内存当中消失。

**2.堆（Heap）**：凡是new出来的东西，都在堆当中。

​		堆内存里面的东西都有一个地址值：十六进制

​		堆内存里面的数据都有一个默认值。（见上）

**3.方法区（Method Area）**：存储**.class**相关信息，包含方法的信息。

**4.本地方法栈（Native Method Stack）**：与操作系统相关。

**5.寄存器（pc Register）**：与CPU相关。



## 11.1 数组的内存图

![11.1插图](F:\研究生\JAVA\JAVASE\JAVASE图\11.1插图.jpg)



## 11.2 数组索引越界异常

数组**索引**编号从0开始，一直到 “数组的长度-1“ 为止。

如果访问数组元素的时候，索引编号并不存在，那么将会发生**数组索引异常**：

`ArrayIndexOutOfBoundException`



## 11.3 空指针异常

所有的引用变量（指向地址），都可以赋值为一个null值，代表其中什么都没有。

数组必须进行new初始化才能使用其中的元素。

如果只是赋值一个null，没有进行new创建，那么将会发生**空指针异常**：

`NullPointerException`



# 12. 类

**面向过程：** 当需要实现一个功能的时候，每一个具体的步骤都要亲力亲为，详细处理每一个细节。

**面向对象：** 当需要实现一个功能的时候，不关心具体的步骤，而是找一个已经具有该功能的人，来帮我做事。 **三大特征：** 封装、继承、多态。

## 12.1 类的定义

**类：** 是一组相关**属性**和**行为**的集合。可以看成是一类事物的模板，使用事物的属性特征和行为特征来描述该类事物。

**属性：** 该事物的状态信息。

**行为：** 该事物能够做什么。

**em.** 

小猫。

属性：名字、体重、年龄、颜色。

行为：走、跑、叫。

```java
public class Cat{
    //属性
    String name;			//没有写在方法里，直接写在class里。
    int weith;
    int age;
    String color;
    //行为
    public void go(){}		//没有static
    public void run(){}		//没有static
    public void call(){}	//没有static	参数-返回值可以有，可以没有。
}
```



**对象：** 是一类事物的具体体现。对象是类的一个**实例**，必然具备该类的属性和行为。

1.导包： `import 包名称.类名称;`

2.创建：`类名称 对象名 = new 类名称();`

3.使用：属性`对象名.name`、方法`对象名.run()`

<!--2022年1月29日00:22:12-->



## 12.2 对象的内存图

<img src="F:\研究生\JAVA\JAVASE\JAVASE图\12.2插图2.jpg"  />

**ps**.两个引用指向同一个对象可以节省**堆**内存。



## 12.3 对象类型作为方法的参数-返回值

当一个对象作为参数。传递到方法当中时：

实际上传递进去的是对象的**地址值**。



当使用一个对象类型作为方法的返回值时：

返回值其实就是对象的**地址值**。

<!--2022年2月3日00:41:37-->



# 13 面向对象--封装性

**封装性**在Java中的体现：

1. 方法就是一种封装；
2. 关键字`_private`也是一种封装。  



## 13.1 _private关键字

**问题描述：**定义Person年龄时，无法阻止不合理的数值被设置进来。

**解决方案：**用`private`关键字将需要保护的成员变量进行修饰。

**ps.** 一旦使用了`private`进行修饰，那么本类当中仍然可以随意访问。但是，超出了本类范围之外就不能在直接访问了。

**命名规则：** getXxx   //不能有参数，返回值类型和成员变量对应。

​							**注：**对于基本类型当中的boolean值，Getter方法一定要写成isXxx，Setter规则不变。 名字是**约定俗成**的。

​					setXxx	//不能有返回值，参数类型和成员变量对应。

**em.**

```java
public class Person {
    String name;
    private int age;
    //间接访问private成员变量，就是定义一对Getter/Setter方法

    public void show() {
        System.out.println("我叫" + name +"年龄" + age);
    }

    // 这个成员方法，专门用于向age设置数据。
    public void setAge(int num) {
        if (num < 100 && num >= 0) {
            age = num;
        } else {
            System.out.println("数据不合理！");
        }

    }

    // 这个成员方法，专门用于获取age的数据。
    public int getAge() {
        return age;
    }
}
```



## 13.2 _this关键字

当方法的局部变量和类的成员变量重名的时候，根据“就近原则”，优先使用局部变量。

如果需要访问本类当中的成员变量，需要使用格式：

`this.成员变量名`

```java
public class Person {
    String name;
    
    public void sayHello(String name){
        System.out.println(name + ", 你好。 我是" + this.name);
    }
```

**ps.** 通过谁调用的方法（即实例变量的名字），谁就是this。

**验证方法：** `System.out.println(this);  //地址值相同`  



## 13.3 _构造方法

1. 构造方法的**名称**需与**类名**相同；
2. 构造方法不要写返回值类型，连void都不写；
3. 构造方法不能return一个具体的返回值；
4. 如果没有编写任何构造方法，编译器会默认一个构造方法，没有参数、方法体什么都不做；
5. 一旦编写了至少一个构造方法，编译器就不再赠送，所以最好写一个。

```java
	public class Student {
        private String name;
        private int age;
        
        public Student(){			//构造方法 类似于python的 __init__
            System.out.println("无参数构造方法执行了！");
        }
        
        public Student(String name, int age) {  //构造方法支持重载。
            this.name = name;
            this.age = age;
        }
        
        //构造完之后如果需要改变成员变量，仍需要调用Getter/Setter方法。
        public void setName(String n){		
            name = n;
        }
        
        public String getName(){
            return name;
        }
        
        public void setAge(int a){
            age = a;
        }
        
        public int getAge(){
            return age;
        }
    }
```



## 13.4 _静态 static关键字

### 13.4.1 修饰成员变量

​		如果一个成员变量使用了`static`关键字,那么被使用的内容不再属于对象自己，而是属于类的，多个对象共享同一份数据。

**em.**

```java
static String room;
private int id;
private static int idCounter = 0;  //计数器，每当new一个新对象后+1
//可以与private一起用

Student one = new Student();
Student two = new Student();

one.room = "101教室";
System.out.println(two.room); // 与one.room相同

public Student(String name, int age){
    this.name = name;
    this.age = age;
    this.id = ++idCounter;
}
public static int getId(){
    return id;
}
public static void setId(int id){
    this.id = id;
}
```



### 13.4.2 修饰成员方法

​		一旦使用`static`修饰成员方法，那么这就成为了静态方法。静态方法不属于对象，而是属于类的。

​		如果没有`static`关键字，那么必须首先创建对象，然后通过对象才能使用它。相反，如果有了`static`关键字，那么可以直接通过类名称使用它。

**ps.** 静态方法强烈推荐通过类名称进行调用，而不是类变量名。

注意事项：

1. 静态不能直接访问非静态。因为在内存当中时现有静态内容，后有的非静态内容。
2. 静态方法当中不能用`this`。因为this代表当前对象，通过谁调用的方法，谁就是当前对象。**静态方法在调用时会被强制编译成类名称调用，而不是对象名。**



### 13.4.3 static内存图

![13.4.3插图](F:\研究生\JAVA\JAVASE\JAVASE图\13.4.3插图.jpg)

**ps.** 根据类名称访问静态成员变量的时候，全程**和对象就没关系，只和类有关系**。



### 13.4.4 静态代码块

静态代码块的格式是：

```java
public class Person {
    static {
        System.out.println("静态代码块执行！");
    }
}
```

**特点：** 当第一次使用本类时，静态代码块执行**唯一**的一次。

​			静态内容总是优先于非静态，所以静态代码块比构造方法先执行。

**典型用途：** 用来**一次性的**对静态成员变量进行赋值。



# 14 常用API (Application Programming Interface)

**API指JDK提供的现成的类。**

具体使用方法查找**JDK API**文档。

只有java.lang包下的内容不需要import语句，其他的都需要。



## 14.1 _Scanner&匿名对象

用于**键盘输入**数据到程序当中。

**使用步骤：**

```java
package com.fun.demo;
import java.util.Scanner;

public class Demo01Scanner{
    public static void main(String [] args){
        //System.in代表从键盘输入。
        Scanner sc = new Scanner(System.in);
        int num = sc.nextInt(); //获取键盘输入的int数字,字符串转int
        String str = sc.next(); //获取键盘输入的字符串
    }
    
    public static Scanner methodAnonymous(){
        return new Scanner(System.in);			//匿名对象写法，用于优化
    }
}
```



## 14.2 _Random

用于生成随机数字。

```java
package com.fun.demo;
import java.util.Random;

public class Demo02Random{
    public static void main(String [] args){
		Random r = methodAnonymous();
        int num1 = r.nextInt(); //生成int范围内的随机一个数字
        int num2 = r.nextInt(3); //生成[0, 3)区间的随机数
        int num3 = r.nextInt(n) + 1; //生成[1, n)区间的随机数
        int num4 = r.nextInt(n+10) - 10; //生成[-10, n)区间的随机数
    }
    
    public static Random methodAnonymous(){
        return new Random();
    }
}
```



## 14.3 _ArrayList

是**大小可变的数组**的实现。

**ps.** ArrayList重写了toString方法，因此直接打印不会出地址值，而是中括号：[]，因此可以作为方法的**参数**以及**返回值**。

如果要在ArrayList中存储基础类型数据，必须使用对应的**“包装类”**：

byte					  **B**yte

short					**S**hort

int						 **Integer**

long					  **L**ong

float					  **F**loat

double				  **D**ouble

char					  **Character**

boolean				**B**oolean	

```java
package com.fun.demo;
import java.util.ArrayList<E>;  //<E>代表泛型，必须是引用类型

public class Demo03ArrayList{
    public static void main(String [] args){
        ArrayList<String> list = new ArrayList<>(); //String类型数组
        
        //添加，返回boolean值，py中的list.append("赵丽颖")
        list.add("赵丽颖"); 
        
        list.get(n);   //获取下标为n的元素，返回String值
        list.remove(m);	//删除下标为m的元素，返回String值
        list.size();	//获取length，返回int值
        list.set(index. element); //修改index下标的值为element
    
    }
}

```



<!--2022年2月8日00:46:32-->

## 14.4 _String 字符串类

字符串是常量；它们的值在创建之后**不能更改**。

程序当中所有的双引号字符串，都是String类的对象。（就算没有new，也照样是。）

**字符串的特点：**

1. 字符串的内容是用不可变的。
2. 正是因为字符串不可改变，所以字符串是可以共享使用的。（节省内存）
3. 字符串效果上相当于是char[]字符数组，但是底层原理是byte[]字节数组(二进制)。

**字符串常见3+1创建方式：**

1. 三种构造：

`public String():`

`public String(char[] array):`

`public String(byte[] array):`

2. 一种直接创建：

`String str = "Hellow" ;    //直接写上双引号就是字符串对象。`



### 14.4.1 常量池

**字符串常量池：** 程序当中直接写上的双引号字符串，就在字符串常量池中。

对于**基本**类型， == 是**数值**比较； 对于**引用**类型， == 是**地址值**比较。

![14.4.1插图](F:\研究生\JAVA\JAVASE\JAVASE图\14.4.1插图.jpg)

**ps.** 双引号直接写的字符串在常量池当中，new的不再池当中。



### 14.4.2 比较相关方法

由于 == 是进行对象的地址值比较，如果确实需要字符串的内容比较，可以使用两个方法：

I. `public boolean equals(Object obj): ` 区分大小写

1. 参数可以是任何对象，只有参数是一个字符串并且内容相同才会返回True，否则返回False。

**em.**

```java
String str1 = "Hellow";
String str2 = "Hellow";
char[] charArray = {'H', 'e', 'l', 'l', 'o', 'w'};
String str3 = new String(charArray);

System.out.println(str1.equals(str2));     //全都是True
System.out.println(str2.equals(str3));
System.out.println(str3.equals("Hellow"));
System.out.println("Hellow".equals(str1));
```

2. equals方法具有对称性，`str1.equals(str2)`和`str2.equals(str1)`效果一样。
3. 如果比较双方是一个常量和一个变量，推荐把常量字符串写在前面。                                          即`"Hellow".equals(str1)` ，避免空指针异常。



II. `public boolean euqalsIgnoreCase(String str):` 忽略大小写

与I中的方法使用方法相同，只是II方法会忽略**英文字母**的大小写差异。

**ps.** 中文不行。



### 14.4.3 获取相关方法

常用方法有：

1. `public int length():` 获取字符串当中含有字符的个数，拿到字符串**长度**。
2. `public String concat(String str):` 将当前字符串和参数字符串拼接成为返回值新的字符串。  **ps.** 直接用 + 拼接舒服。
3. `public char charAt(int index):` 获取指定索引位置的**单个字符**。
4. `public int indexOf(String str):` **查找**参数字符串在本字符串当中首次出现的索引位置，如果没有返回-1。



### 14.4.4 截取相关方法

常用方法有：

1. `public String substring(int index):` 截取从参数位置一直到字符串末尾，返回新字符串。
2. `public String substring(int begin, int end):` 截取 [begin, end) 索引区间的字符串。



### 14.4.5 转换相关方法

常用方法有：

1. `public char[] toCharArray():` 将当前字符串拆分成为字符数组作为返回值。
2. `public byte[] getBytes():` 获得当前字符串底层的字节数据。
3. `public String replace(CharSequence oldString, CharSequence newString):` 将所有出现的老字符串替换成为新的字符串，返回替换之后的新字符串。 CharSequence是一个接口，意思是可以接收字符串类型。

**em.**

```java
String str1 = "How do you do?";
String str2 = str1.replace("o", "*");  //把o替换成*再返回新字符串。
System.out.println(str1 + str2);  //How do you do? H*w d* y*u d*?
// 可以用于屏蔽敏感词 -_-
```



### 14.4.6 分割方法

常用方法有：

`public String[] split(String regex):` 按照参数的规则，将字符串切分成为若干部分。

**em.**

```java
String str1 = "aaa,bbb,ccc";
String[] array1 = str1.split(",");
System.out.println(array[0]);
```

**ps.** split方法的参数其实是一个正则表达式，如果按照英文句点 `.` 进行切分，必须写`\\.` 。



## 14.5 _Arrays 数组工具类

`java.util.Arrays`是一个与数组相关的工具类，里面提供了大量静态方法，用来实现数组常见的操作：

1. `public static String toString(arrays):` 将参数数组变成字符串。
2. `public static void sort(arrays):` 按照默认升序对数组的元素进行排序。

​		**ps.** 如果是数值，`sort`默认按照升序从小到大；

​			  如果是字符串，默认按照字母升序；

​			  如果是自定义类型，那么这个自定义类型的类需要有`Comparable`或者`Comoarator`接口的支持。

**em.** **倒序**排列练习题：

```java
public class Demo02ArraysPractise {
    public static void main(String[] args) {
        String ste = "asdsa64safsaqweopuljxzyuq";
        
        //如何进行升序排列：sort
        //必须是一个数组，才能使用Arrays.sort方法
        //String --> 数组，用toCharArray
        char[] chars = str.toCharArray();
        Arrays.sort(chars); //对字符数组进行升序排列
        
        //需要倒序遍历  IDEA中 chars.fori 生成正序/ chars.forr 生成倒序
        for (int i = char.length - 1; i >= 0; i--) {
            System.out.println(chars[i]);		//先正再倒，完成排列
        }
    }
}
```



## 14.6 _Math 数学工具类

`java.long.Math` 类是数学相关的工具类，里面提供了大量的静态方法，完成与数学运算相关的操作。常用的有：

1. `public static double abs(double num):` 	获取绝对值
2. `public static double ceil(double num):`   向上取整
3. `public static double floor(double num):` 向下取整
4. `public static double round(double num):` 四舍五入
5. `Math.PI` 代表近似 π ；   `Math.E` 代表近似 e 。



## 14.7 BigInteger & BigDecimal

大**数字**类和大**精度**类。





# 15 面向对象--继承性

继承是多态的前提，如果没有继承，就没有多态。

继承只要解决的问题就是：**共性抽取**。（子类之间相同的东西可以交给父类来写）

继承关系中的**特点：**

1. 子类可以拥有父类的”内容“；
2. 子类还可以拥有自己专有的内容。

**格式：**

```java
public class Employee {		// 定义一个父类：员工
    public void method(){
         System.out.println("方法执行！");
    }
}
```

```java
public class Teacher extends Employee {
    // 什么都不写，代表与父类内容相同
}
```

Java语言继承的**三个特点**：

1. Java是**单继承**的。一个类的直接父亲只能有唯一一个。
2. Java可以**多级继承**。最顶端的类叫`java.lang.Object`。
3. 一个子类的直接父类是唯一的，但是一个父类可以有多个子类。



## 15.1 继承中的成员变量访问

​		子类可以直接使用父类中的成员变量。对于成员变量重名，则创建子类对象时，访问有两种方式：

1. 直接通过子类对象访问成员变量：

等号左边是谁，就优先用谁，没有则向上找。

**em.**

```java
Zi zi = new Zi();
System.out.println(zi.num); // 优先子类，没有则向上寻找，都没有则报错
```

2. 简介通过成员方法访问成员变量：

该方法属于谁，就优先用谁，没有则向上找。

```java
public class Zi extends Fu {
    public void methodZi() {
        System.out.println(num);  //子类中没有num，向上找num
    }
}
```

**ps.** 当存在三个重名变量时（父类，子类，方法中）：

```java
public class Zi extends Fu {
    int num = 20;   // 父类中为10
    public void method() {
        int num = 30;
        System.out.println(num);		// 30，局部变量
        System.out.println(this.num);	// 20，本类成员变量
        System.out.println(super.num);	// 10，父类成员变量
    }
}
```



## 15.2 继承中的成员方法访问

在父子类的继承关系当中，创建子类对象，访问成员方法的规则：

​		创建的对象是谁，就优先用谁，如果没有就向上找。

**em.**

```java
public class Zi extends Fu {
    public void methodZi() {		
        System.out.println("子类");  
    }
}
```

```java
public class Demo01ExtendsMeghod {
    public static void main(String [] args) {
        Zi zi = new Zi();
        
        zi.methodZi();
        zi.methodFu();		//子类中没有methodFu，向上找methodFu
    }
}
```



## 15.3 方法的重写(Override)

重写(Override)：在继承关系当中，方法的名称一样，**参数列表也一样**。

重载(Overload)：方法的名称一样，**参数列表不一样**。



**重写的特点：** 创建的是子类对象，则优先用子类方法。

**注意事项：**

1. 必须保证父子类之间方法的名称相同，参数列表也相同。

`@Override`：写在方法前面，用来检测是不是有效的正确覆盖重写。

**em.**

```java
public class Zi extends Fu {
    
    @Override		// 方法名字写错就会报错，不一定要写
    public void method() {	
        super.method();   // 拿父类的过来用，再添加子类更多的内容
        System.out.println("子类");  
    }
}
```

2. 子类方法的返回值必须**小于等于**父类方法的返回值**范围**。

`java.long.Object`类是所有类的公共最高父类。所以父类返回`String`，子类就不能返回`Object`。

3. 子类方法的权限必须大于等于父类方法的权限修饰符。

`public > protected > (default) > private`

`(default)`不是关键字`default`，而是什么都不写，留空。 比如 `int i;`



## 15.4 继承中构造方法的访问

继承关系中父子类构造方法的**特点：**

1. 子类构造方法当中有一个默认隐含的`super();`调用，所以一定是先调用的父类构造，后执行的子类构造。
2. 可以通过`super`关键字来子类构造调用父类重载构造。

**em.**

```java
public class Fu {
    public Fu() {
        System.out.println("父类无参构造"); 
    }
    public Fu(int num) {
        System.out.println("父类有参构造"); 
    }
}
```

```java
public class Zi extends Fu {
    public Zi() {	
        super(num);
        System.out.println("子类构造");   
    }
}
```

3. `super();`的父类构造调用，必须是子类构造方法的**第一个语句**。不能一个子类构造调用多次`super`构造。

## 15.5 _super& _this关键字的三种用法

`super`关键字的三种用法： **（访问父类内容）**

1. 在子类的成员方法中，访问父类的成员变量；  **15.1**
2. 在子类的成员方法中，访问父类的成员方法；  **15.2**
3. 在子类的构造方法中，访问父类的构造方法。  **15.4**



`this`关键字的三种用法：	**（访问本类内容）**

1. 在本类的成员方法中，访问本类的成员变量；

2. 在本类的成员方法中，访问本类的另一个成员方法；

   ```java
   public void methodA() {
       pass;
   }
   public void methodB() {
       this.methodA();		// 起到一个强调的字面作用	
   }
   ```

3. 在本类的构造方法中，访问本类的另一个构造方法。

```java
public Zi() {
    this(123);		// 与15.4中的第三条相同，必须是第一条语句，唯一一个
}
public Zi(int num) {
    pass;
}
```

**ps.** `this(...)`必须是第一条语句，唯一一个，且`super()`**不再赠送**，`this()`里面其实有`super()`。

**图解：**

![15.5插图](F:\研究生\JAVA\JAVASE\JAVASE图\15.5插图.jpg)





# 16 抽象类与接口

## 16.1 抽象

​		如果父类当中的方法不确定如何进行{}方法体实现，那么这就应该是一个**抽象方法**。

### 16.1.1 抽象方法与抽象类定义格式

**抽象方法**就是加上`abstract`关键字，然后去掉大括号，直接分号结束。

**抽象类：**抽象方法所在的类，必须是抽象类才行。在`class`之前加`abstract`即可。

```java
public abstract class Animal {
     // 这是一个抽象方法，代表吃东西，但具体吃什么（大括号内容）不确定。
    public abstract void eat(); 
    
    // 这是普通的成员方法。
    public void normalMethod() {
        
    }
}
```



### 16.1.2 抽象的使用

如何使用抽象类和抽象方法：

1. 不能直接创建`new`抽象类对象；
2. 必须用一个子类继承抽象父类；
3. **普通**子类必须**覆盖重写**抽象父类当中的所有**抽象**方法。除非子类也是抽象类。这相当于抽象子类又自行添加了自己的抽象方法。

**覆盖重写（实现）：**子类去掉抽象方法的`abstract`关键字，然后补上方法体大括号{}。

```java
public class Cat extends Animal {
    @Override
    public void eat() {
        System.out.println("猫吃鱼！（覆盖重写）");
    }
}
```

4. 创建子类对象进行使用。抽象类中可以有**构造方法**，用于子类初始化父类成员。

 

## 16.2 接口(Interface)

接口就是多个类的公共规范，是一种**引用**数据类型。

**最重要**的内容就是其中的：**抽象方法**。

定义接口的格式：

```java
public interface Name {   // 与类名称规则一样，首字母大写。
    // 接口内容
}
```

Java 9中接口可以定义的方法有：

1. 常量
2. 抽象方法
3. 默认方法
4. 静态方法
5. 私有方法



### 16.2.1 抽象方法

```java
public interface MyInterfaceAbstract {
    
    // 这是一个抽象方法
    public abstract void methodAbs();
}
```

**注意事项：**

1. 接口当中的抽象方法，修饰符必须是两个固定的关键字：`public abstract`;

2. 这两个关键字修饰符，可以选择性的省略。

   比如 `abstract void methodAbs();`  `public void methodAbs();` `void methodAbs();`都可以。

3. 方法的三要素可以随意定义。



**接口使用步骤：**

1. 接口不能直接使用，必须有一个“实现类”来“实现”该接口。

```java
public class 实现类名称 implements 接口名称 {
    // ...
}
```

2. 接口的实现类必须覆盖重写接口中所有的抽象方法。与子类继承抽象类相同。如果有没重写的方法，那么该类必须是抽象类。
3. 创建实现类的对象，进行使用。快捷键：Alt+Enete



### 16.2.2 默认方法

```java
public default 返回值类型 方法名称(参数列表) {
    方法体;
}
```

备注：接口默认方法，可以解决接口升级的问题。 只有`public`可以省略不写。

默认方法相当于抽象类中的普通方法，会被实现类继承下去。



**使用步骤：**

1. 接口的默认方法，可以通过接口实现类对象，直接调用。
2. 接口的默认方法，也可以被接口的实现类覆盖重写。



### 16.2.3 静态方法

```java
public static 返回值类型 方法名称(参数列表) {
  	方法体;
}
```

提示：就是将`abstract`或者`defauly`换成`static`即可。`public`可以省略。

注意：不能通过接口实现类的对象来调用接口当中的静态方法。

​			通过接口名称，直接调用其中的静态方法。

```java
MyInterfaceAbstract.methodStaric();
```



### 16.2.4 私有方法

问题描述：

我们需要抽取一个共有方法，用来解决两个默认方法之间重复代码问题。

但是这个共有方法不应该让实现类使用，应该是**私有化**的。

1. 普通私有方法，解决多个默认方法之间重复代码问题：

```java
private 返回值类型 方法名称(参数列表) {
    方法体;
}
```

2. 静态私有方法，解决多个静态方法之间重复代码问题：

```java
private static 返回值类型 方法名称(参数列表) {
    方法体;
}
```



### 16,2,5 常量定义与使用

```java
public static final int NUM = 10;
// 这是一个常量，一旦赋值，不可以修改
```

注意：一旦使用`final`关键字，说明不可改变。使用的时候`接口名称.NUM`。

注意事项：

1. 接口当中的常量可以省略`public static final`，默认写上了。
2. 接口当中的常量，必须进行赋值：不能不赋值。**(会给默认值，且不可更改)**
3. 接口中常量的名称使用完全大写的字母，用下划线分隔。**(推荐命名规则)**



### 16.2.6 实现多个接口(与抽象类区别)

使用接口的**注意事项：**

1. 接口中不能有**静态代码块**和**构造方法**；
2. 一个类的直接父类是唯一的，但是一个类可以同时实现多个接口；

```java
public class MyInterfaceImpl extends Object implements MyInterfaceA, MyInterfaceB {
    // 覆盖重写两个接口中的所有抽象方法
}
```

**ps.** Java当中的任何一个类都是`Object`的子类，只是`extends Object`是默认的，可以不写。

3. 如果实现类所实现的多个接口当中，存在**重复的抽象方法**，那么只需要覆盖重写一次即可。
4. 如果实现类没有覆盖重写所有接口当中的所有抽象方法，那么实现类必须是抽象类。
5. 如果实现类所实现的多个接口当中，存在**重复的默认方法**，那么实现类必须将冲突的默认方法重写。
6. 一个类如果直接父类当中的方法，和接口当中的默认方法产生冲突，优先用父类当中的方法。



### 16.2.7 接口之间多继承

1. 类与类之间是单继承的。直接父类只有一个。
2. 类与接口之间是多实现的。一个类可以实现多个接口。
3. 接口与接口之间是多继承的。

```java
public interface MyIntfaceA {
    //...
}
```

```java
public interface MyIntfaceB {
    //...
}
```

```java
public interface MyIntface extends MyIntfaceA, MyIntfaceB {
    //...
}
```

注意事项：

1. 多个父接口当中抽象方法如果重复，没关系。
2. 多个父接口当中默认方法如果重复，子接口必须覆盖重写，而且带着`dafault`关键字。

<!--2022年2月15日01:25:08-->





# 17 面向对象--多态性

​	**多态**指的是一个对象可以有**多个形态**。比如：小明既有学生形态，又有人类形态。

代码当中体现多态性，其实就是一句话，父类引用指向子类对象。

**格式：**

`父类名称 对象名 = new 子类名称();`

或者：

`接口名称 对象名 = new 实现类名称();`

**ps.**子类就是一个父类，即面向对象的多态性。



## 17.1 多态成员变量访问特点

与继承性中的规则相同：

1. 直接通过对象名称访问成员变量：看等号左边是谁，优先用谁，没有则向上找。
2. 简介通过成员方法访问。该方法属于谁，优先用谁，没有则向上找。

根据多态的规则，无法访问子类**独有的**成员变量。

```java
public class Fu {
    int num = 10;
    
    public void shownum() {
        System.out.println(num);
    }
}
```

```java
public class Zi extends Fu {
    int num = 20;
    int age = 21;
    
    public void shownum() {
        System.out.println(num);
    }
    
    public void methodZi() {
        System.out.println(num);
    }
}
```

```java
public class Demo01MultiFiedld {
    public static void main (String[] arg) {
        Fu obj = new Zi();
        System.out.println(obj.num);  // num==10 显示父类 因为成员变量不能覆盖重写
        System.out.println(obj.age);  // 报错，没有age变量
        obj.shownum();		// num==20 显示子类，因为子类覆盖重写了
    } 
}
```



## 17.2 多态成员方法使用特点

在多态的代码当中，成员方法的访问**规则**是：

​		看`new`的是谁，就优先用谁，没有则向上找。

```java
public class Demo01MultiFiedld {
    public static void main (String[] arg) {
        Fu obj = new Zi();
        System.out.println(obj.num);  // num==10 显示父类 因为成员变量不能覆盖重写
        System.out.println(obj.age);  // 报错，没有age变量
        obj.shownum();		// num==20 显示子类，因为子类覆盖重写了
        obj,methodZi();    // 子有父没有，报错！
    } 
}
```

**ps.** 编译看左边，运行看右边。 而成员变量是：编译看左边，运行还看左边。



## 17.3 使用多态的好处

**好处：**无论右边`new`的时候换成哪个子类对象，等号左边调用的方法都不会变化。

代码美观整洁，易于维护。



## 17.4 对象的上下转型

1. 对象的**向上**转型，其实就是多态写法：

**格式：**`父类名称 对象名 = new 子类名称();`

**含义：**右侧创建一个子类对象，把它当做父类来看待使用。

**注意事项：**向上转型一定是安全的。因为从小范围转向大范围。与自动类型转换相似。



2. 对象的**向下**转型，其实是一个**还原**的动作：

**格式：**`子类名称 对象名 = (子类名称)父类对象;`

**含义：**将父类对象，**还原**成为本来的子类对象。

**注意事项：**必须保证对象本来创建的时候子类名称不变，否则就会报错：`ClassCassException`



## 17.5 _instanceof关键字进行类型判断

如何才能知道一个父类引用的对象，本来是什么子类？

**格式：**

```java
if (Fu instanceof Zi) {		//返回的是boolean值
    Zi zi = (Zi) Fu;	//向下转型
}
```

<!--2022年2月16日00:36:34-->





# 18 _final关键字

`final`关键字代表最终、不可改变的。

常见四种用法：

1. 可以用来修饰一个类；
2. 可以用来修饰一个方法；
3. 可以用来修饰一个局部变量；
4. 可以用来修饰一个成员变量。



## 18.1 _final关键字用于修饰一个类

格式：

```java
public final class MyClass {
    //...
}
```

**含义：**当前这个类**不能**有任何子类。（太监类）但是可以有父类。（Object类）

注意：一个类如果是`final`的，那么其中所有的成员方法都无法进行覆盖重写（因为没子类）。



## 18.2 _final关键字用于修饰一个方法

格式：

```java
public final void method() {
    //...
}
```

含义：当`final`关键字用来修饰一个方法的时候，那么这个方法将不能被覆盖重写。（最终方法）

注意：对于类、方法来说，`abstract`关键字和`final`关键字不能同时使用，因为矛盾。（因为抽象方法一定要被覆盖重写）



## 18.3 _final关键字用于修饰一个局部变量

局部变量即方法内定义的变量。

```java
final int num；
num = 200;   // 这个值无法再改变
//如果是引用类型，那么cla中的地址不可改变，但是地址里面的内容可以改变
final MyClass cla = new MyClass(); 
cla.setName("改变地址里的内容。");
```

一旦使用`final`修饰局部变量，那么该变量一次赋值，终身不变。



## 18.4 _final关键字用于修饰一个成员变量

```java
private final String name = "关晓彤"; //直接赋值
public MyClass() {
    name = "关晓彤";	//构造赋值
}
```

成员变量有默认值，必须在**定义的时候**或者**构造方法**中赋值。（也不能用Setter方法）

**ps.** 如果用构造方法赋值，必须保证所有的重载构造方法中都会对`final`修饰的成员变量赋值。





# 18.5 四种权限修饰符

​						   `public`  >  `protected`  >  `(default)`  >  `private` 

同一个类				 √						√						√					√

同一个包				√						√						√					×

不同包子类			√						√						×					×

不同包非子类		√						×						×					×



注：  `int i = 1;` 什么都不写就代表默认`(default)`。



定义一个类的时候，权限修饰符规则：

1. 外部类：`public` / `(default)`
2. 成员内部类： `public` / `protected` / `(default)` / `private`
3. 局部内部类：**什么都不能写。**





# 19 内部类

如果一个事物的内部包含另一个事物，那么这就是一个类内部包含另一个类。

例如：身体和心脏的关系、汽车和发动机的关系。

内部类分类：

1. 成员内部类
2. 局部内部类（包含匿名内部类）



## 19.1 成员内部类

格式：  编译文件      Body$Heart.class

```java
// 外部类
public class Body {
    
    // 内部类
    public class Heart {
        // 内部类方法
        public void beat() {
            System.out.println("心跳声！");
        }
    } 
    // 外部类方法
    public void methodBody {
        System.out.println("外部类方法");
        new Heart().beat();		//匿名对象，没有名字
    }
}
```

注意：**内用外**，随意访问；**外用内**，需要内部类对象。

如何使用内部类？有两种方式：

1. 间接方式：在外部类的方法当中，使用内部类；然后`main`只是调用外部类的方法。

```java
public class Demo01InnerClass {
    public static void main (String[] arg) {
        Body body = new Body();
        body.methodBody();
    }
}
```

2. 直接方式，公式： 

   `外部类名称.内部类名称 对象名 = new 外部类名称().new 内部类名称();`

```java
Body.Heart heart = new Body().new Heart();
heart.beat();
```



内部类**重名**变量访问：

```java
this.num; //内部类num变量
Outer.this.num； //外部类num变量，只能在内部类里使用
```



## 19.2 局部内部类

如果一个类是定义在一个方法内部，那么这就是一个局部内部类。

“局部”：只有当前所属的方法才能使用它，畜类这个方法外面就不能用了。

定义格式：

```java
public class Outer {
    public void methodOuter() {
        class Inner {		//局部内部类 只能方法内使用
            int num = 10;
            
        	public void methodInner() {
                System.our.println(num);	
            }
        }
    }
}
```



## 19.3 局部内部类_final问题

​	局部内部类，如果希望访问所在的方法的局部变量，那么这个局部变量必须是【有效`fianl`的。

```java
public class MyOuter {
    public void methodOuter() {
        final int num = 10;   //只要num值不变，不写final也行
        
        class MuInner {
            public void methodInner() {
                System.our.println(num);	//不能用
            }
        } 
    }
}
```

写`final`的原因：

1. `new`出来的对象在堆内存当中。
2. 局部变量是跟着方法走的，在栈内存当中。
3. 方法运行结束之后，立即出栈，局部变量就会立即消失。
4. 但是`new`出来的对象会在堆当中持续存在，直到垃圾回收消失。



## 19.4 匿名内部类

如果接口的实现类（或者是父类的子类）只需要使用唯一的一次，

那么这种情况下就可以省略掉该类的定义，改为使用**匿名内部类**。



定义格式： 

```java
接口名称 对象名 = new 接口名称() {  //这个接口的实现类没类名
    // 覆盖重写所有抽象方法
    //...
};  //末尾分号

new 接口名称() {
    public void method() {
        //...
    }
}.method(); 			//这个接口的实现类连对象名都没有
```

注意事项：

1. **匿名内部类**在创建对象的时候，只能使用唯一一次。
2. **匿名对象**只能**调用**唯一一次。



## 19.5 类作为成员变量类型

```java
public class Hero {
    private String name;
    private int age;
    private Weapon weapon;		//武器 是一个自定义的类
}
```

**ps.** 就跟C里的`structure`结构体相似。



## 19.6 接口作为成员变量类型

```java
public class Hero {
    private String name;
    private int age;
    private Weapon weapon = new weapon("火之高兴");//武器 是一个自定义的类
    private Skill skill;  //这是一个接口成员变量 
}
```

```java
Hero hero = new Hero();
hero.setSkill(new SkillImpl());   //需要一个实现类Setter
```



## 19.7 接口作为方法参数及返回值

```java
public class DemoInterface {
    public static void main(String[] arg) {
        // ArrayList是List接口的实现类
        List<String> list = new ArrayList<>();	//多态写法
        
        System.our.println(list.get(0));
        
    }
    public List<String> addNames(List<String> list) {
        list.add("迪丽热巴");
        return list;
    }
}
```

<!--2022年2月18日22:46:46-->





# 19.5 Java常用类介绍

## 1 Object 祖类

`Object`类是类层次结构的根。每个类都是用其作为超（父）类。

**`toString()`方法：**

```java
Person p = new Person();
String s - p.toString();
System.out.println(s);  //显示p的地址值
System.out.println(p);	//显示p的地址值，直接打印对象名，其实就是调用toString()方法。  p = p.toSring()
```

**ps.** 想直接显示对象名，可以重写`toString()`方法来实现。看一个类是否重写了`toString()`方法，也可以直接打印这个对象名字即可。



**`equals()`方法：**

`equals()`方法默认比较的是两个对象的地址值，因此需要重写该方法来比较两个对象的属性值（name，age）。

```java
@Override
public boolean equals(Object obj) {
    Person p = (Person)obj;   //隐藏多态，强转子类
    
    // String类中有自己重写的equals方法。
    boolean b = this.name.equals(p.name) && this.age==p.age;	
    return b;
}
```

扩展：工具类`objects`中的`equals`方法可以防止空指针异常。（加了健壮性判断）



## 2 Date 日期和时间类

类`date`表示特定的瞬间，精确到毫秒。（1000毫秒 = 1秒） 数值类型：**long**

**两个构造器的使用：**

`Date():` 创建一个对应当前时间的Date对象。

`Date(15646L):` 创建指定毫秒数的Date对象。

**两个方法的使用：**

`toString():` 显示当前的年、月、日、时、分、秒。

`getTime():` 获取当前Date对象对应的毫秒数。（时间戳）



```java
public class Demo01Date {
    public static void main(String[] args) {
        Date date = new Date();
        //Sat Feb 19 00:40:17 CST 2022 空参数构造，获取当前系统时间
        System.out.println(date);	
        // Thu Jan 01 08:00:00 CST 1970  时间原点（中国+8区）
        // 有参数构造，将毫秒值转换成Date日期
        System.out.println(new Date(0L));  
        // 1645202832244 把日期转成毫秒的成员方法
        System.out.println(date.getTime());
    }
}
```

**`DateFormat`类用于把日期和文本之间转换：** 子类：`SimpleDateFormat`

`String format(Date date)` 该方法按指定模式转化时间为**字符串**

`Date parse(String source)` 该方法把符合模式的字符串，解析为**Date日期**

模式：（区分大小写）   例： yyyy-MM-dd HH:mm:ss	yyyy年MM月dd日

y		年

M	   月

d		日

H	   时

m	  分

s		秒

模式填写在`SimpleDateFormat`的构造方法中：

`new SimpleDateFormat("yyyy-MM-dd HH:mm:ss")`



## 3 Calendar 日历类

在`Date`之后出现，替换掉了许多`Date`方法。

`Calendar `是一个抽象类，里面提供了很多操作日历字段的方法（YEAR、MONTH、DAY_OF_MONTH、HOUR）

`Calendar `无法直接使用，里面有一个静态方法`getInstance()`，该方法返回了`Calendar`类的子类对象。

```java
Calendar c = Calendar.getInstance();  //多态
System.out.println(c);
//java.util.GregorianCalendar[time=1645259833398,areFieldsSet=true,areAllFieldsSet=true,lenient=true,zone=sun.util.calendar.ZoneInfo[id="Asia/Shanghai",offset=28800000,dstSavings=0,useDaylight=false,transitions=31,lastRule=null],firstDayOfWeek=1,minimalDaysInFirstWeek=1,ERA=1,YEAR=2022,MONTH=1,WEEK_OF_YEAR=8,WEEK_OF_MONTH=3,DAY_OF_MONTH=19,DAY_OF_YEAR=50,DAY_OF_WEEK=7,DAY_OF_WEEK_IN_MONTH=3,AM_PM=1,HOUR=4,HOUR_OF_DAY=16,MINUTE=37,SECOND=13,MILLISECOND=398,ZONE_OFFSET=28800000,DST_OFFSET=0]
int month = c.get(Calendar.MONTH);	//public int get(int field) 方法返回给定日历字段的值
System.out.println(month);	// 1    MONTH=1 西方月份0-11 东方1-12
System.out.println(c.get(Calendar.DATE)); // 19日

c.set(Calendar.YEAR, 9999); //public int set(int field, int value) 方法将给定的日历字段设置为给定值。  field:指定日历字段(YEAR,MONTH...) value:传递字段设置具体的值。

c.add(Calendar.YEAR, 2); //public abstract void add(int field, int amount) 方法根据日历规则，为给定的日历租店添加或减去指定的时间量。 amoint:增加减少量，可正可负。
   
Date date = c.getTime(); //把Calendar转换成Date
```



**JDK8中新日期时间API：** `java.time` 常用**类**有：

本地日期（`LocalDate`）

本地时间（`LocalTime`）

本地日期时间（`LocalDateTime`）

时区（`ZonedDateTime`）

持续时间（`Duration`）

瞬时：（`Instant`）

格式化与解析（`DateTimeFormatter`） 属于`java.time.format.DateTimeFormatter` 类似`SimpleDateFormat`。



## 4 System

可以获取与系统相关的信息或系统级操作，在`System`类的API文档中，常用方法有：

`public static long currentTimeMillis()` ：返回以毫秒为单位的当前时间。

`void exit(int status):` 退出程序，status=0代表正常退出，非零代表异常退出。

`void gc():` 请求系统进行垃圾回收。

`String getProperty(String key):` 获得系统中属性名为key的属性对应的值。



```java
package com.fun.demo04;

// 练习：测试for循环打印1-9999所需要的时间,单位：毫秒

public class Demo04System {
    public static void main(String[] args) {
        long start = System.currentTimeMillis();
        for (int i = 0; i < 100000; i++) {
            System.out.println(i);
        }
        long now = System.currentTimeMillis();
        System.out.println("用时" + (now - start) + "ms"); //用时195ms
    }
}
```

`public static void arraycopy(Object src, int srcPos, Object dest, int destPos, int length)`：将数组中指定的数据拷贝到另一个数组中。

src - 源数组

srcPos - 源数组中起始位置

dest - 目标数组

destPos - 目标数组中起始位置

length - 要复制的数组元素数量



## 5  String相关

### 5.1 String

1. String声明为final，不可被继承。

2. String实现了Serializable接口：表示字符串是支持序列化的。

   实现了Comparable接口：表示String可以比较大小。

3. String内部定义了final char[] value用于存储字符串数据。

4. String代表不可变的字符序列。

5. 对字符串进行**增删改**都是建立一个新的字符串。



**常用方法：**

`int length():` 返回长度

`char charAt(int index):` 返回索引处的字符 

`boolean isEmpty():` 判断是否是空字符串

`String toLowerCase():` 返回将String中的所有字符转换成小写

`String toUpperCase():` 返回将String中的所有字符转换成大写

`String trim():` 返回字符串的副本，忽略前导空白和尾部空白，中间空格不变

`boolean equals(Object obj):` 比较字符串内容是否相同

`boolean equalsIgnoreCase(String anotherString):` 与equals相同，但忽略大小写

`String concat(String str):` 将指定字符串连接到此字符串的结尾。等价于用“+”。

`int compareTo(String anotherString):` 比较两个字符串大小，依据ASCII做减法。

​			使用方法：str1.compareTo(str2);

`String substring(int beginIndex):` 返回一个新的字符串，它是此字符串的从beginIndex开始截取的。

`String substring(int beginIndex, int endIndex):` 返回一个新的字符串，从beginIndex截取到endIndex。

`boolean endWith(String suffix):` 测试此字符串是否以指定的后缀结束。

`boolean startsWith(String prefix):` 测试此字符串是否以指定的前缀开始。

`boolean startWith(String prefix, int toffset):` 测试此字符串从指定索引开始的字符串是否以指定前缀开始。

`boolean contains(CharSequence s):` 当且仅当此字符串包好指定char值序列是，返回true。

`int indexOf(String str):` 返回指定子字符串在此字符串中第一次出现的索引。

`int indexOf(String str, int fromIndex):` 返回指定子字符串在此字符串中从指定索引开始第一次出现的索引。

`int lastIndexOf(String str):` 返回指定子字符串在此字符串中最右边出现处的索引。

`int lastIndexOf(String str, int fromIndex):` 返回指定子字符串在此字符串中最后一次出现的索引。 **以上四种若未找到，均返回-1。**

`replace` 替换

`split` 切割





### 5.2 StringBuilder 字符串缓冲区

字符串是常量，它们的值在创建之后不能更改。**字符串缓冲区支**持可变的字符串。



字符串的底层是被`final`修饰的数组。 `private final byte[] value;`

 进行字符串相加，内存中就会有多个字符串，占用空间多，效率低下。



`StringBuilder`类可以提高字符串的操作效率（看成一个长度可以变换的字符串）

底层也是一个数组，没有`final`修饰： `byte[] value - new byte[16];`



`StringBuilder`类在内存中始终是一个数组，占用空间少，效率高，如果超出了容量，会自动扩容。

```java
StringBuilder bu1 = new StringBuilder("abc"); //String转StringBuilder 
System.out.println(bu1); 		//abc
System.out.println(bu1+"123"); //abc123

//public StringBuilder append(String str) 方法，添加字符串后返回自身。
System.out.println(bu1.append("123")); //abc123  

//public String toString() 方法 将StringBuilde对象转成Sting对象。
bu1.toString();
```



### 5.3 StringBuffer

相较于`StringBuilder`，`StringBuffer`是线程安全的，但效率低。 

三个String字符串底层都是使用char[]存储。

**常用方法：**

`StringBuffer append(xxx):` 提供了很多的append()方法，用于进行字符串拼接。

`StringBuffer delete(int start, int end):` 删除指定位置的内容。

`StringBuffer replace(int start, int end, String str):` 替换[start, end)为str。

`StringBuffer insert(inst offset, xxx):` 指定位置插入xxx。

`StringBuffer reverse():` 把当前字符序列逆转。

`public int indexOf(String str):` 

`public String substring(int start, int end):`

`public int length():`

`public char charAt(int n):`

`public void setCharAt(int n, char ch):` 修改单个字符。

`toString():` 转字符串，遍历。



## 6 Java比较器

说明：Java中的对象，正常情况下，只能进行比较：== 或 != 。不能使用 > 或 < 。若要比较对象的大小。需要使用以下两个接口中的一个，并指明按照什么方式进行排序。（价格、年龄等）

**自然排序：**`java.lang.Comparable`  **(可反复使用)**

1. String、包装类等实现了Comparable接口，重写了compareTo()方法，给出了比较两个对象大小的方法。
2. 像String、包装类重写comparTo方法以后，进行了从小到大的排列。
3. 重写compareTo()的规则：
   1. 如果当前对象的this大于形参对象obj，则返回正整数。
   2. 如果当前对象的this小于形参对象obj，则返回负整数。
   3. 如果相等，则返回0。



**定制排序：**`java.util.Comparator`	**（临时使用）**

1. 背景：当元素的类型没有实现`java.lang.Comparable`接口而又不方便修改代码，或者实现了但排序规则不适合当前的操作，那么可以考虑使用`Comparator`的对象来排序。
2. 重写`compare(Object o1, Object o2)`方法，比较o1和o2的大小：
   1. 如果返回正整数，则表示o1大于o2。
   2. 如果返回0，表示相等。
   3. 返回负整数，表示o1小于o2。

```java
Arrays.sort(arr, new Comparator() {
    //按照字符串从大到小的顺序排列
    @Override
    public int compare(Object o1, Object o2) {
        if (o1 instanceof String && 02 instanceof String) {
            String s1 = (String) o1;
            String s2 = (String) o2;
            return -s1.compareTo(s2);
        }
        throw new RuntimeException("输入的数据类型不一致")
    }
});

```



# 20 包装类

问题描述：

基本数据类型的数据，使用起来非常方便，但是没有对应的方法来操作这些数据，所以我们可以使用一个类，把基本数据类型包装起来，这个类叫**包装类**，在包装类中可以**定义一些方法**，用来操作基本类型的数据。

14.3章节中提到，如果要在ArrayList中存储基础类型数据，必须使用对应的**“包装类”**：

byte					  **B**yte

short					**S**hort

int						 **Integer**

long					  **L**ong

float					  **F**loat

double				  **D**ouble

char					  **Character**

boolean				**B**oolean	



## 20.1 装箱与拆箱

**装箱：** 爸爸基本类型的数据，包装到包装类中（基本数据类型->包装类）

​			构造方法：

​						`Integer(int value)` 构造一个新分配的`Integer`对象

​				    	`Integer(int value)` 表示`String`参数所指示的`int`值

​			静态方法：

​						`static Integer valueOf(int i)` 返回一个表示指定的`int`值得`Integer`实例。

​						`static Integer valueOf(int i)` 表示`String`参数所指示的`int`值



**拆箱：** 在包装类中取出基本类型的数据（包装类->基本数据类型）

​			成员方法：

​						`int intValue()` 以`int`类型返回该`Integer`的值。



## 20.2 自动装箱与自动拆箱

JDK 1.5 之后，基本数据类型和包装类之间可以自动的相互转换。

```java
Integer in = 1;   // 不用写new，相当于Integer in = new Integer(1);

in = in + 2;     
// in + 2 相当于 in.inValue() + 3
// in = in + 2 相当于 in = new Integer(3)
```



## 20.3 基本类型与字符串之间转换

**基本类型 -> 字符串：**

1. 基本类型数据的值 + "":`String s1 = 100+"";`最简单的方式（常用）

2. 使用包装类中的静态方法：

   `static String toString(int i)` 返回一个表示指定整数的`String`对象。

3. 使用String类中的静态方法：

   `static String valueOf(int i)` 返回`int`参数的字符串表示形式。



**字符串->基本类型：**

​	使用包装类的静态方法`parseXX("字符串")`

​		`Integer`类： `static int parseInt(String s)`

​		`Double`类：`static double parseDouble(String s)`





# 21 _Collection集合

集合与数组的区别：

1. **数组**长度固定。**集合**长度可变。
2. **数组**中存储的是统一类型的元素，可以存储基本数据类型值和对象。**集合**存储的都是对象，且对象的类型可以不一致。



## 21.1 集合框架

![21.1插图](F:\研究生\JAVA\JAVASE\JAVASE图\21.1插图.jpg)

![21.1插图2](F:\研究生\JAVA\JAVASE\JAVASE图\21.1插图2.jpg)

`List`接口：有索引、可以存储重复元素、可以保证存取顺序。

​					`add、get、remove、set`

`ArrayList`实现类：底层是**数组**实现的、查询快、增删慢。

​					`add、get、set、size、remove`

`LinkedList`实现类：底层是**链表**实现的、查询慢、增删快。

​					`addFirst、addLast(与add相同)、push(与addFirst相同)、getFirst、getLast、removeFirst、removeLast、pop(与removeFrist相同且都有返回值)、isEmpty`

`Vector`实现类：单线程集合、同步的，被`ArrayList`取代位置。



`set`接口：无索引、不可以存储重复元素、存取无序、遍历要用迭代器或增强for循环。

`HashSet`实现类：底层是**哈希表+红黑树**实现的，无索引、不可以存储重复元素、存取无序。

`LinkedHashSet`实现类：底层是**哈希表+链表**实现的，无索引、不可以存储重复元素、可以保证存取顺序。

`TreeSet`实现类：底层是**二叉树**实现的。一般用于排序。



## 21.2 Collection集合常用功能

`public boolean add(E e)`：添加元素

`public void clear()`：清空集合中所有元素

`public boolean remove(E e)`：删除元素

`public boolean contains(E e)`：判断是否包含给定元素

`public boolean isEmpty()`：判断集合是否为空

`public int size()`：返回元素个数

`public Object[] toArray()`：把集合中的元素，存储到数组中



## 21.3 Iterator迭代器

`Collection`接口中没有索引方法，所以**遍历**要用`Iterator`迭代器。

`hasNext()`：如果迭代具有更多元素，则返回 `true` 。

`next()`：返回迭代中的下一个元素，并移动指针（不是删除元素）。



`Collection`接口中有一个方法：`public Iterator<E> iterator()`，返回此集合中的元素的迭代器：

```java
package com.fun.demo05;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

public class CollectionIterator {
    public static void main(String[] args) {
        Collection<String> coll = new ArrayList<>();

        coll.add("库里");
        coll.add("科比");
        coll.add("姚明");
        coll.add("詹姆斯");
        coll.add("乔丹");
        coll.add("麦迪");
        coll.add("杜兰特");

        Iterator<String> it = coll.iterator();   //接口=实现类 多态

        boolean b = it.hasNext();
        System.out.println(b);          //true
        System.out.println(it.next());  //库里

        while (it.hasNext()) {
            System.out.print(it.next());   //科比姚明詹姆斯乔丹麦迪杜兰特
        }
    }
}
```



## 21.4 增强for循环

`foreach`在`Collection`的父接口`Iterable<T>`中。

格式：

```java
package com.fun.demo05;

import java.util.ArrayList;

public class ReinforceFor {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        for (int i : arr) {
            System.out.print(i);  //12345
        }

        ArrayList<String> str = new ArrayList<>();
        str.add("张三");
        str.add("李四");
        str.add("王五");

        for (String s : str) {
            System.out.print(s); //张三李四王五
        }
    }
}
```



## 21.5 泛型

泛型是一种位置的数据类型，当我们不知道使用什么数据类型的时候，可以使用泛型，

泛型也可以看作是一个变量，用来接收数据类型：

`E e`：Element 元素

`T t`：Type 类型



`ArrayList<E>`集合在定义的时候，不知道会存储什么类型的元素，所以使用泛型。

**创建对象**的时候，就会确定泛型的数据类型，把数据类型作为参数传递给`E`。

```java
ArrayList list = new ArrayList();	//不使用泛型
Iterator<String> it = list.iterator();   //接口=实现类 多态
Object obj = it.next();		//不使用泛型表示
System.out.println(obj);  
/*
好处：可以存储任何数据，因为默认Object类型。
弊端：不安全，不能使用子类特有方法（length()），会引发异常。
*/
```



**自定义泛型：**

类：

```java
public class FanXing<E> {
    private E name;
    
    public E gatName() {
        return name;
    }
    public void setName(E name) {
        this.name = name;
    }
}
```

方法：

```java
public <M> method01(M m) {
    return m;
}
public static <S> method02(S s) {
    return s;
}
```

接口：

```java
public interface FanXingJ<J> {}  
public class Sccc implements FanXingJ<String> {} //让实现类的对象指定泛型

public interface FanXingJ<J> {}
public class Sccc<J>  implements FanXingJ<J> {}
Sccc<String> iface = new Sccc<>();//接口定义泛型
```



**通配符：**`<?>`

不知道使用什么类型来**接收**的时候，此时可以时候`？`，表示通配符。

**ps.** 只能作为**方法参数**传递使用。

```java
public static void printArray(ArrayList<?> list) {
    Iterator<String> it = list.iterator();
    while (it.hasNext()) {
        Object o = it.next();  //不知道什么类型，只能Object类型定义
        System.out.print(o);   
    }
}
```

`<? extends E>`：泛型**上限**限定，代表使用的只能是`E`的**子**类或本身。

`<? super E>`：泛型**下限**限定，代表使用的只能是`E`的**父**类或本身。

<!--2022年2月24日00:06:48-->



## 21.6 红黑树

**特点：**趋近于平衡树，查询速度非常快，查询叶子结点最大次数和最小次数不能超过2倍（平衡树概念，节点高度差不能超过1）。

**约束：**

1. 节点可以是黑色或者红色；
2. 根节点是黑色；
3. 叶子结点是黑色；
4. 每个红色的节点的子节点都是黑色的；
5. 任何一个节点到其每一个叶子结点的所有路径上的黑色节点的数量相同。



## 21.7 哈希表

**哈希值：**是一个十进制的整数，有系统随机给出的一个逻辑地址，不是真实的物理地址。

**方法源码：**

`public native int hashCode();`

`native`：代表方法调用的是本地操作系统的方法。



### 21.7.1 _HashSet集合

`new HashSet<>();` 哈希表： 数组+链表/红黑树(8字节以上查询快)

`Set`集合在调用`add`方法的时候，会调用元素的`hashCode`方法和`equals`方法，判断元素是否重复。

若两个元素的哈希值相同（哈希冲突）且`equals`返回`ture`，则判定两个元素相同，不会把重复元素存储到集合中。



**自定义对象**若想要实现成员变量相同，则哈希值相同，就必须要重写`equals`和`hashCode`方法。IDEA可以快捷生成。



### 21.7.2 _LinkedHashSet集合

`new LinkedHashSet<>();` 哈希表：（数组+链表/红黑树）+链表：多了一条链表（记录元素的存储顺序），保证元素**有序**。

方法与`HashSet`一样。



## 21.7-5 可变参数

```java
public class Demo01VarArgs {
    public static void main(String[] args) {
        int i = add(10,20);
    }
    //int...arr会根据传递过来的参数数量new int[]{...}
    public static int add(int...arr) {	// 可变参数必须写在末尾且只能有一个
        System.out.println(arr);
        System.out.println(arr.length);
        int sum = 0;
        for (int i : arr) {
            sum += i;
        }
        return sum;
    }
}
```

**ps.** 可变参数必须写在**末尾**且只能有**一个**。 `Collections`工具类中的`addAll`方法就是用了可变参数。



# 22 _Map集合（字典）

接口：`Map<K,V>`			**K--key键		V--value值**

将键映射到值的对象。 地图不能包含重复的键; 每个键可以映射到最多一个值。

key不可以重复，value可以重复，与python字典一样。



## 22.1 Map常用实现类

`Class HashMap<K, V> implements Map<K, V>`：哈希表+链表/红黑树，无序。

`Class LinkedHashMap<K,V> implements Map<K, V>`：相较于`HashMap`，有序。



## 22.2 Map接口常用方法

` public V put(K key, V value)`：将指定的值与该映射中的指定键添加到Map集合。

`public V remove(Object key)`：如果存在，从该Map集合中删除一个键的映射。

`public V get(Object key)`：返回到指定键所映射的值，或 `null`如果此映射包含该键的映射。

`boolean containskey(Object key)`：如果此映射包含指定键的映射，则返回 `true` 。

`public Set<K> ketSet()`：返回此Map集合中包含的键的`Set`视图。

`public Set<Map.Entry<K, V>> entrySet()`  ：返回此Map集合中包含的映射的[`Set`](https://www.matools.com/file/manual/jdk_api_1.8_google/java/util/Set.html)视图。



## 22.3 键找值&键值对遍历

**键找值：**

```java
public class SeeMap {
    public static void main(String[] args) {
        Map<String, Integer> mp = new HashMap<>();

        mp.put("迪丽热巴", 165);
        mp.put("古力娜扎", 166);
        mp.put("杨幂", 163);

        System.out.println(mp);

        // 1.使用Map集合中的方法keySet()，把Map集合所有的key取出来，存储到一个Set集合中
        Set<String> set = mp.keySet();

        // 2.遍历Set集合，获取Map集合中的每一个key
        Iterator<String> it = set.iterator();
        while (it.hasNext()) {
            String key = it.next();
            //3. 通过Map集合中的方法get(key)，通过key找到value。
            Integer value = mp.get(key);
            System.out.println(key+"="+value);
        }
    }
}
/*
{迪丽热巴=165, 杨幂=163, 古力娜扎=166}
迪丽热巴=165
杨幂=163
古力娜扎=166
*/
```

**键值对：** 使用内部接口`Map.Entry<K, V>`

```java
public class LookMap {
    public static void main(String[] args) {
        Map<String, Integer> mp = new HashMap<>();

        mp.put("迪丽热巴", 165);
        mp.put("古力娜扎", 166);
        mp.put("杨幂", 163);

        System.out.println(mp);

        // 1.使用Map集合中的方法entry()，把Map集合中的多核Entry对象取出来，存储到一个Set中
        Set<Map.Entry<String, Integer>> set = mp.entrySet();
        // 2.遍历Set集合，获取每一个Entry对象
        Iterator<Map.Entry<String, Integer>> it = set.iterator();
        while (it.hasNext()) {
            map.Entry<String, Integer> entry = it.next();
            // 3.使用Entry对象中的方法getKey()和getValue()获取键与值
            String key = entry.getKey();
            Integer value = entry.getValue();
            System.out.println(key + "=" + value);
        }
    }
}
/*
{迪丽热巴=165, 杨幂=163, 古力娜扎=166}
迪丽热巴=165
杨幂=163
古力娜扎=166
*/
```



## 22.4 HashMap存储自定义键值对数据

`Map`集合保证`key`是唯一的，所以作为`key`的元素，必须重写`hashCode`和`equals`方法，以保证`key`唯一。

**自定义对象**若想要实现成员变量相同，则哈希值相同，就必须要重写`equals`和`hashCode`方法。IDEA可以快捷生成。



## 22.5 LinkedHashMap-Hashtable

`class LinkedHashMap extends HashMap`  继承于`HashMap`集合。区别是有序存储。

`Hashtable<K, V> implements Map<K, V>`：是同步的老集合（jdk1.0），属于线程安全的集合，不能存储null值，null键，和`vector`集合一样，在jdk1.2之后被更先进的集合（`HashMap`、`ArrayList`）取代。

**ps.** `Properties`集合是`Hashtable`的子类，是唯一和IO流相结合的集合。



<!--2022年2月24日23:46:02-->





# 23异常

​	异常指的是程序在执行过程中，出现的非正常的情况，最终会导致JVM的非正常停止。

在Java等面向对象的变成语言中，异常本身是一个**类**，产生异常就是创建异常对象并抛出一个异常对象。Java处理异常的方式是**中断处理**。

**ps.** 异常不是语法错误，语法错了，编译不通过，不会产生字节码文件。



`Throwable`异常根类

​					`Error` 子类，指严重错误Error，无法通过处理的错误，只能事先避免，好比绝症。

​					`Exception` 子类，编译期异常，通常所指的异常，由于操作不当导致，可以避免。

​										`RuntimeException` 运行期异常，Java程序运行过程中出现的错误。



Java异常处理的五个关键字：`try {}-catch() {}` 、`finally`、`throw`、`throws`



## 23.1 throw关键字

**作用：**可以使用throw关键字在指定的方法中抛出指定的异常。

**使用格式：**

```java
public class Demo03Throw {
    public static void main(String[] args) {
        int[] arr = null;
        getElement(arr, 3);
    }

    public static int getElement(int[] arr, int index) {
        if (arr == null) {
            throw new NullPointerException("传递的数组值是null");
        }
        if (index<0 || index>arr.length-1){
            throw new ArrayIndexOutOfBoundsException("数组索引越界");
        }

        int ele = arr[index];
        return ele;
    }
}
/*   会直接中断程序，第二个异常抛不出来。
Exception in thread "main" java.lang.NullPointerException: 传递的数组值时null
	at com.fun.demo07.Demo03Throw.getElement(Demo03Throw.java:11)
	at com.fun.demo07.Demo03Throw.main(Demo03Throw.java:6)
*/
```

**ps.** `Object.requireNonNull()`是一个非空判断，与上面代码块功能类似。

**注意事项：**

1. `throw`关键字必须写在方法的内部。

2. `throw`关键字后边`new`的对象必须是`Exception`或者`Exception`的子类对象。

3. `throw`关键字后边抛出指定的异常对象，我们就必须处理这个异常对象。

   `RuntimeException`或`RuntimeExceptioin`的子类对象默认交给JVM处理；而编译异常（写代码的时候报错），我们就必须处理这个异常，要么`throw`，要么`try...catch`。





## 21.2  throws关键字

**作用：**当方法内部抛出异常对象的时候，那么我们就必须处理这个异常对象，可以使用`throws`关键字处理异常对象，会把异常对象声明抛出给方法的调用者处理，最终交给JVM处理——>中断处理。

**使用格式：**在方法声明时使用。

```java
public class Demo02Throws {
    public static void main(String[] args) throws FileNotFoundException {	// 红线出现在main函数里，所以main用了throws
        readFile("d:\\a.txt");
    }

    public static void readFile(String fileName) throws FileNotFoundException {
        if (!fileName.equals("c:\\a.txt")) {
            throw new FileNotFoundException("传递文件路径错误");
        }
    }
}
/*
Exception in thread "main" java.io.FileNotFoundException: 传递文件路径错误
	at com.fun.demo07.Demo02Throws.readFile(Demo02Throws.java:13)
	at com.fun.demo07.Demo02Throws.main(Demo02Throws.java:8)
*/
```

**ps.** `throws`后面声明的异常父类包含子类，所以声明父类即可。



## 23.3 捕获异常try {}-catch() {}

**作用：** 在`catch`中写出处理异常的代码，保证程序可以继续执行。

1. 使用`try`将可能出现异常代码包装起来，执行过程中，一旦出现异常，就会生成一个对应异常类的对象，根据此对象的类型，取`catch`中进行匹配。

2. 一旦try中的异常对象匹配到某一个catch时，就进入`catch`中进行异常的处理。一旦处理完成，就跳出当前的`try-catch`结构（在没有写`finally`的情况下）。继续执行后面代码。

3. `catch`中的异常类型如果没有子父类关系，则谁声明在上，谁声明在下无所谓。

   `catch`中的异常类型如果满足子父类关系，则要求子类一定声明在父类上面。否则，报错。

```java
public class Demo01Exception {
    public static void main(String[] args) {
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
        Date date = null;
        try {
            date = sdf.parse("1999-0909");  // 编译异常
        } catch (ParseException e) {
            e.printStackTrace();
        }

        int[] arr = {1, 2, 3};
        try {
            System.out.println(arr[3]);         // 运行期异常
        } catch (Exception e) {
            System.out.println(e);
        }

        System.out.println(date);
        System.out.println("后续代码");

        int[] arr_e = new int[1024*1024*1024];  // 错误异常，必须缩小数组长度才能解决
    }
}
/*
java.text.ParseException: Unparseable date: "1999-0909"
	at java.base/java.text.DateFormat.parse(DateFormat.java:396)
	at com.fun.demo07.Demo01Exception.main(Demo01Exception.java:12)
java.lang.ArrayIndexOutOfBoundsException: Index 3 out of bounds for length 3
null
后续代码
Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
	at com.fun.demo07.Demo01Exception.main(Demo01Exception.java:27)
*/
```

**ps.** `try-catch`可以像`switch-case`那样写多个`catch`。



## 23.4 finally代码块

`finally`中的代码一定会被执行，即使`catch`中有异常或者`try`或`catch`中有`return`语句，`finally`也会执行。

```java
public class Demo04Finally {
    public static void main(String[] args) {
        try {
            int a = 10;
            int b = 0;
            System.out.println(a / b);
        }catch (ArithmeticException e) {
            e.printStackTrace();
        }catch (Exception e) {
            e.printStackTrace();
        }finally {
            System.out.println("finally代码块执行!");
        }
    }
}
/*
java.lang.ArithmeticException: / by zero
	at com.fun.demo07.Demo04Finally.main(Demo04Finally.java:8)
finally代码块执行!
*/
```

**应用场景：** 像数据库连接、输入输出流、网络编程Socket等资源，JVM是不能自动回收的，我们需要手动的进行资源的释放。此时的资源释放，就需要声明在`finally`中。



## 23.5 自定义异常

如何自定义异常类：

1. 继承于现有的异常结构：`RuntimeException` 、`Exception`
2. 提供全局常量：`seriaLVersionUID`，表示自定义异常类的唯一标识。
3. 提供重载构造器。

```java
public class MyException extends RuntimeException {
    static final long seriaLVersionUID = -712782163782617831L;

    public MyException(){

    }

    public MyException(String msg) {
        super(msg);
    }
}
```

<!--2022年2月27日00:00:20-->





# 24 进程_线程

## 24.1 程序、进程、线程

**程序(program)：** 是为完成特定任务、用某种语言编写成的一组指令的集合。即指一段静态的代码，静态对象。

**进程(process)：** 是程序的一次执行过程，或是正在运行的一个程序。是一个动态的过程：有它自身的产生、存在、和消亡的过程、------生命周期。

**线程(thread)：** 进程可进一步细化为线程，是一个程序内部的一条执行路径。

​						线程作为调度和执行的单位，每个线程拥有独立的运行栈和程序计数器(pc)，线程切换的开销小。

​						一个进程中的多个线程共享相同的内存单元/内存地址空间。它们从同一堆中分配对象，可以访问相同的变量和对象。这就使得线程间图片通信更简洁、高效。但多个线程操作共享的系统资源可能就会带来安全隐患。



## 24.2 线程的创建和使用*

**判断**程序是不是多线程：能否用一条线画出程序执行顺序。

### 24.2.1 创建(继承Thread类)

**多线程的创建:**

**方式一：**继承`Thread`类

1. 创建一个继承于Thread类的子类；
2. 重写Thread类的run();
3. 创建Thread类的子类的对象；
4. 同个此对象调用start()。

```java
// 创建一个继承于Thread类的子类；
public class Demo01Thread extends Thread {
    //重写Thread类的run()，将此线程执行的操作声明在run()中;
    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            if (i % 2 ==0) {
                System.out.println(i);
            }
        }
    }
}
```

```java
public class ThreadTest {
    public static void main(String[] args) {
        //创建Thread类的子类的对象；
        Demo01Thread thread = new Demo01Thread();

        //同个此对象调用start()。直接调用run()就不是多线程了
        thread.start(); //1.启动当前线程 2.调用当前线程run()
    }
}
```

**注意事项：**

1. 必须调用start()方法才能创建线程，直接调用run()不行。
2. 不可以让已经start()的线程再次执行，会报IllegaLThreadException异常。需要重新创建一个线程的对象。

**匿名写法：**

```java
public class ThreadTest {
    public static void main(String[] args) {
		new Thread(){
            @Override 
            pubilc void run() {
                for (int i = 0; i < 100; i++) {
                    if (i % 2 == 0) {
                        System.out.println(Thread,currentTrread().getName() + ":" + i);
                    }
                }
            }
        }.start();

    }
}
```



### **24.2.2 使用**

**Thread类常用方法：**

1. `start():` 启动当前线程；嗲用当前线程的run()
2. `run():` 通常需要重写Thread类中的此方法，将创建的线程要执行的操作声明在此方法中
3. `currentThread():` 静态方法，返回执行当前代码的线程，可直接使用给main函数命名。
4. `getName():` 获取当前线程名字
5. `setName():` 设置当前线程名字
6. `yiekld():` 释放当前CPU的使用权，但谁抢到不一定。
7. `join():` 在线程a中调用线程b的join()，此时线程a就进入阻塞状态，直到线程b完全执行完以     后，线程a才结束阻塞状态。
8. `stop():` 已过时，强制结束当前线程。
9. `sleep(long millitime):` 静态方法，让当前线程“睡眠”指定的毫秒数。在指定时间内当前线程是阻塞状态。
10. `isAlive():` 判断当前线程是否存活。



**线程的优先级：**

`Thread.MAX_PRIORITY:10`	`// Thread类中的成员变量`

`Thread.MIN_PRIORITY:1`

`Thread.NORM_PRIORITY:5`

1. `getPriority():` 获取优先级
2. `setPriority():` 设置优先级

说明：高优先级线程要抢占低优先级线程cpu的执行权。但只是从概率上讲，高优先级的线程高概率的情况下被执行。并不意味着只有当高优先级的线程执行完以后，低优先级的线程才执行。



### **24.2.3 更多创建多线程方式**（使用Runnable接口）

**方式二：**

1. 创建一个实现了Runnable接口的类
2. 实现类取实现Runnable中的抽象方法：run()
3. 创建实现类的对象
4. 将此对象作为参数传递到Thread类的构造器中，创建Thread类的对象
5. 通过Thread类的对象调用start()

```java
package com.fun.demo08;

public class RunnableDemo01 {
    public static void main(String[] args) {
        RunnableTest t1 = new RunnableTest();
        System.out.println("主线程！");
        Thread t2 = new Thread(t1);		//构造方法重载
        t2.start();
    }
}

class RunnableTest implements Runnable {
    @Override
    public void run() {
        System.out.println("线程创建啦！");
    }
}
```

**方式一**与**方式二**比较：

开发中优先选择方式二。

1. 类是单继承的，而接口实现的方式没有这种局限性。
2. 实现的方式更适合来处理多个线程有共享数据的情况，不用写static。



**JDK5.0新增**的两个线程创建方式：

1. **实现`Callable`接口：** 相比Runnable，功能更强大。

   1. call()可以有返回值。
   2. call()可以抛出异常，被外面的操作捕获，获取异常信息。
   3. Callable是支持泛型的。

2. 实现**线程池**：

   **背景：**经常创建和销毁、使用量特别大的资源，比如并发情况下的线程，对性能影响很大。

​		**思路：** 提前创建好多个线程，放入线程池中，使用时直接获取，使用玩放回池中。可以避免频繁创建销毁、实现重复利用。类似生活中的公共交通工具。

​		**好处：**

1. 提高相应速度。（减少了创建新线程的时间）

2. 降低资源消耗。（重复利用线程池中线程，不需要每次都创建）

3. 便于线程管理。

   `corePoolsize`：核心池大小

   `maximumPoolSize`：最大线程数

   `keepAliveTime`：线程没有任务时最多保持多长时间后会终止

​					



## 24.3 线程的生命周期

![24.3插图](F:\研究生\JAVA\JAVASE\JAVASE图\24.3插图.jpg)



## 24.4 线程的同步*

**多线程潜在的安全问题：**

1. 卖票过程中，出现了重票、错票等线程安全问题。
2. 练习421的卖票系统中，如果一个线程在执行if语句后被占用资源，可能会导致0号票的出现，实际条件是`ticket>0`。

**解决方案：** 当一个线程a在操作ticket的时候，其他线程不能参与进来。直到线程a操作玩ticket时，其他线程才可以开始操作ticket。这种情况即使线程a出现了阻塞，也不能被改变。 

在java中，通过**同步**机制，来解决线程安全问题。	 **同步代码块** 和 **同步方法**

**方式一：同步代码块**

```java
static Object 同步监视器 = new Object();  //需要对象类型，使用接口方式可以考虑this
synchronized(同步监视器) {
    //仅包含需要被同步的代码，操作共享数据的代码，即为只需要被同步代码。
    //同步监视器，俗称：锁。任何一个类的对象，都可以充当锁。
    //要求：多个线程必须要共用同一把锁。
}
```

**方式二：同步方法**

```java
private synchronized void show() {		
    if (ticket > 0) {
        try {
            Thread.sleep(100);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println(Thread.currentThread().getName() + "卖出票号为：" + ticket);
        ticket--;
    }
}
```

**注意事项：**

1. 同步方法仍然涉及到同步监视器，只是不需要显示声明。
2. 非静态同步方法，同步监视器是`this`，静态的同步方法，同步监视器是当前类本身。

<!--2022年3月18日00:46:02-->



**方式三：Lock接口:**   JDK5.0新增

常用实现类：`ReentrantLock`

```java
class Wind implements Runnable {
    private int ticket = 100;
    //1. 实例化ReentrantLock
    private ReentrantLock lock = new ReentrantLock();

    @Override
    public void run() {
        while (true) {
            try {
                //2. 调用锁定方法 lock()
                lock.lock();
                if (ticket > 0) {
                    try {
                        Thread.sleep(100);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }

                    System.out.println(Thread.currentThread().getName() + "卖出票号为：" + ticket);
                    ticket--;
                }
                else {
                    break;
                }
            }finally {
                //3. 调用解锁方法 unlock()
                lock.unlock();
            }
        }
    }
}
```

**面试题：** `synchronized`与`Lock`的异同？

相同点：二者都可以解决线程安全问题

不同：`synchronized`机制在执行相应的同步代码以后，自动的释放同步监视器，`Lock`需要手动启动（`Lock()`），同时结束同步也需要手动的实现（`unlock()`）





## 24.5 线程的通信

例：使用两个线程打印1-100，交替打印。

使用`wait()`来手动阻塞线程，wait会自动释放锁，再用`notify()`唤醒线程。



**线程通信的三个方法：**

1. `wait()` 一旦执行此方法，当前线程就进入阻塞状态，并释放同步监视器。
2. `notify()` 一旦执行此方法，就会唤醒被wait的线程，如果有多个，就唤醒优先级最高的那个。
3. `notifyAll()` 一旦被执行，就会唤醒所有被wait的线程。

**说明：**

1. 这三个方法必须使用在同步代码块或同步方法中。
2. 这三个方法的调用者必须是同步代码块或同步方法中的同步监视器，否则出现`IllegaLMonitorStateException`异常。
3. 这三个方法是定义在`java.lang.Object`类当中。



# 25 枚举类和注解

## **一、枚举类的使用**

1. 枚举类的理解：类的对象只有有限个，确定的。我们称此类为枚举类。
2. 当需要定义一组常量时，强烈建议使用枚举类。
3. 如果枚举类中只有一个对象，则可以作为单例模式的实现方式。



## **二、如何定义枚举类**

**方式一：**JDK5.0之前，自定义枚举类。

```java
package com.fun.demo09;

public class SeasonTest {
    public static void main(String[] args) {
        Season spring = Season.SPRING;
        System.out.println(spring);
    }
}

//自定义枚举类
class Season {
    //1.声明Season对象的属性：private final修饰
    private final String seasonName;
    private final String seasonDesc;

    //2.私有化类的构造器
    private Season(String seasonName, String seasonDesc) {
        this.seasonName = seasonName;
        this.seasonDesc = seasonDesc;
    }

    //3.提供当前枚举类的多个对象：声明为 public static final
    public static final Season SPRING = new Season("春天", "春暖花开");
    public static final Season SUMMER = new Season("夏天", "夏日炎炎");
    public static final Season AUTUMN = new Season("秋天", "秋高气爽");
    public static final Season WINTER = new Season("冬天", "冰天雪地");

    //4.其他诉求1：获取枚举类对象的属性
    public String getSeasonName() {
        return seasonName;
    }

    public String getSeasonDesc() {
        return seasonDesc;
    }

    //4.其他诉求2：提供toString()方法
    @Override
    public String toString() {
        return "Season{" +
                "seasonName='" + seasonName + '\'' +
                ", seasonDesc='" + seasonDesc + '\'' +
                '}';
    }
}
/*
*Season{seasonName='春天', seasonDesc='春暖花开'}
*/
```

**方式二：**JDK5.0时，可以使用`enmu`关键字定义枚举类。

```java
package com.fun.demo09;

public class Stringtest {
    public static void main(String[] args) {
        Season1 summer = Season1.SUMMER;
        System.out.println(summer);         //Season{seasonName='夏天', seasonDesc='夏日炎炎'}

        //定义枚举类默认继承于java.lang.Enum
        System.out.println(Season1.class.getSuperclass());   //class java.lang.Enum
    }
}

//使用enmu关键字枚举类
enum Season1 {
    //1.提供当前枚举类的对象，多个对象之间用','隔开，末尾用‘;’
    SPRING("春天", "春暖花开"),
    SUMMER("夏天", "夏日炎炎"),
    AUTUMN("秋天", "秋高气爽"),
    WINTER("冬天", "冰天雪地");

    //2.声明Season对象的属性：private final修饰
    private final String seasonName;
    private final String seasonDesc;

    //3.私有化类的构造器
    private Season1(String seasonName, String seasonDesc) {
        this.seasonName = seasonName;
        this.seasonDesc = seasonDesc;
    }



    //4.其他诉求1：获取枚举类对象的属性
    public String getSeasonName() {
        return seasonName;
    }

    public String getSeasonDesc() {
        return seasonDesc;
    }

    //4.其他诉求2：提供toString()方法
    @Override
    public String toString() {
        return "Season{" +
                "seasonName='" + seasonName + '\'' +
                ", seasonDesc='" + seasonDesc + '\'' +
                '}';
    }
}
```



## 三、Enum类中的常用方法

`values():` 返回枚举类型的对象数组。该方法可以很方便地遍历所有的枚举类。

`valueOf(String str):` 可以把一个字符串转为对应的枚举类对象。要求字符串必须是枚举类对象的“名字”。如果不是，会报异常：`IllegalArgumentException`

`toString():` 返回当前枚举类对象常量的名称。



## 四、使用enum关键字定义的枚举类实现接口的情况

**情况一：**实现接口，在enum类中实现抽象方法。

**情况二：**每个对象实现不同的方法。

```java
enum Season1 implements info {
    //1.提供当前枚举类的对象，多个对象之间用','隔开，末尾用‘;’
    SPRING("春天", "春暖花开"){
        @Override
        public void show() {
            System.out.println("春天在哪里？")
        }
    },
    SUMMER("夏天", "夏日炎炎"){
        @Override
        public void show() {
            System.out.println("宁夏！")
        }
    },
    AUTUMN("秋天", "秋高气爽"){
        @Override
        public void show() {
            System.out.println("秋天不回来！")
        }
    },
    WINTER("冬天", "冰天雪地"){
        @Override
        public void show() {
            System.out.println("大约在冬季！")
        }
    };

```



## 五、 注解(Annotation)

@Annotation其实就是代码里的**特殊标记**，在不改变原有逻辑的情况下，增加一些补充信息。可以像**修饰符**一样被使用，可用于修饰**包，类，构造器，方法，成员变量，参数，局部变量**的声明，这些信息被保存在Annotation的`name=value`对中。

**实例一：** 文档相关注解

```java
/**
* @author shkstart
* @version 1.0
* @see Math.java
*/
public class JavadocTest {
    /**
    * 程序的主方法，程序的入口
    * @param args String[] 命令行参数
    */
    public static void main(String[] args) {
        
    }
    /**
    * 求圆的面积的方法
    * @param radius double 半径值
    * @return double 圆的面积
    */
    public static double getArea(double radius) {
        return Math.PI * radius * radius;
    }
}
```

**实例二：** 在编译时进行格式检查（JDK内置的三个基本注解）

`@Override` 限定重写父类方法，该注解只能用于方法。

`@Deprecated` 用于表示所修饰的元素（类，方法等）已过时。通常是因为所修饰的结构危险或存在更好的选择。

`@SuppressWarnings` 抑制编译器警告。

**实例三：** 跟踪代码的依赖性，实现替代配置文件功能。

`@WebServlet("/login")` 

<!--2022年3月24日00:07:34-->



### 1. 如何自定义注解

参照`@SuppressWarnings` 定义方法：

```java
public @interface MyAnnotation {
    String value() default "hellow";	//可以用default指定成员默认值
}

@MyAnnotation(value = "自定义")
```

**注：** 如果自定义的注解没有成员，表明是一个表示作用。

如果注解有成员，在使用注解时，需要指定成员值。



### 2. jdk提供的4种元注解

**元注解：** 对现有的注解进行解释说明的注解。

`@Retention` 指明所修饰的Annotation生命周期。

`SOURCE` \ `CLASS`（默认）\ `RUNTIME`（反射获取条件）



`@Target` 用于指定被修饰的Annotation能用于修饰哪些程序元素。



`@Documented` 表示所修饰的注解在被javadoc解析式，保留下来。



`@Inherited` 被修饰的Annotation将具有继承性。







# 26 IO流

解决数据的Input、Output问题。

## 26.1 File类的使用

1. File类的一个对象，代表一个文件或一个文件目录。
2. File类声明在`java.io`包下。
3. File类中涉及到关于文件或文件目录的创建、删除、重命名、修改时间、文件大小的方法，并未涉及到写入或读取文件内容操作。如果需要读取或写入文件内容，必须使用IO流来完成。

**常用构造器：**

```java
public File(String pathname):
```

**String pathname：**文件路径，可以是绝对路径，也可以说是相对路径。



```java
public File(String parent, String child):
```

**String child:**接parent给出的路径后续。可以是文件，也可以说是目录。



```java
public File (File parent, String child):
```

**File parent:**继承File对象给出的路径。套娃。



**常用方法：**

`public String gerAbsolutePath():`获取绝对路径

`public String getPath():`获取路径

`public String getName():`获取名称

`public String getParent():`获取上层文件目录路径。若无，返回null。

`public long length():`获取文件长度（即：字节数）。不能获取目录长度。

`public long lastModified():`获取最后一次的修改时间，毫秒值。



`public String[] list():`获取指定目录下得所有文件或者文件目录的名称数组。相对路径。

`public File[] listFiles():`获取指定目录下的所有文件或者文件目录的FIle数组。绝对路径。



`public boolean renameTo(File dest):`把文件重命名为指定的文件路径。要想保证返回true，需要file1在硬盘中是存在的，且file2不能在硬盘中存在。如果目录路径不同，也会改变文件路径。



`public boolean isDirectory():`判断是否是目录

`public boolean isFile():`判断是否是文件

`public boolean exists():`判断是否存在

`public boolean canRead():`判断是否可读

`public boolean canWrite():`判断是否可写

`public boolean isHidden():`判断是否隐藏



`public boolean createNewFile():`创建文件。若文件存在，则不创建，返回false。

`public boolean mkdir():`创建目录。若此目录存在，则不创建。若此目录上层目录不存在，也不创建。

`public boolean mkdirs():`创建目录。若上层目录不存在，则一并创建。



`public boolean delete():`删除文件或文件夹，java中删除不走回车站。

```java
import java.io.File;

public class FileTest {
    public static void main(String[] args) {
        File f1 = new File("hellow.txt");
        File f2 = new File("F:\\workplace\\javaworkplace\\holloworld\\src\\com\\demo\\demo02\\hi.txt");

        if (f1.renameTo(f2)) {
            System.out.println("true");
        }
        else {
            System.out.println("false");
        }
    }
}
```



## 26.2 I/O原理

I/O技术用于处理设备之间的数据传输。

Java程序中，对于数据的输入/输出造作以**流(stream)**的方式进行。`java.io`包下提供了各种“流”类和接口，通过**标准的方法**输入或输出数据。



按操作**数据单位**不同分为：**字节流（8bit）**`InputStream OutputStream`，**字符流（16bit）**`Reader Write`

按数据流的**流向**不同分为：**输入流，输出流**

按流的**角色**的不同分为：**节点流，处理流**



**抽象基类：**`InputStream OutputStream Reader Write`

**节点流：**`FileInputStream FileOutputStream FileReader FileWrite`

**缓冲流：**`BufferedInputStream BufferedOutputStream BufferedReader BufferedWrite`



### 26.2.1 节点流

#### 26.2.1.1 **`FileReader`**

```java
    @Test
    public void testFileReader() throws IOException {
        //1. 实例化File类的对象,指明要操作的文件
        File file = new File("hellow.txt");
        //2. 提供具体的流
        FileReader fr = new FileReader(file);

        //3. 数据的读入
        //read():返回读入的一个字符。如果达到文件末尾，返回-1
        //方式一
        int data = fr.read();
        while (data != -1) {
            System.out.print((char) data);
            data = fr.read();
        }
        //方式二:语法上修改
        int data;
        while ((data = fr.read()) != -1) {
            System.out.println((char) data);
        }

        //4. 流的关闭操作
        fr.close();
    }
}
```

**说明：**

1. read():返回读入的一个字符。如果达到文件末尾，返回-1；

   1. read(char[] cbuf):返回每次读入cbuf数组中的字符个数。如果达到文件末，返回-1

      ```java
          @Test
          public void TestFileReader1() {
              FileReader fr = null;
              try {
                  //1.File类的实例化
                  File file = new File("hellow.txt");
      
                  //2.FileReader流的实例化
                  fr = new FileReader(file);
      
                  //3.读入的操作
                  //read(char[] cbuf):返回每次读入cbuf数组中的字符个数。如果达到文件末，返回-1
                  char[] cbuf = new char[5];
                  int len;
                  while ((len = fr.read(cbuf)) != -1) {
                      // 错误写法        hellowrld123ld
      //                for (int i = 0; i < cbuf.length; i++) {
      //                    System.out.print(cbuf[i]);
      //                }
                      //正确写法         hellowrld123
                      for (int i = 0; i < len; i++) {
                          System.out.print(cbuf[i]);
                      }
                  }
              } catch (IOException e) {
                  e.printStackTrace();
              } finally {
                  //4.资源的关闭
                  try {
                      fr.close();
                  } catch (IOException e) {
                      e.printStackTrace();
                  }
              }
          }
      ```

      

2. 异常的处理：为了保证流资源一定可以执行关闭操作，需要使用`try-catch-finally`处理。



#### 26.2.1.2 **`FileWriter`**

```java
    // 从内存中写出数据到硬盘的文件里
    @Test
    public void testFileWriter() throws IOException {
        //1.提供File类的对象，指明写出的文件
        File file = new File("hello1.txt");

        //2.提供FileWriter的对象，用于数据的写出
        FileWriter fw = new FileWriter(file);       //若没有文件，会自动创建

        //3.写出的操作
        fw.write("I have a dream!\n");
        fw.write("You need to have a dream!");

        //4.流的关闭处理
        fw.close();
    }
}
```

**说明：**

1. 输出操作，对应的File可以不存在。如果不存在，在输出的过程中，会自动创建此类文件。 
2. 如果存在 ，且流使用的构造器是`FileWriter(file, false)`：对原有文件的覆盖（append参数），true则是在原有基础上添加内容。



#### 26.2.1.3 FileReader&FileWriter结合使用

```java
    // 使用Read和Writer复制文件
    @Test
    public void testFileReadFileWriter() throws IOException {
        File srcFile = new File("hello1.txt");
        File destFile = new File("hello2.txt");

        FileReader fr = new FileReader(srcFile);
        FileWriter fw = new FileWriter(destFile);

        char[] cbuf = new char[5];
        int len;
        while ((len = fr.read(cbuf)) != -1) {
            fw.write(cbuf, 0, len);
        }

        fr.close();
        fw.close();
    }
```



#### 26.2.1.4 字节流的应用

```java
    // 使用Read和Writer复制图片 需要使用字节流，否则无法打开
    @Test
    public void testFileReaderFileWriter() throws IOException {
        File srcFile = new File("person.jpg");
        File destFile = new File("person1.jpg");

        FileInputStream fis = new FileInputStream(srcFile);
        FileOutputStream fos = new FileOutputStream(destFile);

        byte[] buffer = new byte[5];
        int len;
        while ((len = fis.read(buffer)) != -1) {
            fos.write(buffer, 0, len);
        }

        fis.close();
        fos.close();
    }
```

**注意事项：**

对于文本文件(.txt, .java, .c, .cpp, .py等)，需要使用字符流传输，尤其是中文。否则可能出现乱码。复制操作除外。

对于非文本文件(.mp4, .jpg, .avi, .doc, .ppt等)需要使用字节流处理。



### 26.2.2 缓冲流

主要作用是提高文件的读写效率。

原因：内部提供了缓冲区，当缓冲区满后再一次性写入，减少交互次数。

```java
    @Test
    public void BufferedStreamTest() throws IOException {
        //1.造文件
        File srcFile = new File("person.jpg");
        File destFile = new File("person2.jpg");

        //2.造流
        //2.1 造节点流  内层
        FileInputStream fis = new FileInputStream(srcFile);   //
        FileOutputStream fos = new FileOutputStream(destFile);
        //2.2 造缓冲流  外层
        BufferedInputStream bis = new BufferedInputStream(fis);
        BufferedOutputStream bos = new BufferedOutputStream(fos);

        //3.复制的细节：读取、写入
        byte[] buffer = new byte[10];
        int len;
        while ((len = bis.read(buffer)) != -1) {
            bos.write(buffer, 0, len);
        }

        //4.资源关闭
        //关闭顺序要求：先关闭外层的流，再关闭内层的流
        bos.close();
        bis.close();
        //关闭外层的时候，内层也会自动关闭
//        fos.close();
//        fis.close();
    }
```



### 26.2.3 转换流

与缓冲流一样，也属于处理流的一种，提供了字节流与字符流之间的转换。

```java
InputStreamReader:`将`InputStream`转换为`Reader
OutputStreamWriter:`将`Writer`转换为`OutputStream
```

**转换流**属于**字符流**中的处理流。



**解码：**字节、字节数组 --> 字符数组、字符串

**编码：**字符数组、字符串  --> 字节、字节数组 



**字符集：**参数2`charsetName`指明了字符集

常见编码表有：ASCII、ISO8859-1、GB2312、GBK、Unicode、UTF-8等。

```java
    //综合使用InputStreamReader和OutputStreamWrite
    @Test
    public void test_revers() throws Exception {
        //造文件、造流
        File file1 = new File("hello1.txt");
        File file2 = new File("hello3.txt");

        FileInputStream fis = new FileInputStream(file1);
        FileOutputStream fos = new FileOutputStream(file2);

        InputStreamReader isr = new InputStreamReader(fis, "UTF-8");
        OutputStreamWriter osw = new OutputStreamWriter(fos, "gbk");

        //读写过程
        char[] cbuf = new char[20];
        int len;
        while ((len = isr.read(cbuf)) != -1) {
            osw.write(cbuf, 0, len);
        }

        //资源关闭
        isr.close();
        osw.close();
    }
```

### 26.2.4 标准输入、输出流

标准的输入流：`System.in`。默认从键盘输入。

标准的输出流：`System.out`。默认从控制台输出。



System类的`setIn(InputStream is)`/`setOut(PrintStream ps)`方法重新指定输入和输出的流。

```java
/* 从键盘输入字符串，要求将读取到的整行字符串转成大写输出。然后继续进行输入操作， 直至当输入“e“或者”exit“时，退出程序。*/    
//方式一
    @Test
    public void useScan() {
        while (true) {
            Scanner sc = new Scanner(System.in);
            System.out.println("Please input a string:");
            String st = sc.next();
            if (st.equals("e") || st.equals("exit")) {
                break;
            }
            System.out.println(st.toUpperCase());
        }
    }

//方式二   System.in -> 转换流 -> BufferedReader的readLine()
    @Test
    public void uesStemIn() {
        BufferedReader br = null;
        try {
            InputStreamReader isr = new InputStreamReader(System.in);
            br = new BufferedReader(isr);

            while (true) {
                System.out.println("Please input a string:");
                String data = br.readLine();    //读一行的方法
                if ("e".equalsIgnoreCase(data) || "exit".equalsIgnoreCase(data)) {
                    System.out.println("Process end!");
                    break;
                }

                String upperCase = data.toUpperCase();
                System.out.println(upperCase);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (br != null) {
                try {
                    br.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
    }
```



### 26.2.5 打印流

`PrintStream:`字节输出流。

`PrintWriter:`字符输出流。

```java
public void test() {
    PrintStream ps = null;
    try {
        FileOutputStream fos = new FileOutputStream(new File("D:\\IO\\test.txt"));
        //创建打印输出流，设置为自动刷新模式（写入换行符或字节‘\n’时都输刷新输出缓冲区）
        ps = new PrintStream(fos, true);
        if (ps != null) {   //把标准输出流（控制台输出）改成文件
            System.setOut(ps);
        }
        
        for (int i = 0; i <= 255; i++) {//输出ASCII字符
            System.out.print((char) i);
            if (i % 50 == 0) {//每50个数据一行
                System.out.println();   //换行
            }
        }
    } catch (FileNotFoundException e) {
        e.printStackTrace();
    } finally {
        if (br != null) {
            try {
                br.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```



### 26.2.6 数据流

为了方便操作Java语言的基本数据类型和String的数据，可以使用数据流。

```java
DataInputStream
DataOutputStream
    // 将内存中的基本数据类型、字符串写出到文件中
    @Test
    public void testDataStream() throws IOException {
        DataOutputStream dos = new DataOutputStream(new FileOutputStream("data.txt"));

        dos.writeUTF("Klee");
        dos.flush();    //刷新操作，写入已有数据
        dos.writeInt(8);
        dos.flush();
        dos.writeBoolean(false);
        dos.flush();

        dos.close();
    }

    //读取方式
    @Test
    public void testR() throws IOException {
        DataInputStream dis = new DataInputStream(new FileInputStream("data.txt"));

        //读取数据顺序要与写入时顺序一致
        String name = dis.readUTF();
        int age = dis.readInt();
        boolean isMale = dis.readBoolean();

        System.out.println(name+" "+age+isMale);

        dis.close();
    }
```



### 对象流

用于存储和读取**基本数据类型数据**或**对象**的处理流。



**序列化：**用`ObjectInputStream`类保存基本数据类型或对象的机制。

**反序列化：**用`ObjectOutputStream`类读取基本数据类型或对象的机制。

注：不能序列化`static`和`transient`修饰的成员变量。

```java
    // 对象流的使用
    // 序列化过程：将内存中的java对象保存到磁盘中或通过网络传输出去
    @Test
    public void test1() {
        ObjectOutputStream oos = null;

        try{
            oos = new ObjectOutputStream(new FileOutputStream("object.dat"));

            oos.writeObject(new String("我爱北京天安门！"));
            oos.flush();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (oos != null) {
                try {
                    oos.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
    }
   // 反序列化过程：将磁盘中的文件还原为内存中的一个Java对象
    @Test
    public void test2() {
        ObjectInputStream ois = null;
        try {
            ois = new ObjectInputStream(new FileInputStream("object.dat"));

            Object obj = ois.readObject();
            String str = (String) obj;
            System.out.println(str);
        } catch (IOException e) {
            e.printStackTrace();
        } catch (ClassNotFoundException e) {
            e.printStackTrace();
        } finally {
            try {
                ois.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
```

如果需要让某个**对象**支持序列化机制，必须让对象实现以下两个接口之一：

**`Serializable`  `Externalizable`**	（没有任何抽象方法的标识接口）

否则，会抛出`NotSerializableException`异常。

`Serializable`中需要当前类提供一个全局常量`serialVersionUID`：

`static final long serialVersionUID = 5651650L`

**注：**除了当前类需要实现`Serializable`接口之外，还必须保证其内部所有属性都是可序列化的。（默认情况下，基本数据类型都是可序列化的）比如：自定义类的成员变量。



### RandomAccessFile流

直接继承与`Object`类，实现了`DataInput`和`DataOutput`接口。既可以做**输入流**，又可以做**输出流**。

构造器：

`public RandomAccessFile(File file, String mode)`

`public RandomAccessFile(String name, String mode)`

创建`RandomAccessFile`类实例需要指定一个**mode参数**，该参数指定了访问模式：

**r:** 只读 （不会创建文件）

**rw:** 读写

**rwd:** 读写，同步文件内容的更新

**rws:** 读写，同步文件内容和元数据的更新



如果`RandomAccessFile`作为**输出流**，若文件不存在，则创建文件；若文件存在，则**覆盖**原有内容，且默认从头开始覆盖（`seek()`指针默认为0）。

1. 若要**覆盖**到其他位置，需要改变`seek()`的值。

2. 若要**插入**新内容，需先将指针之后的数据保存下来，添加内容后再写入。



# 27 网络编程

直接或间接的通过网络协议与其他计算机实现数据交换，进行通讯。

**问题：**

1. 如何准确地定位网络上一台或多台主机；定位主机上的待定的应用？

   ​	IP和端口号

2. 找到主机后如何可靠高效地进行数据传输？

​			提供网络通信协议：TCP/IP（应用层、传输层、网络层、数据链路层+物理层）



## 27.1 IP和域名

Java中使用`InetAddress`类代表IP。

`getHostName()`方法获取域名

`getHostAddress()`方法获取IP地址



```java
    public static void main(String[] args) {
        try {
            InetAddress inet1 = InetAddress.getByName("192.168.10.14");
            System.out.println(inet1);  //  /192.168.10.14
        } catch (UnknownHostException e) {
            e.printStackTrace();
        }
    }
```



**域名：**（例如 www.baidu.com ）通过DNS（域名解析服务器）解析出对应的IP地址。

```java
InetAddress inet2=InetAddress.getByName("www.atguigu.com");
System.out.println(inet2); //  www.atguigu.com/113.96.109.96
```



**本地回路地址：** 127.0.0.1  对应  localhost

```java
InetAddress inet3 = InetAddress.getByName("localhost");
InetAddress inet = InetAddress.getLocalHost();
System.out.println(inet3+"\n"+inet);
//  localhost/127.0.0.1
//  DESKTOP-E541U9A/10.202.3.69
```



## 27.2 **端口号**

不同的**进程**对应不同的端口号。

被规定为一个16位整数：0~65535

**公认端口：**0~1023。被预先定义的服务通信占用（如：HTTP占用端口80，FTP占用端口21，Telnet占用端口23）

**注册端口：**1024~49151。分配给用户进程或应用程序。（如：Tomcat占用端口8080，MySQL占用端口3306，Oracle占用端口1521等）

**动态/私有端口：**49152~65535

端口号与IP地址的组合得出一个网络套接字：**Socket**



## 27.3 TCP/IP & UDP

**TCP协议：**传输控制协议（Transmission Control Protocol)

三次握手、可靠，效率相对低，比如：打电话

**UDP协议：**用户数据协议（User Datagram Protocol）

不需要建立连接、不可靠、效率高，比如：发短信、发电报



### 27.3.1 TCP网络编程

```java
    //例1：客户端发送信息给服务端，服务端将数据显示在控制台上。
    @Test
    public void client() throws IOException {
        // 1. 创建Socket对象，指明服务器的IP和端口号
        InetAddress inet = InetAddress.getByName("127.0.0.1");	//服务器IP地址
        Socket socket = new Socket(inet, 8899);	//端口号
		// 2. 获取一个输出流，用于输出数据
        OutputStream os = socket.getOutputStream();
        os.write("Hollow! I am client.".getBytes());
		// 3. 资源关闭
        os.close();
        socket.close();
    }

    @Test
    public void server() throws IOException {
        // 1. 创建服务器端的ServerSocket，指明自己的端口号
        ServerSocket ss = new ServerSocket(8899); //端口号
        // 2. 调用accept()方法，表示接受来自于客户端的Socket
        Socket socket = ss.accept();
        // 3. 获取输入流
        InputStream is = socket.getInputStream();
		// 4. 读取输入流中的数据
        ByteArrayOutputStream baos = new ByteArrayOutputStream();
        byte[] buffer = new byte[5];
        int len;
        while ((len = is.read(buffer)) != -1) {
            // String str = new String(buffer, 0, len);
            // System.out.println(str);
            baos.write(buffer, 0, len);  //防止中文乱码写法
            System.out.println(baos.toString());
        }
		// 5. 资源关闭
        baos.close();
        is.close();
        socket.close();
        ss.close();
    }

    //例2：客户端发送文件给服务端，服务端将文件保存在本地。
    @Test
    public void client() throws IOException {
        Socket socket = new Socket(InetAddress.getByName("127.0.0.1"), 9090);

        OutputStream os = socket.getOutputStream();

        FileInputStream fis = new FileInputStream(new File("person.jpg"));

        byte[] buffer = new byte[1024];
        int len;
        while ((len = fis.read(buffer)) != -1) {
            os.write(buffer, 0, len);
        }

        fis.close();
        os.close();
        socket.close();
    }


    @Test
    public void server() throws IOException {
        ServerSocket ss = new ServerSocket(9090);

        Socket socket = ss.accept();

        InputStream is = socket.getInputStream();

        FileOutputStream fos = new FileOutputStream(new File("personServer1.jpg"));

        byte[] buffer = new byte[1024];
        int len;
        while ((len = is.read(buffer)) != -1) {
            fos.write(buffer, 0, len);
        }

        fos.close();
        is.close();
        socket.close();
        ss.close();
    }
    //例3：从客户端发送文件给服务端，服务端保存到本地。并返回“发送成功”给客户端。并关闭相应的连接。
    @Test
    public void client() throws IOException {
        Socket socket = new Socket(InetAddress.getByName("127.0.0.1"), 9090);

        OutputStream os = socket.getOutputStream();

        FileInputStream fis = new FileInputStream(new File("person.jpg"));

        byte[] buffer = new byte[1024];
        int len;
        while ((len = fis.read(buffer)) != -1) {
            os.write(buffer, 0, len);
        }

        socket.shutdownOutput(); //关闭数据的输出，让服务端跳出循环，否则因为阻塞式IO方法，服务端没有明确终止接受信号

        // 接受来自于服务器的数据，并显示在控制台上
        InputStream is = socket.getInputStream();
        ByteArrayOutputStream baos = new ByteArrayOutputStream();
        byte[] buffer1 = new byte[20];
        int len1;
        while ((len1 = is.read(buffer1)) != -1) {
            baos.write(buffer1,0,len1);
        }
        System.out.println(baos.toString());

        baos.close();
        is.close();
        fis.close();
        os.close();
        socket.close();
    }

    @Test
    public void server() throws IOException {
        ServerSocket ss = new ServerSocket(9090);

        Socket socket = ss.accept();

        InputStream is = socket.getInputStream();

        FileOutputStream fos = new FileOutputStream(new File("personServer2.jpg"));

        byte[] buffer = new byte[1024];
        int len;
        while ((len = is.read(buffer)) != -1) {
            fos.write(buffer, 0, len);
        }

        // 向客户端发送反馈信息
        OutputStream os = socket.getOutputStream();
        os.write("OK, Got it!".getBytes());

        os.close();
        fos.close();
        is.close();
        socket.close();
        ss.close();
    }
```



### 27.3.2 UDP网络编程

```java
    @Test
    public void sender() throws IOException {

        DatagramSocket socket = new DatagramSocket();

        String str = "UDP send data!";
        byte[] data = str.getBytes();
        InetAddress inet = InetAddress.getLocalHost();
        DatagramPacket packet = new DatagramPacket(data, 0, data.length, inet, 9090);

        socket.send(packet);

        socket.close();
    }

    @Test
    public void receiver() throws IOException {

        DatagramSocket socket = new DatagramSocket(9090);

        byte[] buffer = new byte[100];
        DatagramPacket packet = new DatagramPacket(buffer, 0, buffer.length);

        socket.receive(packet);

        System.out.println(new String(packet.getData(), 0, packet.getLength()));

        socket.close();
    }
```



## 27.4 URL类

统一资源定位符，对应着互联网的某一资源网址。

**URL格式**通常包括5个部分：

`<传输协议>://<主机名>:<端口号>/<文件名>#片段名?参数列表`

例：`http://localhost:8080/examples/beauty.jpg?username=Tom&password=123`

实例化：

```java
public class URLTest {
    public static void main(String[] args) throws MalformedURLException {
        URL url = new URL("http://localhost:8080/examples/beauty.jpg?username=Tom");

//public String getProtocol() 获取URL的协议名
        System.out.println(url.getProtocol());// http
//public String getHost()     获取URL的主机名
        System.out.println(url.getHost()); // localhost
//public String getPort()     获取URL的端口号
        System.out.println(url.getPort()); // 8080
//public String getPath()     获取URL的文件路径
        System.out.println(url.getPath());// /examples/beauty.jpg
//public String getFile()     获取URL的文件名
        System.out.println(url.getFile());// /examples/beauty.jpg?username=Tom
//public String getQuery()    获取URL的查询名
        System.out.println(url.getQuery());// username=Tom
    }
}
```

**URL下载文件：**

```java
    @Test
    public void downloadURL() throws IOException {
        URL url = new URL("http://localhost:8080/examples/beauty.jpg");

        HttpURLConnection urlConnection = (HttpURLConnection) url.openConnection();

        urlConnection.connect();

        InputStream is = urlConnection.getInputStream();
        FileOutputStream fos = new FileOutputStream("download.jpg");

        byte[] buffer = new byte[1024];
        int len;
        while ((len = is.read(buffer)) != -1) {
            fos.write(buffer, 0, len);
        }
        System.out.println("Download finished !");

        // 涉及到资源关闭，最好使用 try-catch-finally 处理异常
        is.close();
        fos.close();
        urlConnection.disconnect();
    }
```



# 28 反射*

**反射(Reflection)**是被视为**动态语言**的关键，反射机制允许程序在执行期间借助于**Reflection API**取得任何类的内部信息，并能直接操作任意对象的内部属性及方法。	**即通过对象来看类的结构**

**正常方式：**

引入需要的“包类“名称 -> 通过`new`实例化 -> 取得实例化对象

**反射方式：**

实例化对象 -> `getClass()`方法 -> 得到完整的“包类”名称



**动态语言：**在运行时代码可以根据某些条件改变自身结构，例如：新的函数、对象、甚至代码可以被引进，已有的函数可以被删除或是其他结构上的变化。主要动态语言：C#、Python、JavaScript、PHP等。

**静态语言：**运行时结构不可改变的语言。如：Java、C、C++。

反射机制、字节码操作可以让Java获得类似动态语言的特性，称“准动态语言”。



**Java反射机制提供的功能：**

在运行时判断任意一个对象所属的类

在运行时构造任意一个类的对象

在运行时判断任意一个类所具有的成员变量和方法

在运行时获取泛型的信息

在运行时调用任意一个对象的成员变量和方法

在运行时处理注解

生成动态代理



**代码举例：**

```java
public class Person {
    private String name;
    public int age;

    public Person() {
    }

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    private Person(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }

    public void show() {
        System.out.println("hahahahahahahahaha!");
    }

    private String showNation(String nation) {
        System.out.println("I am from " + nation);
        return nation;
    }
 }
```

```java
    // 反射之前对于Person的操作
    @Test
    public void test1() {
        //1. 创建Person类对象
        Person p1 = new Person("Tom", 12);

        //2. 通过对象，调用其内部的属性、方法
        p1.age = 10;
        System.out.println(p1.toString());

        p1.show();

        //在Person类的外部，不可以通过Person的对象调用其内部的私有结构。
        //比如：name属性、showNation()方法以及私有构造器
    }

    // 反射之后,对于Person的操作
    @Test
    public void test2() throws Exception {
        Class clazz = Person.class;
        Constructor cons = clazz.getConstructor(String.class, int.class);
        // 1. 通过反射，创建Person的对象
        Object obj = cons.newInstance("Tom", 12);
        Person p = (Person) obj;
        System.out.println(obj.toString()); //Person{name='Tom', age=12}
        System.out.println(p.toString());   //Person{name='Tom', age=12}

        // 2. 通过反射，调用对象指定的属性、方法
        Field age = clazz.getDeclaredField("age");
        age.set(p, 10);
        System.out.println(p.toString());   //Person{name='Tom', age=10}
        // 调用方法
        Method show = clazz.getDeclaredMethod("show");
        show.invoke(p); //hahahahahahahahaha!

        // 通过反射，可以调用Person类的私有结构。比如：私有的构造器、方法、属性。
        // 调用私有构造器
        Constructor cons1 = clazz.getDeclaredConstructor(String.class);
        cons1.setAccessible(true);
        Person p1 = (Person) cons1.newInstance("Jerry");
        System.out.println(p1); //Person{name='Jerry', age=0}
        // 调用私有属性
        Field name = clazz.getDeclaredField("name");
        name.setAccessible(true);
        name.set(p1, "HanMeimei");
        System.out.println(p1); //Person{name='HanMeimei', age=0}
        // 调用私有方法
        Method showNation = clazz.getDeclaredMethod("showNation", String.class);
        showNation.setAccessible(true);
        String nation = (String) showNation.invoke(p1, "China"); //I am from China
        System.out.println(nation); //China
    }
```



## 28.1 理解Class类并获取Class实例*

关于`java.lang.Class`类的理解：

1. 类的加载过程：

   程序经过javac.exe命令以后，会生成一个或多个字节码文件(.class结尾)，接着我们使用java.exe命令对某个字节码文件进行解释运行。相当于将某个字节码文件加载到内存中。此过程成为类的加载。加载到内存中的类，我们就成为运行时类，此运行时类，就作为Class的一个实例。

2. Class的实例就对应着一个运行时类。

3. 加载到内存中的运行时类，会缓存一定的时间。在此时间之内，我们可以通过不同的方式来获取此运行时类。

```java
    // 获取Class实例的方式
    @Test
    public void test3() throws ClassNotFoundException {
        //方式一：调用运行时类的属性: .class  泛型可加可不加
        Class<Person> clazz1 = Person.class;
        System.out.println(clazz1);     //class com.demo.demoFanShe.Person

        //方式二：通过运行时类的对象
        Person p1 = new Person();
        Class clazz2 = p1.getClass();
        System.out.println(clazz2);     //class com.demo.demoFanShe.Person

       //方式三*：调用Class的静态方法：forName(String classPath)
        Class clazz3 = Class.forName("com.demo.demoFanShe.Person");  //会报异常
        System.out.println(clazz3);     //class com.demo.demoFanShe.Person

        //方式四：使用类的加载器：ClassLoader
        ClassLoader classLoader = Test01.class.getClassLoader(); //当前类名
        Class clazz4 = classLoader.loadClass("com.demo.demoFanShe.Person");
        System.out.println(clazz4);     //class com.demo.demoFanShe.Person
    }
```

**可以有Class对象的类型：**

所有类(class)、接口(interface)、数组( [] )、枚举(enum)、注解@interface(annotation)、基本数据类型(primitive)、void

```java
    @Test
    public void test4() {
        Class c1 = Object.class;
        Class c2 = Comparable.class;
        Class c3 = String[].class;
        Class c4 = int[][].class;
        Class c5 = ElementType.class;
        Class c6 = Override.class;
        Class c7 = int.class;
        Class c8 = void.class;
        Class c9 = Class.class;

        int[] a = new int[10];
        int[] b = new int[100];
        Class c10 = a.getClass();
        Class c11 = b.getClass();
        // 只要元素类型与维度一样，就是同一个Class
        System.out.println(c10 == c11);     // true
    }
```



## 28.2 类的加载于ClassLoader的理解



## 28.3 创建运行时类的对象*



## 28.4 获取运行时类的完整结构



## 28.5 调用运行时类的指定结构*



## 28.6 反射的应用：动态代理



# 29 Lambda

