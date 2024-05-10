---
layout: post
title: c_basic_2_operators_expressions
date: 2023-12-27
tags: [c_cpp]
author: taot
---

运算符与表达式

### 1、常用运算符分类

|  运算符类型  |                   作用                   |
| :----------: | :--------------------------------------: |
|  算术运算符  |             用于处理四则运算             |
|  赋值运算符  |         用于将表达式的值赋给变量         |
|  比较运算符  | 用于表达式的比较，并返回一个真值或者假值 |
|  逻辑运算符  |    用于根据表达式的值返回真值或者假值    |
|   位运算符   |           用于处理数据的位运算           |
| sizeof运算符 |             用于求字节数长度             |

### 2、算术运算符

| 运算符 |                           术语                           |
| :----: | :------------------------------------------------------: |
|   +    |                           正号                           |
|   -    |                           负号                           |
|   +    |                            加                            |
|   -    |                            减                            |
|   *    |                            乘                            |
|   \    | 除（两个整型数据相除，得到的结果是整型 -> 结果向下取整） |
|   %    |             取模（取余），只能对整型数据操作             |
|   ++   |                          前自增                          |
|   --   |                          前自减                          |
|   ++   |                          后自增                          |
|   --   |                          后自减                          |

* 除法运算：

```c
int a=10;
int b=3;
printf("%d\n",a/b);		//3		两个整型数据相除，得到的结果是整型 -> 结果向下取整

float c=10.0;
printf("%d\n",c/b);		//1.42857

int d=++a*10			//d=110, a=11
int e=b++*10			//e=30,b=4
```

* 前自增：先自增，再进行表达式计算
* 后自增：先进行表达式计算，再自增
* 前自减：先自减，再进行表达式计算
* 后自减：先进行表达式计算，再自减

**一般建议使用前自增和前自减，能够更具有可读性；后自增和后自减容易产生二义性****

**前置和后置混用，在不同操作系统由于实现不同会有不同的结果。**

### 3、赋值运算符

| 运算符 |  术语  |
| :----: | :----: |
|   =    |  赋值  |
|   +=   | 加等于 |
|   -=   | 减等于 |
|   *=   | 乘等于 |
|   /=   | 除等于 |
|   %=   | 模等于 |

### 4、比较运算符

比较完成后会返回真或假的布尔值

| 运算符 |   术语   |
| :----: | :------: |
|   ==   |  相等于  |
|  ！=   |  不等于  |
|   <    |   小于   |
|   >    |   大于   |
|   <=   | 小于等于 |
|   >=   | 大于等于 |

### 5、逻辑运算符

| 运算符 | 术语 |
| :----: | :--: |
|   ！   |  非  |
|   &&   |  与  |
|  \|\|  |  或  |

* 所有非零的值都是真
* ！ 非 ：非真为假，非假为真
* ！ 的优先级高于 && 
* 单目运算符优先级高于双目运算符，双目运算符优先级高于三目运算符
* && 与：同真为真，其余为假
* || 或：同假为假，其余为真

### 6、运算符的优先级

| 优先级 | 运算符 |   名称或含义   |         使用形式          | 结合方向 |    说明    |
| :----: | :----: | :------------: | :-----------------------: | :------: | :--------: |
|   1    |   []   |    数组下标    |    数组名[常量表达式]     |  左到右  |            |
|   1    |   ()   |     圆括号     | (表达式)，函数名(形参表)  |  左到右  |            |
|   1    |   .    |    成员对象    |        对象.成员名        |  左到右  |            |
|   1    |   ->   |    成员指针    |     对象指针->成员名      |  左到右  |            |
|   2    |   -    |   负号运算符   |          -表达式          |  右到左  | 单目运算符 |
|   2    |   ~    | 按位取反运算符 |          ~表达式          |  右到左  | 单目运算符 |
|   2    |   ++   |   自增运算符   |    ++变量名，变量名++     |  右到左  | 单目运算符 |
|   2    |   --   |   自减运算符   |    --变量名，变量名--     |  右到左  | 单目运算符 |
|   2    |   *    |   取值运算符   |         *指针变量         |  右到左  | 单目运算符 |
|   2    |   &    |  取地址运算符  |          &变量名          |  右到左  | 单目运算符 |
|   2    |   ！   |  逻辑非运算符  |         ！表达式          |  右到左  | 单目运算符 |
|   2    | (类型) |  强制类型转换  |     (数据类型)表达式      |  右到左  |            |
|   2    | sizeof |   长度运算符   |      sizeof(表达式)       |  右到左  |            |
|   3    |   /    |       除       |       表达式/表达式       |  左到右  | 双目运算符 |
|   3    |   *    |       乘       |       表达式*表达式       |  左到右  | 双目运算符 |
|   3    |   %    |      取余      |   整型表达式%整型表达式   |  左到右  | 双目运算符 |
|   4    |   +    |       加       |       表达式+表达式       |  左到右  | 双目运算符 |
|   4    |   -    |       减       |       表达式-表达式       |  左到右  | 双目运算符 |
|   5    |   <<   |      左移      |       变量<<表达式        |  左到右  | 双目运算符 |
|   5    |   >>   |      右移      |       变量>>表达式        |  左到右  | 双目运算符 |
|   6    |   >    |      大于      |       表达式>表达式       |  左到右  | 双目运算符 |
|   6    |   >=   |    大于等于    |      表达式>=表达式       |  左到右  | 双目运算符 |
|   6    |   <    |      小于      |       表达式<表达式       |  左到右  | 双目运算符 |
|   6    |   <=   |    小于等于    |      表达式<=表达式       |  左到右  | 双目运算符 |
|   7    |   ==   |      等于      |      表达式==表达式       |  左到右  | 双目运算符 |
|   7    |   !=   |     不等于     |      表达式!=表达式       |  左到右  | 双目运算符 |
|   8    |   &    |     按位与     |       表达式&表达式       |  左到右  | 双目运算符 |
|   9    |   ^    |    按位异或    |       表达式^表达式       |  左到右  | 双目运算符 |
|   10   |   \|   |     按位或     |      表达式\|表达式       |  左到右  | 双目运算符 |
|   11   |   &&   |     逻辑与     |      表达式&&表达式       |  左到右  | 双目运算符 |
|   12   |  \|\|  |     逻辑或     |     表达式\|\|表达式      |  左到右  | 双目运算符 |
|   13   |   ?:   |   条件运算符   | 表达式1？表达式2：表达式3 |  右到左  | 三目运算符 |
|   14   |   =    |   赋值运算符   |        变量=表达式        |  右到左  |            |
|   14   |   /=   |    除后赋值    |       变量/=表达式        |  右到左  |            |
|   14   |   *=   |    乘后赋值    |       变量*=表达式        |  右到左  |            |
|   14   |   %=   |   取模后赋值   |       变量%=表达式        |  右到左  |            |
|   14   |   +=   |    加后赋值    |       变量+=表达式        |  右到左  |            |
|   14   |   -=   |    减后赋值    |       变量-=表达式        |  右到左  |            |
|   14   |  <<=   |   左移后赋值   |       变量<<=表达式       |  右到左  |            |
|   14   |  >>=   |   右移后赋值   |       变量>>=表达式       |  右到左  |            |
|   14   |   &=   |  按位与后赋值  |       变量&=表达式        |  右到左  |            |
|   14   |   ^=   | 按位异或后赋值 |       变量^=表达式        |  右到左  |            |
|   14   |  \|=   |  按位或后赋值  |       变量\|=表达式       |  右到左  |            |
|   15   |   ,    |   逗号运算符   |    表达式，表达式，……     |  左到右  |            |

```c
int a=10;
int b=20;
int c=(a,b);		//c=20	逗号运算符是最后一个逗号右侧的表达式的值

int d=b=30;			//b=30,c=30
```

### 7、类型转换

类型转换有两种方法：

* 自动转换（隐式转换）：遵循一定的规则，由编译系统自动完成；
* 强制类型转换：把表达式运算的结果强制转换成所需的数据类型。

#### 7.1、隐式类型转换

类型转换的原则：占用内存字节数少的（值域小）的类型，向占用内存字节数多（值域大）的类型转换，以保证精度不降低。

**char, short $\rightarrow$ signed int $\rightarrow$ unsigned int $\rightarrow$ long $\rightarrow$ double**

**float $\rightarrow$ double** 

```c
float p=3.14;
int w=2;

//隐式类型转换
double sum=p*w;

```

#### 7.2、强制类型转换

强制类型转换运算符不会进行四舍五入，直接去尾

```c
float p=3.14;
int w=2;

//强制类型转换
//(数据类型)
int sum=(int)p*w;

int newSum=(int)(p*w);

```

### 8、程序流程结构

C语言支持三种程序运行结构：顺序结构、选择结构、循环结构

* 顺序结构：程序按顺序执行，不发生跳转
* 选择结构：依据是否满足条件，有选择的执行相应的功能
* 循环结构：依据条件是否满足，重复多次执行某段代码

#### 8.1、选择结构 - if 语句

* 如果表达式结果为真，执行 {} 对应的代码。

```c
// 形式1
if(表达式)
{}

//形式2
if(表达式)
{}
else
{}

//形式3
if(表达式1)
{}
else if(表达式2)
{}
else
{}


//条件嵌套
if(条件1)
{
    if(条件2)
    {}
    else if(条件2)
    {}
    else
    {}
}
else if(条件2)
{}
else
{}

```

#### 8.2、选择结构 - switch 语句

**switch 的执行效率高于 if-else 语句。**

```c
int score;
scanf("%d",&score);

//switch语句
switch (score/10)
{
    case 10:
        printf("优秀\n");
        break;
    case 9:
        printf("优秀\n");
        break;
    case 8:
        printf("良好\n");
        break;
    case 7:
        printf("良好\n");
        break;
    case 6:
        printf("及格\n");
        break;
    default:			//default 可以不要
        printf("不及格\n");
        break;
}

// break 一定要写，否则会将所有的条件都执行一遍
```

#### 8.3、 选择结构 - 条件运算符

三目运算符：

表达式1?表达式2:表达式3

```c
int a=10;
int b=20;

if(a>b)
{
	printf("a>b\n");
}
else
{
    printf("a<=b\n");
}

//三目运算符
a>b?printf("a>b\n"):printf("a<=b\n");
int c;
c=a>b?a:b;

//宏定义表达式
#define MAX(a,b) (a)>(b)?(a):(b)		//计算两数的较大者
int maxValue=MAX(a,b);
```

### 9、循环结构

#### 9.1、循环结构-while语句

```c
while(表达式)
{}


int i=1;
while(i<10)
{
    printf("%d\n",i);
    i++;
}

//100以内的偶数
int j=1;
while(j<=100)
{
    if(j%2==0)
    {
        printf("%d\n",j);
    }
    j++;
}

//7的倍数，数字带7,100以内
int k=1;
while(k<=100)
{
    if(k%7==0||k%10==7||k/10==7)
    {
        printf("%d\n",k);
    }
    k++;
}
```

#### 9.2、循环结构-do - while 语句

**do-while 语句与 while 语句的区别：while 语句先判断，再执行；do - while 语句先执行，再判断**

数学函数使用

```c
#include<math.h>

int c=pow(a,b);
```

#### 9.3、循环结构-for 语句

```c
//for 语句
for( ; ;)
{}

for(循环变量初始化表达式;条件判断表达式;改变循环变量)
{}
// 圆括号内的三个语句可以缺省
// 圆括号内的每个语句可以是多个语句使用逗号连接


for(int i=0;i<10;i++)
{
    printf("%d\n",i);
}

//上面的for循环等价于下面的写法
int i=0;
for( ; ; )
{
    if(i>=10)
    {
        break;
    }
    printf("%d\n",i);
    i++;
}
```

* gcc 编译的时候选择 c 的版本

```shell
# 使用 -std 参数设置C的版本
gcc -o hello.out hello.c -std=c99
```

* 产生随机数
    * 导入头文件 time.h	stdlib.h
    * 添加随机数种子
    * 获取随机数

```c
//产生随机数
srand((unsigned int)time(NULL));		//每次获取的随机数都不一样

int value=rand()%10;					//产生0-9的随机数
```

#### 9.4、嵌套循环

循环语句之间可以相互嵌套。

外层执行一次，内层执行一周。

```c
//sleep函数
#include<windows.h>

//电子时钟
for(int i=0;i<24;i++){
    for(int j=0;j<60;j++){
        for(int k=0;k<60;k++){
            
            //输出之前清屏
            system("cls");
            printf("%02d:%02d:%02d\n",i,j,k);
            //每次打印之后休眠1000毫秒
            Sleep(1000);
        }
    }
}


// 九九乘法口诀
/*
1*1=1
1*2=2 2*2=4
1*3=3 2*3=6 3*3=9
*/

for(int i=1;i<10;i++)
{
    for(int j=1;j<=i;j++)
    {
        printf("%d*%d=%d\t",j,i,i*j);
    }
    printf("\n");
}
```

### 10、跳转语句 break、continue、goto

#### 10.1、break 语句

switch 条件语句和循环语句中都可以使用 break 语句：

* 在 switch 语句中，作用是终止某个 case 并跳出 switch 结构；
* 在循环语句中，作用是跳出当前循环；
* 在嵌套循环语句中，退出当前所在层的循环语句，

#### 10.2、continue 语句

在循环语句中，跳过本次循环。

#### 10.3、goto 语句

无条件跳转，尽量少用。

* 跳转至另一个位置继续执行，跳过一些代码；
* 程序有多个出口，满足不同的条件，执行不同的出口，可以在不同出口前跳转；
* 不要在函数之间跳转
* 跳出死循环

```c
int mian()
{
    printf("Hello World1\n");
    printf("Hello World2\n");
    goto FLAG:
    printf("Hello World3\n");
    printf("Hello World4\n");
    FLAG:
    printf("Hello World5\n");
    printf("Hello World6\n");
    printf("Hello World7\n");
    printf("Hello World8\n");
    
    return 0;
}


//程序有多个出口，可以这样跳转
int mian()
{
    printf("Hello World1\n");
    printf("Hello World2\n");
    goto FLAG:
    printf("Hello World3\n");
    printf("Hello World4\n");
    printf("Hello World7\n");
    printf("Hello World8\n");
    
    return 0;
    
    FLAG:
    printf("Hello World5\n");
    printf("Hello World6\n");
    
    return 1;
}
```