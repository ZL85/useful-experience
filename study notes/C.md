# C

# 第1章 **C 语言概述**

## **1.1 程序语言简述**

### 1.1.1 机器语言

机器语言是低级语言，也称为二进制代码语言，是一种使用 0、1 表示的二进制代码编写指令以执行计算机操作的语言。机器语言的特点是计算机可以直接识别，不需要进行任何翻译。

### 1.1.2 汇编语言

汇编语言是面向机器的程序设计语言。为了减轻开发者使用二进制代码编程的痛苦，用英文字母或符号串来替代机器语言的二进制码，这样就把不易理解和使用的机器语言变成了汇编语言。因此，汇编语言要比机器语言更便于阅读和理解。

### 1.1.3 高级语言

由于汇编语言依赖于硬件体系，并且助记符号数量比较多，所以其运用起来仍然不够方便。为了使程序语言能更贴近人类的自然语言，同时又不依赖于计算机硬件，于是产生了高级语言。这种语言，其语法形式类似于英文，并且因为不需要对硬件进行直接操作，因此易于被普通人所理解与使用。

## **1.2 C 语言特点**

高效、灵活、功能丰富、表达力强、移植性好。

## **1.3 第一个 C 语言程序**

```c
//功能：输出"Hello world!"

#include <stdio.h>              //包含头文件stdio.h
int main()                      //主函数main是程序入口
{
    printf("Hello World!\n");   //输出要显示的字符串
    return 0;                   //程序返回0
}
```

### 1.3.1 #include 指令

编译预处理命令，声明在程序编译之前要预先处理的内容。

include 称为文件包含命令，后面尖括号中的内容称为头文件或首文件。

### 1.3.2 空行

C 语言中空格、空行、跳格并不会影响程序的运行。

### 1.3.3 main 函数声明

程序入口

### 1.3.4 函数体

实现具体功能的语句。

### 1.3.5 执行语句

函数体中要执行的动作内容。

printf函数用于向控制台输出文字或字符。

### 1.3.6 return 语句

main 函数结束标志

### 1.3.7 代码注释

/* */或//

## **1.4 一个完整的 C 程序**

```c
//功能：计算长方形的体积
//某长方体高为10，要求从控制台输入长方体的长和宽，计算出长方体的体积。
#define _CRT_SECURE_NO_WARNINGS

#include<stdio.h>                               //包含头文件stdio.h
#define Height 10                               //定义常量Height"/
int calculate(int Long, int Width);             //用户自定义函数calculate声明

int main()                                      //主函数main
{
    int m_Long;                                 //定义整型变量m_Long，表示长度
    int m_Width;                                //定义整型变量m_Width，表示宽度
    int result;                                 //定义整型变量result，表示体积
    printf("长方体的高度为:%d\n", Height);
    printf("请输入长度\n");
    scanf("%d", &m_Long);                       //输入长方体的长度
    printf("请输入宽度\n");
    scanf("%d", &m_Width);                      //输入长方体的宽度
    result = calculate(m_Long, m_Width);        //调用calculate函数，计算体积
    printf("长方体的体积是:\n");
    printf("%d\n", result);                     //输出体积大小
    return 0;                                   //程序返回0
}

int calculate(int Long, int Width)              //自定义计算体积函数calculate
{
    int result = Long * Width * Height;         //计算体积
    return result;                              //将计算的体积结果返回
}
```

### 1.4.1 定义常量

用 #define 定义了一个符号常量，用符号 Height 代表数值 10。

### 1.4.2 函数声明

声明 calculate 函数，表示后面将给出 calculate 函数的具体定义内容。

### 1.4.3 定义变量

变量的作用是存储数值，使得程序可以利用变量进行计算。C 语言中，使用变量前必须先进行定义，编译器会根据变量类型为其分配内存空间。

### 1.4.4 输入语句

scanf 函数用来接收键盘输入内容，并将输入内容保存在相应变量中。

### 1.4.5 自定义函数

用户根据需要自行定义的函数，如这里是实现计算长方体体积功能。

### 1.4.6 数学运算符语句

将变量 Long、 Width、Height 三者相乘得到的结果保存在 result 变量中。

## **1.5 C 语言程序的格式**

main 函数是 C 程序的入口。

C 程序是由多个函数构成的。

函数体的内容放在 "{}" 中。

每个执行语句都以 ";" 结尾。

英文字符大小写不通用。

要注意空格、空行的合理使用。

# 第2章 **算法**

## **2.1 算法的基本概念**

开发程序要解决的四个问题：算法、数据结构、程序设计方法、语言工具和环境。

算法是解决一个问题的完整步骤的描述（做什么？如何做？）。

算法特性：有穷性、确定性、可行性、输入、输出。

算法优劣：准确性、可读性、健壮性、时间复杂度和空间复杂度。

# 第3章 **数据类型**

## **3.1 编程规范**

### 3.1.1 代码缩进

C 语言中，代码按递进层次依次向右缩进，每次缩进 4 个字符。采用 Tab 键制表位保证缩进的对齐。

### 3.1.2 变量、常量命名规范

常量命名统一为大写格式。

成员变量均已 m_ 开始。

普通变量取与实际意义相关的名称且首字母大写，再在前面添加类型的首字母。

指针名称首字母大写，且在标识符前添加 p 字符。

```c
#define AGE 24      //定义常量
int m_iAge;         //定义整型成员变量
int iNumber;        //定义普通整型变量
int *pAge;          //定义指针变量
```

### 3.1.3 函数命名规范

定义函数时，函数名首字母大写，其后字母根据含义大小写混合。

```c
int AddTwoNum(int num1,int num2);
```

### 3.1.4 注释

尽量采用行注释。如果行注释与代码处于一行，则注释应位于代码右方。如果连续出现多个行注释，并且代码较短，则应对齐注释。

## **3.2 关键字**

关键字（Keywords），又称为保留字，是 C 语言规定的具有特定意义的字符串。C 语言中有 32 个关键字，用户定义的常量、变量、函数等名称不能与关键字相同，否则会出现错误。

| auto | double | int | struct |
| --- | --- | --- | --- |
| break | else | long | switch |
| case | enum | register | typedef |
| char | extern | union | return |
| const | float | short | unsigned |
| continue | for | signed | void |
| default | goto | sizeof | volatile |
| do | while | static | if |

## **3.3 标识符**

C 语言中，为了在程序的运行过程中可以使用变量、常量、函数、数组等，就要为这些形式设定一个名称，而设定的名称就是所谓的标识符。

基本命名规则：

1. 标识符必须以字母或下划线开头，不能以数字或符号开头。
2. 标识符中，除开头外的其他字符可以由字母、下划线或数字组成。
3. C 语言区分大小写。
4. 标识符不能是关键字。
5. 标识符应体现一定的功能含义，便于理解。
6. ANSI 标准规定，标识符可以为任意长度，但外部名必须保证仅前 6 个字符就能唯一地进行区分。

## **3.4 数据类型**

### 3.4.1 基本类型

整型、字符型、实型（浮点型）、枚举类型。

### 3.4.2 构造类型

数组类型、结构体类型、共用体类型。

### 3.4.3 指针类型

值表示某个内存地址（C 语言的精华所在）。

### 3.4.4 空类型

主要用于对函数返回值和函数参数进行限定，当函数不需要返回值时，就可以使用空类型进行设定。

## **3.5 常量**

常量是其值在程序运行过程中不可以改变的量，包括数值型常量（整型常量和实型常量）、字符型常量和符号常量。

### 3.5.1 整型常量

整型常量就是整型常数（没有小数部分），有十进制、八进制和十六进制 3 种表示形式。

十进制：0~9，逢十进一。

八进制：0~7，逢八进一，加上 0 作为前缀。

十六进制：0~9 和字母 A~F（或 a~f），逢十六进一，加上 0x 作为前缀。

整型常量可以是基本整型（int）、长整型（long int）、短整型（short int）、无符号（unsigned）、有符号（signed）。

长整型：在常量后面加上 L 或 l，如 1314L。

无符号整型：在常量后面加上 U 或 u，如 520U。

### 3.5.2 实型常量

实型也称浮点型，由整数和小数两部分组成，用十进制小数点进行分隔。表示实数的方式有小数和指数两种。

小数形式：用十进制小数方法描述实型，如 3.1415926。

指数形式（科学计数形式）：用字母 E 或 e 表示指数形式描述实型，如 45e2 表示的是$45×10^2$。

实型常量中可以使用下划线进行分隔，这些下划线不会影响数字的值，仅提供分隔作用，以方便阅读。

在实型常量后面可以加上 F 或 L 后缀（大小写通用），F 表示该常量是 float 单精度类型，L 表示该常量为 long double 长双精度类型。

若不加后缀则默认是 double 双精度类型。

### 3.5.3 字符型常量

字符型常量需要使用定界符进行限制，包括字符常量和字符串常量。

字符常量：使用一对单直撇引号（' '）括起来的就是字符常量。

字符常量只能包括一个字符、字符常量区分大小写、‘’ 代表的是定界符。

```c
//功能：利用字符常量输出Friday！
#include <stdio.h>
int main()
{
    putchar('F');
    putchar('r');
    putchar('i');
    putchar('d');
    putchar('a');
    putchar('y');
    putchar('!');
    putchar('\n');
    return 0;
}
```

字符串常量：使用双直撇引号（" "）括起来的若干字符序列就是字符串常量。

如果字符串中一个字符都没有，将其称作空串，此时字符串的长度为 0。

C 语言中存储字符串常量时，系统会在字符串的末尾自动添加一个 “\0”，作为字符串的结束标志。

```c
//打印签名
#include <stdio.h>
int main()
{
    printf("静坐常思己过，");
    printf("闲谈莫论人非。");
    return 0;
}
```

字符常量和字符串常量的区别：
定界符不同。
长度不同。
存储方式不同：字符常量中存储的是字符的 ASCII 码值，字符串常量不仅要存储有效的字符，还要存储结尾处的结束标志 "\0"。

### 3.5.4 转义字符

| 转义字符 | 意义 | 转义字符 | 意义 |
| --- | --- | --- | --- |
| \n | 回车换行 | *\* | 反斜杠"" |
| \t | 横向跳到下一制表位 | ' | 单引号 |
| \v | 竖向跳格 | \a | 鸣铃 |
| \b | 退格 | \ddd | 1~3位八进制数所代表的字符 |
| \r | 回车 | \xhh | 1~2位十六进制数所代表的字符 |
| \f | 走纸换页 |  |  |

### 3.5.5 符号常量

用符号名 Height 替代固定值 10，这里使用的符号名就称之为符号常量，可以为编程和阅读带来方便。

```c
//小时和年之间的转换
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#define HOUR 365*24                     //定义符号常量HOUR
int main()
{
    int h, result;                      //定义变量
    printf("请输入小时:\n");
    scanf("%d", &h);                    //输入数据
    result = h / (HOUR);                //进行计算
    printf("一共有%d年\n", result);     //显示结果
    return 0;                           //程序结束
}
```

## **3.6 变量**

变量是在程序运行期间其值可以变化的量，每个变量都属于某种类型，如整型、实型、字符型该类型定义了变量的格式和行为。

程序中用到的变量应集中定义，并放在变量赋值之前。

| 类型 | 关键字 | 字节 | 数值范围 |
| --- | --- | --- | --- |
| 整型 | [signed] int | 4 | -2147483648~2147483647 |
| 无符号整型 | unsigned [int] | 4 | 0~4294967295 |
| 短整型 | [signed] short [int] | 2 | -32768~32767 |
| 无符号短整型 | unsigned short [int] | 2 | 0~65535 |
| 长整型 | long [int] | 4 | -2147483648~2147483647 |
| 无符号长整形 | unsigned long [int] | 4 | 0~4294967295 |
| 字符型 | [signed] char | 1 | -128~127 |
| 无符号字符型 | unsigned char | 1 | 0~255 |
| 单精度型 | float | 4 | $-3.4×10^{-38}\sim3.4×10^{38}$ |
| 双精度型 | double | 8 | $-1.7×10^{-308}\sim1.7×10^{308}$ |
| 长双精度型 | long double | 8 | $-1.7×10^{-308}\sim1.7×10^{308}$ |

```c
//字符型与整型之间相互转化
#include<stdio.h>
int main()
{
    char cChar1;                //定义字符型变量cChar1
    char cChar2;                //定义字符型变量cChar2
    int iInt1;                  //定义整型变量iInt1
    int iInt2;                  //定义整型变量iInt2
    cChar1 = 'a';               //为变量赋值
    cChar2 = 97;
    iInt1 = 'a';
    iInt2 = 97;
    printf("%c\n",cChar1);      //显示结果为a
    printf("%d\n", cChar2);     //显示结果为97
    printf("%c\n", iInt1);      //显示结果为a
    printf("%d\n", iInt2);      //显示结果为97
    return 0;
}
```

## **3.7 变量的存储类别**

静态存储是程序运行时为其分配固定的存储空间，动态存储是在程序运行期间根据需要动态地分配存储空间。

### 3.7.1 auto 变量

auto 关键字用于定义一个局部变量为自动变量，该变量存储在内存的动态存储区中，每次执行到该变量定义语句时，都会产生一个新的变量，并且重新对其初始化。

```c
//auto变量两次加1结果
#include<stdio.h>
void AddOne()
{
	auto int iInt = 1;
	iInt++;
	printf("%d\n", iInt);
}
int main()
{
	printf("第一次调用：\n");
		AddOne();
	printf("第二次调用：\n");
		AddOne();
		return 0;
}
/*关键字auto可以省略，不特别指定情况下，局部变量的存储方式默认为都是auto型。*/
```

### 3.7.2 static 变量

static 变量表示静态变量，存储在内存的静态存储区中。

对于局部变量来说，尽管 static 变量和 auto 变量的作用域都仅限于声明变量的函数之中，但是在语句块执行期间，static 变量将始终保持它的值，并且初始化操作只在第一次执行时起作用，在随后的运行过程中变量将保持语句块上次执行时的值。

```c
//使用static变量记录点击量
#include<stdio.h>
void click()
{
	static int sum = 0;
	sum++;
	printf("此时点击量：%d\n", sum);
}
int main()
{
	click();
	click();
	click();
	click();
	click();
	return 0;
}
```

### 3.7.3 register 变量

register 变量又称为寄存器存储类变量。通过它，程序员可以请求编译器把某个需要频繁访问的局部变量存放在计算机的硬件寄存器中，而不是内存中。这样做的好处是可以提高程序的运行速度。不过这只是反映了程序员的主观意愿，由于 cpu 的寄存器数量有限，实际上编译器可以忽略 register 对变量的修饰。

```c
//加快计算机执行速度
#include<stdio.h>
int main()
{
	register int iInt;		//定义寄存器整型变量
	iInt = 100;
	printf("%d\n", iInt);	//显示结果
	return 0;
}
```

### 3.7.4 extern 变量

一个工程（Project，即项目）是由多个 C 文件组成的，这些源代码文件会分别进行编译，然后链接成一个可执行模块。有时我们需要用到其他 C 文件中的变量，这些变量就需要声明为 extern 型。

extern 变量又称为外部存储变量，常用于声明程序需要使用且已在其他程序文件中定义过的变量。

```c
//打破常规输出100
#include<stdio.h >
int main()
{
	extern int iExtern;			//声明外部整型变量
	printf("%d\n",iExtern);	//显示变量值
	return 0;
}

#include<stdio.h>
int iExtern = 100;	//定义一个整型变量，为其赋值100

```

## **3.8 混合运算**

不同类型的数据之间可以进行混合运算，不同数据类型要先转换成同一类型，然后再进行运算。

![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//1.png)

```c
//不同数据类型间混合运算
#include<stdio.h>
int main()
{
	int int1 = 10;										//定义整型变量
	int int2 = 6;
	char cChar = 'a';									//定义字符变量，a的ASCII码值为97
	float fFloat1 = 1.5f;							//定义单精度型变量
	float fFloat2 = 3.2f;
	double result = (int1 + cChar - fFloat1 + fFloat2 * int2);//得到混合运算的结果
	printf("%f\n", result);						//输出变量值
	return 0;
}
```

# 第4章 **运算符与表达式**

## **4.1 表达式**

C 语言中，表达式由操作符和操作数组成。

表达式的返回值具有逻辑特性：如果返回值非零，那么返回的是真值，否则返回的是假值，可以将表达式放在程序控制流语句中，形成条件表达式。

```c
//编程中的数学运算
#include<stdio.h>
int main()
{
	int iNumber1=3, iNumber2=7, iNumber3;

	printf("The first number is %d.\n", iNumber1);
	printf("The second number is %d.\n", iNumber2);

	iNumber3 = iNumber1 + 10;
	printf("The first number add 10 is %d.\n", iNumber3);

	iNumber3 = iNumber2 + 10;
	printf("The second number add 10 is %d.\n", iNumber3);

	iNumber3 = iNumber1 + iNumber2;
	printf("The result number of first add second is %d.\n", iNumber3);

	return 0;
}
```

## **4.2 赋值运算符与赋值表达式**

"=" 就是赋值运算符，作用是将一个数据赋给一个变量，也可将一个表达式的值赋给一个变量。

### 4.2.1 变量赋初值

```c
//类型 变量名 = 常数;
int a = 100;

//类型 变量名 = 表达式;
float fprice = fBase + Day*3;
```

```jsx
/*
出租车每千米路程需要3元，李女士要到10千米远的地方，后来发现走错了，之后又坐出租车返回3千米，计算她需要花多少钱才能
到达目的地。
*/
#include<stdio.h>
#define PRICE 3		//定义常量，表示每公里路程的费用
int main()
{
	int journey1 = 10;//定义变量，表示目的地的距离
	int journey2 = 3;	//定义变量，表示返回路程的距离
	int money;				//定义变量，表示最终的费用
	money = journey1 * PRICE + journey2 * PRICE;//计算费用， 将右侧表达式的计算结果赋给变量money"/
	printf("总共花了%d元\n", money);//输出结果
	return 0;
}
```

### 4.2.2 自动类型转换

把较短的数值类型变量的值赋给较长的数值类型变量时，较短的数值类型变量其值会自动升级为较长的数值类型，数据信息不会丢失。但把较长的数值类型变量的值赋给较短的数值类型变量时，数据会降低级别显示。当数据大小超过较短的数值类型的可表示范围时，就会发生数据截断。

C 语言中，整数的默认类型是 int，浮点数的默认类型是 double。如果一个表达式中数字都是 int 型，则表达式结果也默认为是 int 型。

### 4.2.3 强制类型转换

强制类型转换的一般形式：

```c
（类型名）（表达式）

float i= 10.1f;
int j=(int) i;
//在变量前使用包含要转换类型的括号，就对变量进行了强制类型转换。
```

```c
//计算载货区摆放箱子的数量

/*
一辆货车运输箱子，载货区宽2米，长4米，一个箱子宽1.5米，长1.5米，计算可以运输多少个箱子。注意，箱子数必须为整数，不存在半个箱子。
*/

#include<stdio.h>								          //包含头文件
int main()										            //主函数main
{
	int width = 2, length = 4, num;				  //定义变量，并赋初值，表示载货区规格
	float f = 1.5f;								          //表示箱子规格
	num = (int)(width/f)*(int)(length/f);		//通过强制类型转换，计算最大箱子承载数
	printf("载货区一层可以放%d个箱子\n", num);
	return 0;
}
```

如果某个表达式要进行强制类型转换，需要将该表达式用括号括起来，否则将只对表达式中的第一个变量或常量进行强制类型转换。

## **4.3 算术运算符与算术表达式**

C 语言中运算符分为单目运算符（一个操作数）和双目运算符（两个操作数）。其中，算术运算符用于实现正、负、加、减、乘、除、求余等运算。单目正和单目负运算符的优先级最高。双目运算符中，乘法、除法和取模运算符的优先级比加法和减法运算符高。

### 4.3.1 算术运算符

| 符号 | 功能 |
| --- | --- |
| + | 正 |
| - | 负 |
| * | 乘法 |
| / | 除法 |
| % | 取模 |
| + | 加法 |
| - | 减法 |

### 4.3.2 算术表达式

算术表达式：使用算数运算符的表达式称为算术表达式。

两整数相除的的结果为整数，如 7/4 的结果为 1，舍去小数部分，若其中一个为负数，机器会“向 0 取整”，即为 -1，取整后向 0 靠拢。

```c
/*
平均加速度，即速度的变化量除以这个变化所用的时间。现有一辆轿车用了8.7秒从每小时0千米加速到每小时100千米，计算并输出这辆轿车的平均加速度。
*/
#include<stdio.h>
int main()
{
	int V1 = 0 / 3600, V2 = 100000 / 3600;	//定义两个变量，将速度单位km/h转换为m/s
	float t = 8.7f;							            //定义变量，表示所用时间
	double a;								                //定义变量，表示加速度
	a = (V2 - V1) / t;					           	//计算加速度
	printf("加速度a=%f\n", a);
	return 0;
}
```

参与算术运算的两个数中只要有一个为实型，整个表达式的结果就是 double 型，这是因为所有实数都是按 double 型进行设定的。

### 4.3.3 优先级与结合性

表达式求值时，通常会按照运算符的优先级别从高到低依次执行。

当优先级相同时，结合方向为“自左至右”。

### 4.3.4 自增/自减运算符

自增运算符 ++（使变量 +1）、自减运算符 --（使变量 -1）。

自增、自减运算符可以放在变量的前面或者后面，放在变量前面称为前缀，放在后面称为后缀。

当自增、自减运算符出现在表达式内部，作为运算的一部分时，前缀和后缀对运算结果的影响是不一样的。如果运算符放在变量前，那么变量将先完成自增或自减运算，再以增减后的结果参与表达式运算；如果运算符放在变量后，那么变量将先参加表达式运算，之后再进行自增或自减。

```c
//自增自减运算符作为前缀后缀时的不同结果。

#include<stdio.h>
int main()
{
	int iNumber1 = 3;									//定义变量，赋值为3
	int iNumber2 = 3;
	int iResultPreA, iResultLastA;						//定义变量，存储自增运算的前缀和后缀结果
	int iResultPreD, iResultLastD;						//定义变量，存储自减运算的前缀和后缀结果
	iResultPreA = ++iNumber1;							//前缀自增运算
	iResultLastA = iNumber2++;							//后缀自增运算
	printf("The Addself ...\n");
	printf("the iNumber1 is:%d\n", iNumber1);			//显示自增运算后自身的数值
	printf("the iResultPreA is:%d\n", iResultPreA);		//得到自增表达式中的结果
	printf("the iNumber2 is:%d\n", iNumber2);			//显示自增运算后自身的数值
	printf("the iResultLastA is:%d\n", iResultLastA);	//得到自增表达式中的结果

	iNumber1 = 3;										//恢复变量的值为3
	iNumber2 = 3;
	iResultPreD = --iNumber1;							//前缀自减运算
	iResultLastD = iNumber2--;							//后缀自减运算/
	printf("The Deleteself ...\n");
	printf("the iNumber1 is:%d\n", iNumber1);			//显示自减运算后自身的数值
	printf("the iResultPreD is:%d\n", iResultPreD);		//得到自减表达式中的结果
	printf("the iNumber2 is:%d\n", iNumber2);			//显示自减运算后自身的数值
	printf("the iResultLastD is:%d\n", iResultLastD);	//得到自减表达式中的结果
	return 0;											//程序结束
}
```

自增、自减运算符是单目运算符，因此表达式和常量不可以进行自增、自减运算。例如 5++,(a+5)++ 都是不合法的。

## **4.4 关系运算符**

### 4.4.1 关系运算符

| 符号 | 功能 |
| --- | --- |
| > | 大于 |
| >= | 大于等于 |
| < | 小于 |
| <= | 小于等于 |
| == | 等于 |
| != | 不等于 |

### 4.4.2 关系表达式

关系运算符可对两个值进行比较，返回一个真值或者假值。真值为 1，表示指定关系成立，假值为 0，表示指定关系不成立。

关系运算符常用来构造条件表达式，用在流程控制语句中。

### 4.4.3 优先级与结合性

关系运算符的结合性是自左向右的。

```c
/*
一个小孩跑完步去买水，如果他手里的零钱多于2元，卖家会说:“你可以买可乐。”如果手里的零钱少于2元，卖家会说:“你可以买矿泉水。”试用if语句模拟两人对话的场景。
*/
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main()
{
	int money;							        //定义变量，用来保存钱数
	printf("输入手里的钱数:\n");
	scanf("%d", &money);				    //输入钱数
	if(money >= 2)						      //利用关系运算符判断钱数是否大于等于2
		printf("你可以买可乐\n");
	else								            //利用关系运算符判断钱数是否大于等于2
		printf("你可以买矿泉水\n");
	return 0;
}
```

## **4.5 逻辑运算符与逻辑表达式**

逻辑运算符可根据表达式的真假属性返回真值或假值。在 C 语言中，表达式的值非零，那么其值为真。非零的值用于逻辑运算，则等价于 1；假值总是为 0。

### 4.5.1 逻辑运算符

| 符号 | 功能 | 示例 | 含义 |
| --- | --- | --- | --- |
| && | 逻辑与 | A&&B | A、B两个表达式都为真时，逻辑运算结果为真
A、B两个表达式只要有一个为假，逻辑运算结果为假 |
| || | 逻辑或 | A||B | A、B两个表达式都为假时，逻辑运算结果为假
A、B两个表达式只要有一个为真，逻辑运算结果为真 |
| ! | 逻辑非 | !A | A表达式都为真，逻辑运算结果为假
A表达式都为假，逻辑运算结果为真 |

### 4.5.2 逻辑表达式

一般形式：

```c
表达式 逻辑运算符 表达式
```

### 4.5.3 优先级和结合性

"&&" 和 "||" 是双目运算符，要求有两个操作数，结合方向自左至右；"!" 是单目运算符，要求有个操作数，结合方向自右向左；逻辑运算符优先级从高到低依次为 "!"、"&&"、"||"。

```c
/*某模特公司招聘，要求年龄大于等于25岁且身高大于等于1.7米，才通知参加面试和笔试，否则就不能进行面试和笔试。*/
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main()
{
	float height;						//定义变量，表示身高
	int age;							//定义变量，表示年龄
	printf("请输入您的年龄和身高：\n");		//输出提示信息
	scanf("%d %f", &age, &height);			//输入年龄、身高
	if (age >= 25 && height >= 1.7)			//如果年龄大于或等于25岁且身高大于或等于1.7米
	{
		printf("恭喜您通过了本公司的初选，请您及时到本公司参加面试和笔试。\n");	//输出初选通过信息
	}
	else
	{
		printf("对不起，您不符合我们公司的要求。\n");						//输出婉拒信息
	}
		return 0;													//程序结束
}
```

## **4.6 逗号运算符与逗号表达式**

C 语言中，逗号运算符可以将多个表达式分隔开来。一般形式：

```c
表达式1,表达式2,...,表达式n
```

逗号表达式又称为顺序求值运算符，其求解过程是：先求解表达式 1，再求解表达式 2，一直求解到表达式 n，整个逗号表达式的值是表达式 n 的值。

赋值运算符优先级比逗号运算符高。

```c
//要先执行逗号运算，可以用括号运算符
#include <stdio.h>
int main()
{
	int iValue1 = 10, iValue2 = 43, iValue3 = 26, iResult = 0;	//定义4个变量并赋值
	iResult = iValue1++, --iValue2, iValue3 + 4;				        //计算第一个逗号表达式
	printf("the result is %d\n", iResult);						          //将结果输出显示
	iResult = (iValue1++, --iValue2, iValue3 + 4);			      	//计算第二个逗号表达式
	printf("the result is %d\n", iResult);						          //将结果输出显示
	return 0;
}
```

## **4.7 复合赋值运算符**

C 语言独有，使代码更精炼，可以提高编译效率。

```c
Value = Value + 3;
Value += 3;
```

```c
//简化赋值运算
#include<stdio.h>								            	//包含头文件//
int main()											              //主函数main
{
	int iValue=7;								               	//定义变量iValue并赋值
	iValue += iValue *= iValue /= iValue - 5;		//计算得到iValue变量值，从右往左计算
	printf("the result is %d\n", iValue);			  //将计算结果输出
	return 0;
}
```

## **4.8 运算符的优先级总结**

下面按照优先级从小到大的排列顺序列出 C 语言中所有运算符的优先级和结合性。

| 优先级 | 运算符 | 含义 | 结合性 |
| --- | --- | --- | --- |
| 1 | () | 圆括号 | 自左向右 |
|  | [] | 下标运算符 |  |
|  | -> | 指向结构体成员运算符 |  |
|  | . | 结构体成员运算符 |  |
| 2 | ! | 逻辑非运算符 | 自右向左 |
|  | ~ | 按位取反运算符 |  |
|  | ++ | 自增运算符 |  |
|  | -- | 自减运算符 |  |
|  | - | 负号运算符 |  |
|  | * | 指针运算符 |  |
|  | & | 地址与运算符 |  |
|  | sizeof | 长度运算符 |  |
| 3 | *、/、% | 乘、除、求余运算符 | 自左向右 |
| 4 | +、- | 加、减运算符 |  |
| 5 | <<、>> | 左移、右移运算符 |  |
| 6 | <、<=、>、>= | 小于、小于或等于、大于、大于或等于运算符 |  |
| 7 | ==、!= | 等于、不等于运算符 |  |
| 8 | & | 按位与运算符 |  |
| 9 | ^ | 按位异或运算符 |  |
| 10 | | | 按位或运算符 |  |
| 11 | && | 逻辑与运算符 |  |
| 12 | || | 逻辑或运算符 |  |
| 13 | ?: | 条件运算符 | 自右向左 |
| 14 | =、+=、-=、*=、/=、%=
>>=、<<=、&=、^=、|= | 赋值运算符 |  |
| 15 | , | 逗号运算符 | 自左向右 |

```c
//求n!
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int i, n, sum=1;
	printf("请输入n的值：\n");
	scanf("%d", &n);
	while (n == 0)
	{
		printf("%d的阶乘是%d\n", n,sum);
		break;
	}
	for (i = 1; i <= n; i++)
		{
			sum *= i;
		}
	printf("%d的阶乘是%d\n", n, sum);
	return 0;
}
```

# 第5章 **常用的数据输入/输出函数**

## **5.1 语句**

一条语句经过编译后，会产生若干条机器指令。

声明部分不算语句，因为不产生机器操作，只对变量提前进行了定义。

## **5.2 字符数据的输入/输出**

### 5.2.1 字符输出函数

putchar 函数，作用是向显示设备输出一个字符，一次只能输出一个字符。语法格式：

```c
int putchar (int ch);
```

使用该函数时要添加头文件 stdio.h，参数 ch 可以是字符型变量或整型变量，也可以是常量。

```c
//输出字符A
putchar('A')
//输出转义字符
putchar('\101')
```

```c
//打印喵喵字符
#include<stdio.h>
int main()
{
	putchar('\101');			//使用转义字符输出字符A
	putchar('(');				  //输出多个字符常量，打印喵喵字符画
	putchar('=');
	putchar('^');
	putchar('_');
	putchar('^');
	putchar('=');
	putchar(')');
	putchar('\n');				//输出转义字符，实现换行

	putchar('^');				  //输出多个字符常量，打印笑脸
	putchar('_');
	putchar('^');
	putchar('\n');

	putchar('@');			    //输出多个字符常量，打印大眼萌
	putchar('_');
	putchar('@');
	putchar('\n');

	return 0;
}
```

### 5.2.2 字符输入函数

getchar 函数，从终端（输入设备）输入一个字符，getchar 没有参数，一次只能接受一个字符，可以不返回值，直接放在 printf 函数中使用。语法格式：

```c
int getchar();
```

使用该函数时要添加头文件 stdio.h，函数的值就是从输入设备得到的字符。

```c
//从键盘输入一个字符并赋给变量cChar
cChar = getchar();
```

```c
//输出字符对应的ASCII码值
#include<stdio.h>
int main()
{
	char i;									              //定义变量
	printf("请输入字符:\n");
	i = getchar();							          //将用户输入的字符赋给变量
	printf("对应的ASCII码值为%d\n",i);		//输出对应的ASCII码值
	return 0;
}

//利用字符型和整型之间的转换用printf函数输出对应的ASCII码值

```

```c
//用getchar函数获取回车符
#include<stdio.h>
int main()
{
	char cChar1;			    //定义变量
	cChar1 = getchar();		//将用户输入的字符赋给变量
	putchar(cChar1);	  	//输出字符
	putchar('\n');			  //输出转义字符换行
	//getchar();删除此行得到换行符	//注意此行，getchar输入字符
	putchar(getchar());		//得到输入字符，直接输出
	putchar('\n');			  //换行
	return 0;
}
```

getchar 函数也可以不返回值，而是直接放在 printf 函数中使用。

```c
printf("%c\n",getchar());
```

## **5.3 字符串输入/输出**

### 5.3.1 字符串输出函数

puts 函数，作用是输出一个字符串到屏幕上。语法格式：

```c
int puts(char *str);
```

使用该函数时要添加头文件 stdio.h，形式参数 str 是一个字符指针变量，用来接收要输出的字符串。

```c
//使用puts输出一个字符串
puts("What's up?")
```

puts 函数会在字符串中判断 “\0” 结束符，遇到结束符时，后面的字符不再输出，并且自动换行。

```c
puts("I LOVE\0 CHINA!");
//只会输出"I LOVE"
```

编译器会在字符串常量末尾自动添加 “\0” 结束符。

```c
//打印各种各样的ILOVECHINA
#include<stdio.h>
int main()
{
	char* Char = "ILOVECHINA!";		//定义字符串指针变量并赋初值
	puts("ILOVECHINA!");			    //输出字符串常量
	puts("I\0LOVE\0CHINA!");	   	//输出字符串常量，其中加入两个结束符“\0”
	puts(Char);						        //输出字符串变量的值
	Char = "ILOVE\0CHINA!";		  	//改变字符串变量的值
	puts(Char);						        //输出改变后的字符串变量的值
	return 0;
}

```

### 5.3.2 字符串输入函数

gets 函数，作用是将读取的字符串保存在 str 变量中，直到出现新的一行为止，其新行的换行符将会转换为空终止符 “\0”。语法格式：

```c
char *gets(char *str);
```

使用该函数时要添加头文件 stdio.h，str 是一个字符指针变量，用来存储用户输入的字符串。

```c
//定义字符数组变量cString，然后使用gets函数获取输入字符
gets(cString);
```

cString 变量获取了字符串，并将最后的换行符转换成了终止字符。

```c
//模拟用户注册系统
//首先提醒用户输入账号、密码、姓名和身份证号，注册完毕后，显示用户输入的注册信息。
#include <stdio.h>
int main()
{
	char account[20], password[20], name[20], IDcard[20];	//定义 4个字符数组变量
	puts("请输入账号:");									//提示信息
	gets(account);										    //获取账号字符串
	puts("请输入密码:");									//提示信息
	gets(password);								    		//获取密码字符串
	puts("请输入姓名:");									//提示信息
	gets(name);										      	//获取姓名字符串
	puts("请输入身份证号:");								//提示信息
	gets(IDcard);									      	//获取身份证号字符串
	puts("注册完成，信息如下:");
	puts("您输入的账号为:");								//提示信息
	puts(account);									    	//输出账号字符串
	puts("您输入的密码为:");								//提示信息
	puts(password);									    	//输出密码字符串
	puts("您输入的姓名为:");								//提示信息
	puts(name);											      //输出姓名字符串
	puts("您输入的身份证号为:");						//提示信息
	puts(IDcard);										      //输出身份证号字符串
	return 0;
}
//puts的作用是输出一行，不论输入的字符串的内容是什么，都会在最后加上'\n'之后再输出。
```

## **5.4 格式输出函数**

printf 函数，作用是向终端输出若干任意类型的数据，语法格式：

```c
printf(格式控制，输出列表);
```

### 5.4.1 格式控制

格式控制是用双引号括起来的字符串，也称为转换控制字符串。

格式字符：用来进行格式说明的字符，作用是将输出的数据转换为指定格式，通常以 “%” 开头。

普通字符：需要原样输出的字符。

### 5.4.2 输出列表

输出列表列出的是要进行输出的一些数据，可以是变量或表达式。

printf 是函数，“格式控制”和“输出列表”都是函数参数，一般形式：

```c
printf(参数1,参数2,...参数n)
```

函数中的每个参数都必须按照给定的格式和顺序依次输出。

```c
//输出一个字符型变量和整型变量
printf("the Int is %d,the Char is %c\n",iInt,cChar);
```

| 格式字符 | 功能说明 |
| --- | --- |
| %d、%i | 用来输出有符号的十进制整数 |
| %u | 用来输出无符号的十进制整数 |
| %o | 用来输出无符号的八进制整数 |
| %x、%X | 用来输出无符号的十六进制整数，%x表示以小写形式输出，%X同理 |
| %c | 用来输出单个字符 |
| %s | 用来输出字符串 |
| %f | 用来输出实数，以小数形式输出 |
| %e、%E | 用来输出实数，以指数形式输出 |
| %g、%G | 以%e或%f中宽度较短的格式输出，不输出无意义的0 |

printf 函数中，除 X、E、G 外，其他格式字符必须使用小写字母。

```c
//牛吃草问题
#include <stdio.h>						//包含头文件
int main()								    //主函数main
{
	int graNum, graSum, num;		//graNum为一头牛吃的草量，graSum为总草量，num为结果
	graNum=2,graSum=45;					//为变量赋值
	num = graSum / graNum;			//利用表达式计算结果
	printf("%d cows eat enough!\n",num);
	return 0;
}
```

附加字符放在 “%” 符号和上述格式字符间，要想输出 “%” 符号，使用 “%%” 进行输出。

| 附加字符 | 功能说明 |
| --- | --- |
| l | 用于输出长整型数，可加在d、o、x、u的字母前面 |
| m | 用于指定输出数据字段宽度，数字或字符在域内向右对齐 |
| n | 对实数，表示输出n位小数；对字符串，表示截取的字符个数 |
| - | 用于指定输出的数字或字符在域内向左对齐 |

```c
//对输出的数据进行更精准的格式控制
#include<stdio.h>
int main()
{
	long iLong = 100000;						               //定义长整型变量，为其赋值
	printf("the Long is %ld\n", iLong);			       //使用%ld输出长整型变量
	printf("the string is:%sKeJi\n", "MingRi");	   //%s，输出字符串"MingRi" (按实际长度输出)
	printf("the string is:%10sKeJi\n", "MingRi");	 //%10s, 输出宽度为10, 右对齐，左补空
	printf("the string is:%-10sKeJi\n", "MingRi"); //%-10s，输出宽度为10,左对齐，右补空
	printf("the string is:%10.2sKeJi\n", "MingRi");//%10.2s，输出宽度为10，截取2个字符右对齐输出
	printf("the string is:%-10.2sKeJi\n","MingRi");//%-10.2s，输出宽度为10,截取2个字符左对齐输出
	return 0;
}
```

## 5.5 格式输入函数

scanf 函数，功能是按照指定的格式接收用户在键盘上输入的数据，最后将数据存储在指定的变量中。一般格式：

```c
scanf(格式控制，地址列表);
```

“格式控制”参数与 printf 函数相同，"%d" 表示十进制整型，"%c" 表示单个字符；“地址列表”参数用于给出接收数据变量的地址。

```c
//得到一个整型数据
scanf("%d",&iInt);
```

"&" 是取地址符号，表示取 iInt 变量的地址。

scanf 函数中，当输入的数据是基本类型，如整型、字符型、实型时，需要使用取地址符号。

当输入的变量本身就是一个地址时，如数组名、字符串指针等，不需要再使用 “&” 符号。

| 格式字符 | 功能说明 |
| --- | --- |
| %d，%i | 用来输入有符号的十进制数 |
| %u | 用来输入无符号的十进制数 |
| %o | 用来输入无符号的八进制数 |
| %x,%X | 用来输入无符号的十进制数，大小写作用相同 |
| %c | 用来输入单个字符 |
| %s | 用来输入字符串 |
| %f | 用来输入实数，以小数形式输入 |
| %e，%E | 用来输入实数，以指数形式输入 |
| %g，%G | 用来输入实数，与%f或%e作用相同 |

格式字符 “%s” 用来输入字符串。将字符串送到一个字符数组中，在输入时以非空白字符开始，以第一个空白字符结束，字符串以串结束标志 “\0” 作为最后一个字符。

```c
//根据身高和体重计算BMI值
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main()
{
	float height, weight;						    	//定义height为身高，weight为体重
	double BMI;									        	//定义身体质量指数BMI
	printf("请输入身高、体重:\n");					//提示信息
	scanf("%f %f", &height, &weight);			//输入身高、体重，“&”是取地址符号，表示取变量的地址。
	BMI = weight / (height * height);			//计算BMI值
	printf("您的身体质量指数(BMI):%f\n", BMI);
	return 0;
}
```

程序是怎样将输入的内容分别保存到两个指定变量中的呢? scanf 函数使用空白字符分隔输入的数据，这些空白字符包括空格、换行和制表符（tab） 。本例中使用了换行作为空白字符。

使用 scanf 函数输入数据时，实际输入的变量格式必须与 scanf 函数参数中指定的变量格式、顺序一一对应

| 附加字符 | 功能说明 |
| --- | --- |
| l | 用于输入长整型数据(如%ld、%lo、%lx、%lu)以及double型数据(如%lf、%le) |
| h | 用于输入短整型数据(如%hd、%ho、%hx) |
| n | 用于指定输入数据的字段宽度，多余的数据将被忽略 |
| * | 表示指定的输入项在读入后不赋给相应的变量 |

```c
//输入不同类型的数据
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	long iLong;														          //长整型变量
	short iShort;													          //短整型变量
	int iNumber1 = 1;												        //整型变量，为其赋值1
	int iNumber2 = 2;												        //整型变量，为其赋值2
	char cChar[10];												        	//定义字符数组变量
	printf("Enter the long integer\n");
	scanf("%ld", &iLong);											      //%ld，输入长整型数据
	printf("Enter the short integer\n");
	scanf("%hd", &iShort);											    //%hd，输入短整型数据
	printf("Enter the number:\n");
	scanf("%d*%d", &iNumber1, &iNumber2);						//%d*%d，输入整型数据，忽略第2个输入的数
	printf("Enter the string but only show three character\n");
	scanf("%3s", cChar);											      //%3s，输入字符串，只接收前3个字符
	printf("the long integer is: %ld\n", iLong);		//显示长整型值
	printf("the short interger is: %hd\n", iShort);	//显示短整型值
	printf("the Number1 is: %d\n", iNumber1);				//显示整型iNumber1的值
	printf("the Number2 is: %d\n", iNumber2);				//显示整型iNumber2的值
	printf("the three character are: %s\n", cChar);	//显示字符串
	return 0;
}
```

```c
//计算圆的周长和球的体积
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#define PI 3.14
int main()
{
	float r;
	double c, v;
	printf("请输入半径：\n");
	scanf("%f", &r);
	c = PI * r * 2;
	printf("周长是：%.2f\n", c);
	v = (4 / 3) * PI * r * r * r;
	printf("体积是：%.2f\n", v);
	return 0;
}
```

## 5.6 顺序程序设计应用

```c
//交换数值
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>									            //包含头文件
int main()										              	//主函数main
{
		int x, y;									                //定义变量
		printf("please enter two numbers : \n");	//提示信息
		/*
		scanf("x=%d,y=%d", &x, &y);				        //输入x,y数值
		x = y - x;									              //交换x,y的值
		y = y - x;
		x = y + x;
		printf("x=%d,y=%d\n", x, y);				      //输出交换后的数值
		*/
		scanf("%d %d", &x, &y);						        //输入x,y数值
		x = y - x;									              //交换x,y的值
		y = y - x;
		x = y + x;
		printf("%d %d\n", x, y);					        //输出交换后的数值
		return 0;
}
```

```c
//英文大小写字符相互转换
//将大写字符的ASCII码加上32,即可转换成小写字符的ASCII码
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	char cBig;										           //定义字符变量，表示大写字符
	char cSmall;								             //定义字符变量，表示小写字符
	puts("Please enter capital character:"); //输出提示信息
	cBig = getchar();								         //得到用户输入的大写字符
	puts("Minuscule character is:");				 //输出提示信息
	cSmall = cBig + 32;								       //将大写字符转换成小写字符
	//printf("%c\n", cSmall);							   //输出小写字符
	putchar(cSmall);
	printf("\n");
	return 0;

}
```

```c
//显示菱形图案
#include<stdio.h>
int main()
{
	printf("%4c\n", '*');
	printf("%c", '*');
	printf("%3c", '*');
	printf("%3c\n", '*');
	printf("%4c\n", '*');
	return 0;
}
```

# 第6章 选择结构程序设计

## 6.1 if 语句

### 6.1.1 if 语句形式

一般形式：

```c
if(表达式) 语句
```

括号中的表达式就是要进行判断的条件，语句则是要执行的对应操作。

if 语句中，首先判断表达式的值，然后根据该值的真假情况决定后续程序流程。表达式的值非 0，就表示为真；否则就是假值。

```c
//语句块
if(Signal==1)
{
	printf("the Signal Light is %d:\n",iSignal);
	printf("Cars can run!");
}
```

将执行的语句都放在大括号中，这样当 if 语句判断条件为真时，语句块内的内容将会全部被执行。

```c
/*
模拟此场景：一位职工早上上班打卡，她的工位号是13，密码是111，输入正确门禁卡会出现“谢谢，已签到”的字样
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int loc, ser;						        //定义变量loc表示工位号，ser表示密码
	printf("请输入工位号，密码：\n");
	scanf("%d %d", &loc, &ser);			//输入工位号和密码
	if (loc = 13 && ser == 111)			//判断输入是否相同
	{
		printf("谢谢，已签到\n");
	}
	else
	{
		printf("对不起，工位号或密码有错误。\n");
	}
	return 0;
}
```

### 6.1.2 if else 语句形式

一般形式：

```c
If(表达式)
{
	语句块1;
}
else
{
	语句块2;
}
```

else 语句必须跟在一个 if 语句的后面，不能独立使用。

```c
//判断条件真假
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int iNumber;															//定义变量
	printf("Enter a number：\n");
	scanf("%d", &iNumber);						        //输入数字
	if(iNumber)																//判断变量的值
	{
		printf("The value is true and the number is : %d\n", iNumber);		//判断为真时执行输出
	}
	else
	{
		printf("The value is flase and the number is : %d\n", iNumber);		//判断为假时执行输出
	}
	return 0;
}
```

使用 if else 语句判断用户输入的数值。输入的数字为 0，表示条件为假；输入的数字为非 0，表示条件为真。

在使用 if 语句比较浮点数时，不要使用浮点值，这样就会导致实际结果的偏差，因为浮点值属于近似值。

### 6.1.3 else if 语句形式

一般形式：

```c
If(表达式1)
{
	语句块1;
}
else If(表达式2)
{
	语句块2;
}
else If(表达式3)
{
	语句块3;
}
...
else If(表达式m)
{
	语句块m;
}
else
{
	语句块n;
}
```

```c
//计算分段函数的值
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int x, y;							//定义变量x,y
	printf("请输入x的值:\n");
	scanf("%d", &x);					//输入x的数
	if (x < 1)							//判断输入的x是否小于1
	{
		y = x;							//如果为真，将x的值赋给y
		printf("y=%d\n", y);			//输出y的值
	}
	else if (x >= 1 && x < 10)			//判断输入的x是否大于等于1且小于10
	{
		y = 2 * x - 1;					//如果为真，将2*x-1的值赋给y
		printf("y=%d\n", y);			//输出y的值*/
	}
	else								//x为其他数值时
	{
		y = 3 * x - 11;					//如果为真，将3*x-11的值赋给y
		printf("y=%d\n", y);			//输出y的值
	}
	return 0;
}
```

## 6.2 if 的嵌套形式

if 语句中还可以包含一个或多个 if 语句，称为 if 语句的嵌套。一般形式：

```c
If(表达式1)
{
	If(表达式2)
	{
		语句块1;
	}
	else
	{
		语句块2;
	}
}
else
{
	If(表达式3)
	{
		语句块3;
	}
	else
	{
		语句块4;
	}
}
```

if 语句、if...else 语句、else if 语句可以根据相互需要互相嵌套一定要注意 if 与 else 的配对情况，else 总是与前面最近未配对的 if 进行配对。

```c
/*
粽子有甜的，有咸的。甜粽子有5元和10元的，咸粽子有4元和12元的编写程序，根据输入的口味和钱数，判断并打印出能吃到哪种粽子
其中，输入1代表选择甜粽子，其他数字代表选择咸粽子，用户输入1和12，输出“您可以吃到10元的甜粽子”。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int type, money;									            //定义变量type表示粽子口味，money表示钱数
	printf("数字1表示甜粽子，否则就是咸粽子。\n");
	printf("请输入粽子口味和可支付金额：\n");
	scanf("%d %d", &type, &money);						    //输入口味和手中的钱数
	if (type == 1)										            //如果输入数字等于1，表示选择甜粽子
	{
		if (money >= 5 && money < 10)					      //判断输入的钱数，如果大于等于5且小于10
			printf("您可以吃到5元的甜粽子。\n");	    	//输出信息
		else if (money >= 10)							          //判断输入的钱数，如果大于等于10
			printf("您可以吃到10元的甜粽子。\n");	  	//输出信息
		else											                  //输入的钱数不够
			printf("您不可以吃到甜粽子\n");				    //输出信息
	}
	else											                  	//如果输入其他数字，表示选择咸粽子
	{
		if (money >= 4 & money < 12)				      	//判断输入的钱数，如果大于等于4且小于12
			printf("您可以吃到4元的咸粽子。\n");	    	//输出信息
		else if (money >= 12)							          //判断输入的钱数，如果大于等于12
			printf("您可以吃到12元的咸粽子\n");		   	//输出信息
		else										                  	//输入的钱数不够
			printf("您不可以吃到咸粽子。\n");		    	//输出信息
	}
	return 0;
}
```

## 6.3 条件运算符

用 if 语句实现对两个数中最大值的求解：

```c
if(a>b)
{
	max=a;
}
else
{
	max=b;
}
```

用条件运算符简化：

```c
max=(a>b)?a:b;
```

条件运算符“?:”一般形式：

```c
表达式1 ? 表达式2 : 表达式3;
```

首先对第一个表达式的值进行检验，值真，返回第二个表达式的结果值；值假，返回第三个表达式的结果值。

```c
/*
出租车行驶时，路径不足3千米，收取起步价6元；路程如果超过3千米，则会在起步价金额上加上超出部
分的费用(按每千米2元收费)。使用条件运算符进行判断选择
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int jour, fee;								              //定义变量jour表示行驶路程，fee表示车费
	printf("请输入出租车走的公里数：\n");		    //提示输入出租车行驶的路程
	scanf("%d", &jour);							            //输入公里数
	fee = (jour < 3) ? 6 : 6 + (jour - 3) * 2;	//利用条件运算符计算费用
	printf("所花的费用是%d元\n", fee);			      //输出所花的费用
	return 0;
}
```

## 6.4 switch 语句

C 语言中可以使用 switch 语句直接处理多分支选择的情况，将程序代码的可读性提高。

### 6.4.1 switch 语句形式

switch 语句是多分支选择语句，一般形式：

```c
switch(表达式)
{
	case 情况1:
		语句块1;
	case 情况2:
		语句块2;
...
	case 情况n:
		语句块n;
	default:
		默认语句块;
}
```

switch 后面的表达式就是要进行判断的条件，然后使用 case 关键字表示检验条件符合的各种情况，其后的各语句块是相应的操作。其中还有一个 default 关键字，作用是如果没有符合条件的情况，那么执行 default 后的默认情况语句。

switch 语句检验的条件必须是一个整型表达式，这意味着其中也可以包含运算符和函数调用，而 case 语句检验的值必须是整型常量，即常量表达式或常量运算。

break 语句可用于跳出 switch 结构，不再执行下面的代码。

switch 语句中，如果所有 case 后面的值都不能匹配 switch 语句的条件，就执行 default 语句后面的代码。其中，任意两个 case 语句都不能使用相同的常量值；每个 switch 结构只能有一个 default 语句，而且 default 可以省略。

### 6.4.2 多路开关模式的 switch 语句

将某个 case 语句后的语句块及 break 去掉后，可以设计出多路开关模式的 switch 语句。

```c
switch(表达式)
{
	case 1:
		语句块1;
		break;
	case 2:
	case 3:
		语句块3;
		break;
...
	case n:
	default:
		默认语句块;
		break;
}
```

在 case2 后不使用 break 语句，那么符合 case2 检验与符合 case3 检验时的输出效果是一样的，多路开关模式可使得多种检验条件执行同一个操作。

```c
/*
要求使用switch语句判断输入的月份属于哪个季节。已知3、4、5月是春季，6、7、8月为夏季，9、10、11月为秋季，12、1、2月为冬季
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int month;								         //定义变量month表示月份
	printf("please enter a month：\n");
	scanf("%d", &month);					     //输入月份
	switch (month)							       //根据月份判断季节
	{
		//多路开关模式
		case 3:
		case 4:
		case 5:
			printf("%d is spring\n", month);//3、4、5月是春季
			break;
		//多路开关模式
		case 6:
		case 7:
		case 8:
			printf("%d is summer\n", month);//6、7、8月是夏季
			break;
		//多路开关模式
		case 9:
		case 10:
		case 11:
			printf("%d is autumn\n", month);//9、10、11月是秋季
		//多路开关模式
		case 12:
		case 1:
		case 2:
			printf("%d is winter\n", month);//12、1、2月是冬季
		default:
			printf("error!!!\n");			      //无此月份
	}
	return 0;
}
```

## 6.5 if…else 语句与 switch 语句的区别

### 6.5.1 语法比较

使用时 if 配合 else 关键字，先对条件进行判断；switch 配合 case 关键字，后进行判断。

### 6.5.2 效率的比较

if…else 结构对少量的检验，判断速度比较快，随着检验深度的增加，会逐渐变慢。

switch 结构中，除 default 默认情况比其他情况都快外，对其他每一项 case 的检验速度都是相同的。

当需要判定的情况较少时（分支四个以下），使用 if...else 结构比使用 switch 结构检验速度快，否则应选择 switch 结构。

```c
/*
给10086移动客服中心打电话，如果不是移动电话的用户，则提示“暂时无法提供服务”；
如果是移动的用户，则提示“查询话费请拨1，人工服务请拨0”。用户输入1之后，显示话费余额。
*/
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main()
{
	int telephone, num;								//定义两个变量，分别表示电话号码和选择的服务
	printf("请输入您要拨打的电话：\n");
	scanf("%d", &telephone);
	if (telephone == 10086)
	{
		//是移动用户，则进行以下操作
		printf("您好，欢迎致电中国移动，客服将为您提供以下服务：查询话费请拨1，人工服务请按0。\n");
		scanf("%d", &num);
		switch (num)
		{
		case 1:
			printf("您的话费余额为9.89元\n");
			break;
		case 0:
			printf("您好，欢迎使用移动客服业务，为了保证通话质量，您的通话将会被录音，谢谢合作。\n");
			break;
		default:
			printf("对不起，系统没有此业务");
		}
	}
	else
	{
		printf("暂时无法提供服务。\n");
	}
	return 0;
}
```

# 第7章 循环控制

用循环语句来处理程序开发中简单而重复的工作。

## 7.1 循环语句

C 语言中有 3 种循环语句：while、do…while、for。

## 7.2 while 语句

使用 while 语句可以解决当某个条件满足时反复执行某个循环体的问题。一般形式：

```c
while(表达式)
{
	语句块(循环体);
}
```

while 语句首先检验一个条件，也就是括号中的表达式。当条件为真时，就执行紧跟其后的循环体语句或者语句块。每执行一遍循环，程序都将回到 while 语句处，重新检验条件是否满足。如果一开始条件就不满足，则跳过循环体中的语句，直接执行后面的程序代码。如果第一次检验时条件满足，那么在第一次或其后的循环过程中，必须得有使条件为假的操作，否则循环将无法终止。

无法终止的循环常被称为死循环或者无限循环。

```c
while(sum<100)
{
	iSum+=1;
}
printf("iSum为：%d",iSum);
```

```c
//计算n~100的累加和(while版)
/*
用户输入一个值，从这个值开始，依次与之后的连续若干个自然数相加，当该自然数大于100时结束，并输出这若干个自然数的和
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int n, sum=0;
	printf("请输入一个自然数：\n");
	scanf("%d", &n);
	while (n <= 100)
	{
		sum += n;
		n++;
	}
	printf("结果为：%d\n", sum);
	return 0;
}
```

使用 while 语句时，很容易多执行一次或少执行一次循环，这类错误被称为“差一错误”。

```c
//细菌的繁殖数量(while版)
/*
生物实验室做单细胞细菌繁殖实验。 一代菌落中只有一个细菌，二代菌落中分裂成两个细菌，三代菌落中分裂成4个细菌，
以此类推，每代细菌数量都会成倍数增长。计算第十二代菌落中的细菌数量。使用while循环语句实现
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int x = 1, num = 1,n;
	printf("请输入菌落的代数：\n");
	scanf("%d", &n);
	while (x <= n)
	{
		num *= 2;
		x++;
	}
	printf("第%d代菌落中的细菌数量是%d。\n",n, num);
	return 0;
}
```

## 7.3 do…while 语句

在有些情况下，不论条件是否满足，循环过程必须执行至少一次，这时可以采用 do…while 语句，先执行循环体语句块中的内容，然后判断循环条件是否成立。一般形式：

```c
do
{
	语句块(循环体);
}while(表达式)
```

do…while 语句是这样执行的，首先执行一次循环体语句中的内容，然后判断表达式，当表达式的值为真时，返回重新执行循环体语句，然后再次判断表达式，直到表达式的值为假，此时循环结束。

while 语句和 do while 语句的区别在于：while 语句在每次循环之前检验条件，do while 语句在每次循环之后检验条件。

在使用 do while 语句时，条件表达式要放在 while 关键字后面的括号中，最后必须加上一个分号 (;)。

```c
//计算n~100的累加和(do...while版)
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int n, sum = 0;
	printf("请输入一个自然数：\n");
	scanf("%d", &n);
	do
	{
		sum += n;
		n++;
	} while (n <= 100);
	printf("结果为：%d\n", sum);
	return 0;
}
```

## 7.4 for 语句

### 7.4.1 for 循环语句

一般形式：

```c
//3个表达式之间用分号隔开
for(表达式1;表达式2;表达式3;)
{
	语句块(循环体);
}
```

执行到 for 语句时，程序首先计算第 1 个表达式的值，接着计算第 2 个表达式的值，如果第 2 个表达式的值为真，程序就执行循环体中的内容，并计算第 3 个表达式，然后检验第 2 个表达式，执行循环，如此反复直到第 2 个表达式的值为假，退出循环。

for 语句的形式也可以简单表示为：

```c
for(循环变量赋初值;循环条件;循环变量改变)
{
	语句块;
}

//实现一个循环输出的操作
for(i=1;i<100;i++)
{
	printf("the i is:%d",i);
}
```

```c
//计算小球的反弹高度
/*
一个球从80米高度自由落下，每次落地后反弹的高度为原高度的一半，计算小球第6次反弹的高度。
要求使用for循环语句计算小球反弹高度
*/
#include<stdio.h>
int main()
{
	int high = 80, i;
	for (i = 0; i < 6; i++)
	{
		high /= 2;
		printf("当前小球高度是%d\n", high);
	}
	printf("第6次反弹高度是%d\n", high);
	return 0;
}

```

for 循环的执行过程也可以使用 while 循环来表示：

```c
表达式1;
while(表达式2)
{
	语句块;
	表达式3;
}
```

```c

//计算n~100的累加和（for版）
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int i, sum = 0;
	printf("请输入一个自然数：\n");
	for (scanf("%d",&i); i <= 100; i++)
	{
		sum += i;
	}
	printf("结果是；%d\n", sum);
	return 0;
}
```

### 7.4.2 for 循环的变体

**1. for 语句中省略表达式 1**

表达式 1 的作用是对循环变量设置初值，如果省略了表达式 1，就会影响对表达式 2（即循环条件）的判断。为保证程序正常运行，应在 for 语句之前先给循环变量赋值。

```c
for(;iNumber<10;iNumber++)
```

省略表达式 1 时，其后分号不能省略。

```c
//求n!
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int n, i=1, sum = 1;
	printf("请输入n的值：\n");
	scanf("%d", &n);
	if (n >= 0)
	{
		for (; i <= n; i++)					//在for语句前给循环变量赋值
		{
			sum *= i;
		}
		printf("%d!=%d", n, sum);
	}
	else
	{
		printf("您输入的值不符合要求！\n");
	}
	return 0;
}
```

**2. for 语句中省略表达式 2**

表达式 2 给出的是循环条件，如果表达式 2 省略，则无法判断循环条件，也即默认表达式 2始终为真，因此循环将无终止地进行下去。

```c
for(iCount=1;;iCount++)
{
	sum+=iCount;
}

//等同于以下while语句
iCount=1;
while(1)
{
	sum+=iCount;
	iCount++;
}
```

for 循环中表达式 2 是不能省略的。

**3. for 语句中省略表达式 3**

表达式 3 用于改变循环变量，可以省略，但此时程序设计人员应在循环体内增加类似功能的语句，以保证循环能正常结束，否则程序也会无终止地循环下去。

```c
for((iCount=1;iCount<50;)
{
	sum+=iCount;
	iCount++;
}
```

### 7.4.3 for 循环中的逗号应用

在 for 语句中，表达式 1 和表达式 3 处除了可以使用简单的表达式，还可以使用逗号表达式，即包含一个以上的简单表达式，中间用逗号间隔，在逗号表达式内按照自左至右顺序求解，整个逗号表达式的值为其最右边的表达式的值。

```c
//在表达式1处为变量iCount和iSum设置初始值:
for(iSum=0,iCount=1;iCount<100;iCount++)
{
	iSum=iSum+iCount;
}
//或者在表达式3处执行循环体变量自加操作两次:
for(iCount=1;iCount<100;iCount++,iCount++)
{
	iSum=iSum+iCount;
}
//相当于
for(iCount=1;iCount<100;iCount=iCount+2)

```

```c
//计算1~100所有偶数的累加结果
/*
在本实例中，为变量赋初值的操作都放在for语句中，并且对循环变量进行两次自加操作，这样所求
出的结果就是所有偶数的和
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int iCount, iSum;
	//在for循环中为变量赋值，对循环变量进行两次自增运算
	for (iSum = 0, iCount = 0; iCount <= 100; iCount++, iCount++)
	{
		iSum += iCount;
	}
	printf("The result is %d.\n", iSum);
	return 0;
}

//iCount++, iCount++相当于iCount=iCount+2
```

浮点值的误差是不可避免的。如果在 for 循环的条件表达式中使用浮点值，那么将导致数值错误。因此，建议开发者不要使用浮点类型定义 for 语句的循环变量。

```c
//计算1-3+5-7+9~-99+100
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int i1,i2,iSum1=0, iSum2=0, iSum;
	for (i1 = 1; i1 <= 101; i1 += 4)
	{
		iSum1 += i1;
	}
	for (i2 = 3; i2 <= 99; i2 += 4)
	{
		iSum2 += i2;
	}
	iSum = iSum1 - iSum2;
	printf("1-3+5-7+9-...-99+101=%d\n", iSum);
	return 0;
}
```

## 7.5 循环嵌套

循环嵌套：一个循环体内还可以包含一个或多个其他循环结构。

### 7.5.1 while 循环中嵌套 while 循环

```c
while(表达式)
{
	语句块;
	while(表达式)
	{
		语句块;
	}
}
```

### 7.5.2 do…while 循环中嵌套 do…while 循环

```c
do
{
	语句块;
	do
	{
		语句块;
	}while(表达式);
}while(表达式);
```

### 7.5.3 for 循环中嵌套 for 循环

```c
for(表达式;表达式;表达式)
{
	语句块;
	for(表达式;表达式;表达式)
	{
		语句块;
	}
}
```

### 7.5.4 do…while 循环中嵌套 while 循环

```c
do
{
	语句块;
	while(表达式)
	{
		语句块;
	}
}while(表达式);
```

### 7.5.5 do…while 循环中嵌套 for 循环

```c
do
{
	语句块;
	for(表达式;表达式;表达式)
	{
		语句块;
	}
}while(表达式);
```

```c
/*
中国古典《算经》中有一道著名的百钱买鸡问题：鸡翁一，值钱五；鸡母一，值钱三；鸡雏三，值钱一；
百钱买百鸡，问翁母雏各几只？利用循环嵌套输出结果
*/
#include<stdio.h>
int main()
{
	int x, y, z;													                //定义变量x为鸡翁，y为鸡母，z为鸡雏
	for (x = 0; x < 20; x++)										          //for循环，最多可以买20个鸡翁
	{
		for (y = 0; y < 33; y++)									          //循环嵌套，最多可以买33个鸡母
		{
			z = 100 - x - y;										              //鸡雏的数量，三者满足100只鸡
			if (5 * x + 3 * y + z / 3.0 == 100)					    	//判断这3种鸡要花100
				printf("鸡翁=%d,鸡母=%d,鸡雏=%d\n", x, y, z);		//如果为真，输出结果
		}
	}

	for (int t = 0; t <= 3; t++)
	{
		x = 4 * t;
		y = 25 - 7*t;
		z = 75 + 3*t;
		printf("鸡翁=%d,鸡母=%d,鸡雏=%d\n", x, y, z);
	}

	return 0;
}

/*
中国古代数学家张丘建在他的《算经》中提出了著名的“百钱买百鸡问题”：鸡翁一，值钱五，鸡母一，
值钱三，鸡雏三，值钱一，百钱买百鸡，问翁、母、雏各几何？

题目分析与算法设计
设鸡翁、鸡母、鸡雏的个数分别为x,y,z，题意给定共100钱要买百鸡，若全买公鸡最多买20只，显然x的值
在0~20之间；同理，y的取值范围在0~33之间，可得到下面的不定方程：
5x+3y+z/3=100
x+y+z=100
所以此问题可归结为求这个不定方程的整数解。
由程序设计实现不定方程的求解与手工计算不同。在分析确定方程中未知数变化范围的前提下，可通过对未
知数可变范围的穷举，验证方程在什么情况下成立，从而得到相应的解

程序说明与注释
#include<stdio.h>
void main()
{
	int x,y,z,j=0;
	printf("Following are possible plans to buy 100 fowls with 100 Yuan.\n");
	for(x=0;x<=20;x++)  														                //外层循环控制鸡翁数
	{
		for (y = 0; y <= 33; y++)													            //内层循环控制鸡母数y在0~33变化
		{
			z = 100 - x - y;														                //内外层循环控制下，鸡雏数z的值受x,y的值的制约
			if (z % 3 == 0 && 5 * x + 3 * y + z / 3 == 100)							//验证取z值的合理性及得到一组解的合理性
			{
				printf("%2d:cock=%2d hen=%2d chicken=%2d\n", ++j, x, y, z);
			}
		}
	}
}
运行结果
Follwing are possible plans to buy 100 fowls with 100 Yuan.
1 : cock = 0 hen = 25 chicken = 75
2 : cock = 4 hen = 18 chicken = 78
3 : cock = 8 hen = 11 chicken = 81
4 : cock = 12 hen = 4 chicken = 84 
*/
```

```c
//本实例要求打印出乘法口诀表，每一项都是行和列的相乘算式。
#include<stdio.h>
int main()
{
	printf("\t乘法口诀表\n");
	int iRow, iColumn;												//定义变量iRow为行，iColumn为列
	for (iRow = 1; iRow <= 9; iRow++)
	{
		for (iColumn = 1; iColumn <= iRow; iColumn++)
		{
			printf("%d*%d=%d\t", iRow, iColumn, iRow * iColumn);	//使用制表符控制间距，可排列更整齐
		}
		printf("\n");
	}
	return 0;
}

/*
在本实例中用到两次for循环，第一个for循环可看成乘法口诀表的行数，同时也是每行进行乘法运算的第
一个因子；第二个for循环范围的确定建立在第一个for循环的基础上，即第二个for循环的最大取值是第一
个for循环中变量的值
*/
```

```c
//打印杨辉三角
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#define N 14
void main()
{
    int i, j, k, n = 0, a[N][N];           /*定义二维数组a[14][14]*/
    while (n <= 0 || n >= 13)              /*控制打印的行数不要太大，过大会造成显示不规范*/
    {                             
        printf("请输入要打印的行数：\n");
        scanf("%d", &n);
    }
    printf("%d行杨辉三角如下：\n", n);
    for (i = 1; i <= n; i++)
    {
        a[i][1] = a[i][i] = 1;              /*两边的数令它为1，因为现在循环从1开始，就认为a[i][1]为第一个数*/
    }
    for (i = 3; i <= n; i++)
    {
        for (j = 2; j <= i - 1; j++)
        {
            a[i][j] = a[i - 1][j - 1] + a[i - 1][j];/*除两边的数外都等于上两顶数之和*/
        }
    }
    for (i = 1; i <= n; i++) {
        {
            for (k = 1; k <= n - i; k++)
            {
                printf("   ");                      /*这一行主要是在输出数之前打上空格占位，让输出的数更美观*/
            }
            for (j = 1; j <= i; j++)                /*j<=i的原因是不输出其它的数，只输出我们想要的数*/
            {
                printf("%6d", a[i][j]);
            }
        }

        printf("\n");                                /*当一行输出完以后换行继续下一行的输出*/
    }
    printf("\n");
}
```

```c
//输出金字塔形状
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main()
{
	int i, j, k, n;
	printf("请输入行数：\n");
	scanf("%d", &n);
	for (i = 1; i <= n; i++)
	{
		for (j = 1; j <= n - i; j++)
		{
			printf(" ");
		}
		for (k = 1; k <= 2 * i - 1; k++)
		{
			printf("*");
		}
		printf("\n");
	}
	return 0;
}
```

## 7.6 转移语句

转移语句包括 goto 语句、break 语句和 continue 语句。

### 7.6.1 goto 语句

goto 语句为无条件转移语句，可以使程序立即跳转到函数内部的任意一条可执行语句处，goto 关键字后面带一个标识符，该标识符是同一个函数内某条语句的标号（标号可以出现在任何可执行语句前面，并且以一个冒号 “:”）作为后缀。一般形式：

```c
goto 标识符;

goto Show;
printf("the message before ShowMessage");
Show:
		printf("ShowMessage");
//第二行printf函数不执行
```

跳转方向可以向前，也可以向后，可以跳出一个循环，也可以跳入一个循环。

```c
//下一步还是退出
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h >
int main()
{
	int iStep;									            //定义变量，表示外层for循环的步骤号
	int iSelect;								            //定义变量，保存用户输入的选项
	for (iStep = 1; iStep < 10; iStep++)		//外层for循环，记录循环的次数(步骤号)。
	{
		printf("步骤号:%d\n", iStep);			    //输出当前循环的步骤号
		do										                //内层do...while循环，保证用户输入0或99
		{
			printf("请输入一个选择序号: \n");	  //输出提示信息
			printf("(0是退出，99是下一步)\n");
			scanf("%d", &iSelect);				      //用户输入选择
			if (iSelect == 0)					          //判断输入的是否为0
			{
				goto exit;						            //如果是0, 执行goto跳转语句
			}
		} while (iSelect != 99);				      //判断用户输入，只要不是99就重新输入序号
	}
	exit:										                //跳转语句执行位置
		printf("退出程序\n");
		return 0;
}
```

### 7.6.2 break 语句

break 语句用于终止并跳出当前循环，然后继续执行后面的代码。一般形式：

```c
break;

//在while循环语句中使用break语句
while(1)
{
	printf("Break");
	break;
}
```

break 语句不能用于除循环语句和 switch 语句之外的任何其他语句中，另外，在多层嵌套循环中，break 语句只能跳出当前循环。

循环体中的 break 语句和 switch...case 分支结构中的 break 语句的作用是不同的。

```c
/*
使用for语句执行循环输出10次的操作，在循环体中判断输出的次数。当循环变量为5次时，使用break语句跳出循环，终止循环输出操作
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h >
int main()
{
	int iCount;
	for (iCount = 0; iCount <= 10; iCount++)
	{
		if (iCount == 5)
		{
			printf("Break here!\n");
			break;
		}
		printf("The counter is %d.\n", iCount);
	}
	return 0;
}
```

### 7.6.3 continue语句

continue 语句作用就是结束本次循环，即跳过循环体中尚未执行的部分，直接执行下一次的循环操作。一般形式：

```c
continue;
```

continue 语句和 break 语句的区别是：continue 语句只结束本次循环，而不是终止整个循环的执行；break 语句则是结束整个循环过程，不再判断执行循环的条件是否成立。

```c
//寻找continue
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h >
int main()
{
	int iCount;
	for (iCount = 0; iCount <= 10; iCount++)
	{
		if (iCount == 5)
		{
			printf("Continue here!\n");
			continue;
		}
		printf("The counter is %d.\n", iCount);
	}
	return 0;
}
```

# 第8章 数组

用数组存储大量相同类型的数据。

## 8.1 一维数组

### 8.1.1 **一维数组的定义**

一组相同类型数据的线性集合。定义形式：

```c
类型说明符 数组标识符[常量表达式];
```

类型说明符：表示数组中元素的类型。

数组标识符：表示该数组型变量的名称，命名规则与变量名一致。

常量表达式：定义了数组中存放的数据元素个数，即数组长度。

```c
//定义一个包含5个整型元素的数组
int iArray[5];
```

### 8.1.2 **一维数组的引用**

数组定义后，可以引用其中的数组元素，引用方式为“数组标识符[下标]”。

例如，引用数组 iArray 中的第三个变量，格式为 iArray[2]。数组下标从 0 开始的，iArray[0] 表示第一个元素，iArray[1] 表示第二个元素，以此类推…

数组下标可以是整型常量或整型表达式。

```c
//使用数组保存手机号
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int iArray[11], index;					      //定义数组及变量为基本整型
	printf("请输入手机号：\n");
	for (index = 0; index < 11; index++)	//逐个输入手机号码，保存为数组元素
	{
		scanf("%d", &iArray[index]);
	}
	printf("手机号是：\n");
	for (index = 0; index < 11; index++)	//循环输出数组中的元素
	{
		printf("%d", iArray[index]);
	}
	printf("\n");
	return 0;
}
```

### 8.1.3 一维数组的初始化

```c
//定义数组时直接对数组元素赋初值（数组元素值放在一对大括号中）
intarray[6]={1,2,3,4,5,6};

//如果只给一部分数组元素赋值，则未赋值的元素默认为被赋值0
int array[6]={1,2,3};

//当对全部数组元素都赋值时，可以不指定数组长度
int array[]={1,2,3,4};
//系统默认该数组变量的长度为4

```

```c
//计算篮球平均成绩
#include<stdio.h>
int main()
{
	int grade[10] = { 12,5,21,15,32,10,25,14,30,20 };	//定义数组，给出球员的10场比赛成绩
	int total = 0;										                //定义变量，表示总成绩
	int i;
	float avg;											                  //定义变量，表示平均成绩
	for (i = 0; i < 10; i++)							            //循环累计总成绩
	{
		total += grade[i];
	}
	avg = ((float)total / 10);							          //计算平均成绩
	printf("篮球比赛的平均成绩是: %f\n ", avg);
	return 0;
}
```

### 8.1.4 一维数组的应用

```c
//输出插队之后的编号
/*
体育课上，老师按身材高矮给20名同学编号。刚编完号，一位男生姗姗来迟，老师比对后将他排
在8号位置，并重新排列后面的同学。使用数组，输出男生插队后有变化的学生编号
*/
#include<stdio.h>
int main()
{
	//定义数组及变量为基本整型
	int iArray[20] = { 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20 }, index;
	int iArray1[21] = { 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21 }, index1;
	printf("体育老师按身材高矮排队编号，老师排好，编号是：\n");								//提示信息
	for (index = 0; index < 20; index++)													//循环输出插队前所有学生的编号
	{
		printf("%d ", iArray[index]);
	}
	printf("\n");
	printf("重新排列插队男生及后面的同学，他们的编号是：\n");	//男生插入后，从8号开始重新编号
	for (index1 = 7; index1 < 21; index1++)													//从下标7开始，循环输出后续编号
	{
		printf("%d ", iArray1[index1]);
	}
	printf("\n");
	return 0;
}
```

## 8.2 二维数组

### 8.2.1 二维数组的定义

看作特殊的一维数组，其各个元素任然是一个数组。定义形式：

```c
数据类型 数组名[常量表达式1][常量表达式2];
```

“常量表达式 1”定义了二维数组的行数，“常量表达式 2”定义了二维数组的列数。不管是行下标还是列下标，其索引都是从 0 开始的。一个 m 行 n 列的二维数组 array[m][n]，其行下标取值范围为 0~m-1，列下标取值的范围为 0~n-1，最大下标元素 array[m-1][n-1]。

```c
int array[3][4];
//C语言中数组是按行优先排列的
array[0][0]、array[0][1]、array[0][2]、array[0][3]
array[1][0]、array[1][1]、array[1][2]、array[1][3]
array[2][0]、array[2][1]、array[2][2]、array[2][3]
```

### 8.2.2 二维数组的引用

二维数组的引用形式为“数组名[下标][下标]”，例如，array[1][2] 表示对 array 数组的第 2 行第 3 个元素进行引用，与一维数组一样，二维数组也要注意下标越界的问题！

### 8.2.3 二维数组的初始化

```c
//将所有数据写在一个大括号内，按照数组元素排列顺序对元素赋值
int array[2][2]={1,2,3,4};
//大括号内的数据少于数组元素的个数，则系统会默认后面未被赋值的元素值为0

//为所有元素赋初值时，可以省略行下标，但不能省略列下标
int array[][3]={1,2,3,4,5,6};

//分行给数组元素赋值，可以只对部分元素赋值
int array[2][3]={{1,2,3},{4,5,6}}

//直接对数组元素赋值
int array[2][3];
array[0][0]=1;
array[0][1]=2;
```

```c
/*
一个3x3的网格，将1-9的数字放入方格中(矩阵中心元素为5)，使得每行、每列以及每条对角线上
的3个数相加都相同。通过键盘为二维数组元素赋值，并显示二维数组。
2       7       6
9       5       1
4       3       8
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int a[3][3];							      //定义二维数组
	int i, j;								        //定义循环控制变量
	for (i = 0; i < 3; i++)					//先行后列，依次输入数据，为数组元素赋值
	{
		for (j = 0; j < 3; j++)
		{
			printf("a[%d][%d]=", i, j);
			scanf(" %d", &a[i][j]);
		}
	}
	printf("输出二维数组：\n");			//信息提示
	for (i = 0; i < 3; i++)					//先行后列，循环输出所有数组元素的值
	{
		for (j = 0; j < 3; j++)
		{
			printf("%d\t", a[i][j]);		//使用制表符控制间距，可排列更整齐
		}
		printf("\n");						      //使数组元素分行显示
	}
	return 0;
}
```

### 8.2.4 二维数组的应用

```c
/*
本实例中，把二维数组中各行的元素换成列元素，各列的元素换成行元素，生成一个新的二维数组。
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int a[2][3], b[3][2];				  //定义两个数组
	int i, j;							        //定义两个循环变量

	for (i = 0; i < 2; i++)				//先行后列，输入数据，为数组元素赋值
	{
		for (j = 0; j < 3; j++)
		{
			printf("a[%d][%d]=", i, j);
			scanf("%d", &a[i][j]);
		}
	}
	printf("输出二维数组：\n");		//信息提示
	for (i = 0; i < 2; i++)				//先行后列，循环输出二维数组a中的元素
	{
		for (j = 0; j < 3; j++)
		{
			printf("%d\t", a[i][j]);
		}
		printf("\n");					      //使数组元素分行显示
	}
	for (i = 0; i < 2; i++)				//将数组a转置后存入数组b中
	{
		for (j = 0; j < 3; j++)			
		{
			b[j][i] = a[i][j];			  //通过行列互换，b为a的转置数组
		}
	}
	printf("输出转置后的二维数组：\n");
	for (i = 0; i < 3; i++)				//先行后列，循环输出二维数组b中的元素
	{
		for (j = 0; j < 2; j++)
		{
			printf("%d\t", b[i][j]);
		}
		printf("\n");					      //使数组元素分行显示
	}
	return 0;
}
```

```c
//打印数组对角线上的字符
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	char ccArray[5][5] = 
	{
	{'a','b','e','d','e'},
	{'b','a','8','d','d'},
	{'c','d','a','e','c'},
	{'d','j','f','a','b'},
	{'e','d','a','f','a'},
	};
	int i, j;
	for (i = 0; i < 5; i++)
	{
		j = i;
		printf("对角线上的字符是：\n", ccArray[i][j]);
	}
	return 0;
}
```

## 8.3 字符数组

### 8.3.1 字符数组的定义

数组中的元素类型为字符型，字符数组中的每个元素可以存放一个字符。定义形式：

```c
char 数组标识符[常量表达式];

//定义一个字符数组cArray，该数组中包含5个字符型的变量元素
char cArray[5];
```

### 8.3.2 字符数组的引用

也采用下标的形式。

```c
//引用数组cArray中的元素，并依次赋值
cArray[0]='H';
cArray[1]='e';
cArray[2]='l';
cArray[3]='l';
cArray[4]='o';
```

### 8.3.3 字符数组的初始化

```c
//定义一个包含5个元素的字符数组
//逐个字符赋给数组中的元素
char cArray[5]={'H','e','l','l','o'};

//定义字符数组的同时进行初始化，此时可省略数组长度
char cArray[]={'H','e','l','l','o'};

//利用字符串给字符数组赋初值
char cArray[]={"Hello"};
//或
char cArray[]="Hello";
```

### 8.3.4 字符数组的结束标志

在 C 语言中，使用字符数组保存字符串时，系统会自动为其添加 ”\0“ 作为结束符。也就是说用字符串方式赋值会比用字符逐个赋值要多占一个字节，多占的这个字节用于存放字符串结束标识 ”\0“。

```c
char cArray[]="Hello";
//等价于
char cArray[]={'H','e','l','l','o','\0'};
//等价于
char cArray[6]={'H','e','l','l','o','\0'};
```

![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//2.png)

如果在一个字符数组中先后存放多个不同长度的字符串，则应使数组长度大于最长的那个字符串的长度。

### 8.3.5 字符数组的输入输出

使用格式字符 ”%c” 和 ”%s”。

使用格式字符 ”%c” 可以实现数组中字符的逐个输入与输出。

```c
for(i=0;i<5;i++)
{
	printf("%c",cArray[i]);//逐个输出数组元素
}
```

使用格式字符 ”%s” 可以将整个字符串输入或输出。

```c
char cArray[]="GoodDay!"
printf("%s",cArray);//输出字符串
```

使用 ”%s” 输出字符串时，需要注意以下几种情况：

输出字符串不包括结束符 ”\0”。

printf 函数中的输出项是字符数组名 cArray，而不是数组中元素名 cArray[0] 等。

即使数组长度大于字符串实际长度，也只会输出到 ”\0” 为止。

如果一个字符数组中包含多个 ”\0” 结束字符，则在遇到第一个 ”\0” 时输出就结束。

C 语言中只存在字符类型，不存在字符串类型。字符类型只能存放单个字符，如果要存放字符串，就需要使用字符数组。当然，也可以使用字符型指针存放字符串。

### 8.3.6 字符数组的应用

```c
//随机输入一个字符串，计算其长度
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#define A 'abcd'
int main()
{
	int iIndex;									//循环控制变量
	int length = 0;							//定义变量length，保存字符串长度
	char cArray[80];						//定义字符数组，保存用户输入的字符串
	printf("请输入字符串：\n");
	gets(cArray);								//用gets函数输入字符串
	//循环字符数组，直到遇到“\0”结束
	for (iIndex = 0; cArray[iIndex] != '\0'; iIndex++)
	{
		length++;									//每遍历一个字符，字符串长度加1
	}
	//输出字符串长度
	printf("字符串长度是：%d\n字符串A的长度是：%d\n", length,sizeof(A));
	return 0;
}
```

## 8.4 多维数组

多维数组的声明和二维数组相同，只是下标更多。一般形式：

```c
数据类型 数组名[常量表达式1][常量表达式2]...[常量表达式n]

//三维数组
int iArray1[3][4][5]
//四维数组
int iArray2[3][4][5][6]
```

数组元素的位置可以通过偏移量计算，对三维数组 a[m][n][p] 来说，元素 a[i][j][k] 所在的地址是从 a[0][0][0] 算起到 i*n*p+j*p+k 个单位的位置。

## 8.5 数组的排序算法

### 8.5.1 选择法排序

每次在待排序数组中查找最大或最小的数组元素，将其值与最前面没有进行过排序的数组元素的值互换。这里，由大到小排序应查找最大值，由小到大排序则应查找最小值。

```c
//选择法从小到大
/*
本实例中，声明了一个整型数组和两个整型变量。其中，整型数组用于存储用户输入的10个数值，而整型变量用于存储数值最
小的数组元素和该元素的位置。通过双层循环进行选择法排序，最后将排好序的数组元素输出。
*/
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main()
{
	int i, j;
	int a[10];										//定义数组，存储用户输入的10个数
	int iTemp;										//定义变量，表示最小的数组元素
	int iPos;										  //定义变量，表示元素位置
	printf("为数组元素赋值：\n");
	for (i = 0; i < 10; i++)			//输入10个数，为数组元素赋值
	{
		printf("a[%d]=", i);
		scanf("%d", &a[i]);
	}
	//使用选择法对数组元素从小到大排序
	for (i = 0; i < 9; i++)				//设置外层循环下标为0~8,表示前9个数组元素
	{
		iTemp = a[i];								//假设当前元素为最小值
		iPos = i;									  //记录最小元素位置
		for (j = i + 1; j < 10; j++)//设置内层循环下标为i+1~9，表示剩下的未排序数组元素部分
		{
			if (a[j] < iTemp)					//如果后续的元素中有数比前面设定的最小值还小
			{
				iTemp = a[j];						//重新设定最小值
				iPos = j;							  //修正最小元素位置
			}
		}
		a[iPos] = a[i];							//此两行代码用于将最小的数组元素和当前排序次数对应的数组元素互换
		a[i] = iTemp;
	}
	printf("排序结果如下: \n");
	for (i = 0; i < 10; i++)			//输出数组
	{
		printf("%d\t", a[i]);				//用制表位分隔数据
	}
	printf("\n");
	return 0;
}
```

### 8.5.2 冒泡排序

每次比较数组中相邻的两个数组元素的值，将较小的数排在较大的数前面，可实现数组元素从小到大排序。每次将较大的数排在较小的数前面，可实现数组元素从大到小排序。

```c
//冒泡法从小到大
/*
声明一个整型数组和一个整型变量，整型数组用于存储用户输入的数字，整型变量作为两个元素交换时的中间变量，通过双层循环
进行冒泡法排序，最后将排好序的数组输出。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int i, j;
	int a[10];
	int iTemp;
	printf("为数组元素赋值: \n");
	for (i = 0; i < 10; i++)				//输入10个数，为数组元素赋值
	{
		printf("a[%d]=", i);
		scanf("%d", &a[i]);
	}
	//采用冒泡法使数组元素从小到大排序*/
	for (i = 1; i < 10; i++)				//外层循环元素的下标为1~9, 表示后9个数组元素
	{
		for (j = 9; j >= i; j--)			//内层循环元素的下标为9~i,表示从最后一个元素开始向前循环
		{
			if (a[j] < a[j - 1])			  //如果前一个数比后一个数大
			{
				//交换两个数组元素的值，使小数前移，如同冒泡
				iTemp = a[j-1];
				a[j - 1] = a[j];
				a[j] = iTemp;
			}
		}
	}
	printf("排序结果如下: \n");
	for (i = 0; i < 10; i++)				//输出数组
	{
		printf("%d\t", a[i]);				  //用制表位分隔数据
	}
	printf("\n");
	return 0;
```

### 8.5.3 交换法排序

将每一位数与其后的所有数一一比较，如果发现符合条件的数据，则交换数据。首先，用第一个数依次与其后的所有数进行比较，如果存在比其值大（小）的数，则交换这两个数，继续向后比较其他数直至最后一个数。然后再使用第二个数与其后面的数进行比较，如果存在比其值大（小）的数，则交换这两个数。继续向后比较其他数，直至最后一个数比较完成。

```c
//交换法从小到大
/*
声明一个整型数组和一个整型变量，其中整型数组用于存储用户输入的数字，整型变量则作为两个元素交换时的中间变量，然后
通过双层循环进行交换法排序，最后将排好序的数组输出。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int i, j;
	int a[10];
	int iTemp;
	printf("为数组元素赋值: \n");
	for (i = 0; i < 10; i++)			//输入10个数，为数组元素赋值
	{
		printf("a[%d]=", i);
		scanf("%d", &a[i]);
	}
	//采用交换法使数组元素从小到大排序
	for (i = 0; i < 9; i++)				//外层循环元素下标为0~8, 表示前9个数组元素
	{
		for (j = i + 1; j < 10; j++)//内层循环元素下标为i+1~9，表示后面的待比较数组元素
		{
			if (a[j] < a[i])			    //如果后一个数比前一一个数小
			{
				iTemp = a[i];			      //交换两个数组元素的值，使小数前移
				a[i] = a[j];
				a[j] = iTemp;
			}
		}
	}
	printf("排序结果如下: \n");
	for (i = 0; i < 10; i++)			//输出数组
	{
		printf("%d\t", a[i]);			  //用制表位分隔数据
	}
	printf("\n");
	return 0;
}
```

### 8.5.4 插入法排序

抽出一个数据，在前面的数据中寻找相应的位置插入，然后继续下一个数据，直到完成排序。

```c
//插入法从小到大
/*
声明一个整型数组和两个整型变量，其中整型数组用于存储用户输入的数字，一个整型变量作为两个元素交换时的中间变量，
一个用于记录数组元素的位置，然后通过双层循环进行交换法排序，最后将排好序的数组输出。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int i;
	int a[10];
	int iTemp;
	int iPos;
	printf("为数组元素赋值: \n");
	for (i = 0; i < 10; i++)						        //输入10个数，为数组元素赋值
	{
		printf("a[%d]=", i);
		scanf("%d", &a[i]);
	}
	//采用插入法使数组元素从小到大排序
	for (i = 1; i < 10; i++)						        //外层循环元素下标为1~9, 表示后9个数组元素
	{
		iTemp = a[i];//设置插入值
		iPos = i - 1;
		while ((iPos >= 0) && (iTemp < a[iPos]))	//内层循环， 寻找插入值的位置
		{
			a[iPos + 1] = a[iPos];					        //插入数值
			iPos--;
		}
		a[iPos + 1] = iTemp;
	}
	printf("排序结果如下: \n");					      	//输出数组
	for (i = 0; i < 10; i++)
	{
		printf("%d\t", a[i]);					          	//用制表位分隔数据
	}
	printf("\n");
	return 0;
}
```

### 8.5.5 折半法排序

又称为快速排序，其基本原理为：选择一个中间值（在程序中使用数组中间元素的值），然后把比中间值小的元素放在左边，比中间值大的元素放在右边（具体的实现是从两边查找，找到一对后进行交换），然后再对左右两边分别递归使用折半法排序过程。

```c
//折半法从小到大
/*
在本实例中声明了一个整型数组，用于存储用户输入的数字，再定义一个函数，用于对数组元素进行排序，最后将排序好的数组输出。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
void CelerityRun(int left, int right, int array[]);	//声明函数

int main()
{
	int i;
	int a[10];
	printf("为数组元素赋值: \n");
	for (i = 0; i < 10; i++)						//输入10个数，为数组元素赋值
	{
		printf("a[%d]=", i);
		scanf("%d", &a[i]);
	}
	CelerityRun(0, 9, a);							  //调用折半排序函数
	printf("排序结果如下: \n");
	for (i= 0; i < 10; i++)							//输出数组
	{
		printf("%d\t", a[i]);					    //用制表位分隔数据
	}
	printf("\n");
	return 0;
}

void CelerityRun(int left, int right, int array[])	//定义折半排序函数
{
	int i, j;
	int middle, iTemp;
	i = left;
	j = right;
	middle = array[(left + right) / 2];				        //求中间值
	do
	{
		while ((array[i] < middle) && (i < right))	    //从左查找小于中间值的数
			i++;
		while ((array[j] > middle) && (j > left))	      //从右查找大于中间值的数
			j--;
		if (i <= j)									                    //如果找到一对值
		{
			iTemp = array[i];					                  	//交换两个值
			array[i] = array[j];
			array[j] = iTemp;
			i++;
			j--;
		}
	} while (i <= j);						                  		//如果两边的下标交错，就停止(完成一次)
	if (left < j)									                    //递归左半边
		CelerityRun(left, j, array);
	if (right > i)								                  	//递归右半边
		CelerityRun(i, right, array);
}
```

## 8.6 数组应用

### 8.6.1 反转输出字符串

```c
/*
定义两个字符数组，一个表示源字符串，另一个表示反转后的目标字符串。在源字符串中从第一个字符开始遍历，将第一个字符赋给
目标字符串的最后一个字符，将第二个字符赋给目标字符串的倒数第二个字符，依此类推，这样就实现了字符串的反转。
*/

#include<stdio.h>
int main()
{
	int i;
	char String[7] = { "mrsoft" };			  	//定义源字符串
	char Reverse[7] = { 0 };					      //定义反转字符串
	int size;
	size = sizeof(String);						      //计算源字符串长度
	for (i = 0; i < 6; i++)						      //循环读取字符
	{
		Reverse[size - i - 2] = String[i];		//源字符串倒序存入反转字符串
	}
	printf("输出源字符串： %s\n", String);		//输出源字符串
	printf("输出目标字符串：%s\n", Reverse);	//输出目标字符串
	return 0;	
}
```

### 8.6.2 输出系统日期和时间

```c
/*
设计一个程序，当用户输入0时显示帮助信息，输入1时显示系统日期，输入2时显示系统时间，输入3时退出系统。
要实现上述功能，需要解决两个问题：一是要不断地保持程序运行，等待用户输入命令，防止main函数结束；二是要获取系统日期和时间。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<time.h>

int main()
{
	int command[4] = { 0,1,2,3 };       //定义一个数组
	int num;
	struct tm* sysTime;
	printf("如需帮助可输入数字0!\n");   //输出提示信息
	printf("请输入命令符：\n");
	while (1)                          //通过while循环，保证始终等待用户输入
	{
		scanf("%d", &num);               //获得输入数字
		//判断用于输入的字符
		if (command[0] == num)           //如果用户输入数字0
		{
			//输出帮助信息
			printf("输入数字1显示系统日期，输入数字2显示系统时间，输入数字3退出系统! \n");
		}
		else if (command[1] == num)      //如果用户输入数字1
		{
			time_t nowTime;
			time(&nowTime);                //获取系统日期
			sysTime = localtime(&nowTime); //转换为系统日期
			printf("系统日期： %d-%d-%d \n", 1900 + sysTime->tm_year, sysTime->tm_mon + 1, sysTime->tm_mday);//输出信息
		}
		else if (command[2] == num)      //如果用户输入数字2
		{
			time_t nowTime;
			time(&nowTime);                //获取系统时间
			sysTime = localtime(&nowTime); //转换为系统时间
			printf("系统时间：%d:%d:%d \n", sysTime->tm_hour, sysTime->tm_min, sysTime->tm_sec);
		}
		else if (command[3] == num)      //如果用户输入数字3
		{
			return 0;                      //退出系统
		}
		printf("请输入命令符: \n");      //输出提示信息
	}
	return 0;
}
```

### 8.6.3 字符串的加密和解密

```c
/*
设计一个加密和解密算法，对一个指定的字符串加密后，再利用解密函数对密文解密，显示明文信息。加密的方式是将字符串中每个字符
加上它在字符串中的位置和一个偏移值5。以字符串“mrsoft”为例，第一个字符m在字符串中的位置为0，那么它对应的密文是'm'+0+5,即r。
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<string.h>

int main()
{
	int result = 1;
	int i;
	int count = 0;
	char Text[128] = { '\0' };							      	//定义一个明文字符数组
	char cryptograph[128] = { '\0' };					      //定义一个密文字符数组
	while (1)
	{
		if (result == 1)									            //如果用户输入1, 加密明文
		{
			printf("请输入要加密的明文: \n");			      //输出提示信息
			scanf("%s", &Text);								          //获取输入的明文
			count = strlen(Text);
			for (i = 0; i < count; i++)						      //遍历明文
			{
				cryptograph[i] = Text[i] + i + 5;		      //设置加密字符
			}
			cryptograph[i] = '\0';							        //设置字符串结束标记
			printf("加密后的密文是: %s\n", cryptograph);	//输出密文信息
		}
		else if (result == 2)								          //如果用户输入2,解密字符串
		{
			count = strlen(Text);
			for (i = 0; i < count; i++)						      //遍历密文字符串
			{
				Text[i] = cryptograph[i] - i - 5;			    //设置解密字符
			}
			Text[i] = '\0';								            	//设置字符串结束标记
			printf("解密后的明文是: %s\n", Text);		  	//输出明文信息
		}
		else if (result == 3)								          //如果用户输入3, 退出系统
		{
			break;											                //跳出循环
		}
		else
		{
			printf("请输入命令符: \n");						      //输出提示信息
		}
		printf("输入1加密新的明文，输入2对刚加密的密文进行解密，输入3退出系统: \n");
		printf("请输入命令符: \n");							      //输出提示信息，提示用户输入指令
		scanf("%d", &result);							          	//获取输入的命令字符
	}
	return 0;
}
```

# 第9章 函数

大型程序一般会被分为若干个程序模块，每个模块实现一个特定功能。C 语言中，由函数实现子程序，由子程序实现模块功能。

## 9.1 函数概述

构成 C 程序的基本单元是函数，函数中包含着程序的可执行代码。

每个 C 程序的入口和出口都位于 main 函数中，但并不需要把所有指令都放在 main 函数中。一般的做法是将程序划分成若干个模块，每个模块完成一部分功能，不同的程序模块可以由不同的人来完成，从而提高软件开发的效率。

主函数可以调用其他函数，其他函数间也可以相互调用。函数可以有参数和返回值，通过它们实现数据间的传递。在主函数中调用其他函数，这些函数执行完毕之后会返回 main 函数中。通常把这些被调用的函数称为下层函数。函数调用发生时，立即执行被调用的函数，而调用者则进入等待的状态，直到被调用函数执行完毕。

```c
//编写三个函数
#include<stdio.h>
void Fish();
void Cook();
void Poem();

int main()
{
	Fish();
	Cook();
	Poem();
	return 0;
}
void Fish()
{
	printf("钓鱼！\n");
}
void Cook()
{
	printf("做饭！\n");
}
void Poem()
{
	printf("写诗\n");
}
```

源文件：由一个或者多个函数组成。C 语言以源程序为单位进行编译，而不是以函数为单位进行编译。

库函数：由 C 语言系统提供，用户无须定义，调用前也不必做类型说明，但需要在程序开始部分包含有该函数原型的头文件。

例如，要使用能在控制台显示信息的 printf 函数，需在程序开始时包含 stdio.h 头文件；要使用字符串操作函数 strlen、strcmp 等时，需在程序开始时包含 string.h 头文件。

用户自定义函数：用户编写的用来实现特定功能的函数。例如，Cook、Fish 和 Poem 函数都是自定义函数。

## 9.2 函数的定义和声明

### 9.2.1 函数的定义

函数的定义是为了让编译器知道函数的功能，一个函数应包括函数头和函数体。语法格式：

```c
返回值类型 函数名(参数列表)
{
	函数体//函数实现特定功能的过程
}
```

**1. 函数头**

函数头是函数的入口，标志着一段函数代码的开始。函数头包括返回值类型、函数和参数列表 3 个部分。

![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//3.png)

返回值类型：函数返回值的类型，必须是 C 语言中的某个数据类型。

函数名：函数的标识符，在一个C程序中应保持唯一。

参数列表：调用参数时，用于将主调函数中的实际参数复制到该列表对应的形式参数中。可以没有参数，也可以有多个参数。

**2. 函数体**

函数体位于函数头的下方位置，由一对大括号括起来，大括号决定了函数体的范围。函数要实现的特定功能，都是在函数体部分通过代码语句完成的，最后通过return语句返回实现的结果。

定义函数时的特殊情况：

无参函数：没有参数列表的函数。

空函数：没有任何内容，也没有什么实际功能的函数。一般形式：

```c
类型说明符 函数名()
{
}
```

实际开发中，有时某个函数还未编好，或者后续要拓展某个函数，这时就会先用一个空函数代替，先占个位置，待后续时机成熟再用编好的函数取代它。

C 语言中，函数的定义是互相平行、独立的，函数体内不能再包含其他函数的定义。

### 9.2.2 **函数的声明**

函数的声明是为了让编译器预先知道有这么一个函数，以及函数的名称、参数、返回值类型等信息。一般形式：

```c
返回值类型 函数名(参数列表);
```

函数声明语句最后要用 ";" 作为结尾。

```c
//声明一个函数
Int ShowNumber(int iNumber);
```

```c
//交换量个数值
#include<stdio.h>
int exchange(int a, int b);						      //声明exchange函数

int main()
{
	int a = 3, b = 5;							            //定义整型变量
	printf("交换前数值：a=%d b=%d\n", a, b);	//提示信息
	exchange(a,b);								            //调用exchange函数
	return 0;
}
int exchange(int a, int b)						      //定义exchange函数，用于交换两个数的值
{
	int c;										                //交换数值
	c = a;
	a = b;
	b = c;
	printf("交换后数值：a=%d b=%d\n", a, b);	//输出交换之后的数值
}
```

如果先定义函数，再调用函数，则不再需要进行函数声明，此时函数定义已包含了函数声明的作用。

## 9.3 函数参数

多数情况下，主调函数和被调函数之间存在着数据传递关系，这种数据传递是通过函数参数来实现的。函数参数的作用是传递数据给函数使用，函数利用接收到的数据进行具体的操作处理。

### 9.3.1 形式参数与实际参数

函数的参数分为形式参数和实际参数两种。

**1. 形式参数**

声明和定义函数时，函数名后面括号中的参数称为形式参数。这些参数只是定义了类型，在实际参数传入前并没有实际意义，因此叫作形式参数，简称形参。

**2. 实际参数**

调用函数时，函数名后面括号中的参数称为实际参数。调用函数的过程就是真正使用这个函数的过程，此时调用者会传递一些要实际参与运算的参数给被调用函数，这些实际参与运算的参数就是实际参数，简称实参。

```c
int Minus(int iNumber1,int iNumber2)//定义Minus函数，有两个int型参数
{
	int iResult;
	iResult=iNumber1-iNumber2;
	return iResult;                   //返回计算结果
}
int main()
{
	...
	iResult=Minus(9,4);               //调用Minus函数，代入实参9、4，函数执行9-4运算
	...
}
```

函数参数可以是常量、变量、数组、指针等，也可以是表达式。

### 9.3.2 数组作函数参数

**1. 数组元素作为函数参数**

```c
//输出数组元素
#include<stdio.h>
void ShowMember(int iMember);

int main()
{
	int i, iCount[10];
	for (i = 0; i < 10; i++)
	{
		iCount[i] = i;
	}
	for (i = 0; i < 10; i++)
	{
		ShowMember(iCount[i]);						//函数实参为数组元素
	}
	return 0;
}
void ShowMember(int iMember)
{
	printf("Show the member is %d\n", iMember);
}
```

**2. 数组名作为函数参数**

C 语言中，数组名表示的是数组中第一个元素的地址。因此，当数组名作为函数实参时，传递的是数组的地址。

```c
//使用数组名作为函数的实参和形参，实现数组的赋值和输出
#include<stdio.h>
void Evaluate(int iArrayName[10]);							//声明赋值函数，形参为一个数组名
void Display(int iArrayName[10]);							  //声明输出函数，形参为一个数组名
int main()
{
	int iArray[10];											          //定义一个具有十个元素的整型数组
	Evaluate(iArray);
	Display(iArray);
	return 0;
}

/*
进行数组元素的输出
*/
void Display(int iArrayName[10])							   //定义输出函数，形参为一个数组
{
	int i;
	for (i = 0; i < 10; i++)
	{
		printf("the member number is %d\n", iArrayName[i]);
	}
}
/*
进行数组元素的赋值
*/
void Evaluate(int iArrayName[10])
{
	int i;
	for (i = 0; i < 10; i++)
	{
		iArrayName[i]=i;
	}
}

/*
调用Evaluate函数，数组名iArray作为函数实参，传递的是数组的地址。
在Evaluate函数中，使用数组iArrayName作为形参，接受对应的地址空间，并对数组进行赋值操作。
*/
```

**3. 可变长度数组作为函数参数**

数组作为函数参数时，如果未指明数组大小，就属于长度可变的数组作为函数参数。

```c
//不使用库函数实现字符串连接功能
#include<stdio.h>
void _strcat(char str1[], char str2[])
{
	int i, j;										        //定义控制变量
	for (i = 0; str1[i] != '\0'; i++);	//字符数组1中循环
	for (j = 0; str2[j] != '\0'; j++)		//字符数组2中循环
			str1[i + j] = str2[j];					//字符串连接
	str1[i + j] = '\0';
}
int main()
{
	char str1[100], str2[200];
	printf("请输入字符串1：\n");
	gets(str1);
	printf("请输入字符串2：\n");
	gets(str2);
	_strcat(str1, str2);
	printf("连接之后的字符串是：%s\n", str1);
	return 0;
}
```

## 9.4 函数的调用和返回

### 9.4.1 函数的调用

函数的调用方式有三种：语句调用、表达式调用和函数参数调用。

**1. 语句调用**

函数调用作为一个独立语句出现，就称为语句调用。这是最常用的函数调用方式，可以有返回值，也可以没有返回值。

```c
Display();
```

**2. 表达式调用**

当函数调用出现在一个表达式中时，函数必须返回一个确定的值，作为表达式运算的一部分。

```c
iResult=iNum*AddTwoNum(3,5);
//函数AddTwoNum的返回值将与iNum3执行乘法，得到的结果赋值给iResult变量。
```

```c
//实现欧姆定律的功能
/*
在本实例中，定义一个函数，其功能是利用欧姆定律(R=U/I)计算电阻值，并在表达式中调用该函数，使其返回值参与运算。
*/
#include<stdio.h>
void TwoNum(float iNum1, float iNum2);

int main()
{
	TwoNum(5, 10);
	return 0;
}
void TwoNum(float iNum1, float iNum2)
{
	float iTempResult;
	iTempResult = iNum1 / iNum2;
	printf("电阻值是：%f\n", iTempResult);
}
```

**3. 函数参数调用**

函数调用还可以出现在函数参数中。此时，函数的返回值将作为参数使用。

```c
iResult=AddTwoNum(10,AddTwoNum(3,5));
//AddTwoNum函数的功能还是进行两个数相加，然后将相加的结果作为函数的一个参数，继续进行计算。
```

```c
//判断体温是否正常
/*
本实例编写getTemperature函数得到体温值，将其返回的体温数据交给judgeTemperature函数，作为参数使用。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
void judgeTemperature(float temperature);			//声明函数
float getTemperature();

int main()
{
	judgeTemperature(getTemperature());				  //调用函数
	return 0;
}

float getTemperature()								        //定义函数
{
	float temperature;
	printf("please input a temperature：\n");
	scanf("%f", &temperature);
	printf("当前体温是：%.1f\n", temperature);
	return temperature;
}

void judgeTemperature(float temperature)			 //定义函数
{
	if (temperature <= 37.3 && temperature >= 36)
	{
		printf("体温正常\n");
	}
	else
	{
		printf("体温不正常\n");
	}
}
```

### 9.4.2 函数的返回

```c
//返回语句
return 0；
```

return 语句的作用两个：

**1. 退出函数，返回主调程序中**

C 程序中终止函数执行返回到调用函数位置的两种方法：

函数体中所有语句都执行完毕，遇到结束符号 ”}” 自动返回。

遇到 return 语句，随即返回。

**2. 返回一个值，供主调函数使用**

定义函数时需要明确指定函数返回值的类型，函数定义的返回值类型决定最终返回值的类型。

return 语句后面的括号可以省略，即 return 0 和 return (0) 是相同的。另外，函数也可以没有返回值。例如，返回值类型为 void 的函数就没有返回值。

```c
//返回体温
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
float getTemperature();								//声明函数，函数返回值类型为float型

int main()
{
	getTemperature();				            //调用函数
	return 0;
}

float getTemperature()								//定义函数
{
	float temperature;
	printf("please input a temperature：\n");
	scanf("%f", &temperature);
	printf("当前体温是：%.1f\n", temperature);
	return temperature;
}
```

### 9.4.3 函数的嵌套调用

C 语言虽然不允许进行函数嵌套定义，但却可以函数嵌套调用，即可在一个函数体内可以调用另外一个函数。

```c
//利用嵌套函数模拟CEO分派工作的过程。这里简化任务的完成过程，只输出一条语句表示逐级分派任务(即调用函数)的过程。
#include<stdio.h>

void CEO();					//声明4个函数
void Manager();
void AssistantManager();
void Clerk();

int main()
{
	CEO();
	return 0;
}

void CEO()
{
	printf("CEO交代给总经理\n");
	Manager();
}

void Manager()
{
	printf("总经理交代给部门经理\n");
	AssistantManager();
}

void AssistantManager()
{
	printf("部门经理交代给各个职员\n");
	Clerk();
}

void Clerk()
{
	printf("职员开始执行\n");
}
```

### 9.4.4 函数的递归调用

递归调用：函数自己调用自己

![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//4.png)

递归之所以能实现，是因为函数的每个执行过程在栈中都有自己的形参和局部变量副本，这些副本和该函数的其他执行过程不发生关系。这种机制是当代大多数程序设计语言实现子程序结构的基础。

```c
/*
在本实例中，定义一个字符串数组，为其赋值一系列名称，通过递归函数调用，逆序显示名单。
注意，本例之所以能逆序输出名单，是因为嵌套函数返回时是从最内层到最外层逐层返回。
*/
#include<stdio.h>
void DisplayNames(char** cNameArray);		//声明递归函数DisplayNames，参数为指针的指针

char* cNames[] =
{
	"Aaron",
	"Jim",
	"Charles",
	"Sam",
	"Ken",
	"end"									                //设定一个结束标识
};

int main()
{
	DisplayNames(cNames);					        //调用DisplayNames函数
	return 0;
}

void DisplayNames(char** cNameArray)
{
	if (*cNameArray == "end")			       	//定义DisplayNames函数
	{
		return;								              //如果是，函数结束返回
	}
	else
	{
		DisplayNames(cNameArray + 1);		    //如果不是，递归调用本身
		printf("%s\n", *cNameArray);
	}
}
```

![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//5.png)

## 9.5 内部函数和外部函数

函数是 C 程序中的最小单位，可以把一个或多个函数保存为一个文件，这个文件就称为源文件。当一个源程序由多个源文件组成时，多个文件之间的函数可以相互调用。当然我们也可以通过将其设置为内部函数，禁止其被其他文件调用。因此，根据能不能被其他文件调用， C 语言又把函数分为两类: 一类是内部函数，另一类是外部函数。

### 9.5.1 内部函数

定义一个函数，如果该函数只能被所在的源文件使用，那么就称这样的函数为内部函数。内部函数又称为静态函数。使用内部函数，可以使函数只局限在函数所在的源文件中，如果在不同的源文件中有同名的内部函数，则这些同名函数间是互不干扰的。

定义内部函数时，要在函数返回值和函数名前面加上关键字 static 进行修饰。一般形式：

```c
static 返回值类型 函数名(参数列表)

//定义一个功能为加法运算且返回值是int型的内部函数
static int Add(int iNum1,int iNum2)
```

使用内部函数的好处是，不同开发者编写函数时，不必再担心函数是否会与其他源文件中的函数同名。因为内部函数只在所在源文件中有效，不同源文件中即使有相同的函数名，也没有关系。

```c
//显示"Hello World!"
//使用内部函数，通过一个函数对字符串进行赋值，再通过一个函数对字符串进行输出显示。
#define _CRT_SECURE_NO_WARnINGS
#include<stdio.h>

static char* GetString(char* pString)			//定义字符串赋值函数
{
	return pString;//返回字符
}
static void ShowString(char* pString)			//定义字符串输出函数
{
	printf("%s\n", pString);					//显示字符
}
int main()
{
	char* pMyString;							//定义字符串变量
	pMyString = GetString("Hello World!");
	ShowString(pMyString);
	return 0;
}
```

### 9.5.2 外部函数

外部函数是可以被其他源文件调用的函数。定义外部函数时，使用关键字 extern 进行修饰。同样，使用外部函数时，要先用 extern 声明所用的函数是外部函数。一般形式：

```c
extern 返回值类型 函数名(参数列表)

//定义一个功能为加法运算且返回值是int型的外部函数
static int Add(int iNum1,int iNum2)
```

C 语言中，定义函数时如果未指明是内部函数还是外部函数，系统将默认此函数为外部函数。也就是说，定义外部函数时可以省略关键字 extern。

```c
//求三角形的内角度数
//一个三角形的3个内角度数之比为2:3:3，求个内角的度数。使用外部函数编写程序求解。
//main1
#include<stdio.h>
extern void GetAngle(int a, int b, int c)						//定义GetAngle函数
{
	float a1 = 0, b1 = 0, c1 = 0;								      //定义3个变量，用来表示三角形的3个内角
	a1 = (float)180 * a / (a + b + c);							  //求每个内角的度数
	b1 = (float)180 * b / (a + b + c);
	c1 = (float)180 * c / (a + b + c);
	printf("内角度数分别是：a=%.1f°b=%.1f°c=%.1f°\n", a1, b1, c1);	
}
//main2
#include<stdio.h>
extern void GetAngle(int a, int b, int c);	        //声明外部函数
int main()
{
	GetAngle(2, 3, 3);						                    //调用main1中的GetAngle函数
	return 0;
}
```

## 9.6 局部变量和全局变量

作用域决定了程序中变量的作用范围：局部变量的作用域是局部的，如函数体内；全局变量的作用域是整个程序。

### 9.6.1 局部变量

在函数内部定义的变量是局部变量。我们前面学习的实例中绝大多数变量都只是局部变量，这些变量声明在函数内部，无法被其他函数所使用。函数的形式参数也属于局部变量，作用范围仅限于函数内部的所有语句块。

在语句块内声明的变量仅在该语句块内部起作用，当然也包括嵌套在其中的子语句块。

```c
/*
本实例在不同的位置定义一些变量，并为其赋值来表示变量的所在位置，最后输出显示其变量值，通过输出的信息来观察局部变量的
作用范围。
*/
#include<stdio.h>//包含头文件
int main()//主函数main
{
	int iNumber1;//定义变量
	printf("米线店套餐如下: \n1: 考神套餐 2:单身套餐 3:情侣套餐\n");
	if (iNumber1 = 1)
	{
		int iNumber2;//iNumber2的作用域在if语句块中
		printf("考神套餐13元\n");
		if (iNumber2 = 2)
		{
			int iNumber3;//iNumber3的作用域在if语句块中
			printf("单身套餐9.9元\n");
			if (iNumber3 = 3)
			{
				printf("情侣套餐20元\n");
			}
		}
	}
	return 0;
}
```

C 语言中，位于不同作用域的变量可以使用相同的标识符，也就是变量名可以相同。如果内层作用域中定义的变量和已经声明的某个外层作用域中的变量有相同名称，在内层中使用这个变量名，此时的变量名表示的是外层变量还是内层变量呢？答案是：内层作用域中的变量将屏蔽外层作用域中的同名变量，直到结束内层作用域为止。这就是局部变量的屏蔽作用。

```c
//局部变量的屏蔽作用
#include<stdio.h>
int main()//主函数main
{
	int iNumber1 = 1;               //定义第1个iNumber1变量
	printf("%d\n", iNumber1);       //输出第1个iNumber1的变量值
	if (iNumber1 > 0)
	{
		int iNumber1 = 2;             //定义第2个iNumber1变量
		printf("%d\n", iNumber1);     //输出第2个iNumber1的变量值
		if (iNumber1 > 0)
		{
			int iNumber1 = 3;           //定义第3个iNumber1变量
			printf("%d\n", iNumber1);   //输出第3个iNumber1的变量值
		}
		printf("%d\n", iNumber1);     //再次输出第2个iNumber1的变量值
	}
	printf("%d\n", iNumber1);       //再次输出第1个iNumber1的变量值
	return 0;
}
```

### 9.6.2 全局变量

全局变量是在所有函数外部声明的变量，可以在程序的任意位置进行访问，属于源文件。如果外部文件要访问要用extern关键字进行引用修饰。全局变量可增加函数间的数据联系。同一文件中的所有函数都能引用全局变量的值，因此如果在一个函数中改变了全局变量的值，就能影响到其他函数，相当于各个函数间有了一个直接传递通道。

```c
//模拟连锁超市价格调整
#include<stdio.h>
int iGlobalPrice=100;							     /*设定商店的初始价格*/
void Store1Price();							       /*声明函数，代表第1个连锁店*/
void Store2Price();						         /*代表第2个连锁店*/
void Store3Price();						         /*代表第3个连锁店*/
void ChangePrice();							       /*更改连锁店的统一价格*/

int main()
{
	printf("原价格 : %d\n",iGlobalPrice);/*先显示价格改变之前所有连锁店的价格*/
	Store1Price();							         /*显示1号连锁店的价格*/
	Store2Price();							         /*显示2号连锁店的价格*/
	Store3Price();							         /*显示3号连锁店的价格*/
	ChangePrice();                       /*调用函数，改变连锁店的价格*/
	printf("修改的价格是: %d\n",iGlobalPrice);
	Store1Price();							         /*显示1号连锁店的当前价格*/
	Store2Price();							         /*显示2号连锁店的当前价格*/
	Store3Price();						           /*显示3号连锁店的当前价格*/
	return 0;
}
/*定义1号连锁店的价格函数*/
void Store1Price()
{
	printf("商品1的价格 : %d\n",iGlobalPrice);
}
/*定义2号连锁店的价格函数*/
void Store2Price()
{
	printf("商品2的价格 : %d\n",iGlobalPrice);
}
/*定义3号连锁店的价格函数*/
void Store3Price()
{
	printf("商品3的价格 : %d\n",iGlobalPrice);
}
/*定义更改连锁店价格函数*/
void ChangePrice()
{
	printf("您想要改价格吗？如果是，改的价格是: ");
	scanf("%d",&iGlobalPrice);
}
```

## 9.7 函数应用

编译系统通常会提供一些标准库函数，以供用户快速调用。不同的编译系统，提供的库函数会略有差异。下面介绍 ANSI C 提供的部分常用的库函数。

### 9.7.1. 数学函数

使用数学函数时，要包括 math.h 头函数，即要在程序开始处添加 #include<math.h>。

**1. abs 函数**

功能是求解整数的绝对值。函数形式：

```c
int abs(int i);

//求一个负数绝对值
int iAbsoluteNumber;
int iNumber=-12;
iAbsoluteNumber=abs(iNumber);
```

**2. labs 函数**

功能是求解长整型数的绝对值。函数形式：

```c
long labs(long n);

//求一个长整型数绝对值
long iAbsoluteNumber;
long iNumber=-1234567890L;
iAbsoluteNumber=labs(iNumber);
```

**3. fabs 函数**

功能是求解实型数的绝对值。函数形式：

```c
double fabs(double x);

//求一个实型数绝对值
double fAbsoluteNumber;
double fNumber=-1234.0;
fAbsoluteNumber=fabs(fNumber);
```

```c
//使用abs函数计算两人相差的岁数
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<math.h>

int main()
{
	int iAbsoluateNumber;							            //定义整型变量
	int iNumber;
	int differ, ab;
	printf("输入年龄：\n");
	scanf("%d %d", &iAbsoluateNumber, &iNumber);	//输入两个年龄
	differ = iAbsoluateNumber - iNumber;			    //相差的年龄
	ab = abs(differ);								              //求相差的绝对值
	printf("两人相差%d岁\n", ab);				        	//显示输出相差的年龄
	return 0;
}
```

**4. sin 函数**

功能是求解正弦。函数形式：

```c
double sin(double x);

//求一个角正弦值
double fResultSin;
double fXsin=0.5;
fResultSin=sin(fXsin);
```

**5. cos 函数**

功能是求解余弦。函数形式：

```c
double cos(double x);

//求一个角正弦值
double fResultCos;
double fXcos=0.5;
fResultCos=cos(fXcos);
```

**6. tan 函数**

功能是求解正切。函数形式：

```c
double tan(double x);

//求一个角正弦值
double fResultTan;
double fXtan=0.5;
fResultTan=tan(fXtan);
```

```c
//求梯形顶角及正切值
#include<stdio.h>
#include<math.h>		        /*包含头文件math.h*/

int main()
{ 
	double fResultTan;	      /*用来保存正切值*/

	int Result;	
	Result=90+45;             /*求顶角*/
	fResultTan =tan(Result);	/*调用正切函数*/
	printf("另一个内角是:%d\n",Result);
    printf("正切值是：%f\n",fResultTan);

	return 0;
}
```

### 9.7.2 字符函数

使用时要先包含头文件 ctype.h，即要在程序开始处添加 #include<ctype.h>。

**1. isalpha 函数**

功能是检测某个字符是否是字母，是则返回非 0 值，否则返回 0。函数形式：

```c
int isalpha(int ch);

//判断输入的字符是否为字母
char c;
scanf("%c",&c);
isalpha(c);
```

**2. isdigit 函数**

功能是检测某个字符是否是数字，是则返回非 0 值，否则返回 0。函数形式：

```c
int isdigit(int ch);

//判断输入的字符是否为数字
char c;
scanf("%c",&c);
isdigit(c);
```

**3. isalnum 函数**

功能是检测某个字符是否是字母或者数字，是则返回非 0 值，否则返回 0。函数形式：

```c
int isalnum(int ch);

//判断输入的字符是否为字母或数字
char c;
scanf("%c",&c);
isalnum(c);
```

```c
//判断输入字符的类型
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<ctype.h>

void SwitchShow(char c);

int main()
{
	char cCharPut;
	char cCharTemp;

	printf("请第一次输入一个字符：\n");
	scanf("%c", &cCharPut);
	SwitchShow(cCharPut);
	cCharTemp = getchar();//接收回车符

	printf("请第二次输入一个字符：\n");
	scanf("%c", &cCharPut);
	SwitchShow(cCharPut);
	cCharTemp = getchar();

	printf("请第三次输入一个字符：\n");
	scanf("%c", &cCharPut);
	SwitchShow(cCharPut);
	cCharTemp = getchar();

	return 0;
}

void SwitchShow(char cChar)
{
	if (isalpha(cChar))
	{
		printf("您输入的是字母：%c\n", cChar);
	}

	if (isdigit(cChar))
	{
		printf("您输入的是数字：%c\n", cChar);
	}

	if (isalnum(cChar))
	{
		printf("您输入的是字母或者数字：%c\n", cChar);
	}
	else
	{
		printf("您输入的既不是字母也不是数字：%c\n", cChar);
	}
}

//在main函数中调用getchar函数其作用是获取一个字符，这里为了防止回车符被当做输入的字符，调用getchar函数预先提取走回车符。
```

### 9.7.3 字符串处理函数

使用时要先包含头文件 string.h，即要在程序开始处添加 #include<string.h>。

**1. strcpy 函数**

用于复制特定长度的字符串到另个字符串中。语法格式：

```c
strcpy (字符数组1,字符数组2)
//功能：把字符数组2中的字符串复制到字符数组1中，字符串结束标志“\O”也一同复制。复制过去的内容将覆盖字符数组1中的对应内容。
```

字符数组 1 要有足够的长度，否则无法装下待复制的字符串。

“字符数组 1”必须写成数组名形式；而“字符数组 2”可以是数组名，也可以是一个字符串常量，这时相当于把一个字符串赋予该字符数组。

不能用赋值语句将一个字符串常量或字符数组直接赋给一个字符数组。

```c
/*
在main函数体中定义两个字符数组，通过键盘输入获取两个字符串并分别输出，调用strcpy函数将源字符数组中的字符串赋值给目标字
符数组，最后输出目标字符数组。
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<string.h>

int main()
{
	char str1[30], str2[30];
	printf("输入目标字符串：\n");
	gets(str1);
	printf("输入源字符串：\n");
	gets(str2);
	printf("输出目标字符串：\n");
	puts(str1);
	printf("输出源字符串：\n");
	puts(str2);
	strcpy(str1, str2);
	printf("调用strcpy函数进行字符串复制：\n");
	printf("复制字符串之后的目标字符串：\n");
	puts(str1);
	return 0;
}
```

**2. strcat 函数**

用于连接字符串。语法格式：

```c
strcat (字符数组1,字符数组2)
//功能：把字符数组2中的字符串连接到字符数组1的字符串后面，并删去字符数组1中原有的串结束标志“\0”。
```

字符数组 1 要有足够的长度，以保证能装下连接后的字符串。

```c
/*
编写程序，接受用户输入的目录和文件名，然后输出文件的完整路径。
在main函数体中定义两个字符数组，分别存储输入的目录和文件名，调用strcat函数将文件名字符串连接到目录字符串的后面，最后
输出目录字符数组。
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<string.h>
int main()
{
	char str1[30], str2[30];
	printf("输入目录：\n");
	gets(str1);						    //输入目录字符串
	printf("输入文件名：\n");
	gets(str2);						    //输入文件名字符串
	printf("输出目录：\n");
	puts(str1);						    //输出目录
	printf("输出文件名：\n");
	puts(str2);						    //输出文件名
	strcat(str1, str2);				//调用strcat函数进行字符串连接
	printf("文件全路径:\n");
	puts(str1);						    //输出连接后的字符串，即文件的完整路径
	return 0;
}
```

**3. strcmp 函数**

用于字符串比较。语法格式：

```c
strcmp (字符数组1,字符数组2)
/*
功能：按照ASCII码顺序比较两个数组中的字符串，并返回比较结果。两个字符串比较时，若出现不同的字符，则以第一个不同字符的
比较结果作为整个比较的结果。
*/
```

返回值如下：

字符串 1 = 字符串 2，返回值为 0。

字符串 1 > 字符串 2，返回值为正数。

字符串 1 < 字符串 2，返回值为负数。

字符串比较不能使用关系运算符，也不能使用赋值运算符。

```c
/*
在自动取款机上取钱时，需要输入密码，密码正确方能取到钱。本实例中，正确的密码为574824，只有3次密码输入机会，如果3次都
输错了，就提示“请到人工处办理解锁”。
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<string.h>
int main()
{
	char password[20] = { "574824" };						//定义变量，保存正确的密码字符串
	char pwstr[20];											        //定义变量，保存用户输入的密码字符串
	int i = 1;
	while (i <= 3)											        //循环执行3次密码输入
	{
		printf("输入密码字符串: \n");
		gets(pwstr);										          //输入密码字符串
		if (strcmp(password, pwstr))						  //比较两个密码，如果不相同
		{
			printf("第%d次，密码字符串输入错误! \n", i);
		}
		else//如果相同
		{
			printf("密码正确，请选择服务! \n");			//输出下一步业务提醒
			break;											            //退出
		}
		i++;
	}
	if (i == 4)
	{
		printf("输入字符串错误3次!请到人工处办理解锁\n");
	}
	return 0;
}
```

**4. strupr 和 strlwr 函数**

用于字符串的大小写转换。语法格式：

```c
strupr (字符数组名)
//功能:将数组中存放的字符串的小写字母转换成大写字母，其他字母不变。

strlwr (字符数组名)
//功能:将数组中存放的字符串的大写字母转换成小写字母，其他字母不变。
```

```c
/*
将张三的邮箱地址ZhangSan@MRSOFT.COM全部转换为小写或大写。
在main函数体中定义两个字符数组，分别用来存储要转换的字符串和转换后的字符串，然后根据用户输入的操作指令，判断应
调用strupr函数还是strlwr函数，进行大小写转换。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<string.h>
int main()
{
	char text[20] = "ZhangSan@MRSOFT.COM", change[20];
	printf("原字符串为: %s\n", text);					        //输出要转换的字符串
	strcpy(change, text);								              //复制要转换的字符串
	_strlwr(change);									                //字符串转换为小写
	printf("转换成小写字母的字符串为: %s\n", change);	//输出转换后的字符串
	_strupr(change);									                //字符串转换为大写
	printf("转换成大写字母的字符串为: %s\n", change);	//输出转换后的字符串
	return 0;
}
```

**5. strlen 函数**

有时需要知道字符串的长度，虽然通过循环判断字符串结束标志 “\0” 也能获得字符串的长度，但毕竟实现起来相对烦琐。这时可以
使用 strlen 函数来计算字符串的长度。语法格式：

```c
strlen(数组名)
//功能：计算数组中存放的字符串的实际长度(不含字符串结束标志“\0”)。
```

```c
/*
在本实例中的main函数体中定义一个字符数组，用来存储用户输入的字符串，然后调用strlen函数计算字符串长度，并使用
if..else...语句判断密码长度是否等于6。
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<string.h>
int main()
{
	char text[50];						//定义字符数组，保存密码字符串
	printf("输入一个密码: \n");
	scanf("%s", &text);					//输入用户密码
	if (strlen(text) == 6)				//计算密码长度并判断是否等于6
	{
		printf("输入密码是6位\n");
	}
	else
	{
		printf("输入密码不是6位\n");
	}
	return 0;							//程序结束
}
```

# 第10章 指针

## 10.1 指针的相关概念

### 10.1.1 地址与指针

通常来说，系统会按字节对每个内存单元进行编号，这些内存单元就好比是许多带有编号的小房间，要想使用内存，就需要知道房间编号。

编译系统为每个变量都分配了一个能满足其类型大小的内存单元地址，访问该地址就能找到对应变量。

取地址符 ”&” 的作用是获取变量在内存中的地址。

![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//6.png)

我们将变量的地址形象化地称为该变量的“指针”，意思是通过它能访问以它为地址的内存单元。

### 10.1.2 变量与指针

变量的地址是变量和指针之间的连接纽带。所谓“指向”，是通过地址来体现的。因为指针变量通常指向一个变量的地址，所以将一个变量的地址赋给指针变量后，这个指针变量就“指向”了该变量。例如，将变量i的地址&i存放到指针变量 p 中，p 就指向 i。

![将变量i的地址&i存放到指针变量p中，p就指向i](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//7.png)

将变量i的地址&i存放到指针变量p中，p就指向i

程序代码中一般通过变量名对内存单元进行存取操作，但代码编译后，会将变量名转换为该变量在内存中的存放地址，后续对变量值的存取都是通过该地址进行的。

低级语言（如汇编语言）中一般直接通过地址来访问内存单元，高级语言中一般使用变量名来访问内存单元。C 语言作为高级语言，仍然提供了通过地址来访问内存单元的方式。

### 10.1.3 指针变量

一个变量的地址称为该变量的指针。如果有一个变量专门用来存放另一个变量的地址，它就是指针变量。在 C 语言中有专门用来存放内存单元地址的变量类型，即指针类型。

**1. 指针变量的定义**

一般形式：

```c
类型说明 * 变量名
//"*"表示该变量是一个指针变量，"变量名"即为定义的指针变量名，"类型说明"表示本指针变量所指向的变量的数据类型。
```

**2. 指针变量的赋值**

```c
//定义指针变量的同时进行赋值
int a;
int *p=&a;

//先定义指针变量，后赋值
int a;
int *p;
p=&a;

//如果先定义指针变量之后再赋值，赋值时指针变量前不再加"*"。
```

```c
/*
从键盘中输入一个数，利用指针将这个数的地址以十六进制形式输出
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int a;											    //定义整型变量
	int* ipointer1;									//定义指针变量
	printf("请输入数据: \n");
	scanf("%d", &a);								//输入一个数
	ipointer1 = &a;									//将地址赋给指针变量
	printf("转化十六进制为: %x\n", *ipointer1);		//以十六进制形式输出该数
	return 0;
}
```

**3. 指针变量的引用**

引用指针变量是对变量进行间接访问的一种形式。引用指针变量的形式为“*指针变量”，其含义是引用指针变量所指向的值。

没有初始化的指针变量俗称“野指针”，使用时容易产生错误（导致不合法的内存空间）。良好的编程习惯是在定义指针变量时就将其初始化为 NULL，由于 NULL 处禁止写入，所以一旦有错误，可以将错误造成的危害降到最小。

```c
//使用指针比较两个数的大小
#include<stdio.h>
int main()
{
	int a = 10, b = 11;						//定义两个整型变量并初始化
	int* ipointer1, * ipointer2;	//定义两个整型指针变量
	ipointer1 = &a;							  //将地址赋给指针变量
	ipointer2 = &b;
	if (*ipointer1 > *ipointer2)	//使用指针比较两数大小
	{
		printf("a的值大\n");
	}
	else
	{
		printf("b的值大\n");
	}
	return 0;
}
```

**4. “&” 和 “*” 运算符**

运算符 “&” 和 “*” 都是单目运算符。“&” 是取地址运算符，用于返回一个操作数的地址。“*” 是指针运算符，用于返回指定地址内保存的变量值。

例如，“p=&i;” 是将变量i的内存地址赋给指针变量 p。“q=*p;” 是将指针 p 指向的变量，即变量 i 的值赋给 q，假如变量 i 的值是 5，则 q 的值也是 5。

**5. “&*” 和 “*&”**

下面通过两条语句来分析 “&*” 和 “*&” 运算的区别。如果有如下语句：

```c
int a;
p = &a;
```

因为 “&” 和 “*” 的优先级相同，按自右而左的方向结合，因此 “&*p” 先进行 “*” 运算 “*p” 相当于变量 a；再进行 “&” 运算，“&*p” 就相当于取变量 a 的地址。“*&a” 先进行 “&” 运算，“&a” 就是取变量 a 的地址，然后执行 “*” 运算，“*&a” 就相当于取变量 a 所在地址的值，实际就是变量 a。

```c
//本实例定义了3个指针变量，使用“&*”计算c = i + j，计算后输出变量i,j,c的地址值。
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	long i, j, c;								//定义变量
	long* p, * q, * n;					//定义指针变量
	printf("please input the numbers:\n");
	scanf("%ld %ld", &i, &j);		//输入数据
	c = i + j;									//实现两数相加
	p = &i;										  //将地址赋给指针变量
	q = &j;
	n = &c;
	printf("%ld\n", &*p);				//利用“&*"输出变量i的地址
	printf("%ld\n", &*q);				//利用" &*”输出变量j的地址
	printf("%ld\n", &*n);				//利用“&*"输出变量c的地址
	return 0;
}
```

```c
/*
杯子的底面积是60平方厘米，杯中装上8厘米高的水，杯子和水的总质量为0.6千克(水的密度是每立方米103千克，
重力加速度g的值为每千克10牛顿)，利用“*&”计算水对杯子产生的压强。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	double a = 1000 * 10 * 8 * 0.001;          //定义变量并计算压强
	double* p;                                 //定义指针变量
	p = &a;                                    //将地址赋值给指针变量
	printf("根据压强公式：\n");
	printf("水对杯子产生压强为%.1lf Pa\n", *&a);//利用“*&”输出压强
	return 0;
}

/*
压强的计算公式是：p=F/S，压强的单位是帕斯卡（简称帕），符号是Pa。 
增大压强的方法有：在受力面积不变的情况下增加压力或在压力不变的情况下减小受力面积。 
减小压强的方法有：在受力面积不变的情况下减小压力或在压力不变的情况下增大受力面积。
*/
```

### 10.1.4 指针自增自减运算

指针自增自减运算是按照它所指向的数据类型的直接长度进行增或减。

```c
//输出整型变量的地址
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	int i1;
	int* p1;
	printf("Please input a number: \n");
	scanf("%d", &i1);
	p1 = &i1;
	printf("The result1 is %d\n", p1);
	p1++;
	printf("The result2 is %d\n", p1);

	short i2;
	short* p2;
	printf("Please input a number: \n");
	scanf("%d", &i2);
	p2 = &i2;
	printf("The result1 is %d\n", p2);
	p2++;
	printf("The result2 is %d\n", p2);

	return 0;
}
```

## 10.2 数组与指针

使用数组时，系统需要提供一段连续的内存来存储数组中的各元素，如果把数组的地址赋给指针变量，就可以通过指针变量来引用数组。下面就介绍如何用指针来引用一维数组及二维数组元素。

### 10.2.1 一维数组与指针

定义一维数组时，系统会在内存中为其分配一段存储空间，数组名就是数组在内存中的首地址。若再定义一个指针变量，并将数组的首地址传给指针变量，则该指针就指向了这个一维数组。例如：

```c
int *p,a[10];
p=a;
```

这里 a 是数组名，也就是数组的首地址，将它赋给指针变量 p，也就是将数组 a 的首地址赋给 p。也可以写成如下形式：

```c
int *p,a[10];
p=&a[0] ;
```

上面的语句是将数组 a 中首个元素的地址赋给指针变量 p。由于 a[0] 的地址就是数组的首地址，因此上述两条赋值语句的操作效果完全相同。

```c
/*
定义两个指针变量，再定义两个一维数组，将两个数组元素分别赋给两个指针。
利用for循环输入两个数组的值(100以内开始5个数和后5个数)，再用for循环和指针输出数组值。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
void main()
{
	/*int* p, * q, a[5], b[5], i;					//定义变量
	p = &a[0];									          //将数组首地址赋给指针
	q = b;
	printf("Please intput array a:\n");		//提示输入数组a
	for (i=0;i<5;i++)							        //利用&a[i]形式输入数组a
		scanf("%d", &a[i]);
	printf("Please intput array b:\n");		//提示输入数组b
	for (i = 0; i < 5; i++)						    //利用&b[i]形式输入数组b
		scanf("%d", &b[i]);
	printf("array a is:\n");					    //提示输出数组a元素
	for (i = 0; i < 5; i++)
		printf("%5d", *(p + i));
	printf("\n");
	printf("array b is:\n");					    //提示输出数组a元素
	for (i = 0; i < 5; i++)
		printf("%5d", *(q + i));
	printf("\n");
	return 0;*/

	int* p, * q, a[5], b[5], i;					 //定义变量
	p = &a[0];									         //将数组首地址赋给指针
	q = b;
	printf("Please intput array a:\n");	 //提示输入数组a
	for (i = 0; i < 5; i++)						   //利用p++形式输入数组a
		scanf("%d", p++);
	printf("Please intput array b:\n");	 //提示输入数组b
	for (i = 0; i < 5; i++)						   //利用q++形式输入数组b
		scanf("%d", q++);

	p = a;										           //将指针变量p和q重新指向数组a和数组b在内存中的起始位置
	q = b;

	printf("array a is:\n");					   //提示输出数组a元素
	for (i = 0; i < 5; i++)
		printf("%d\t", *p++);					     //利用p++形式输出数组a
	printf("\n");
	printf("array b is:\n");					   //提示输出数组a元素
	for (i = 0; i < 5; i++)
		printf("%d\t", *q++);					     //利用q++形式输出数组b
	printf("\n");
	return 0;
}
```

### 10.2.2 二维数组与指针

对于一个 m 行 n 列的二维数组 a[m][n]，其元素地址的表示方法如下。

a 表示二维数组的首地址，也表示数组第 1 行的首地址，a+1 表示第 2 行的首地址，a+m 表示第 m+1 行的首地址。

a[0]+n 表示数组第 1 行第 n+1 个元素的地址，a[m]+n 表示第 m+1 行第 n+1 个元素的地址。

&a[0] 表示数组第1行的首地址，&a[m] 表示第 m+1 行的首地址。

&a[0][0] 既可以表示数组第 1 行 1 列的首地址，也可以看作整个数组的首地址。&a[m][n] 就是第 m+1 行 n+1 列元素的地址。

指针也可表示地址，因此通过指针可以引用二维数组中的元素。

((a+m)+n) 和 *(a[m]+n) 含义相同，都表示数组第 m+1 行第 n+1 列元素。

```c
//输出3*5矩阵
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
main()
{
	/*
	int a[3][5], i, j;
	printf("Please input:\n");
	for (i = 0; i < 3; i++)				//控制二维数组的行数
	{
		for (j = 0; j < 5; j++)			//控制二维数组的列数
		{
			scanf("%d", a[i] + j);		//利用a[i]+j形式输入二维数组元素
		}
	}
	printf("The array is:\n");
	for (i = 0; i < 3; i++)				//控制二维数组的行数
	{
		for (j = 0; j < 5; j++)			//控制二维数组的列数
		{
			printf("%d\t", *a[i] + j);//利用a[i]+j形式输出二维数组元素
		}
		printf("\n");
	}
	*/

	int a[3][5], i, j,*p;
	p = a[0];							         //定义p为第1行元素的首地址
	printf("Please input:\n");
	for (i = 0; i < 3; i++)				 //控制二维数组的行数
	{
		for (j = 0; j < 5; j++)		   //控制二维数组的列数
		{
			scanf("%d", p++);		       //利用p++形式输入二维数组元素
		}
	}
	p = a[0];							         //再次定义p为第1行元素的首地址
	printf("The array is:\n");
	for (i = 0; i < 3; i++)				 //控制二维数组的行数
	{
		for (j = 0; j < 5; j++)			 //控制二维数组的列数
		{
			printf("%d\t", *p++);		   //利用p++形式输出二维数组元素
		}
		printf("\n");
	}
}
```

```c
/*
将一个3行5列二维数组的第3行元素输出
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
main()
{
	int a[3][5], i, j, (*p)[5];
	p = &a[0];								//定义p为第1行元素的首地址
	printf("Please input:\n");
	for (i = 0; i < 3; i++)					//控制二维数组的行数
	{
		for (j = 0; j < 5; j++)				//控制二维数组的列数
		{
			scanf("%d", *(p+i)+j);			//使用*(p+i)+j形式输入二维数组元素
		}
	}
	p = &a[2];								//定义p为第3行元素的首地址
	printf("The array's third line is:\n");
	{
		for (j = 0; j < 5; j++)				//控制二维数组的列数
		{
			printf("%d\t", *(*p + j));		//利用*(p+i)+j形式输出二维数组元素
		}
		printf("\n");
	}
}
```

利用指针引用二维数组的关键是要记住 *(a+i) 与 a[i] 是等价的。

### 10.2.3 字符串与指针

可以通过两种方式访问一个字符串，一是使用字符数组，二是使用字符指针。

```c
/*
利用字符型指针输出字符串“hello world”
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
main()
{
	char* string = "hello world";	//定义字符型指针变量
	printf("%s\n", string);
}

/*
语句“char *string="hello world",等价于下面两条语句:
char* string;
string = "hello world";
*/
```

```c
/*
不使用string.h函数库中的strcpy函数，利用指针实现字符串复制功能，具体代码如下:
*/

#include <stdio.h>
void _strcopy(char* str1, char* str2);
int main()
{
	char str1[] = "you are beautiful";				//定义字符串1
	char str2[] = "";								          //定义字符串2
	_strcopy(str1, str2);							        //调用自定义函数strcopy
	printf("复制之后的字符串为: %s\n", str2);	//输出复制之后结果
	return 0;
}

void _strcopy(char*str1, char*str2)					//用户自定义函数，用于实现字符串复制
{
	while (*str1 != '\0')							        //将字符串1中的字符逐个复制到字符串2中
	{
		*str2 = *str1;
		str1++;
		str2++;
	}
	*str2 = '\0';						             			//在字符串2的末尾添加结束符“\O”
}
```

### 10.2.4 指针数组

一个数组，如果其元素均为指针类型数据，则该数组称为指针数组。也就是说，指针数组中的每一个元素都相当于一个指针变量。一维指针数组定义形式：

```c
类型名 数组名[数组长度]
```

```c
/*
英语小测，有一题是根据汉语填写英语。语文、数学、英语、化学、生物、物理的英语分别为
Chinese、math、English、chemistry、biology和physics,用指针数组输出对应的英文。
*/

#include <stdio.h>
int main()
{
	int i;
	char* test[] = {
		"Chinese",
		"math",
		"chemistry",
		"biology",
		"physics"
	};								          //定义了一个指针数组，对其中的元素赋初值
	printf("答案是：\n");
	for (i = 0; i < 6; i++)
	{
		printf("%s\n", test[i]);	//输出指针数组中的各元素
	}
	return 0;
}
```

## 10.3 指向指针的指针

一个指针可以指向整型变量、实型变量、字符型变量，当然也可以指向另一个指针，此时称其为指向指针的指针。

指向指针的指针定义形式：

```c
类型标识符 **指针变量名;
/*
例如，“int **p;”的含义为定义一个指针变量p,它指向另一个指针变量，该指针变量又指向一个基本整型变量。
由于指针运算符“*”自右左结合，所以上述定义相当于“int* (*p);”。
*/
```

![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//8.png)

```c
/*
利用指向指针的指针，输出化学周期表前20个元素中的金属元素。
*/

#include<stdio.h>
int main()
{
	int i;								    //定义循环控制变量
	char** p;							    //定义一个指向指针的指针变量
	char* element[] =					//定义一个指针数组，并为其赋初值
	{
	"锂",
	"铍",
	"钠",
	"铝",
	"钾",
	"钙",
	};
	for (i = 0; i< 7; i++)		//输出指针数组中的各元素
	{
		p = element + i;
		printf("%s\n", *p);
	}
	return 0;
}
```

```c
/*
利用指向指针的指针输出一维数组中其值为偶数的元素，并统计偶数的个数，具体代码如下:
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
main()
{
	/*
	int a[10], * p1, ** p2, i, n = 0;			//定义数组、指针等为基本整型
	printf("please input:\n");
	for (i = 0; i < 10; i++)					    //给数组a中各元素赋值
		scanf("%d", &a[i]);
	p1 = a;										            //将数组a的首地址赋给p1
	p2 = &p1;									            //将指针p1的地址赋给p2
	printf("the array is:");
	for (i= 0; i < 10; i++)
	{
		if (*(*p2+i)%2==0)						      //如果是偶数
		{
			printf("%5d", *(*p2 + i));			  //输出数组中的偶数元素
				n++;							              //偶数个数加1
		}
	}
	printf("\n");
	printf("the even number is: %d\n", n);
	*/

	int a[10], * p1, ** p2, n = 0;			  //定义数组、指针等为基本整型
	printf("please input:\n");
	for (p1 = a; p1 - a < 10; p1++)			  //指针p1从a的首地址开始变化
	{
		p2 = &p1;							              //将指针p1的地址赋给p2
		scanf("%d", *p2);					          //通过指针变量给数组元素赋初值
	}							
	printf("the array is:");
	for (p1 = a; p1 - a < 10; p1++)
	{
		p2 = &p1;							              //再次将指针p1的地址赋给p2
		if (**p2 % 2 == 0)					        //如果是偶数
		{
			printf("%5d", **p2);			        //输出数组中的偶数元素
			n++;							                //偶数个数加1
		}
	}
	printf("\n");
	printf("the even number is: %d\n", n);
}
```

## 10.4 指针变量作函数参数

整型变量、实型变量、字符型变量、数组名和数组元素等均可作为函数参数。此外，指针型变量也可以作为函数参数。

```c
//交换两个变量的值
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
void swap(int* a, int* b)			//自定义swap函数，形参为两个指针，功能是实现两个变量值的交换
{
	int temp;
	temp = *a;
	*a = *b;
	*b = temp;
}

main()
{
	int x, y;
	int* p_x, * p_y;
	printf("输入两个数：\n");
	scanf("%d %d", &x, &y);			//输入两个数
	p_x = &x;
	p_y = &y;
	swap(p_x, p_y);					    //调用swap函数交换变量的值
	printf("x=%d y=%d\n", x, y);
}
```

在函数调用过程中，主调函数与被调用函数之间有一个数值传递的过程，这种数值传递是单向的，只能把实参的值传给形参。也就是说，在自定函数体中，即使此时形参的值发生了改变，也无法再传递回来，因此实参的值不会发生变化。这就是为什么普通整型作为函数形参时不能实现 x 和 y 值互换的原因。通过指针传递参数，可以减少值传递带来的开销，也可以使函数调用不产生值传递。

```c
/*
首先定义交换函数swap，参数是指针变量：然后再定义比较大小的函数exchange，参数也是指针变量，并且在exchange函数中
嵌套交换函数swap。在主函数中，调用exchange函数将输入的3个数按降序输出
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
void swap(int* p1, int* p2)//自定义交换函数
{
	int temp;
	temp = *p1;
	*p1 = *p2;
	*p2 = temp;
}

void exchange(int* pt1, int* pt2, int* pt3)//自定义降序排序函数exchange
{
	if (*pt1 < *pt2)
	{
		swap(pt1, pt2);
	}
	if (*pt1 < *pt3)
	{
		swap(pt1, pt3);
	}
	if (*pt2 < *pt3)
	{
		swap(pt2, pt3);
	}
}
int main()
{
	int a, b, c, * q1, * q2, * q3;
	puts("Please intput three key numbers you want to rank: ");
	scanf("%d %d %d", &a, &b, &c);
	q1 = &a;
	q2 = &b;
	q3 = &c;
	exchange(q1, q2, q3);
	printf("%d %d %d\n", a, b, c);
	return 0;
}
```

C 语言中实参变量和形参变量之间的数据传递是单向的“值传递”方式。指针变量作函数参数也是如此，调用函数不可能改变实参指针变量的值，但可以改变实参指针变量所指向变量的值。

```c
/*
下面介绍如何使用指向数组的指针变量作为函数参数。这里，形参和实参均为指针变量。
*/

/*
利用指针变量作函数参数编写程序，根据输入的各班人数求刚入学的初中新生的总人数。
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
void SUM(int* p, int n)					//自定义SUM函数，用于求和
{
	int i, sum = 0;
	for (i = 0; i < n; i++)				//循环各班人数并求和
	{
		sum += *(p + i);				    //相加
	}
	printf("新生总人数是：%d\n", sum);
}

int main()
{
	int* pointer, a[10],i;
	pointer = a;
	printf("请输入每个班级的人数：\n");
	for (i = 0; i < 10; i++)
	{
		scanf("%d", &a[i]);				  //输入各班的人数
	}
	SUM(pointer, 10);					    //调用SUM函数求总人数
	return 0;
}
```

```c
/*
冒泡排序的基本思想：如果要对n个数进行冒泡排序，则要进行n-1轮比较，在第一轮比较中要从后到前进行n-1次两两比较，在
第j轮比较中要进行n-j次两两比较。
*/

/*
使用指针变量作为函数参数实现冒泡法排序，代码如下:
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
/*
void order(int* p, int n)						  //自定义冒泡排序函数
{
	int i, j, t;
	for (i = 0; i < n - i; i++)
	{
		for (j = 0; j < n - 1 - i; j++)
		{
			if (*(p + j) > *(p + j + 1))		//判断相邻两个元素的大小
			{
				t = *(p + j);
				*(p + j) = *(p + j + 1);
				*(p + j + 1) = t;
			}
		}
	}
	printf("排序后数组是：\n");
	for (i = 0; i < n; i++)
	{
		printf("%5d", *(p + i));				  //输出数组中排序后的元素
	}
	printf("\n");
}
main()
{
	int a[20], i, n;
	printf("请输入数组元素的个数：\n");
	scanf("%d", &n);							      //请输入数组元素的个数
	printf("请输入各个元素：\n");
	for (i = 0; i < n; i++)
	{
		scanf("%d", a + i);						    //给数组元素赋初值
	}
	order(a, n);
}
*/

void order(int a[], int n)						//自定义冒泡排序函数
{
	int i, j, t;
	for (i = 0; i < n - i; i++)
	{
		for (j = 0; j < n - 1 - i; j++)
		{
			if (*(a + j) > *(a + j + 1))		//判断相邻两个元素的大小
			{
				t = *(a + j);
				*(a + j) = *(a + j + 1);
				*(a + j + 1) = t;
			}
		}
	}
	printf("排序后数组是：\n");
	for (i = 0; i < n; i++)
	{
		printf("%5d", *(a + i));				  //输出数组中排序后的元素
	}
	printf("\n");
}

main()
{
	int a[20], i, n;
	int* p;
	p = a;										         //定义p为数组a的首地址
	printf("请输入数组元素的个数：\n");
	scanf("%d", &n);							     //请输入数组元素的个数
	printf("请输入各个元素：\n");
	for (i = 0; i < n; i++)
	{
		scanf("%d", p++);						     //给数组元素赋初值
	}
	p = a;										         //再次定义p为数组a的首地址
	order(a, n);
}

//数组名是数组的首地址；形参是数组，实参是指针变量。
```

```c
/*
大福超市员工布置水果区，店长要求按照水果名称升序的顺序摆放。
各水果的名称及对应单价如下:
苹果(apple) : 3.50
橘子(tangerine) : 2.50
柚子(grapefriu) : 3.00
香蕉(banana) : 2.00
橙子(orange) : 2.99
菠萝( pineapple) : 4.99
葡萄(grape) : 5.00
火龙果(pitaia) : 6.80
编写程序，按照水果名称的首字母将水果升序排序。
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<string.h>
void sort(char* strings[], int n)					    //自定义排序函数
{
	char* temp;
	int i, j;
	for (i = 0; i < n; i++)
	{
		for (j = i + 1; j < n; j++)
		{
			if (strcmp(strings[i], strings[j]) > 0)	//比较两个字符串的大小
			{
				temp = strings[i];					          //如果前面字符比后面大，则互换
				strings[i] = strings[j];
				strings[j] = temp;
			}
		}
	}
}

int main()
{
	int n = 8;
	int i;
	char** p;
	char* name[] = {
		"apple",
		"tangerine",
		"grapefriu",
		"banana",
		"orange",
		"pineapple",
		"grape",
		"pitatia"
	};
	p = name;
	sort(p, n);											      //调用排序函数sort
	printf("排序后的水果单如下：\n");
	for (i = 0; i < n; i++)
	{
		printf("%s\n", name[i]);						//输出排序后的字符串
	}
	return 0;
}
```

```c
/*
利用指针作为函数参数找出一个数组每行最大的数，并将这些数相加求和。
*/

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#define N 4
void max(int(*a)[N], int m)								//自定义函数max，求数组每行的最大元素
{
	int value, i, j, sum = 0;
	for (i = 0; i < m; i++)
	{
		value = *(*(a + i));							    //将一行中的首个元素赋给value
		for (j = 0; j < N; j++)
		{
			if (*(*(a + i) + j) > value)				//判断其他元素是否小于value
			{
				value = *(*(a + i) + j);				  //把比value大的数值重新赋给value
			}
		}
		printf("第%d行的最大数是：%d\n", i, value);
		sum += value;
	}
	printf("\n");
	printf("每行中最大数相加之和是：%d\n", sum);
}

main()
{
	int a[3][N], i, j;
	int(*p)[N];
	p = &a[0];
	printf("please input: \n");
	for (i = 0; i < 3; i++)								   //给二维数组元素赋值
	{
		for (j = 0; j < N; j++)
		{
			scanf("%d", &a[i][j]);
		}
	}
	max(p, 3);											         //调用max函数，指针变量作为函数参数
}
```

## 10.5 返回指针值的函数

指针变量也可以指向一一个函数。函数在编译时会被分配一个入口地址，该入口地址就称为函数的指针。可以用一个指针变量指向函数，然后通过该指针变量调用此函数。

一个函数可以带回一个整型值、字符值、实型值等，也可以带回指针型的数据，即地址。其概念与之前介绍的类似，只是带回的值的类型是指针类型而已。返回指针值的函数简称为指针函数。

定义指针函数的一般形式：

```c
类型名 *函数名(参数列表)

int *fun(int x,int y)
/*
fun是函数名，调用它以后能得到一个指向整型数据的指针。
x和y是函数fun的形式参数，这两个参数均为基本整型。
函数名前面有一个“*”，表示此函数是指针型函数。
类型说明是int,表示返回的指针指向整型变量。
*/
```

```c
//求长方形周长
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int* per(int a, int b);
int Perimeter;
void main()
{
	int iWidth, iLength;
	int *iResult;
	printf("请输入长方形的长：\n");
	scanf("%d", &iLength);
	printf("请输入长方形的宽：\n");
	scanf("%d", &iWidth);
	iResult = per(iWidth, iLength);				//调用函数per
	printf("长方形周长是：%d\n",*iResult);
}
int* per(int a, int b)							    //自定义求周长函数per，返回值为指针
{
	int* p;
	p = &Perimeter;
	Perimeter = (a + b) * 2;
	return p;									            //返回指针
}
```

## 10.6 指针数组作main函数的参数

main 函数是运行所有程序的入口，由系统调用。当处于操作命令状态下，输入 main 所在的文件名，系统即调用 main 函数。

main 函数一般是没有参数的。但实际上，main 函数也可以是有参函数，其带参形式如下:

```c
main(int argc,char *argv[])
```

有两个参数，一个整型和一个指针数组。当一个 C 源程序经过编译、链接后，会生成扩展名为 .exe 的可执行文件，该文件可直接在操作系统下运行。对于 main 函数来说，其实际参数和命令是一起给出的，也就是一个命令行包括命令名和需要传给 main 函数的参数。

命令行的一般形式如下：

```c
命令名 参数1 参数2 ... 参数n
//其中，命令名”就是可执行文件的文件名，命令名和其后参数之间须用空格分隔。
```

命令行与 main 函数的参数间存在一定关系。 假设命令行为:

```c
filel happy bright glad
```

这里，file1 为文件名，就是 filel.c 经编译、链接后生成的可执行文件 file1.exe，其后跟 3 个参数。以上命令行与 main 函数中的形式参数关系如下：参数 argc 记录了命令行中命令与参数的个数，这里包括 file1、happy、bright 和 glad，共 4 个，指针数组的大小由参数的值决定，这里为 char *argv[4]。

```c
/*
利用指针数组作main函数的形參，可以向程序传送命令行参数。
参数字符串的长度是不定的，参数数量也是任意的，并不规定具体个数。
*/
#include<stdio.h>
main(int argc, char* argv[])
{
	printf("the list of perameter: \n");
	printf("命令名：\n");
	printf("%s\n", *argv);
	printf("参数个数：\n");
	printf("%d\n", argc);
}
```

# 第11章 结构体和共用体

## 11.1 结构体

有时我们需要定义一些复杂的数据类型，它可能包括多个不同属性，每个属性需要用不同的类型来表示。该怎么实现呢? C 语言中，可以把一些有内在联系的不同变量组织起来，封装成一个整体，即定义成一个结构体（structure） ，以此来表示一种新的数据类型。之后，就可以像处理基本数据类型那样，对结构体类型进行各种操作。

### 11.1.1 结构体类型的声明

结构体是一种构造类型，它由若干成员组成。其成员可以是一个基本数据类型，也可以是另一个构造类型。声明一个结构体的过程，就是创建一种新的类型名的过程。

声明结构体时使用的关键字是 struct，其一般形式如下：

```c
struct 结构体名
{
成员列表
};
```

关键字 struct 表示声明的是一个结构体，“结构体名” 表示要创建的新类型名，大括号中的“成员列表”包括构成该结构体的所有成员。
注意，声明结构体时大括号后的分号 “;” 不能遗漏。

```c
//例如，商品一般包括产品名称、形状、颜色、功能、价格和产地等属性
下面来创建“商品(Product) ”这种类型，声明代码如下:
struct Product			  //声明商品结构体
{
	char cName[10];			//产品名称
	char cShape[20];		//形状
	char cColor[10];		//颜色
	char cFunc[20];			//功能
	int iPrice;				  //价格
	char CArea[20];			//产地
};
/*
上述代码使用关键字struct声明了一个名为Product的结构体类型，在结构体中定义了6个变量，分别表示产品名称、形状、颜色、
功能、价格和产地，并为其设置了相对应的类型。
*/
```

### 11.1.2 结构体变量的定义

声明完结构体后，就创建了一种新的类型名，后续就可以使用这种新的类型名定义变量。定义结构体变量的方式有如下 3 种。

1. 先声明结构体类型，再定义变量。

例如，使用前面声明的 Product 结构体类型定义两个结构体变量 product1 和 product2，代码如下：

```c
struct Product			  //声明商品结构体
{
	char cName[10];			//产品名称
	char cShape[20];		//形状
	char cColor[10];		//颜色
	char cFunc[20];			//功能
	int iPrice;				  //价格
	char CArea[20];			//产地
};
struct Product product1;//定义结构体类型变量
struct Product product2;
/*
在一些大型开发中，为了便于修改和使用，常常将结构体类型的声明放在一个头文件中，这样在其他源文件中如果需要使用
该结构体类型，则可以用#include命令将该头文件包含到源文件中。
*/
```

2. 声明结构类型的同时定义结构体变量。例如：

```c
struct Product			  //声明商品结构体
{
	char cName[10];			//产品名称
	char cShape[20];		//形状
	char cColor[10];		//颜色
	char cFunc[20];			//功能
	int iPrice;				  //价格
	char CArea[20];			//产地
}product1，product2;	//定义结构体类型变量
```

3. 直接定义结构体类型变量（此时不需要给出结构体名称）。例如：

```c
struct					      //声明商品结构体
{
	char cName[10];			//产品名称
	char cShape[20];		//形状
	char cColor[10];		//颜色
	char cFunc[20];			//功能
	int iPrice;				  //价格
	char CArea[20];			//产地
}product1，product2;	//定义结构体类型变量
/*
需要注意的是，类型与变量是不同的。例如，只能对变量进行赋值操作，不能对类型进行操作。
这就像使用int型定义变量iInt,可以为iInt赋值，但不能为int赋值。
编译时，不对类型分配空间，只对变量分配空间。
*/
```

4. 结构体的成员仍然可以是结构体类型的变量：

```c
struct date//日期结构体
{
	int year;				//年
	int month;			//月 
	int day;				//日
struct student		//学生结构体
{
	int num;				//学号
	char name[30];	//姓名
	char sex;				//性别
	int age;				//年龄
	struct date birthday;	//出生日期
}student1.student2;
/*
以上代码声明了一个date结构体类型，成员包括年、月、日；还声明了一个student结构类型，并且定义了两个结构体变量
student1和student2。在struct student结构体类型中，可以看到有一个成员是表示学生的出生日期，使用的是struct date
结构体类型。
*/
```

### 11.1.3 结构体变量的引用

定义了结构体类型变量以后，就可以引用该变量，引用形式为“结构变量名.成员名”。例如：

```c
product1.cName="I cebox";
product1.iPrice=2000;
```

对结构体变量进行赋值、存取或运算，实质上就是对结构体成员进行操作。上面的赋值语句就是对 product1 结构体变量中的成员 cName 和 iPrice 两个变量进行赋值。

如果成员本身又属于一个结构体类型，就需要使用若干个成员运算符 “.” 找到最低一级的成员，对其进行赋值、存取以及运算操作。

例如，对上面定义的 student1 变量中的出生日期进行赋值：

```c
student1.birthday.year-1986;
student1.birthday.month=12;
student1.birthday.day=6;
//不能使用student1.birthday访问student1变量中的成员birthday,因为birthday本身也是一个结构体变量。
```

结构体变量的成员可以像普通变量一样，进行各种运算。例如：

```c
product2.iPrice=product1.iPrice+500;
product1.iPrice++;
```

因为 “.” 运算符的优先级最高，所以 product1.iPrice++ 是 product1.iPrice 成员进行自加运算，而不是先对 iPrice 进行自加运算。

还可以对结构体变量成员的地址进行引用，也可以对结构体变量的地址进行引用，例如：

```c
scanf("%d",&product1.Price);//输入成员iPrice的值
printf("%o",&product1);			//输出product1的首地址
```

```c
//本实例首先定义一个表示老师的结构体，成员包括姓名、年龄和教龄;然后在主函数中使用该结构体定义一个老师，先赋值，再输出。
#define _CRT_SECURE_NO_WARNINGS
#include"stdio.h"
#include<string.h>
struct Teacher							//声明教师结构体
{
	char name[64];						//姓名
	int age;							    //年龄
	int seniority;						//教龄
};

int main()
{
	struct Teacher a_teacher;					   //定义结构体变量
	strcpy(a_teacher.name, "名师");		   //将姓名赋值给结构体变量
	a_teacher.age = 35;							     //年龄
	a_teacher.seniority = 10;					   //教龄
	printf("姓名：%s\n", a_teacher.name);//输出结构体变量
	printf("年龄：%d\n", a_teacher.age);
	printf("教龄：%d\n", a_teacher.seniority);
	return 0;
}
```

### 11.1.4 结构体类型的初始化

结构体类型与其他基本类型一样，也可以在定义结构体变量时指定初始值。

```c
struct Student
{
	char cName[20];
	char cSex;
	int iGrade;
}student1={"HanXue","W",3};//定义结构体变量并设置初始值
```

定义的变量后面使用等号，初始化值放在大括号中，数据顺序与结构体的成员列表顺序一致。

```c
/*
本实例演示了两种初始化结构体的方式，一种是在声明结构体及定义变量的同时进行初始化，另一种是在定义结构体变量后进行初始化。
*/

#include<stdio.h>
struct Student   //学生结构体
{
	char cName[20];//姓名
	char cSex;     //性别
	int iGrade;    //年级
}student1 = { "HanXue",'W',3 };                       //方式1：定义结构体时，直接赋初始值

int main()
{
	struct Student student2 = { "WangJiasheng",'M',3 }; //方式2：后续再定义变量并赋切始值"
	printf("第一个学生信息: \n");                        //以下将第一个结构体中的数据输出
	printf("姓名: %s\n", student1.cName);
	printf("性别: %c\n", student1.cSex);
	printf("年级: %d\n", student1.iGrade);
	printf("第二个学生信息: \n");                        //以下将第二个结构体中的数据输出
	printf("姓名: %s\n", student2.cName);
	printf("性别: %c\n", student2.cSex);
	printf("年级: %d\n", student2.iGrade);
	return 0;
}
```

并不是所有的结构体成员都可以赋值，如果某个成员使用 const 做了限定，就不可以再对其赋值。

## 11.2 结构体数组

当要定义 10 个整型变量时，可以使用数组的形式。当要定义 10 个结构体类型变量时，也可以使用数组的形式，这时的数组被称为结构体数组。结构体数组与普通数组的区别在于：数组中的每个元素都是根据要求定义的结构体类型，而不是基本类型。

### 11.2.1 定义结构体数组

定义结构体数组的方式与定义结构体变量的方法相同，其一般形式如下：

```c
struct 结构体名
{
	成员列表;
}数组名;
```

例如，定义一个学生信息的结构体数组，其中包含 5 个学生的信息，代码如下：

```c
struct Student			//学生结构体
{
	char cName[20];		//姓名
	int iNumber;			//学号
	char cSex;				//性别
	int iGrade;				//年级
}student[5];				//定义结构体数组
//上述代码中，定义结构体类型的同时定义了结构体数组student[5]。
```

除此以外，也可以先声明结构体类型再定义结构体数组：

```c

struct Student student[5];	//定义结构体数组
```

或者直接定义结构体数组（此时不需要给出结构体名称）：

```c
struct 						  //学生结构体
{
	char cName[20];		//姓名
	int iNumber;			//学号
	char cSex;				//性别
	int iGrade;				//年级
}student[5];				//定义结构体数组
```

数组中各数据在内存中的存储是连续的。

### 11.2.2 初始化结构体数组

初始化结构体数组的一般形式如下:

```c
struct 结构体名
{
	成员列表;
}数组名={初始值列表};

//例如，为学生结构体数组进行初始化操作，代码如下:
struct Student			//学生结构体
{
	char cName[20];		//姓名
	int iNumber;			//学号
	char cSex;				//性别
	int iGrade;				//年级
}student[5]={
{"WJ",12062212,'M',3},
{"YL",12062213,'W',3},
{"JX",12062214,'W',3},
{"ZM",12063315,'M',3},
{"HL",12062216,'M',3}
};							    //定义定义数组并设置初始值
```

为数组进行初始化时，最外层的大括号表示列出的是数组中的元素。因为每个元素都是结构体类型，所以也都使用大括号括起来，其中包含每一个结构体元素的成员数据。

定义数组 student 时，也可以不指定数组中的元素个数，这时编译器会根据数组后面的初始化值列表中给出的元素个数，来确定数组中元素的个数。例如：

```c
student[]={...};
```

同样，也可以先声明结构体数组，后续再进行初始化。

```c
struct Student			//学生结构体
{
	char cName[20];		//姓名
	int iNumber;			//学号
	char cSex;				//性别
	int iGrade;				//年级
}student[5];				//定义结构体数组
struct Student student[5]={
{"WJ",12062212,'M',3},
{"YL",12062213,'W',3},
{"JX",12062214,'W',3},
{"ZM",12063315,'M',3},
{"HL",12062216,'M',3}
};							    //初始化结构体数组
```

```c
//显示销售前5名的产品
#include<stdio.h>
struct Goods						//商品结构体
{
	char cName[20];				//商品名
	int iNumber;					//销售量
}goods[5] = {
	{"面膜",1458792365},
	{"洁面",325656550},
	{"洗发素",324655854},
	{"护发素",256897412},
	{"卸妆膏",155655655}
};									    //定义结构体变量并初始化

int main()							//主函数main
{
	int i;
	for (i = 0; i < 5; i++)
	{
		printf("NO%d 产品：\n", i + 1);
		printf("商品名是：%s，销量：%d\n", goods[i].cName, goods[i].iNumber);
		printf("\n");
	}
	return 0;
}
```

## 11.3 结构体指针

一个指向结构体变量的指针，指向的是结构体变量的起始地址。除此以外，指针变量还可以指向结构体数组以及数组中的元素。

### 11.3.1 指向结构体变量的指针

定义结构体指针的一般形式如下：

```c
结构体类型 *指针名；

//例如，定义一个指向struct Student的结构体类型pStruct指针变量，代码如下：
struct Student *pStruct;
```

指针指向的是结构体变量的地址，因此可以使用指针来访问结构体中的成员，方式有两种。

第一种方法是使用成员运算符 “.” 引用结构成员，形式为 “(*pStruct).成员名”。

```c
//例如，pStruct指针指向student1结构体变量，可以采用如下方式引用其中的成员。
(*pStruct).iNumber=12061212;
//注意，*pStruct一定放在括号内，这是因为成员运算符“.”的优先级最高，如果不使用括号，就会先执行“.”运算然后才是“*”运算。
```

```c
//登记新员工信息
#include<stdio.h>									//包含头文件
struct People										  //定义人员结构体
{
	char cName[20];									//姓名
	int iNumber;									  //职位号
	char cS[20];									  //部门
}people = { "张伟",14,"开发部" };	//对结构体变量初始化

int main()
{
	struct People* pStruct;					       //定义结构体类型指针
	pStruct = &people;							       //指针指向结构体变量
	printf("-----信息如下-----\n");	               
	printf("姓名: %s\n", (*pStruct).cName);//使用指针输出结构体成员
	printf("职工号: %d\n", (*pStruct).iNumber);
	printf("部门: %s\n", (*pStruct).cS);
	return 0;
}
```

第二种方法是使用指向运算符 “->” 引用结构成员，形式为 “pStruct->成员名”。

```c
//例如，使用指向运算符引用一个变量的成员:
pStruct->iNumber=12061212;
```

注意，在使用 “->” 引用成员时，要注意分析以下情况。

pStruct->iGrade：表示指向的结构体变量中成员 iGrade 的值。

pStruct->iGrade++：表示指向的结构体变量中成员 iGrade 的值，使用后该值加 1。

++pStruct->iGrade：表示指向的结构体变量中成员 iGrade 的值加 1，计算后再进行使用。

总结一下，假如 student 为结构体变量，pStruct 为指向结构体变量的指针，则以下 3 种引用形式的效果是完全等价的。

```c
student.成员名
(*pStruct).成员名
pStruct->成员名
```

```c
//打印购票信息
//在本实例中，定义结构体变量但不对其进行初始化操作，使用指针指向结构体变量并为其成员进行赋值操作。

#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<string.h>
struct Ticket					//定义车票结构体
{
	char cName[20];			//姓名
	int iNumber;				//票价
	char S[20];					//乘车区间
	char cAddress[20];	//车次
	char c[20];					//开车时间
}ticket;

int main()
{
	struct Ticket* pStruct;						      //定义结构体变量
	pStruct = &ticket;							        //指针指向结构体变量
	strcpy(pStruct->cName, "张伟");				  //赋值
	pStruct->iNumber = 285;
	strcpy(pStruct->S, "长春-北京");
	strcpy(pStruct->cAddress, "D71");
	strcpy(pStruct->c, "2021年2月20日09:08开");
	printf("姓名: %s\n", ticket.cName);			//输出结构体成员
	printf("票价: %d元\n", ticket.iNumber);
	printf("乘车区间: %s\n", ticket.S);
	printf("车次: %s\n", ticket.cAddress);
	printf("开车时间: %s\n", ticket.c);
	return 0;
}
```

### 11.3.2 指向结构体数组的指针

结构体指针变量指向结构体数组时，指针变量的值就是结构体数组的首地址。还可以直接指向结构体数组中的元素，这时指针变量的值就是该结构体数组元素的首地址。

```c
//例如，定义一个结构体数组student[5]，使用结构体指针指向该数组，代码如下：
struct Student* pStruct;
pStruct=student;
```

因为数组不使用下标时表示的是第一个数组元素的地址，所以指针指向数组的首地址。如果要指针指向第 3 个元素，则在数组名后附加下标，然后再数组名前使用取地址符 “&”。

```c
pStruct=&student[2];
```

```c
//显示5名同学信息
#include<stdio.h>
struct Student			//学生结构体
{
	char cName[20];		//姓名
	int iNumber;			//学号
	char cSex;				//性别
	int iGrade;				//年级
}student[5] = {
{"WJ",12062212,'M',3},
{"YL",12062213,'W',3},
{"JX",12062214,'W',3},
{"ZM",12063315,'M',3},
{"HL",12062216,'M',3}
};							    //定义定义数组并设置初始值

int main()
{
	struct Student* pStruct;
	int index;
	pStruct = student;
	for (index = 0; index < 5; index++, pStruct++)
	{
		printf("NO%d名学生：\n", index + 1);//首先输出学生的名次
		//使用变量index做下标，输出数组中的元素数据
		printf("姓名：%s\n学号：%d\n性别：%c\n年级：%d\n", pStruct->cName, pStruct->iNumber, pStruct->cSex, pStruct->iGrade);
		printf("\n");
	}
	return 0;
}
```

### 11.3.3 结构体作为函数参数

使用函数时，其参数也可以是结构体变量。形式有 3 种：使用结构体变量作为函数参数、使用指向结构体变量的指针作为函数参数、使用结构体变量的成员作为函数参数。

**1. 使用结构体变量作为函数参数**

结构体变量作为函数参数时，采取的是“值传递”方式，即会将结构体变量所占内存单元的内容全部顺序传递给形参，形参也必须是同类型的结构体变量。

```c
void Display(struct Student stu);
```

在形参位置使用结构体变量，但是函数调用期间，形参也要占用内存单元。这种传递方式在空间和时间上开销都比较大。另外，根据函数参数传值方式，如果在函数内部修改了变量中成员的值，则改变的值不会返回到主调函数中。

```c
//求语数外3科平均分
#include<stdio.h>
struct Student							//学生结构体
{
	char cName[20];						//姓名
	float fScore[3];					//分数
}student={"ZongLiang",98.5f,89.0,93.5f};//定义变量

void Display(struct Student stu)
{
	printf("-----信息如下-----\n");
	printf("姓名：%s\n", stu.cName);
	printf("语文：%.2f\n", stu.fScore[0]);
	printf("数学%.2f\n", stu.fScore[1]);
	printf("英语%.2f\n", stu.fScore[2]);
	printf("平均分：%.2f\n", (stu.fScore[0] + stu.fScore[1] + stu.fScore[2]));
}

int main()
{
	Display(student);
	return 0;
}
```

**2. 使用指向结构体变量的指针作为函数参数**

在传递结构体变量的指针时，只是将结构体变量的首地址进行传递，并没有将变量的副本进行传递。

```c
void Display(struct Student* stu);
```

这样使用形参 stu 指针就可以引用结构体变量中的成员了。需要注意的是，因为传递的是变量的地址，如果在函数中改变成员中的数据，那么返回主调函数时变量会发生改变。

```c
//修改英语成绩
#include<stdio.h>
struct Student								//学生结构体
{
	char cName[20];							//姓名
	float fScore[3];						//分数
}student = { "ZongLiang",98.5f,89.0,93.5f };//定义变量

void Display(struct Student *stu)			      //形参作为结构体变量的指针
{
	printf("-----信息如下-----\n");
	printf("姓名：%s\n", stu->cName);		      //使用指针引用结构体变量中的成员
	printf("英语%.2f\n", stu->fScore[2]);	    //输出英语的分数
	stu->fScore[2]=90.0f;					            //更改成员变量的值
}

int main()
{
	struct Student* pStruct = &student;				//定义结构体变量指针
	Display(pStruct);								          //调用函数，结构变量作为实参进行传递
	printf("修改后的英语%.2f\n", pStruct->fScore[2]);	//输出成员的值
	return 0;
}
```

**3. 使用结构体变量的成员作为函数参数**

该方式与普通变量作为实参是一样的，是值传递。

```c
Display(student.fScore[0]);
```

## 11.4 嵌套的结构体

结构体中的成员不仅可以是基本类型，也可以是结构体类型。例如，定义一个电脑结构体类型，其中的成员包括电源、机箱、显示器和内置零部件。其中，内置零部件又属于一个结构体类型，包括 CPU、主板、显卡3个成员。电脑这样的结构体类型就是嵌套的结构体。

```c
//输出电脑零件
#include<stdio.h>
struct in				//电脑内置零件结构体
{
	char in1[10];		//内置零件1
	char in2[10];		//内置零件2
	char in3[10];		//内置零件3
};

struct out
{
	char out1[30];		//零件1
	char out2[30];		//零件2
	char out3[30];		//零件3
	struct in ware;		//内置零件
}computer={"电源","机箱","显示器",{"CPU","主板","显卡"}};//为结构体变量初始化

int main()
{
	printf("外置设备：\n");
	printf("(1)%s\n", computer.out1);
	printf("(2)%s\n", computer.out2);
	printf("(3)%s\n", computer.out3);
	printf("内置设备：\n");
	printf("(1)%s\n", computer.ware.in1);
	printf("(2)%s\n", computer.ware.in2);
	printf("(3)%s\n", computer.ware.in3);
	return 0;
}
```

## 11.5 链表

### 11.5.1 链表概述

链表是一种常见的数据结构。链表中有一个头指针，指向一个变量，这个变量称为元素。在链表中每个元素包括数据部分和指针部分。数据部分用来存放元素所包含的数据，而指针部分用来指向下一个元素。最后一个元素的指针指向 NULL，表示指向的地址为空。

![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//9.png)

链表这种数据结构需要使用指针来实现，因此链表中所有结点都会包含一个指针变量，以保存下一个结点的地址。

```c
//例如，设计一个链表表示一个班级，链表中的节点表示学生，代码如下：
struct Student
{
char CName[20];		    	//姓名
int iNumber;			      //学号
struct Student* pNext;	//指向下一个结点的指针
};
```

向链表中添加结点时，原最后一个结点的指针将保存新添加的结点地址，新结点的指针将指向空（NULL）。添加完成后，新结点将成为链表中的最后一个结点，可见，不用担心链表长度会超出范围。

### 11.5.2 创建动态链表

链表并不是一开始就设定好大小的，而是根据结点多少动态创建的。动态创建结点时，首先要为其分配内存，下面先来了解一下动态分配内存空间需要用到的3个函数。

**1. malloc 函数**

用于在内存中动态分配一块 size 大小的内存空间。

```c
void* malloc(unsigned int size);
```

malloc 函数会返回一个指针，该指针指向分配的内存空间。如果出现错误，则返回 NULL。

**2. calloc 函数**

用于在内存中动态分配 n 个长度为 size 的连续内存空间。

```c
void* calloc(unsigned n,unsigned size);
```

calloc 函数会返回一个指针，该指针指向动态分配的连续内存空间的首地址。如果出现错误，则返回 NULL。

**3. free 函数**

用于释放指针 ptr 指向的内存区，使该部分能够被其他变量使用。

```c
void free(void* ptr);
```

free 函数无返回值，注意，ptr 是最近一次调用 calloc 或 malloc 函数时返回的指针。

如何建立动态链表？

```c
/*
所谓动态链表就是程序在运行过程中从无到有地建立起一个链表，即一个一个地分配节点的内存空间，然后输入节点中的数据，
并建立节点间的相连关系。假设需要将某班的学生信息存放在一个链表结构中，该怎么实现？
*/

//首先要创建一个节点结构，表示每一个学生：
struct Student
{
char CName[20];			    //姓名
int iNumber;			      //学号
struct Student* pNext;	//指向下一个结点的指针
};

//然后定义一个Create函数，用来创建链表。该函数将返回链表的头指针：
int iCount;															    //定义全局变量，表示链表长度
struct Student* Create()										//创建链表函数Create
{
	struct Student* pHead = NULL;							//初始化链表，使头指针为空
	struct Student* pEnd, * pNew;
	iCount = 0;														    //初始化链表长度
	pEnd = pNew = (struct Student*)malloc(sizeof(struct Student));//动态分配一块内存空间
	printf("please first enter Name ,then Number\n");
	scanf("%s", &pNew->cName);								//输入学生信息
	scanf("%d", &pNew->iNumber);
	while (pNew->iNumber != 0)								//当新增加的学号不为空时
	{
		iCount++;													      //结点数加1
		if (iCount == 1)										  	//如果第一个结点
		{
			pNew->pNext = pHead;									//使得指向为空
			pEnd = pNew;											    //跟踪新加入的结点
			pHead = pNew;											    //头指针指向首结点
		}
		else
		{
			pNew->pNext = NULL;										//新结点的指针为空
			pEnd->pNext = pNew;										//原来的尾结点指向新结点
			pEnd = pNew;											    //pEnd指向新结点
		}
		pNew = (struct student*)malloc(sizeof(struct Student));//再次分配结点内存空间
		scanf("%s", &pNew->cName);
		scanf("%d", &pNew->iNumber);
	}
	free(pNew);														    //释放没有用到的空间
	return pHead;
}
```

### 11.5.3 输出链表

如何将链表中的数据显示输出？

```c
//定义Print函数，用来输出链表中的数据：
void Print(struct Student* pHead)									      //输出结点函数Print
{
	struct Student* pTemp;											          //循环所用的临时指针
	int iIndex = 1;													              //表示链表中结点的序号
	printf("-----the List has %d members-----\n", iCount);//消息提示
	printf("\n");													                //换行
	pTemp = pHead;													              //临时指针得到首结点的地址
	while (pTemp != NULL)
	{
		printf("the NO%d member is:\n", iIndex);
		printf("the name is: %s\n", pTemp->cName);					//输出姓名
		printf("the number is: %d\n", pTemp->iNumber);			//输出学号
		printf("\n");												                //输出换行
		pTemp = pTemp->pNext;										            //移动临时指针到下一结点处
		iIndex++;													                  //进行自加运算
	}
}
```

```c
//编写一个包含学生信息的链表结构，并将链表中的信息显示输出。
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<stdlib.h>

struct Student
{
	char cName[20];			    //姓名
	int iNumber;			      //学号
	struct Student* pNext;	//指向下一个结点的指针
};

int iCount;															//定义全局变量，表示链表长度
struct Student* Create()								//创建链表函数Create
{
	struct Student* pHead = NULL;					//初始化链表，使头指针为空
	struct Student* pEnd, * pNew;
	iCount = 0;														//初始化链表长度
	pEnd = pNew = (struct Student*)malloc(sizeof(struct Student));//动态分配一块内存空间
	printf("please first enter Name ,then Number\n");
	scanf("%s", &pNew->cName);						//输入学生信息
	scanf("%d", &pNew->iNumber);
	while (pNew->iNumber != 0)						//当新增加的学号不为空时
	{
		iCount++;													  //结点数加1
		if (iCount == 1)										//如果第一个结点
		{
			pNew->pNext = pHead;							//使得指向为空
			pEnd = pNew;											//跟踪新加入的结点
			pHead = pNew;											//头指针指向首结点
		}
		else
		{
			pNew->pNext = NULL;								//新结点的指针为空
			pEnd->pNext = pNew;								//原来的尾结点指向新结点
			pEnd = pNew;											//pEnd指向新结点
		}
		pNew = (struct student*)malloc(sizeof(struct Student));//再次分配结点内存空间
		scanf("%s", &pNew->cName);
		scanf("%d", &pNew->iNumber);
	}
	free(pNew);														//释放没有用到的空间
	return pHead;
}
void Print(struct Student* pHead)				//输出结点函数Print
{
	struct Student* pTemp;								//循环所用的临时指针
	int iIndex = 1;												//表示链表中结点的序号
	printf("-----the List has %d members-----\n", iCount);//消息提示
	printf("\n");													//换行
	pTemp = pHead;												//临时指针得到首结点的地址
	while (pTemp != NULL)
	{
		printf("the NO%d member is:\n", iIndex);
		printf("the name is: %s\n", pTemp->cName);			//输出姓名
		printf("the number is: %d\n", pTemp->iNumber);	//输出学号
		printf("\n");												            //输出换行
		pTemp = pTemp->pNext;										        //移动临时指针到下一结点处
		iIndex++;													              //进行自加运算
	}
}

int main()
{
	struct Student* pHead;	//定义头结点
	pHead = Create();		    //创建结点
	Print(pHead);			      //输出链表
	return 0;				        //程序结束
}
```

## 11.6 链表的相关操作

### 11.6.1 插入结点

链表中，可以在头结点位置插入结点，也可以在中间位置插入结点，还可以像创建链表那样在最后插入结点，这3种插入操作的思路是一样的。下面主要介绍第一种插入方式，即在链表的头结点位置插入结点。

```c
//设计一个函数Insert，用来向链表中插入结点：
struct Student* Insert(struct Student* pHead)				      //插入结点函数Insert
{
	struct Student* pNew;									                  //指向新分配的空间
	printf("-----插入第1名信息-----\n");					          //提示信息
	pNew = (struct student*) malloc(sizeof(struct Student));//分配内存空间，并返回指向该内存空间的指针
	scanf("%s" &pNew->cName);
	scanf("%d", &pNew->iNumber);
	pNew->pNext = pHead;									                  //新结点指针指向原来的首结点
	pHead = pNew;											                      //头指针指向新结点
	iCount++;												                        //增加链表结点数量
	return pHead;
}
```

上述代码中，先为要插入的新结点分配内存，然后向新结点中输入数据，这样一个结点就创建完成了。接下来将这个结点插入链表中。首先将新结点的指针指向原来的首结点，保存首结点的地址。然后将头指针指向新结点，完成结点的连接操作，最后增加链表的结点数量。

修改 main 函数的代码，添加插入结点操作的函数 Insert：

```c
int main()
{
	struct Student* pHead;//定义头结点
	pHead=Create();       //创建结点
	pHead=Insert(pHead);  //插入结点
	Print(pHead);         //输出链表
	return 0;
}
```

### 11.6.2 删除结点

可以发现，要删除一个结点，首先要找到这个结点的位置，例如 NO2 结点，然后将 NO1 结点的指针指向 NO3 结点，最后将 NO2 结点的内存空间释放掉，这样就完成了结点的删除操作。

```c
//编写删除节点操作的函数Delete：
void Delete(struct Student* pHead, int index)	//删除结点函数Delete
{
	int t;													            //控制循环变量
	struct Student* pTemp;									    //临时指针
	struct Student* pPre;									      //表示要删除结点前的结点
	pTemp = pHead;											        //得到头结点
	pPre = pTemp;
	printf("-----删除NO%d名成员-----\n", iIndex);
	for (i = 1; i < iIndex; i++)							  //for循环，使pTemp指向要删除的结点
	{
		pPre = pTemp;
		pTemp = pTemp->pNext;
	}
	pPre->pNext = pTemp->pNext;								  //连接删除结点两边的结点
	free(pTemp);											          //释放要删除结点的内存空间
	iCount--;												            //减少链表中的元素个数
}
```

```c
//完整链表操作
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<stdlib.h>

struct Student
{
	char cName[20];			    //姓名
	int iNumber;		      	//学号
	struct Student* pNext;	//指向下一个结点的指针
};

int iCount;															//定义全局变量，表示链表长度
struct Student* Create()								//创建链表函数Create
{
	struct Student* pHead = NULL;					//初始化链表，使头指针为空
	struct Student* pEnd, * pNew;
	iCount = 0;														//初始化链表长度
	pEnd = pNew = (struct Student*)malloc(sizeof(struct Student));//动态分配一块内存空间
	printf("please first enter Name ,then Number\n");
	scanf("%s", &pNew->cName);						//输入学生信息
	scanf("%d", &pNew->iNumber);
	while (pNew->iNumber != 0)						//当新增加的学号不为空时
	{
		iCount++;													  //结点数加1
		if (iCount == 1)										//如果第一个结点
		{
			pNew->pNext = pHead;							//使得指向为空
			pEnd = pNew;											//跟踪新加入的结点
			pHead = pNew;											//头指针指向首结点
		}
		else
		{
			pNew->pNext = NULL;								//新结点的指针为空
			pEnd->pNext = pNew;								//原来的尾结点指向新结点
			pEnd = pNew;											//pEnd指向新结点
		}
		pNew = (struct student*)malloc(sizeof(struct Student));//再次分配结点内存空间
		scanf("%s", &pNew->cName);
		scanf("%d", &pNew->iNumber);
	}
	free(pNew);														//释放没有用到的空间
	return pHead;
}
void Print(struct Student* pHead)				//输出结点函数Print
{
	struct Student* pTemp;								//循环所用的临时指针
	int iIndex = 1;												//表示链表中结点的序号
	printf("-----the List has %d members-----\n", iCount);//消息提示
	printf("\n");													//换行
	pTemp = pHead;												//临时指针得到首结点的地址
	while (pTemp != NULL)
	{
		printf("the NO%d member is:\n", iIndex);
		printf("the name is: %s\n", pTemp->cName);		//输出姓名
		printf("the number is: %d\n", pTemp->iNumber);//输出学号
		printf("\n");												          //输出换行
		pTemp = pTemp->pNext;										      //移动临时指针到下一结点处
		iIndex++;													            //进行自加运算
	}
}

struct Student* Insert(struct Student* pHead)			//插入结点函数Insert
{
	struct Student* pNew;											      //指向新分配的空间
	printf("-----插入第1名信息-----\n");						//提示信息
	pNew = (struct student*)malloc(sizeof(struct Student));//分配内存空间，并返回指向该内存空间的指针
	scanf("%s",&pNew->cName);
	scanf("%d", &pNew->iNumber);
	pNew->pNext = pHead;											      //新结点指针指向原来的首结点
	pHead = pNew;													          //头指针指向新结点
	iCount++;														            //增加链表结点数量
	return pHead;
}

void Delete(struct Student* pHead, int iIndex)		//删除结点函数Delete
{
	int i;															            //控制循环变量
	struct Student* pTemp;										    	//临时指针
	struct Student* pPre;											      //表示要删除结点前的结点
	pTemp = pHead;													        //得到头结点
	pPre = pTemp;
	printf("-----删除NO%d名成员-----\n", iIndex);
	for (i = 1; i < iIndex; i++)									  //for循环，使pTemp指向要删除的结点
	{
		pPre = pTemp;
		pTemp = pTemp->pNext;
	}
	pPre->pNext = pTemp->pNext;										 //连接删除结点两边的结点
	free(pTemp);													         //释放要删除结点的内存空间 
	iCount--;														           //减少链表中的元素个数
}

int main()
{
	struct Student* pHead;	//定义头结点
	pHead = Create();		    //创建结点
	pHead = Insert(pHead);	//插入结点
	Delete(pHead, 2);		    //删除第二个节点
	Print(pHead);			      //输出链表
	return 0;
}
```

链表的产生弥补了数组的一些不足。在数组中插入或删除元素时，需要设计算法来移动数组元素，非常麻烦。但链表也有不足，在链表中查找元素远远不如数组有效率，所以两者的使用都要因地制宜。

## 11.7 共用体

### 11.7.1 共用体的概念

共用体也称为联合体，它使几种不同类型的变量存放到同一段内存单元中。共用体在某一时刻只能有一个值，即某个数据成员的值。由于所有成员共用同一块内存，因此共用体的大小就等于最大成员的大小。

定义共用体的类型变量的一般形式如下:

```c
union 共用体名
{
成员列表
}变量列表;
```

例如，下面的代码定义一个共用体，包括的数据成员有整型、字符型和实型：

```c
union DataUnion
{
int ilnt;
char cChar;
float fFloat;
}variable;//定义共用体变量
```

其中，variable 为定义的共用体变量，而 union DataUnion 是共用体类型。共用体也可以像结构体那样，将类型的声明和变量的定义分开：

```c
union DataUnion variable;
```

可以看到，共用体和结构体定义变量的方式很相似。需要注意的是，结构体变量的大小是其所包括的所有数据成员大小的总和，其每个成员都有自己的内存单元；共用体的大小则为所包含数据成员中最大内存长度的大小。例如，上面定义的共用体变量 variable 的大小就与 float 类型的大小相等。

### 11.7.2 共用体变量的引用

共用体变量定义完成后，就可以引用其中的数据成员，引用形式为”共用体变量.成员名”。

```c
//引用variable变量中的成员数据
variable.ilnt;
variable.cChar;
variable.fFloat;
```

不能在输出语句中直接引用共用体变量。

```c
//选择一种交通工具回家
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<string.h>

struct bus				    //声明公交车结构体类型
{
	char name[64];
};

struct subway			    //声明地铁结构体类型
{
	char name[64];
};

union Transportation	//声明公共交通共用体类型
{
	struct bus b;
	struct subway s;
};

int main()
{
	union Transportation t;
	strcpy(t.b.name, "公交车");
	strcpy(t.s.name, "地铁");
	printf("员工选择%s\n", t.b.name);
	printf("员工选择%s\n", t.s.name);
	return 0;
}
```

### 11.7.3 共用体变量的初始化

定义共用体变量时，可以同时进行初始化操作。同样，初始化值需要放在一对大括号中。

注意，对共用体变量初始化时，只需要一个初始化值就足够了，其类型必须和共用体的第一个成员的类型相一致。如果共用体的第一个成员是一个结构体类型，则初始化值中可以包含多个用于初始化该结构体的表达式。

```c
/字符型和整型的亲密关系
#include<stdio.h>
union DataUnion												//声明共用体类型
{
	int iInt;														//成员变量
	char cChar;
};

int main()
{
	union DataUnion Union = { 97 };			 //定义共用体变量并进行初始化
	printf("iInt：%d\n", Union.iInt);		 //输出成员变量数据
	printf("cChar：%c\n", Union.cChar);
	return 0;
}
```

共用体变量可以赋值吗？

其实是可以的，只是赋的值仍然是一个相同类型的共用体类型。引用共用体变量名也可以得到一个值，这个值就是共用体对象本身的值。

### 11.7.4 共用体类型的数据特点

同一内存虽然可用来存放不同类型的成员，但每次只能存放一种类型，而不能同时存放所有类型。也就是说，共用体中只有一个成员能起作用，其他成员不起作用。

共用体变量中，起作用的永远是最后存放的成员。存入新成员后，原有的成员将失去作用。

共用体变量的地址和它的各成员地址是一样的。

不能对共用体变量名赋值，也不能企图引用变量名来得到一个值。

## 11.8 枚举类型

实际问题中，有些变量会被限定在一个有限范围内，如一周有 7 天，一年有 12 个月等。如果把这些变量声明为整型、字符型或其他类型，显然是不妥的。为此，C 语言提供了枚举类型。

枚举类型是一种基本数据类型，不能再被分拆。利用关键字 enum 可以声明枚举类型，并使用枚举类型定义变量。一个枚举变量包含一组相关的标识符，每个标识符都对应一个整数值，称为枚举常量。

```c
//例如，定义一个枚举类型变量，其中每个标识符都对应一个整数值:
enum Colors(Red,Green,Blue);
//Colors就是定义的枚举类型变量，括号中第一个标识符对应着数值0，第二个对应于1，依此类推。
```

每个标识符都必须是唯一的，而且不能采用关键字或当前作用域内其他相同的标识符名。

```c
//在定义枚举类型的变量时，可以为某个特定的标识符指定其对应的整型值，紧随其后的标识符对应的值依次加1。例如:
enum Colors (Red=1,Green,Blue);
//这样的话，Red的值为1，Green为2，Blue为3。
```

```c
//选择喜欢的颜色
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
enum Color { Red = 1, Blue, Green } color;		//定义枚举变量，并初始化
int main()
{
	int icolor;																	//定义整型变量
	printf("1代表红色,2代表蓝色,3代表绿色。\n");
	printf("请输入您要选择的数字: ");
	scanf("%d", &icolor);												//输入数据
	switch (icolor)															//判断 icolor值
	{
	case Red:																	  //枚举常量，Red表示1
		printf("选择红色\n");
		break;
	case Blue:																	//枚举常量,Blue表示2
		printf("选择蓝色\n");
		break;
	case Green:																  //枚举常量,Green表示3
		printf("选择绿色\n");
			break;
	default:
		printf("???\n");
		break;
	}
	return 0;
}
```

# 第12章 位运算

## 12.1 位与字节

数据在内存中是以二进制的形式存放的。位是计算机存储数据的最小单位，一个二进制位可以表示 0、1 两种状态，多个二进制位组合起来便可表示多种信息。

## 12.2 位运算操作符

| 位运算符 | 含义 |
| --- | --- |
| & | 按位与 |
| | | 按位或 |
| ~ | 取反 |
| ^ | 按位异或 |
| << | 左移 |
| >> | 右移 |

### 12.1.1 按位与运算符

按位与运算符 “&” 是双目运算符，功能是使参与运算的两个数对应的二进位相与，即对应的两个二进位均为 1 时，结果为 1，否则为 0。

```c
//年龄值进行与运算
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
void main()
{
	unsigned result;												//定义无符号变量
	int age1, age2;													//定义变量
	printf("请输入第一个人年龄age1: ");			//提示输入年龄1
	scanf("%d", &age1);											//输入年龄1
	printf("请输入第二个人年龄 age2: ");			//提示输入年龄2
	scanf("%d", &age2);											//输入年龄2
	printf("age1=%d, age2=%d", age1, age2);	//显示年龄
	result = age1 & age2;										//计算相与运算的结果
	printf("\nage1&age2=%u\n", result);			//输出计算结果
}
```

初学者很容易将 “&” 与 “&&” 运算符混淆，下面总结一下它们的区别。

“&&” 是逻辑与运算符，相当于生活中的“与”，如我与你。其含义为：两个条件同时成立，逻辑与运算的结果为真，否则为假。

“&” 是位运算符，且为双目运算符，当两个位都为 1 时，结果才为 1，否则为 0。

### 12.2.2 按位或运算符

按位或运算符 “|” 是双目运算符，功能是使参与运算的两个数对应的二进位相或，即只要对应的两个二进位有一个为 1，结果就为 1。

```c
//0xEFCA与本身进行按位或运算
#include<stdio.h>
int main()
{
	int a = 0xEFCA, result;				//定义变量
	result = a | a;								//计算或运算的结果
	printf("a|a=%X\n",result);		//输出结果
	return 0;
}
```

同样，初学者也很容易将 “|” 与 “||” 运算符混淆，下面总结一下它们的区别。

“||” 是逻辑运算符，相当于生活中的“或者”，如我或者你。其含义为：两个条件中有一个成立，逻辑或运算的结果就是“真”。

“|” 是位运算符，且为双目运算符，当两个位都为 0 时，结果才为 0，否则为 1。

### 12.2.3 取反运算符

取反运算符 “~” 为单目运算符，具有右结合性。其功能是对参与运算的数的各二进位按位求反，即将 0 变成 1，1 变成 0。

```c
//将输入的数取反运算
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
main()
{
	unsigned result;							//定义无符号变量
	int a;
	printf("please input a : ");
	scanf("%d", &a);
	printf("a=%d", a);
	result = ~a;									//求a的反
	printf("\n~a = %o\n", result);//以八进制形式输出
}
```

### 12.2.4 按位异或运算符

按位异或运算符 “^” 是双目运算符。其功能是对参与运算的两个数对应的二进位相异或，即当对应的两个二进位数相异时结果为 1，否则结果为 0。

```c
//求两个数异或值
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
main()
{
	unsigned result;								//定义无符号数
	int a, b;
	printf("please input a : ");
	scanf("%d",&a);
	printf("please input b : ");
	scanf("%d", &b);
	printf("a=%d,b=%d",a, b);
	result = a ^ b;									//求a与b按位异或的结果
	printf("\na^b=%u\n", result);
}

/*
异或操作的一个主要用途就是能使特定的位翻转。
异或操作的另一个主要用途，就是在不使用临时变量的情况下实现两个变量值的互换。
例如，x=9，y=4，将x和y的值互换可用如下方法实现：
x=x^y;
y=y^x;
x=x^y;
*/
```

按位异或运算经常被用到一些简单的加密算法中。

### 12.2.5 左移运算符

左移运算符 “<<” 是双目运算符，其功能是把 “<<” 左边的运算数的各二进位全部左移若干位，由 “<<” 右边的数指定移动的位数，高位丢弃，低位补 0。

将 a 左移一位相当于 a 乘以 2，将 a 左移两位相当于 a 乘以 4，但这种简捷计算只限于移出位不包含 1 的情况。若是将十进制数 64 左移两位（假设 64 以一个字节即 8 位存储），则移位后的结果将为 0（01000000→00000000），这是因为 64 在左移两位时将 1 移出了。

```c
//将15进行左移
#include<stdio.h>
main()
{
	int x = 15;
	x = x << 2;											//x左移2位
	printf("左移2位的结果：%d\n", x);
	x = x << 3;											//x左移3位
	printf("再左移3位的结果：%d\n", x);
}
```

### 12.2.6 右移运算符

右移运算符 “>>” 是双目运算符，其功能是把 “>>” 左边的运算数的各二进位全部右移若干位，“>>” 右边的数指定移动的位数。例如，a>>2 即把 a 的各二进位向右移动两位，假设 a=00000110，右移两位后为 00000001，a 由原来的 6 变成了 1。

对于有符号数，右移时需要注意符号位的问题。当为正数时，最高位一般补 0；当为负数时，最高位是补 0 还是补 1，取决于编译系统的规定。移入 0 的称为“逻辑右移”，移入 1 的称为“算术右移”。

```c
//将30和-30右移
#include<stdio.h>
int main()
{
	int x = 30, y = -30;
	x = x >> 3;																//x右移3位
	y = y >> 3;																//y右移3位
	printf("x右移3位, y右移3位的结果：%d,%d\n", x, y);
	x = x >> 2;																//x右移2位
	y = y >> 2;																//y右移2位
	printf("x再右移2位, y再右移2位的结果：%d,%d\n", x, y);
	return 0;
}
```

## 12.3 循环移位

循环移位就是将移出的低位放到该数的高位，或者将移出的高位放到该数的低位。

![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//10.png)

循环左移：

首先将x的左端 n 位先放到 z 的低 n 位中，

```c
z=x>>(32-n);
```

然后将 x 左移 n 位，其右面低 n 位补 0，

```c
y=x<<n;
```

最后将 y、z，进行按位或运算。

```c
y=y|z;
```

```c
//循环左移
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
left(unsigned value, int n)						   //自定义左移函数
{
	unsigned z;
	z = (value >> (32 - n))|(value << n);  //循环左移的实现过程
	return z;
}

int main()
{
	unsigned a;
	int n;
	printf("请输入一个数:\n");
	scanf(" %o",&a);										  	//输入一个八进制数
	printf("请输入要移位的位数(>0)：\n");
	scanf("%d", &n);										    //输入要移位的位数
	printf("循环左移的结果:%o\n", left(a,n));//将左移后的结果输出
	return 0;
}
```

循环右移：

首先将 x 的右端 n 位先放到 z 的高 n 位中，

```c
z=x<<(32-n);
```

然后将 x 右移 n 位，其左端高 n 位补 0，

```c
y=x>>n;
```

最后将 y、z，进行按位或运算。

```c
y=y|z;
```

```c
//循环右移
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
right(unsigned value, int n)								//自定义右移函数
{
	unsigned z;
	z = (value << (32 - n)) | (value >> n);		//循环右移的实现过程
	return z;
}

void main()
{
	unsigned a;
	int n;
	printf("请输入一个数:\n");
	scanf(" %o", &a);									        //输入一个八进制数
	printf("请输入要移位的位数(>0)：\n");
	scanf("%d", &n);											    //输入要移位的位数
	printf("循环右移的结果:%o\n", right(a, n));//将右移后的结果输出
}
```

## 12.4 位段

### 12.4.1 位段的概念与定义

位段是一种特殊的结构体类型，其所有成员的长度均以二进制位为单位进行定义，结构体中的成员被称为位段。

位段的一般定义形式如下：

```c
struct 结构体名
{
	类型变量名1:长度;
	类型变量名2:长度;
	...
	类型变量名n:长度;
}
```

一个位段必须是 int、unsigned 或 signed 中的一种。例如，CPU 的状态寄存器按位段类型定义如下：

```c
struct status						//状态寄存器位段
{
unsigned sign:1;				//符号标志
unsigned zero:1;				//零标志
unsigned carry:1;				//进位标志
unsigned parity:1;			//奇偶溢出标志
unsigned half_carry:1;	//半进位标志
unsigned negative : 1;	//减标志
}flags;
```

### 12.4.2 位段相关说明

位段类型和位段变量的定义，以及位段成员的引用，均与结构体类型和结构体变量相同。

在下面定义的位段结构中，各位段都只占用一个二进制位：

```c
struct attribute
{
unsigned font:1;
unsigned color:1;
unsigned size:1;
unsigned dir:1;
}
```

如果某位段需要表示多于两种状态，也可将该位段设置为占用多个二进制位。例如，字体大小有 4 种状态，则可将上面的位段结构改写成如下形式：

```c
struct attribute
{
unsigned font:1;
unsigned color:1;
unsigned size:2;
unsigned dir:1;
}
```

某一位段要从另一个字节开始存放，可写成如下形式：

```c
struct status
{
unsigned a:1;
unsigned b:1;
unsigned c:1;
unsigned :0;
unsigned d:1;
unsigned e:1;
unsigned f:1
}flags;
```

原本 a、b、c、d、e、f 这 6 个位段是连续存储在一个字节中的。由于加入了一个长度为 0 的无名位段，因此其后的 3 个位段从下一个字节开始存储，一共占用两个字节。

可以使各位段占满一个字节，也可以不占满一个字节。例如：

```c
struct packed_data
{
unsigned a:2;
unsigned b:2;
unsigned c:1;
int i;
}data;
```

一个位段必须存储在一个存储单元（通常为 1 字节）中，不能跨两个存储单元。如果本单元不够容纳某位段，则从下一个单元开始存储该位段。

可以用 “%d”、“%x”、“%u”、“%o” 等格式字符，以整数形式输出位段。

在数值表达式中引用位段时，系统自动将位段转换为整型数。

# 第13章 预处理

## 13.1 宏定义

宏定义是预处理命令的一种，它提供了一种可以替换源代码中字符串的机制。简单来说，宏定义指令 #define 用来定义一个标识符和一个字符串，以这个标识符来代表这个字符串，在程序中每次遇到该标识符时就用所定义的字符串替换它。宏定义的作用相当于给指定的字符串起了一个别名。

C 语言并没有规定 #define 必须写在函数外面，只是规定这条命令必须单独占一个完整的逻辑行。其作用范围是 #define 出现的位置到所在源文件结束，或到相应的 #undef 预处理指令处。如果需要 #define 预处理命令仅在某个函数内有效，完全可以把它写在函数内。

### 13.1.1 不带参数的宏定义

不带参数的宏定义，其一般形式如下:

```c
#define 宏名 字符串
```

“#” 表示这是一条预处理命令。

宏名是一个标识符，必须符合 C 语言中对标识符的限定。宏名要简单且意义明确，一般习惯用大写字母表示，以便与变量名相区别。

字符串可以是常数、表达式、格式字符串等。

例如，下面宏定义的作用是在程序中用 PI 替代 3.14159。编译预处理时，每当在源程序中遇到 PI，就自动用 3.14159 代替。

注意，宏定义不是 C 语句，不需要在行末加分号。

```c
#define PI 3.14159
```

使用#define进行宏定义的好处是：当需要改变一个常量时，只需改变#define命令行，整个程序的常量都会改变，大大提高了程序的灵活性。

宏名定义后，即可成为其他宏名定义中的一部分。例如，下面代码定义了正方形的边长SIDE、周长PERIMETER及面积AREA的值。

```c
#define SIDE 5
#define PERIMETER 4*SIDE
#define AREA SIDE*SIDE
```

前面强调过，宏替换是以字符串代替标识符。因此，可定义一个标准的邀请语：

```c
#define STANDARD "You are welcome to join us ."
printf (STANDARD);
```

编译程序时，遇到标识符STANDARD，就用"You are welcome tojoin us."替换。

关于不带参数的宏定义，有以下几点需要注意。

如果在字符串中出现宏名，则不进行替换。

如果字符串多于一行，可在行末用反斜杠“\”进行续行。

#define命令出现函数外时，宏名的有效范围为定义命令之后到此源文件结束。

可以用#undef命令终止宏定义的作用域，例如：

```c
#include<stdio.h>
#define TEST "this is an example"
main()
{
	printf(TEST);
	#undef TEST;
}
```

通常会将所有#define放到文件开始处或独立的文件中，而不是将它们分散到整个程序中。

宏定义是一种预处理命令，不同于变量定义，它只做字符替换，而不分配内存空间。

### 13.1.2 带参数的宏定义

带参数的宏定义，不仅要进行字符串替换，还要进行参数替换。其一般形式如下：

```c
#define宏名(参数表) 字符串
```

```c
//本实例中，要求对两个数实现乘法和加法混合运算
#include<stdio.h>
#define MIX(a,b) ((a)*(b)+(b))		//宏定义，求两个数的混合运算
main()
{
	int x = 5, y = 9;
	printf("x,y: \n");
	printf("%d,%d\n", x, y);
	printf("the mix number is: %d\n", MIX(x, y));
}
```

对于带参数的宏定义，有以下几点需要注意。

宏定义时，参数要加括号。如不加括号，则结果可能是正确的，也可能是错误的。

宏扩展必须使用括号来保护表达式中优先级低的操作符，以确保调用时能达到预期效果。

对带参数的宏的展开，只是用宏名后括号内的实参字符串代替#define命令行中的形参。

宏定义时，宏名与带参数的括号之间不要加空格，否则会将空格以后的字符都作为替代字符串的一部分。

在带参宏定义中，形式参数不分配内存单元，因此不必做类型定义。

## 13.2 #include命令

使用#include命令可将其他源文件的内容包含进来，即将其他文件包含到本文件之中。被读入的源文件必须用双引号或尖括号括起来。例如，下面两行代码均表示包含了标准输入╱输出库文件stdio.h，后续可直接使用其中的函数而不用再定义。

```c
#include "stdio.h"
#include <stdio .h>
```

双引号和尖括号的区别如下。

尖括号：此为标准方式，系统会直接到存放C库函数头文件所在的目录中寻找要包含的文件。

双引号：系统先在用户当前目录中寻找要包含的文件，若找不到，再到存放C库函数头文件所在的目录中寻找要包含的文件。

file1.cfile2.cfile1.c

通常情况下，包含库函数时,使用尖括号可以节省查找时间;包含用户自定义文件时，使用双引号比较快捷。

```c
//一年长一岁

//age.c
#include<stdio.h>
#include "age.h"
int main()
{
	int age = 3;
	age = A;
	P("年龄是"D"岁\n", age);
	return 0;
}
//age.h
#define P printf		//定义头文件
#define D "%d"
#define A (age+1)
```

经常用在文件头部的被包含文件称为标题文件或头文件，一般以.h为后缀。一般情况下，将如下内容放到.h文件中。

宏定义。

结构、联合和枚举声明。

typedef声明。

外部函数声明。

全局变量声明。

使用文件包含为实现程序修改提供了方便。当需要修改某些参数时，不必逐个修改程序，只需修改一个文件(头部文件)即可。

关于文件包含，有以下几点需要注意。

一个#include命令只能指定一个被包含的文件。

文件包含是可以嵌套的，即在一个被包含文件中还可以包含另一个被包含文件。

若age.c中包含文件age.h，则预编译后两者会成为一个文件。如果age.h中有全局静态变量，则该全局变量在age.c文件中也有效，这时不需要再用extern声明。

## 13.3 条件编译

C语言预处理器提供了条件编译功能。一般情况下，源程序中的所有行都会参加编译。如果希望其中一部分内容只在满足一定条件时才进行编译，这时就需要使用条件编译命令。使用条件编译可以非常方便地处理程序的调试版本和正式版本，同时还会增强程序的可移植性。

### 13.3.1 #if命令

#if的基本含义是：如果#if命令后的参数表达式为真，则编译#if到#endif之间的程序段，否则跳过这段程序。#endif命令用来表示#if段的结束。

#if命令的一般形式如下：

```c
#if 常数表达式
		语句段
#endif
```

如果常数表达式为真，则该段程序被编译，否则跳过该段程序（不编译）。

```c
//与50进行比较
//用#if和#define实现与50进行比较。如果等于50，就计算i=i+50; 如果大于50，就计算i++; 如果小于50，就计算i--。
#include<stdio.h>
#define NUM 50
main()
{
	int i = 0;
#if NUM>50			//判断NUM是否大于50
	i++;
#endif
#if NUM==50
	i+=50;
#endif
#if NUM<50
	i--;
#endif
	printf("目前的值是：%d\n", i);
}
```

#else的作用是为#if为假时提供另一种选择，其作用和前面讲过的条件判断中的else相近。

```c
//判断是否是能被9527整除的偶数
#include<stdio.h>//包含头文件
#define iInput 19054//定义宏，用iInput代替19054
int main()
{
	printf("当前是：%d\n", iInput);														//显示宏定义的数据
#if iInput>0																							//判断条件，如果是正数
	if (iInput % 9527 == 0 && iInput % 2 == 0)									//如果能被9527整除且为偶数
		printf("能被9527整除的偶数\n");													//输出信息
#else
#if iInput<0																							//如果为负数
	printf("当前为负数：%d\n", iInput);													//输出结果
#else																									//若果是其他情况
	printf("不能被9527整除的偶数，此时数据为：%d\n", iInput);			//显示不满足条件的数据
#endif
#endif
	return 0;																							//程序结束
}
```

#elif指令用来建立“如果……或者如果……”这样阶梯状多重编译操作选择，与多分支if语句中的else if类似。

#elif的一般形式如下：

```c
#if 表达式1
	语句段1;
#elif 表达式2
	语句段2;
#elif 表达式3
	语句段3;
	...
#elif 表达式n
	语句段n;
#endif
```

```c
//判断输入的体温是否为正常体温
#include<stdio.h>
#define NUM 50
main()
{
	int i = 0;
#if NUM>50
	i++;
#elif NUM==50
	i += 50;
#else
	i--;
#endif
printf("i is：%d\n", i);
}
```

### 13.3.2 #ifdef及#ifndef命令

在#if条件编译命令中，需要判断符号常量所定义的具体值。但有时并不需要判断具体值，只需要知道这个符号常量是否被定义了，这时可以采用另一种条件编译的方法，即#ifdef与#ifndef命令，分别表示“如果有定义”及“如果无定义”。

#ifdef的一般形式如下：

```c
#ifdef 宏替换名
	语句段
#endif
```

其含义是：如果宏替换名已被定义过，则对语句段进行编译；如果未定义#ifdef后面的宏替换名，则不对语句段进行编译。

#ifdef可与#else连用，形式如下：

```c
#ifdef 宏替换名
	语句段1
#else
	语句段2
#endif
```

其含义是：如果宏替换名已被定义过，则对语句段1进行编译;如果未定义#ifdef后面的宏替换名，则对语句段2进行编译。

#ifndef的一般形式如下：

```c
#ifndef 宏替换名
	语句段
#endif
```

其含义是：如果未定义#ifndef后面的宏替换名，则对语句段进行编译;如果定义#ifndef后面的宏替换名，则不执行语句段。

同样，#ifndef也可以与#else连用，一般形式如下：

```c
#ifndef 宏替换名
	语句段1
#else
	语句段2
#endif
```

其含义是：如果未定义#ifndef后面的宏替换名，则对语句段1进行编译;如果定义#ifndef后面的宏替换名，则对语句段2进行编译。

```c
//模拟银行叫号服务
#include<stdio.h>
#define STR "100号"					//定义宏常量
int main()
{
#ifdef STR
	printf(STR);
	printf("能办理业务\n");
#endif
	printf("\n");
#ifndef ABC
	printf("没取到号不能办理业务\n");
#endif
	return 0;
}
```

### 13.3.3 #undef命令

使用#undef命令可以删除事先定义好的宏定义。其一般形式如下：

```c
#undef宏替换名
```

使用#undef命令可将宏名限制在特定的代码段中。例如：

```c
#define MAX_SIZE 100
char array [MAX_SIZE];
#undef MAX_SIZE
```

上述代码中，首先使用#define定义标识符MAX_SIZE，然后使用#undef删除宏定义。也就是说，遇到#undef语句之前，MAX_SIZE的定义都是有效的。

### 13.3.4 #line命令

#line命令用于显示_LINE_与_FILE_的内容。_LINE_用于存放当前编译行的行号，_FILE_用于存放当前编译的文件名。

#line命令的一般形式如下：

```c

#line 行号["文件名"]
```

其中，行号为任一正整数，可选的文件名为任意有效文件标识符。行号为源程序中当前行号，文件名为源文件的名字。#line命令主要用于调试及其他特殊应用。

```c
#line 100 "13.7 输出当前行号和文件名"
#include<stdio.h>
int main()
{
	printf("1.当前行号：%d\n", __LINE__);
	printf("2.当前文件名：%s\n", __FILE__);
	printf("3.当前文件创建日期：%s\n", __DATE__);
	printf("4.当前文件创建时间：%s\n", __TIME__);
	return 0;
}
```

### 13.3.5 #pragma命令

**1. #pragma命令**

#pragma命令用于设定编译器状态，或指示编译器完成一些特定动作。一般形式如下：

```c
#pragma 参数
```

message参数：在编译信息窗口中输出的相应信息。

code_seg参数：设置程序中函数代码存放的代码段。

once参数：保证头文件被编译一次。

**2. 预定义宏名**

ANSI标准说明了以下5个预定义宏替换名。

**LINE：**当前被编译代码的行号。

**FILE：**当前源程序的文件名称。

**DATE：**当前源程序的创建日期。

**TIME：**当前源程序的创建时间。

**STDC：**判断当前编译器是否为标准C。其值为1，是标准C，否则不是标准C。

宏名的书写比较特别，书写时两边都要由下画线构成。如果编译不是标准的，则可能仅支持以上宏名中的几个，或根本不支持。
编译程序有时还提供其他预定义的宏名。

# 第14章 文件

## 14.1 文件概述

文件是一组相关数据的有序集合，这个数据集有一个名称，叫作文件名。

所有文件都可以通过流进行输入、输出操作。与文本流和二进制流相对应，文件可以分为文本文件和二进制文件两大类。文本文件也称为ASCII文件，保存时每个字符对应一个字节，存放对应的ASCII码。二进制文件按二进制编码方式保存文件内容。

按文件内容看，可分为源文件、目标文件、可执行文件、头文件和数据文件等。

从用户角度(或所依附的介质)看，文件可分为普通文件和设备文件两种。

普通文件：指驻留在磁盘或其他外部介质上的一个有序数据集。

设备文件：指与主机相连的各种外部设备，如显示器、打印机、键盘等。操作系统中把外部设备也看作一个文件来进行管理，把它们的输入、输出等同于对磁盘文件的读和写。

## 14.2 文件基本操作

文件的基本操作包括文件的打开和关闭。除标准的输入、输出文件外，其他所有文件都必须先打开再使用，使用后还必须关闭该文件。

### 14.2.1 文件指针

文件指针是一个指向文件有关信息的指针，这些信息包括文件名、状态和当前位置，保存在一个结构体变量中。使用文件时需要在内存中为其分配空间，用来存放文件的基本信息。该结构体类型是由系统定义的，C语言规定该类型为FILE型，其声明如下：

```c
typedef struct
{
	short level;
	unsigned flags;
	char fd;
	unsigned char hold;
	short bsize;
	unsigned char* buffer;
	unsigned ar* curp;
	unsigned istemp;
	short token;
}FILE;
```

上述代码中，使用typedef定义了一个FILE结构体类型，编写程序时可直接使用FILE类型来定义变量。注意，定义变量时不必将结构体内容全部给出，只需写成如下形式(fp是一个指向FILE类型的指针变量)：

```c
FILE* fp;
```

不可以通过定义FILE类型变量来操作文件。FILE型数据对象的位置由库函数确定，C语言中只能通过FILE* 类型的指针来操作文件。

### 14.2.2 文件的打开

fopen函数用来打开一个文件，打开文件的操作就是创建一个流。fopen函数的原型在stdio.h中，其调用形式一般如下：

```c
FILE* fp;
fp=fopen(文件名，使用文件方式);
```

其中，“文件名”是将要被打开文件的文件名，“使用文件方式”是指对打开文件进行的读写方式。

| 文件使用方式 | 含义 |
| --- | --- |
| r(只读) | 打开一个文本文件，只允许读数据 |
| w(只写) | 打开或建立一个文本文件，只允许写数据 |
| a(追加) | 打开一个文本文件，并在文件末尾写数据 |
| rb(只读) | 打开一个二进制文件,只允许读数据 |
| wb(只写) | 打开或建立一个二进制文件，只允许写数据 |
| ab(追加） | 打开一个二进制文件,并在文件末尾写数据 |
| r+(读写) | 打开一个文本文件,允许读和写 |
| w+(读写） | 打开或建立一个文本文件,允许读写 |
| a+(读写) | 打开一个文本文件,允许读,或在文件末追加数据 |
| rb+(读写) | 打开一个二进制文件,允许读和写 |
| wb+(读写) | 打开或建立一个二进制文件，允许读和写 |
| ab+(读写) | 打开一个二进制文件,允许读,或在文件末追加数据 |

例如，以只读方式打开名为123的文本文档文件，代码如下：

```c
FILE* fp;
fp=fopen("123.txt","r");
```

如果使用fopen函数打开文件成功，则返回一个有确定指向的FILE类型指针;若打开失败，则返回NULL。文件打开失败的原因通常是以下3个方面：

指定的盘符或路径不存在。

文件名中含有无效字符。

以r模式打开一个不存在的文件。

### 14.2.3 文件的关闭

文件使用完毕后，应使用fclose函数将其关闭。fclose函数的原型也在stdio.h中，调用形式如下：

```c
fclose(文件指针);
```

正常完成关闭文件操作时，fclose函数的返回值为0，否则返回EOF。例如：

```c
fclose (fp);
```

在程序结束之前应关闭所有文件，这样做的目的是防止因为没有关闭文件而造成的数据丢失。

## 14.3 文件的读写

### 14.3.1 fputc函数

fputc函数用于把一个字符写到磁盘文件（fp所指向的文件）中。其一般形式如下：

```c
ch=fputc(ch, fp);
```

其中，ch是要写入的字符，可以是一个字符常量，也可以是一个字符变量。fp是文件指针变量，如果函数写入成功，则返回值就是写入的字符；如果写入失败，则返回EOF。

```c
/*
创业指导课上，老师要求每个学生说一句关于创业的经典语录。
将马云的经典语录“Together we creat a team culture，rather than complaining about culture.”写到文件中，以“#”结束输入。
*/
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<stdlib.h>
int main()
{
	FILE* fp;
	char ch;
	if ((fp = fopen("E:\\Users\\ZL\\source\\repos\\-14-\\temp文件\\1.txt", "w")) == NULL)
	{
		printf("不能打开文件\n");
		exit(0);
	}
	printf("请输入名人名言：\n");
	ch = getchar();
	while (ch != '#')
	{
		fputc(ch, fp);
		ch = getchar();
	}
	fclose(fp);
	return 0;
}
```

### 14.3.2 fgetc函数

fgetc函数用于从指定文件(f指向的文件）中读取一个字符赋予ch。其一般形式如下：

```c
ch=fgetc (fp);
```

注意，文件必须以读或读写方式打开。当函数遇到文件结束符时，将返回文件结束标志EOF。

```c
//读取诗句
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	FILE* fp;						//定义一个指向FILE类型结构体的指针变量
	char ch;						//定义变量及数组为字符型
	fp = fopen("E:\\Users\\ZL\\source\\repos\\-14-\\temp文件\\早发白帝城.txt", "r");//以只读方式打开指定文件
	ch = fgetc(fp);			//fgetc函数读取一个字符并赋予ch
	while (ch != EOF)		//当读取的字符值等于EOF时，结束循环。如果不等于EOF
	{
		putchar(ch);			//将读取的字符输出到屏幕上
		ch = fgetc(fp);		//*fgetc函数继续读取下一个字符并赋予ch
	}
	printf("\n");
	fclose(fp);					//关闭文件
	return 0;
}
```

fgets函数和gets函数的区别如下。

gets函数读完回车换行（'\n')，并不存储它;fgets函数存储换行符并在其后写一个null character ('\0')。

不能简单地把fgets函数理解为gets函数限制字符数目的stdin加强版。

在改用fgets函数后，应该注意把字符串末尾之前的'\n'删除。

### 14.3.3 fputs函数

fputs函数与fputc函数类似，用于向指定的文件写入一个字符串。其一般形式如下：

```c
fputs(字符串,文件指针)
```

其中，字符串可以是字符串常量，也可以是字符数组名、指针或变量。

```c
//录入歌词
#include<stdio.h>
#include<process.h>
int main()
FILE* fp;
char filename[30], str[30];
r定义两个字符型数组* /
printf(-请输入文件路径:Mn");
	scanf("%s", filename);
广“输入文件名 *
if (fp = fopen(filename, "w))==NULL)
	产判断文件是否打开失败 * I
	{
	printf(“不能打开文件n请按任意键结束n); getchar();
	exit(O);
	}
printf("请输入歌词:Mn");
提示输入字符串I
getchar() :
	gets(str); fputs(str, fp);
r将字符串写入f所指向的文件中* I
fclose(fp);
return 0;
```

### 14.3.4 fgets函数

fgets函数与fgetc函数类似，用于从指定的文件中读取一个字符串到字符数组中。其一般形式如下：

```c
fgets(字符数组名,n,文件指针);
```

其中，n表示读取的字符串中字符的个数（包含“\0”) 。

```c
//读取歌词
#finclude<stdio.h>
#include<process.h>
int main()
FILE"fp;
char filename[30].str[30];
//定义两个字符型数组
printf("请输入文件路径:\n");
scanf("%s", filename);
//输入文件名
f((fp = fopen(filename, "r") == NULL)
//判断文件是否打开失败
{
	printf("不能打开文件Nn请按任意键结来in"); getchar();
	exit(O);
	fgets(str, sizeof(str).fp);
	//读取磁盘文件中的内容
	printf("%s", str);
	printf("ln"); 
	fclose(fp);
	return O;
}
```

### 14.3.5 fprintf函数

前面讲过printf和scanf函数，两者都是格式化读写函数。fprintf和fscanf函数与之相似,但读写对象不是终端，而是磁盘文件。

fprintf函数的一般形式如下：

```c
ch=fprintf(文件类型指针,格式字符串,输出列表);

//例如，下面语句的作用是将整型变量i的值以“%d”的格式输出到fp指向的文件中。
fprintf ( fp, "%d" ,i ) ;
```

```c
#include<stdio.h>
#include<process.h>
int main()
{
	FILE* fp;
	//定义一个指向FILE类型结构体的指针变量
	int = 1;
	int j = 2;
	char filename[30]:
	//定义一个字符型数组
	printf("请输入保存文件路径:n);
	//输入文件名
	scanf("%s", filename);
	if((fp = fopen(filename, "w))==NULL)
	{
		//判断文件是否打开失败"
		printf("不能打开文件Nn请按任意键结束\n");
		getchar();
		exit(O);
	}
	//写入fp所指的磁盘文件中
	fprintf(fp."%4dn".i);
	fprintf(fp."%2d", i) :
	fprintf(fp."%4dln"".i);
	fprintf(fp." % d"".i); 
	fprintf(fp. % 3d".j);
	fprintf(fp," % 4din".i);
	fclose(fp);
	return O;
}
```

### 14.3.6 fscanf函数

fscanf函数的一般形式如下：

```c
fscanf(文件类型指针,格式字符串，输入列表);

//例如，下面语句的作用是读取fp指向文件中的i的值。
fscanf(fp,"%d",&i);
```

```c
#include<stdio.h>
#include<process.h>
int main()
{
	FILE* fp; char ij;
	char filename[30];
	//定义一个字符型数组
	printf("请输入文件路径:ln");
	scanf("%s", filename);
	//输入文件名
	if ((fp = fopen(filename."r") == NULL)
	//判断文件是否打开失败
	{
		printf("不能打开文件tn请按任意键继续n"); 
		getchar();
		exit(O);
	}
	for (i = 0; i < 15; i++)
	{
		fscanf(fp."%c", &j);
		printf("%d answer is:%5cn", i + 1, J);
	
	}
	fclose(fp) :
	fclose(fp); 
	return O;
}
```

### 14.3.7 fread函数和fwrite函数

实际开发中，往往需要对整块数据进行读写，例如，对一个结构体类型变量值进行读写。下面介绍可实现整块读写功能的fread和 fwrite函数。

fread函数的功能是:从fp指向的文件中读取count次，每次读size字节，读取的信息保存在buffer地址中。其一般形式如下：

```c
fread (buffer,size , count, fp);
```

fwrite函数的功能是：将buffer地址开始的信息输出count次，每次写size字节到fp指向的文件中。其一般形式如下：

```c
fwrite (buffer,size, count, fp);

/*
buffer :一个指针。对fwrite函数来说，是待输出数据的地址(起始地址)﹔对fread函数来说，是待读取数据存放的地址。
size:要读写的字节数。
count:要读写多少个size字节的数据项。
fp:文件型指针。
*/

//例如，下面的语句表示从f指向的文件中每次读取两个字节并保存在数组a中，连续读取3次。
fread(a, 2,3,fp);

//下面的语句表示将数组a中的信息每次输出两个字节到fp指向的文件中，连续输出3次。
fwrite(a ,2,3,fp);
```

```c
//新实习生信息
#include<stdio.h>
#include<process.h>
struct address_list									    /*定义结构体，存储实习生成绩信息*/
{
    char name[10];
    char adr[20];
    char tel[15];
} info[100];
void save(char *name, int n)				    /*自定义save函数*/
{
    FILE *fp;										        /*定义一个指向FILE类型结构体的指针变量*/
    int i;
    if((fp = fopen(name, "wb")) == NULL)/*以只写方式打开指定文件*/
    {
        printf("不能打开文件\n");
        exit(0);
    }
    for(i = 0; i < n; i++)
        if(fwrite(&info[i], sizeof(struct address_list), 1, fp) != 1)	/*将一组数据输出到fp所指的文件中*/
            printf("写入有误\n");				/*如果写入文件不成功，则输出错误*/
    fclose(fp);										      /*关闭文件*/
}
void show(char *name, int n)						/*自定义show函数*/
{
    int i;
    FILE *fp;									        	/*定义一个指向FILE类型结构体的指针变量*/
    if((fp = fopen(name, "rb")) == NULL)/*以只读方式打开指定文件*/
    {
        printf("不能打开文件\n");
        exit(0);
    } 
    for(i = 0; i < n; i++)
    {
        fread(&info[i], sizeof(struct address_list), 1, fp);/*从fp所指向的文件读入数据存到score数组中*/
        printf("%15s%20s%20s\n", info[i].name, info[i].adr,info[i].tel);
    }
    fclose(fp);										      /*关闭文件*/
}
int main()
{
    int i, n;										        /*变量类型为基本整型*/
    char filename[50];							  	/*数组为字符型*/
    printf("一共几名?\n");
    scanf("%d", &n);									  /*输入实习生数*/
    printf("请输入文件路径:\n");
    scanf("%s", filename);							/*输入文件所在路径及名称*/
    printf("请输入姓名，地址，手机号\n");
    for (i = 0; i < n; i++)							/*输入实习生信息*/
    {
        printf("NO%d", i + 1);
        scanf("%s%s%s", info[i].name, info[i].adr, info[i].tel);
        save(filename, n);							/*调用函数save*/
    }
	printf("信息如下:\n");
    show(filename, n);								  /*调用函数show*/
}
```

## 14.4 文件的定位

对文件进行操作时，往往不需要从头开始，而是只操作指定内容。这时，就需要使用文件定位函数来实现对文件的随机读取。下面介绍3个随机读写函数。

### 14.4.1 fseek函数

fseek函数的作用是移动文件内部的位置指针。其一般形式如下：

```c
fseek(文件类型指针，位移量，起始点);
```

“文件类型指针”指向被移动的文件；

“位移量”表示移动的字节数，一般为long型数据，以保证文件长度大于64KB时不会出错；

“起始点”表示从何处开始计算位移量，一般是文件首、文件当前位置和文件尾，其表示方法如表14.2所示。

| 起始点 | 表示符号 | 数字表示 |
| --- | --- | --- |
| 文件首 | SEEK-SET | 0 |
| 文件当前位置 | SEEK-CUR | 1 |
| 文件尾 | SEEK-END | 2 |

例如，下面的语句表示将位置指针从当前位置向后退20个字节。

```c
fseek(fp,-20L,1);
```

注意，fseek函数一般用于二进制文件。在文本文件中使用时，由于要进行转换，计算的位置会出现错误。

文件的随机读写在移动位置指针之后进行，即可用前面介绍的任一种读写函数进行读写。

```c
//快递员送快递

/*
快递员通常会将收货人电话的后4位写到快递包裹上，作为取货号使用。编写程序，例如收货人电话是123****8900，则输出
取货号8900。运行程序前，需要在E盘设置goods.txt文件，内容是收货人的手机号。代码如下:
*/
#include<stdio.h>
#include<process.h>
int main()
{
	FILE *fp;
	char filename[30],str[50];          /*定义两个字符型数组*/
	printf("请输入文件路径:\n");
	scanf("%s",filename);               /*输入文件名*/
	if((fp=fopen(filename,"wb"))==NULL) /*判断文件是否打开失败*/
	{
		printf("不能打开文件!\n请按任意键继续\n");
		getchar();
		exit(0);
	}
	printf("请输入字符串:\n");
	getchar();
	gets(str);
	fputs(str,fp);
	fclose(fp);
	if((fp=fopen(filename,"rb"))==NULL) /*判断文件是否打开失败*/
	{
		printf("不能打开文件!\n请按任意键继续\n");
		getchar();
		exit(0);
	}
	fseek(fp,7L,0);
	fgets(str,sizeof(str),fp);
	printf("\n取货号为:\n");
	puts(str);
	fclose(fp);
    return 0;
}
```

### 14.4.2 rewind函数

rewind函数用于将位置指针重返文件开头，没有返回值。其一般形式如下：

```c
int rewind(文件类型指针)
```

```c
//给支付宝设置密码
/*
给支付宝设置密码时，用户输入一次密码后，会提示再输入一次密码，模拟此场景。运行程序之前，需要在E盘设置
password.txt文件，内容是设置的密码。
*/

#include<stdio.h>
#include<process.h>
int main()
{
	FILE *fp;
	char ch,filename[50];
	printf("请输入文件路径:\n");
	scanf("%s",filename);	              /*输入文件名*/						 
	if((fp=fopen(filename,"r"))==NULL) 	/*以只读方式打开该文件*/			 
	{
		printf("不能打开文件\n");
		exit(0);
	}
	printf("\n输入密码:\n");
	ch = fgetc(fp);				
	while (ch != EOF)				
	{
		putchar(ch);    /*输出字符*/							 
		ch = fgetc(fp); /*获取fp指向文件中的字符*/							 
	}
   
	rewind(fp);       /*指针指向文件开头*/
	printf("\n请再次输入密码:\n");
	ch = fgetc(fp);			
	while (ch != EOF)					
	{
		putchar(ch); 		/*输出字符*/							 
		ch = fgetc(fp);			
	}
	printf("\n");
	fclose(fp); 	    /*关闭文件*/								 
    return 0;
}
```

### 14.4.3 ftell函数

ftell函数可得到流式文件中的当前位置，并使用相对于文件头的位移量表示。其一般形式如下：

```c
long ftell(文件类型指针)
```

当ftell函数的返回值为-1L时，表示出错。

```c
//设置银行卡密码

/*
银行卡密码只能是6位，设置6位，表示设置密码成功，否则失败。运行程序前，先在E盘设置cipher.txt文件，内容
是银行卡密码。具体代码如下:
*/
#include<stdio.h>
#include<process.h>
int main()
{
		FILE *fp; 								  /*定义一个指向FILE类型结构体的指针变量*/
		int n;
		char ch,filename[50];
		printf("请输入文件路径:\n");
		scanf("%s",filename);				/*输入文件位置*/ 
		if((fp=fopen(filename,"r"))==NULL)/*判断是否能打开文件*/ 
		{
			printf("不能打开此文件\n");
			exit(0);
		}
		printf("密码为:");
		ch = fgetc(fp);							/*读出一个字符*/
		while (ch != EOF)				
		{
			putchar(ch);								 
			ch = fgetc(fp); 						 
		}
			n=ftell(fp);							/*输出长度*/
    	if(6==n)									/*判断长度是否等于6*/
			printf("\n设置密码成功\n");
    	else
			printf("\n设置密码失败\n");
		fclose(fp); 								/*关闭文件*/		 
      return 0;
}
```

当需要将某个文件中的内容复制到另一个文件中时，可使用fseek函数将文件指针指向文件尾，这样就可以将另一个文件中的内容逐个写到该文件中所有内容的后面，从而实现复制操作。

```c
//将两个文件内容合并到一起

/*
在E盘创建两个文件saying1、 saying2，其中saying1.txt内容是“花儿凋谢不再开，”,，saying2.txt内容是“光阴一去
不再来。”。编写程序，将文件2的内容复制到文件1中，代码如下:
*/
#include<stdio.h>
#include<process.h>
main()
{
	FILE *fp1,*fp2;
	char ch,filename1[30],filename2[30];
	printf("请输入文件1的名字：\n");
	scanf("%s",filename1);
	printf("请输入文件2的名字：\n");
	scanf("%s",filename2);
	if((fp1=fopen(filename1,"ab+"))==NULL)
	{
		printf("不能打开文件，请按任意键继续\n");
		getchar();
		exit(0);
	}
	if((fp2=fopen(filename2,"rb"))==NULL)
	{
		printf("不能打开文件，请按任意键继续\n");
		getchar();
		exit(0);
	}
	fseek(fp1,0L,2);
	while((ch=fgetc(fp2))!=EOF)
	{
		fputc(ch,fp1);
	}
	fclose(fp1);
	fclose(fp2);
}
```

# 第15章 存储管理

## 15.1 内存组织方式

### 15.1.1 数据的存放方式

程序编写完成后，需要先装载到计算机的内核或者半导体内存中，然后才能运行。计算机程序一般被组织成4个逻辑段：可执行代码、静态数据、动态数据（堆）和栈。

可执行代码和静态数据存储在固定的内存位置。

动态数据需要系统动态分配内存，一般存放在堆区的内存池中。

局部数据对象、函数参数，以及调用函数和被调用函数的联系，存放在栈区的内存池中。

### 15.1.2 堆与栈

**1. 堆**

内存的全局存储空间中，程序可动态分配和释放的内存块称为自由存储空间，也称为堆。

C程序中，用malloc和free函数来从堆中动态地分配和释放内存。

```c
//使用malloc函数分配一个整型变量的内存空间，在使用完该空间后，使用free函数进行释放。

#include <stdlib.h>
#include<stdio.h>
int main()
{
	int* pInt;									           //定义指针
	pInt = (int*)malloc(sizeof(int));			 //分配内存
	*pInt = 20;									           //使用分配的内存
	printf("《绝地生存》占%dG空间\n",*pInt);//输出信息
	free(pInt);									           //释放内存
	return 0;
}
```

**2. 栈**

程序不会像处理堆那样，在栈中显式地分配内存。当程序调用函数和声明局部变量时，系统将自动分配内存。

栈是一个后进先出的“压入弹出式”数据结构。程序运行时，每向栈中压入一个对象，栈指针就会向下移动一个位置。当系统从栈中弹出一个对象时，最晚进栈的对象将被先弹出，然后栈指针向上移动一个位置。如果栈指针位于栈顶，则表示栈是空的;如果栈指针指向最下方数据项的后一个位置，则表示栈为满的。

![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//11.png)

程序员经常利用栈处理那些适合用“后进先出”逻辑描述的编程问题。栈不需要程序员编写代码去维护，而是运行时由系统自动处理。
系统自动维护和后进先出是栈区别于堆的显著标志。

栈是如何工作的呢？通过函数调用来看一下栈的整体操作过程。

当函数A调用函数B时，系统将会把函数A的所有实参和返回地址压入栈中，栈指针将移到合适的位置来容纳这些数据。最后进栈的是函数A的返回地址。

当函数B开始执行后，系统把函数B的自变量压入栈中，并把栈指针再向下移，以保证有足够的空间来存储函数B声明的所有自变量。

当函数A的实参压入栈后，函数B就在栈中以自变量形式建立了形参。函数B内部的其他自变量也是存放在栈中的。由于这些进栈操作，栈指针已经移到了所有局部变量之下。但是函数B记录了刚开始执行时的初始栈指针，以这个指针为参考，用正偏移量或负偏移量来访问栈中的变量。

当函数B准备返回时，系统会弹出栈中的所有自变量，这时栈指针移到了函数B刚开始执行时的位置。接着，函数B返回，系统从栈中弹出返回地址，函数A就可以继续执行了。

当函数A继续执行时，系统还能从栈中弹出调用者的实参，于是栈指针又回到了调用发生前的位置。

```c
//函数调用中的栈操作
#include<stdio.h>
void DisplayB(char* string)
{
	printf("%s\n", string);
}

void DisplayA(char* string)
{
	char String[20] = "Hello World!";
	printf("%s\n", string);
	DisplayB(String);
}

int main()
{
	char String[20] = "Love China!";
	DisplayA(String);
	return 0;
}
```

## 15.2 动态管理

### 15.2.1 malloc函数

malloc函数的功能是在内存中动态地分配一块size大小的内存空间。其原型如下：

```c
void* malloc(unsigned int size);
```

使用malloc函数，要包含stdlib.h头文件。malloc函数会返回一个指针，指向分配的内存空间。如果分配出现错误，则返回NULL。

使用malloc函数分配的内存空间位于堆中，而不是栈中。因此，在使用完这块内存之后，一定要将其释放掉，释放内存空间使用的是free函数。

例如，使用malloc函数分配一个整型内存空间：

```c
int* pInt;                     //定义指针
pInt=(int*)malloc(sizeof(int));//指针指向分配的int型空间
```

首先定义指针pInt，用来保存分配的内存地址。在使用malloc函数分配内存空间时，需要指定内存空间的大小(size)，这里调用sizeof函数就可以得到指定类型的大小。malloc函数成功分配内存空间后会返回一个指针，因为分配的是一个int型空间，所以返回指针时也应该使用对应的int型指针，这样就要进行强制类型转换。最后将函数返回的指针赋值给指针pInt，就可以保存动态分配的整型空间地址了。

```c
//使用动态分配空间存储演唱会人数
#include<stdio.h>
#include<stdlib.h>
int main()
{
	int* iIntMalloc;
	iIntMalloc = (int*)malloc(sizeof(int));
	*iIntMalloc = 10000;
	printf("现场有%d人\n", *iIntMalloc);
	free(iIntMalloc);
	return 0;
}
```

malloc函数不能忽略返回值。C语言规定，如果所申请的内存分配不成功，malloc函数的返回值为null pointer，也就是NULL。
在这种情况下，如果继续运行之后的代码，程序就会产生崩溃。所以在申请分配内存后，应及时检查内存分配是否成功。

### 15.2.2 calloc函数

calloc函数的功能是在内存中动态分配n个长度为size的连续内存空间。其原型如下：

```c
void* calloc (unsigned n, unsigned size);
```

使用calloc函数，也要包含头文件stdlib.h。calloc函数会返回一个指针，该指针指向动态分配的连续内存空间的首地址。当空间分配错误时，返回NULL。

例如，使用calloc函数分配一个整型数组内存空间：

```c
int pArray;//定义指针
pArray=(int*)calloc(3,sizeof(int));//指针指向分配的数组内存
/*
pArray为一个整型指针，使用calloc函数分配3个整型内存空间给一个数组，3表示分配数组中元素的个数，int表示元素的类型。
最后将返回的指针赋予pArray指针变量，pArray指向的就是该数组的首地址。
*/
```

```c
//动态分配数组内存
//在本实例中，动态分配一个指针。使用strcpy函数为字符数组赋值，再进行输出，以验证分配的内存是否正确保存了数据。
#define _CRT_SECURE_NO_WARNINGS
#include<stdlib.h>								     //包含头文件
#include<stdio.h>
#include<string.h>
int main()
{
	char* ch;									           //定义指针
	ch = (char*)calloc(30, sizeof(char));//分配一段字符数组内存
	strcpy(ch, "清华大学出版社");				 //复制字符串
	printf("%s\n", ch);							     //输出字符串
	free(ch);									           //释放空间
	return 0;
}
```

### 15.2.3 realloc函数

realloc函数的功能是将ptr指针指向的内存空间大小改为size。其原型如下：

```c
void* realloc(void* ptr, size_t size);
```

使用realloc的数前，要先包含头文件stdlib.h。size表示新分配的内存空间的大小，其值可以是任意的，既可以比原来的数值大，也可以比原来的数值小。返回值是一个指向新地址的指针，如果出现错误，则返回NULL。

例如，将分配的实型空间大小改为整型大小，代码如下：

```c
double* fDouble
fDouble=(double*)malloc(sizeof(double));	//定义实型指针,分配一个实型空间
iInt=realloc(fDouble,sizeof(int));			  //定义整型指针,将实型空间改为整形空间
/*
其中，fDouble指向分配的实型空间，之后使用realloc函数改变fDouble指向的空间大小，将其大小设置为整型，然后将
改变后的内存空间地址返回，赋值给iInt整型指针。
*/
```

```c
//重新分配内存
#include<stdio.h>
#include<stdlib.h>
int main()
{
	int* iInt;										                //定义整型指针
	char* cChar;									                //定义字符型指针
	iInt = (int*)malloc(sizeof(int));				      //使用malloc分配整型空间
	printf("整型数据内存是:%d\n", sizeof(*iInt)); //输出空间的大小
	cChar = realloc(iInt, sizeof(char));			    //使用realloc改变分配的空间大小
	printf("字符数据内存是:%d\n", sizeof(*cChar));	//输出空间的大小
	return 0;
}
```

函数malloc、calloc和realloc都可以动态分配空间，它们之间的区别在于：

malloc函数分配一块内存空间，且不进行初始化；

calloc函数分配连续多块大小相同的内存空间，且会将其初始化为零；

realloc函数主要用于调整内存空间的大小。

### 15.2.4 free函数

free函数的功能是释放指针ptr指向的内存区域，使该内存区域能被其他变量所使用。其原型如下：

```c
void free(void* ptr);
```

其中，ptr是最近一次调用calloc或malloc函数时返回的值。free函数无返回值。

例如，释放一个分配给整型变量的内存空间：

```c
free (pInt);
//代码中，pInt为一个指向整型大小的内存空间，使用free函数将其进行释放。
```

```c
//释放内存空间
#include<stdio.h>
#include<stdlib.h>
int main()
{
	int* pInt;								//定义整型指针
	pInt = (int*)malloc(sizeof(pInt));		//分配整型空间
	*pInt = 100;							//赋值
	printf("分配的值是:%d\n", *pInt);			//将值进行输出
	free(pInt);								//释放该内存空间
	printf("释放完内存的值是:%d\n", *pInt);//将值进行输出
	return 0;
}
```

## 15.3 内存泄漏与内存丢失

### 15.3.1 内存泄露

使用malloc等函数分配过内存后，还需要使用free函数及时释放内存。如果不进行释放，就会造成内存泄漏，甚至会导致系统崩溃。

free函数可以实时地执行回收内存操作。如果程序很简单，程序结束之前不会使用过多的内存，不会降低系统的性能，可以不用写free函数。程序结束后，操作系统会自动完成释放的功能。

但是在开发大型程序时，如果不及时通过free函数释放内存，后果是很严重的。例如，程序中可能要重复一万次分配10MB的内存，如果每次分配内存后都使用free函数及时释放用完的内存空间，那么整个程序只需要使用10MB内存就可以运行。
如果不使用free函数释放用完的内存空间，整个程序就要使用100GB的内存!这其中包括绝大部分的虚拟内存，由于虚拟内存的操作需要读写磁盘，所以会极大地影响到系统的性能，甚至导致系统崩溃。

因此，实际开发中，使用malloc函数分配内存后，应及时地写出一个free函数释放内存。这是一个良好的编程习惯，不但在处理大型程序时非常有必要，也在一定程度上体现了程序的优美和健壮性。

### 15.3.2 内存丢失

下面来看一个内存丢失的例子。例如：

```c
pOld= (int*)malloc(sizeof(int));
pNew= (int*)malloc(sizeof(int));
```

这两段代码创建了两块内存，并且将内存地址分别赋给了指针pOld和pNew，此时指针pOld和pNew分别指向两块内存。
如果接下来进行这样的操作：

```c
pOld=pNew ;
```

则pOld指针就指向了pNew指向的内存地址。这时再进行释放内存操作：

```c
free (pOld);
```

由于pOld所指向的内存空间是原来pNew指向的，于是这块空间被释放了。但是pOld原来指向的那块内存空间还没有被释放(因为没有指针指向这块内存)，这块内存就造成了丢失。

# 第16章 网络套接字编程

## 16.1 计算机网络基础

### 16.1.1 IP地址

为了使网络上的计算机能够彼此识别对方，每台计算机都被赋予了一个独一无二的IP地址。

IP地址是由IP协议规定的32位的二进制数表示，最新的IPv6协议已将IP地址升级为128位。

32位的IP地址主要分为前缀和后缀两部分。前缀表示计算机所属的物理网络，后缀用于确定该网络上的唯一一台计算机。

在互联网上，每一个物理网络都有唯一的网络号，根据网络号的不同，可以将IP地址分为5类，即A类、B类、C类、D类和E类。其中，A类、B类和C类属于基本类，D类用于多播发送，E类属于保留类。

| 类型 | 范围 |
| --- | --- |
| A类 | 0.0.0.0~127.255.255.255 |
| B类 | 128.0.0.0~191.255.255.255 |
| C类 | 192.0.0.0~223.255.255.255 |
| D类 | 224.0.0.0~239.255.255.255 |
| E类 | 240.0.0.0~247.255.255.255 |

有几个IP地址是特殊的，它们有单独的用途：

- 网络地址：主机地址为0的表示网络地址，如128.111.0.0。
- 广播地址：在网络号后跟所有位全是1的IP地址，表示广播地址。
- 回送地址：127.0.0.1表示回送地址，用于测试。

### 16.1.2 OSI七层参考模型

开放系统互联（Open System Interconnection，OSI）是国际标准化组织（ISO）为了实现计算机网络的标准化而颁布的参考模型。OSI参考模型将网络中的数据传输划分为7层，每一层使用下层的服务，并向上层提供服务。

| 层次 | 名称 | 功能描述 |
| --- | --- | --- |
| 第7层 | 应用层(Application) | 负责网络中应用程序与网络操作系统之间的联系。例如，建立和结束使用者之间的连接，管理建立相互连接使用的应用资源 |
| 第6层 | 表示层(Presentation) | 用于确定数据交换的格式，解决应用程序之间在数据格式上的差异，并负责设备之间需要的字符集和数据转换 |
| 第5层 | 会话层(Session) | 用户应用程序与网络层的接口，用于建立与其他设备的连接（即会话），并对会话进行有效的管理 |
| 第4层 | 传输层(Transport) | 提供会话层和网络层之间的传输服务，该服务从会话层获得数据，必要时对数据进行分割。然后将数据正确无误地传送到网络层。 |
| 第3层 | 网络层(Network) | 将传输的数据封包。然后通过路由选择、分段组合等控制，将信息从源设备传送到目标设备 |
| 第2层 | 数据链路层(Data Link) | 修正传输过程中的错误信号，能够提供可靠的通过物理介质传输数据的方法 |
| 第1层 | 物理层(Physical) | 利用传输介质为数据链路层提供物理连接，本层规范了网络硬件的特性、规格和传输速度 |

### 16.1.3 地址解析

所谓地址解析，是指将计算机的协议地址解析为物理地址，即MAC（Medium Access Control）地址，又称为媒体访问控制地址。

通常，在网络上由地址解析协议（ARP）来实现地址解析。

下面以本地网络上的两台计算机通信为例，介绍ARP协议解析地址的过程。

假设主机A和主机B处于同一个物理网络上，主机A的IP地址为192.168.1.21，主机B的IP地址为192.168.1.23，当主机A与主机B通信时，主机B的IP地址192.168.1.23将按如下步骤解析为物理地址。

1. 主机A从本地ARP缓存中查找IP地址192.168.1.23对应的物理地址。用户可以在命令行窗口中输入“`arp -a`”命令查看本地ARP缓存。
   
    ![Untitled](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//12.png)
    
2. 如果主机A在ARP缓存中没有发现192.168.1.23映射的物理地址，将发送ARP请求帧到本地网络上的所有主机。在ARP请求帧中包含了主机A的物理地址和IP地址。
3. 本地网络上的其他主机接收到ARP请求帧后，检查是否与自己的IP地址匹配，如果不匹配，则丢弃ARP请求帧。如果主机B发现与自己的IP地址匹配，则将主机A的物理地址和IP地址添加到自己的ARP缓存中，然后主机B将自己的物理地址和IP地址发送给主机A，当主机A接收到主机B发来的信息后，将用这些信息更新ARP缓存。
4. 主机B的物理地址确定后，主机A就可以与主机B通信了。

### 16.1.4 域名解析

在Internet上存在许多计算机，为了防止主机名相同，Internet管理机构采取在主机名后加后缀名的方法标识一台主机，该后缀名被称为域名。

例如www.mingrisoft.com，主机名为www，域名为mingrisoft.com。

这里的域名为二级域名，其中com为一级域名，表示商业组织，mingrisoft为本地域名。

为了能够利用域名进行不同主机间的通信，需要将域名解析为IP地址，称之为域名解析。

域名解析是通过域名服务器来完成的。

假如主机A的本地域名服务器是dns.local.com，根域名服务器是dns.mr.com；所要访问的主机B的域名为www.mingribook.com，域名服务器为dns.mrbook.com。

1. 当主机A通过域名www.mingribook.com访问主机B时，将发送解析域名www.mingribook.com的报文，本地域名服务器收到请求后，首先查询本地缓存，如果没有该记录，则向根域名服务器dns.mr.com发出请求，要求解析域名www.mingribook.com。
2. 根域名服务器dns.mr.com收到请求后查询本地记录，如果发现mingribook.com NS dns.mrbook.com信息，将给出dns.mrbook.com的IP地址，并将结果返回给主机A的本地域名服务器dns.local.com.
3. 当本地域名服务器dns.local.com收到信息后，会向主机B的域名服务器dns.mrbook.com发送解析域名www.mingribook.com的报文。
4. 域名服务器dns.mrbook.com收到请求后，开始查询本地的记录，发现www.mingribook.com A 211.120.X.X类似的信息，将结果返回给主机A的本地域名服务器dns.local.com，其中211.120.X.X表示域名www.mingribook.com的IP地址。

### 16.1.5 TCP/IP协议

TCP/IP（Transmission Control Protocal/Internet Protocal，传输控制协议/网际协议）是互联网上最流行的协议，它能够实现互联网上不同类型操作系统的计算机相互通信。对于网络开发人员，必须了解TCP/IP协议的结构。TCP/IP协议将网络分为4层，分别对应于OSI参考模型的7层结构。表16.3列出了TCP/IP协议与OSI参考模型的对应关系。

| TCP/IP协议 | OSI参考模型 |
| --- | --- |
| 应用层(包括Telnet、FTP、SNTP协议) | 会话层、表示层和应用层 |
| 传输层(包括TCP、UDP协议) | 传输层 |
| 网络层(包括ICMP、IP、APR等协议) | 网络层 |
| 数据链路层 | 物理层和数据链路层 |

由上表可以发现，TCP/IP不是单个协议，而是一个协议簇，包含多种协议，其中最主要的协议是网际协议（IP）和传输控制协议（TCP）。

下面给出TCP/IP中一些主要的协议结构。

**1. TCP协议**

传输控制协议（TCP）是一种提供可靠数据传输的通用协议，它是TCP/IP体系结构中传输层上的协议。在发送数据时，应用层的数据传输到传输层，加上TCP的首部，数据就构成了报文。报文是网际层IP的数据，如果再加上IP首部，就构成了IP数据报。

TCP协议的C语言数据描述如下：

```c
typedef struct HeadTCP{
	WORD SourcePort;  //16位源端口号
	WORD DePort;      //16位目的端口号
	DWORD SequenceNo; //32位序号
	DWORD ConfirmNo;  //32位确认序号
	BYTE HeadLen;     //与Flag为一个组成部分，首部长4位，保留6位，6位标识，共16位
	BYTE Flag;
	WORD WndSize;     //16位窗口大小
	WORD CheckSum;    //16位校验和
	WORD UrgPtr;      //16位紧急指针
}HEADTCP;
```

**2. IP协议**

IP协议又称为网际协议，它工作在网络层，主要提供无链接数据报传输。IP协议不保证数据报的发送，但可以最大限度地发送数据。

IP协议的C语言数据描述如下：

```c
typedef struct HeadIP{
	unsigned char headerlen:4;  //首部长度，占4位
	unsigned char version:4;    //版本，占4位
	unsigned char servertype;   //服务类型，占8位，即1个字节
	unsigned short totallen;    //总长度，占16位
	unsigned short id;          //与idoff构成标识符，共占16位，前3位是标识，后13位是片偏移
	unsigned short idoff;
	unsigned char ttl;          //生存时间，占8位
	unsigned char proto;        //协议，占8位
	unsigned short checksum;    //首部检验和，占16位
	unsigned int sourceIP;      //源IP地址，占32位
	unsigned int destIP;        //目的IP地址，占32位
}HEADIP;
```

**3. ICMP协议**

ICMP协议又称为网际控制报文协议。它负责网络上设备状态的发送和报文检查，可以将某个设备的故障信息发送到其他设备上。

ICMP协议的C语言数据描述如下：

```c
typedef struct HeadICMP{
	BYTE Type;  //8位类型
	BYTE Code;  //8位代码
	WORD ChkSum;//16位校验和
}HEADICMP;

```

**4. UDP协议**

用户数据报协议（UDP）是一个面向无连接的协议，采用该协议，两个应用程序不需要先建立连接。它为应用程序提供一次性的数据传输服务。UDP协议不提供差错恢复，不能提供数据重传，因此该协议传输数据安全性略差。

UDP协议的C语言数据描述如下：

```c
typedef struct HeadUDP
{
	WORD SourcePort;//16位源端口号
	WORD DePort;    //16位目的端口号
	WORD Len;       //16位UDP长度
	WORD ChkSum;    //16位UDP校验和
}HEADUDP;
```

### 16.1.6 端口

虽然计算机可通过IP地址来标识自己，但两台计算机具体通信时，还会出现一个问题。假设主机A中的应用程序A1想与主机B中的应用程序B1通信，如何知道是主机A中的A1应用程序而不是其他应用程序与主机B中的应用程序通信呢？当主机B接收到数据时，它又该如何知道数据是发往应用程序B1（此时主机B中可能同时运行着多个应用程序）的呢?

为了解决上述问题，TCP/IP协议提出了“端口”的概念，用于标识具体通信的应用程序。当应用程序（严格说应该是进程）与某个端口绑定后，系统会将收到的给该端口的数据送往该应用程序。端口通常用一个16位的无符号整数值来表示，范围为0~65535，低于256的端口系统保留端口，用于系统进程的通信，其他端口则是自由端口，可以由进程自由使用。

### 16.1.7 套接字的引入

美国伯克利大学在UNIX上推出了一种应用程序访问通信协议的操作系统调用套接字（socket） 。socket的出现，使得程序员可以很方便地访问TCP/IP，进而开发各种网络应用程序。后来，套接字被引入Windows操作系统，成为网络应用程序开发的有效工具。

套接字存在于通信区域中，通信区域也称为地址族，主要用于将通过套接字通信的进程的公有特性综合在一起。套接字通常只与同一区域的套接字交换数据。Windows Sockets只支持一个通信区域——AF_INET网际域，使用网际协议族通信的进程使用该域。

### 16.1.8 网络字节顺序

不同的计算机存放多字节值的顺序不同，有的机器在起始地址存放低位字节，有的机器在起始地址存放高位字节。例如，基于Intel CPU的PC机采用低位先存的方式。

由于不同的计算机存放数据字节的顺序不同，因此发送数据后再接收该数据时，有可能无法查看所接收到的数据。为了保证数据的正确性，在网络协议中需要指定网络字节顺序，TCP/IP协议使用16位整数和32位整数的高位先存格式。

## 16.2 套接字基础

套接字是网络通信的基本构件，最初是加利福尼亚大学伯克利分校为UNIX开发的网络通信编程接口。为了在Windows操作系统上使用套接字，20世纪90年代初，微软和第三方厂商共同制定了一套标准，即Windows Socket规范，简称WinSock。

### 16.2.1 套接字概述

所谓套接字，实际上是一个指向传输提供者的句柄。在WinSock中，就是通过操作该句柄来实现网络通信和管理的。

根据性质和作用的不同，套接字可以分为原始套接字、流式套接字和数据包套接字3种。

- 原始套接字：是在WinSock 2规范中提出的，它能够使程序开发人员对底层的网络传输机制进行控制，在原始套接字下接收的数据中包含IP头。
- 流式套接字：提供双向、有序、可靠的数据传输服务。该类型套接字在通信前需要双方建立连接，大家熟悉的TCP协议采用的就是流式套接字。
- 数据包套接字：提供双向的数据流，但不能保证数据传输的可靠性、有序性和无重复性。UDP协议采用的就是数据包套接字。

### 16.2.2 TCP套接字的socket编程

TCP是面向连接的可靠的传输协议。利用TCP协议进行通信时，首先要建立通信双方的连接。一旦连接建立完成，就可以进行通信。TCP提供了数据确认和数据重传的机制，保证了发送的数据一定能到达通信的对方。

基于TCP，面向连接的socket编程的**服务器端**程序流程如下：

1. 创建套接字socket。
2. 将创建的套接字绑定（bind）到本地的地址和端口上。
3. 设置套接字的状态为监听状态（listen），准备接受客户端的连接请求。
4. 接受请求（accept） ，同时返回得到一个用于连接的新套接字。
5. 使用这个新套接字进行通信（通信函数使用send/recv）。
6. 通信完毕，释放套接字资源（closesocket）。

基于TCP，面向连接的socket编程的**客户端**程序流程如下：

1. 创建套接字socket。
2. 向服务器发出连接请求（connect） 。
3. 连接后，与服务器进行通信操作（send/recv） 。
4. 释放套接字资源（closesocket）。

在服务器端，当调用accept函数时，程序就会进行等待，直到有客户端调用connect函数发送连接请求，然后服务器接受该请求，这样服务器端与客户端就建立了连接，可以开始通信了。

在服务器端要建立套接字绑定到指定的主机IP和端口上等待客户的请求，但是对于客户端来说，当发起连接请求并被接受后，在服务器端就保存了该客户端的IP地址和端口号的信息。对于服务器端来说，一旦建立连接，实际上它已经保存了客户端的IP地址和端口号的信息，因此可以利用返回的套接字进行与客户端的通信。

### 16.2.3 UDP套接字的socket编程

UDP是无连接的不可靠的传输协议。采用UDP进行通信时，不需要建立连接，可以直接向一个IP地址发送数据，但是不能保证对方能收到。

对于基于UDP，面向无连接的套接字编程来说，服务器端和客户端的概念不是特别的严格。可以把服务器称为接收端，客户端就是发送数据的发送端。

基于UDP，面向无连接的socket编程的**接收端**程序流程如下。

1. 创建套接字socket。
2. 将套接字绑定（bind）到一个本地地址和端口上。
3. 等待接收数据（recvfrom） 。
4. 释放套接字资源（closesocket） 。

基于UDP，面向无连接的socket编程的**发送端**程序流程如下。

1. 创建套接字socket。
2. 向服务器发送数据（sendto） 。
3. 释放套接字资源（closesocket） 。

基于UDP的套接字编程中，仍然需要使用bind进行绑定。虽然面向无连接的socket编程无须建立连接，但为了完成通信，首先应启动接收端，等待接收发送端发来的数据，这样接收端就必须告诉它自己的地址和端口。因此，必须调用bind函数将套接字绑定到一个本地地址和端口上。

基于UDP的套接字编程时，利用的是sendto和recvfrom两个函数实现数据的发送和接收；基于TCP的套接字编程时，发送数据使用的是send函数，接收数据使用的是recv函数。

## 16.3 套接字函数

### 16.3.1 套接字常用函数介绍

**1. WSAStartup函数**

WSAStartup函数的功能是初始化套接字库。其原型如下：

```c
int WSAStartup(WORD wVersionRequested, LPWSADATA lpWSAData);
```

- WSAStartup函数用于初始化Ws2_32.dIl动态链接库。在使用其他套接字函数之前，必须先初始化Ws2_32.dll动态链接库。
- wVersionRequested：表示调用者使用的WinSock版本，高字节记录修订版本，低字节记录主版本。例如，如果WinSock的版本为2.1，则高字节记录1，低字节记录2。
- lpWSAData：WSADATA结构指针，详细记录了Windows套接字的相关信息。其定义如下：

```c
typedef struct  WSAData{
	WORD wVersion;
	WORD wHighVersion;
	char szDescription[WSADESCRIPTION_LEN+1];
	char szSystemStatus[WSASYS_STATUS_LEN+1];
	unsigned short iMaxSockets;
	unsigned short iMaxUdpDg;
	char FAR* lpVendorInfo;
}WSADATA,FAR* LPWSADATA;
```

- wVersion：表示调用者使用的WS2_32.dll动态库的版本号。
- wHighVersion：表示WS2_32.dll支持的最高版本，通常与wVersion相同。
- szDescription：表示套接字的描述信息，通常没有实际意义。
- szSystemStatus：表示系统的配置或状态信息，通常没有实际意义。
- iMaxSockets：表示最多可以打开多少个套接字。在WinSock 2及以后的版本中，该成员将被忽略。
- iMaxUdpDg：表示数据报的最大长度。在WinSock 2及以后的版本中，该成员将被忽略。
- lpVendorInfo：表示套接字的厂商信息。在WinSock 2及以后的版本中，该成员将被忽略。

例如，使用WSAStartup初始化套接字，版本号为2.2：

```c
WORD wVersionRequested;//WORD(字)，类型为unsigned short
WSADATA WSAData;//库版本信息结构
//定义版本类型，将两个字节组合成一个字，前面是低字节，后面是高字节
wVersionRequested=MAKEWORD(2,2);//表示版本号
//加载套接字库，初始化Ws2_32.dll动态链接库
WSAStartup(wVersionRequested,&wsaData)
```

从上面的代码中可以看出，MAKEWORD宏的作用是：根据给定的两个无符号字节，创建一个16位的无符号整型，将创建的值赋予wVersionRequested变量，表示套接字的版本号。

**2. socket函数**

socket函数的功能是创建一个套接字。其原型如下：

```c
SOCKET socket(int af,int type,int protocol)
```

- af：表示一个地址家族，通常为AF_INET。
- type：表示套接字类型。
    - 如果为SOCK_STREAM，表示创建面向连接的流式套接字；
    - 如果为SOCK_DGRAM，表示创建面向无连接的数据报套接字；
    - 如果为SOCK_RAW，表示创建原始套接字。
    
    对于这些值，用户可以在winsock2.h头文件中找到。
    
- protocol：表示套接字采用的协议，如果用户不指定，可以设置为0。
- 返回值：创建的套接字句柄。

例如，使用socket函数创建一个套接字socket_server：

```c
//创建服务器套接字
//AF_INET表示指定地址族，SOCK_STREAM表示流式套接字TCP，特定的地址家族相关的协议
socket_server=socket(AF_INET,SOCK_STREAM,0);
```

在上面代码中，如果socket函数调用成功，就会返回一个新的SOCKET数据类型的套接字描述符。使用定义好的套接字socket_server进行保存。

**3. bind函数**

bind函数的功能是将套接字绑定到指定的端口和地址上。其原型如下：

```c
int bind(SOCKET s,const struct sockaddr FAR* name,int namelen);
```

- s：套接字标识。
- name：sockaddr结构指针，包含了要结合的地址和端口号。
- namelen：表示name缓冲区的长度。
- 返回值：如果函数执行成功，则返回值为0，否则为SOCKET_ERROR。

在创建了套接字后，应该将该套接字绑定到本地的某个地址和端口上，这时就需要使用bind函数了。例如，使用bind函数绑定一个套接字：

```c
SOCKADDR_IN Server_add;//服务器地址信息结构
Server_add.sin_family=AF_INET;//地址族，必须是AF_INET，注意只有它不是网络字节顺序
Server_add.sin_addr.S_un.S_addr=htonl(INADDR_ANY);//主机地址
Server_add.sin_port=htons(5000);//端口号
bind(socket_server,(SOCKADDR*)&Server_add,sizeof(SOCKADDR));//使用bind函数进行绑定
```

**4. listen函数**

listen函数的功能是将套接字设置为监听模式。对于流式套接字，必须处于监听模式才能够接收客户端套接字的连接。该函数的原型如下：

```c
int listen(SOCKET s,int backlog);
```

- s：套接字标识。
- backlog：表示等待连接的最大队列长度。例如，如果backlog被设置为2，此时有3个客户端同时发出连接请求，那么前两个客户端连接会放置在等待队列中，第3个客户端会得到错误信息。

例如，使用listen函数设置套接字为监听状态：

```c
listen(socket_server,5);
```

上述代码中，设置套接字为监听状态，为连接做准备，最大等待的数目为5。

**5. accept函数**

accept函数的功能是接受客户端的连接。在流式套接字中，只有当套接字处于监听状态时，才能接受客户端的连接。该函数的原型如下：

```c
SOCKET accept(SOCKET s,struct sockaddr FAR* addr,int FAR* addrlen);
```

- s：套接字标识，它应处于监听状态。
- addr：sockaddr_in结构指针，包含一组客户端的端口号、IP地址等信息。
- addrlen：用于接收参数addr的长度。
- 返回值：一个新的套接字，对应于已经接受的客户端连接。对于该客户端的所有后续操作，都应使用这个新的套接字。

例如，使用accept函数接受客户端的连接请求，代码如下：

```c
//接受客户端的发送请求，等待客户端发送connect请求
socket_receive=accept(socket_server,(SOCKADDR*)&Client_add,&Length);
```

其中，socket_receive用于保存接受请求后返回的新的套接字，socket_server为绑定在地址和端口上的套接字，而Client_add是有关客户端的IP地址和端口的信息结构，最后的Length是Client_add的大小(可以使用sizeof函数取得，然后用Length变量保存)。

**6. closesocket函数**

closesocket函数的功能是关闭套接字。其原型如下：

```c
int closesocket(SOCKET s);
```

其中，s是套接字标识。如果参数s设置了SO_DONTLINGER选项，则调用该函数后会立即返回。此时如果有数据尚未传送完毕，则会继续传递数据，然后再关闭套接字。

例如，使用closesocket函数关闭套接字，释放客户端的套接字资源，代码如下：

```c
closesocket(socket_receive);//释放客户端的套接字资源
```

在代码中，socket_receive是一个套接字，当不使用时就可以利用closesocket函数将其资源释放。

**7. connect函数**

connect函数的功能是发送一个连接请求。其原型如下：

```c
int connect(SOCKET s,const struct sockaddr FAR* name,int namelen);
```

- s：套接字标识。
- name：表示套接字s要连接的主机地址和端口号。namelen:表示name缓冲区的长度。
- 返回值：如果函数执行成功，则返回值为0，否则为sOCKET_ERROR。用户可以通过WSAGETLASTERROR得到其错误描述。

例如，使用connect函数与一个套接字建立连接，代码如下：

```c
connect(socket_send,(SOCKADDR*)&Server_add,sizeof(SOCKADDR));
```

在上面代码中，socket_send表示要与服务器建立连接的套接字，而Server_add是要连接的服务器地址信息。

**8. htons函数**

htons函数的功能是将一个16位的无符号短整型数据从主机排列方式转换为网络排列方式。其原型如下：

```c
u_short htons(u_short hostshort);
```

- hostshort：主机排列方式的16位无符号短整型数据。
- 返回值：网络排列方式的16位无符号短整型数据。

例如，使用htons函数对一个无符号短整型数据进行转换，代码如下：

```c
Server_add.sin_port=htons(5000);
```

在上面代码中，Sever_add是有关主机地址和端口的结构，其中sin_port表示的是端口号。因为端口号要使用网络排列方式，所以使用htons函数进行转换，设定新的端口号。

**9. htonl函数**

htonl函数的功能是将一个无符号长整型数据从主机排列方式转换为网络排列方式。其原型如下：

```c
u_long htonl(u_long hostlong);
```

- hostlong：主机排列方式的32位无符号长整型数据。
- 返回值：网络排列方式的32位无符号长整型数据。

其使用方式与htons函数相似，不过是将一个32位数值转换为TCP/IP网络字节顺序。

**10. inet_addr函数**

inet_addr函数的功能是将一个由点分十进制表示的IP地址字符串转换为32位的无符号长整型数据。其原型如下：

```c
unsigned long inet_addr(const char FAR* cp);
```

- cp：表示IP地址的字符串。
- 返回值：32位无符号长整型数据。

例如，使用inet_addr函数将一个以点分十进制格式表示的IP地址192.168.1.43转换为32位的无符号长整型数据，代码如下：

```c
erver_add.sin_addr.S_un.S_addr=inet_addr("192.168.1.43");
```

**11. recv函数**

recv函数的功能是从面向连接的套接字中接收数据。其原型如下：

```c
int recv(SOCKET s,char FAR* buf,int len,int flags);
```

- s：套接字标识。
- buf：表示接收数据的缓冲区。
- len:表示buf的长度。
- flags：表示函数的调用方式。如果为MSG_PEEK，表示查看传来的数据，在序列前端的数据会被复制一份到返回缓冲区中，但是这个数据不会从序列中移走;如果为MSG_OOB，表示处理Out-Of-Band数据，也就是外带数据。

例如，使用recv函数接收数据，代码如下：

```c
recv(socket_send,Receivebuf,100,0);
```

其中，socket_send是用于连接的套接字，Receivebuf是用来接收保存数据的空间，100是该空间的大小。

**12. send函数**

send函数用于在面向连接方式的套接字间发送数据。其原型如下：

```c
int send(SOCKET s,const char FAR* buf,int len,int flags);
```

- s：套接字标识。
- buf：表示存放要发送数据的缓冲区。
- len：表示缓冲区长度。
- flags：表示函数的调用方式。

例如，使用send函数发送数据，代码如下：

```c
send(socket_receive,Sendbuf,100,0);
```

在上面代码中，socket_receive用于连接的套接字，而Sendbuf保存要发送的数据，100为该数据的大小。

**13. recvfrom函数**

recvfrom函数用于接收一个数据报信息并保存源地址。其原型如下：

```c
int recvfrom(SOCKET s,char FAR* buf,int len,int flags,struct sockaddr FAR* from,int FAR* fromlen);
```

- s：表示准备接收数据的套接字。
- buf：指向缓冲区的指针，用来接收数据。len:表示缓冲区的长度。
- flags：表示函数的调用方式。
- from：一个指向地址结构的指针，用来接收发送数据方的地址信息。
- fromlen：表示缓冲区的长度。

**14. sendto函数**

sendto函数用于向一个特定的目的方发送数据。其原型如下：

```c
int sendto(SOCKET s,const char FAR* buf,int len,int flags,const struct sockaddr FAR* to,int tolen);
```

- s：套接字标识符（可能已经建立连接）。
- buf：指向缓冲区的指针，该缓冲区包含将要发送的数据。
- len：表示缓冲区的长度。
flags：表示函数的调用方式。
- to：指定目标套接字的地址。
- tolen：表示缓冲区的长度。

**15. WSACleanup函数**

WSACleanup函数用于释放为Ws2_32.dll动态链接库初始化时分配的资源。其原型如下：

```c
int WSACleanup(void);
```

例如，使用该函数可关闭动态链接库，代码如下：

```c
WSACleanup();//关闭动态链接库
```

### 16.3.2 基于TCP的网络聊天程序

```c
//网络聊天服务器端的程序
//本实例将实现一个基于TCP的网络聊天程序，根据有关TCP套接字socket编程中服务器的设计过程，编写下面的代码。
#include<stdio.h>
#include<winsock.h>							/*引入winsock头文件*/

int main(){
	/*------------------------------------------------------------------*/
	/*---------------------定义变量---------------------------------*/
	/*------------------------------------------------------------------*/
	char Sendbuf[100];							/*发送数据的缓冲区*/
	char Receivebuf[100];						/*接收数据的缓冲区*/
	int SendLen;								/*发送数据的长度*/
	int ReceiveLen;								/*接收数据的长度*/
	int Length;								/*表示SOCKADDR的大小*/

	SOCKET socket_server;						/*定义服务器套接字*/
	SOCKET socket_receive;  					/*定义用于连接套接字*/

	SOCKADDR_IN Server_add;					/*服务器地址信息结构*/
	SOCKADDR_IN Client_add;					/*客户端地址信息结构*/

	WORD wVersionRequested;					/*字（word）：unsigned short*/
	WSADATA wsaData;						/*库版本信息结构*/
	int error;									/*表示错误*/

	/*------------------------------------------------------------------*/
	/*--------------------初始化套接字库-------------------------*/
	/*------------------------------------------------------------------*/
	/*定义版本类型。将两个字节组合成一个字，前面是低字节，后面是高字节*/
	wVersionRequested = MAKEWORD(2, 2);	
	/*加载套接字库，初始化Ws2_32.dll动态链接库*/
	error = WSAStartup(wVersionRequested, &wsaData);	
	if(error!=0)
	{
		printf("加载套接字失败！");
		return 0;								/*程序结束*/
	}
	/*判断请求加载的版本号是否符合要求*/
	if(LOBYTE(wsaData.wVersion) != 2 ||
		   HIBYTE(wsaData.wVersion) != 2) 
	{	
		WSACleanup();							/*不符合，关闭套接字库*/
		return 0;								/*程序结束*/
	}

	/*------------------------------------------------------------------*/
	/*-------------------设置连接地址-----------------------------*/
	/*------------------------------------------------------------------*/
	Server_add.sin_family=AF_INET;/*地址家族，必须是AF_INET，注意只有它不是网络字节顺序*/
	Server_add.sin_addr.S_un.S_addr=htonl(INADDR_ANY);/*主机地址*/
	Server_add.sin_port=htons(5000);/*端口号*/

	/*-------------------创建套接字--------------------------------*/
	/*AF_INET表示指定地址族，SOCK_STREAM表示流式套接字TCP，特定的地址家族相关的协议*/
	socket_server=socket(AF_INET,SOCK_STREAM,0);

	/*------------------------------------------------------------------*/
	/*---绑定套接字到本地的某个地址和端口上----*/
	/*------------------------------------------------------------------*/
			/*socket_server为套接字，(SOCKADDR*)&Server_add为服务器地址*/
	if(bind(socket_server,(SOCKADDR*)&Server_add,sizeof(SOCKADDR))==SOCKET_ERROR)
	{
		printf("绑定失败\n");
	}

	/*------------------------------------------------------------------*/
	/*--------------------设置套接字为监听状态----------------*/
	/*------------------------------------------------------------------*/
		/*监听状态，为连接做准备，最大等待的数目为5*/
	if(listen(socket_server,5)<0)
	{
		printf("监听失败\n");
	}
	
	/*------------------------------------------------------------------*/
	/*----------------------接受连接--------------------------------*/
	/*------------------------------------------------------------------*/
	Length=sizeof(SOCKADDR);
	/*接受客户端的发送请求，等待客户端发送connect请求*/
	socket_receive=accept(socket_server,(SOCKADDR*)&Client_add,&Length);
	if(socket_receive==SOCKET_ERROR)
	{
		printf("接受连接失败");
	}

	/*------------------------------------------------------------------*/
	/*-------------------进行聊天-----------------------------------*/
	/*------------------------------------------------------------------*/
	while(1)								/*无限循环*/
	{	
		/*-------------------接收数据-----------------------------------*/
		ReceiveLen =recv(socket_receive,Receivebuf,100,0);
		if(ReceiveLen<0)
		{
			printf("接收失败\n");
			printf("程序退出\n");
			break;
		}
		else
		{
			printf("client say: %s\n",Receivebuf);
		}	
		
		/*-------------------发送数据-----------------------------------*/
		printf("please enter message:");
		scanf("%s",Sendbuf);
		SendLen=send(socket_receive,Sendbuf,100,0);
		if(SendLen<0)
		{
			printf("发送失败\n");
		}
	}

	/*------------------------------------------------------------------*/
	/*--------------------释放套接字，关闭动态库-------------*/
	/*------------------------------------------------------------------*/
	closesocket(socket_receive);				/*释放客户端的套接字资源*/
	closesocket(socket_server);				/*释放套接字资源*/
	WSACleanup();							/*关闭动态链接库*/
	return 0;
}

//运行程序之前，要先添加相应的库文件ws2_32.lib
```

```c
//网络聊天客户端的程序
//根据有关TCP套接字socket编程中的客户端设计过程，编写下面的代码：
#include<stdio.h>
#include<winsock.h>								/*引入winsock头文件*/

int main()
{
	/*------------------------------------------------------------------*/
	/*----------------------定义变量--------------------------------*/
	/*------------------------------------------------------------------*/
	char Sendbuf[100];							/*发送数据的缓冲区*/
	char Receivebuf[100];						/*接收数据的缓冲区*/
	int SendLen;								/*发送数据的长度*/
	int ReceiveLen;								/*接收数据的长度*/

	SOCKET socket_send;						/*定义套接字*/
	SOCKADDR_IN Server_add;					/*服务器地址信息结构*/

	WORD wVersionRequested;					/*字（word）：unsigned short*/
	WSADATA wsaData;						/*库版本信息结构*/
	int error;									/*表示错误*/

	/*------------------------------------------------------------------*/
	/*---------------------初始化套接字库------------------------*/
	/*------------------------------------------------------------------*/
				/*定义版本类型。将两个字节组合成一个字，前面是低字节，后面是高字节*/
	wVersionRequested = MAKEWORD(2, 2);	
				/*加载套接字库，初始化Ws2_32.dll动态链接库*/
	error = WSAStartup(wVersionRequested, &wsaData);	
	if(error!=0)
	{
		printf("加载套接字失败！");
		return 0;								/*程序结束*/
	}
				/*判断请求加载的版本号是否符合要求*/
	if(LOBYTE(wsaData.wVersion) != 2 ||
		   HIBYTE(wsaData.wVersion) != 2) 
	{	
		WSACleanup();							/*不符合，关闭套接字库*/
		return 0;								/*程序结束*/
	}

	/*------------------------------------------------------------------*/
	/*----------------------设置服务器地址-----------------------*/
	/*------------------------------------------------------------------*/
	Server_add.sin_family=AF_INET;/*地址家族，必须是AF_INET，注意只有它不是网络字节顺序*/
	/*服务器的地址，将一个点分十进制表示为IP地址，inet_ntoa是将地址转换成字符串*/
	Server_add.sin_addr.S_un.S_addr = inet_addr("192.168.1.43");
	Server_add.sin_port=htons(5000);/*端口号*/

	/*------------------------------------------------------------------*/
	/*-----------------------进行连接服务器----------------------*/
	/*------------------------------------------------------------------*/
	/*客户端创建套接字，但是不需要绑定，只需要和服务器建立起连接即可*/
	/*socket_sendr表示的是套接字，Server_add是服务器的地址结构*/
	socket_send=socket(AF_INET,SOCK_STREAM,0);

	/*------------------------------------------------------------------*/
	/*----------------------创建用于连接的套接字--------------*/
	/*------------------------------------------------------------------*/
	/*AF_INET表示指定地址族，SOCK_STREAM表示流式套接字TCP，特定的地址家族相关的协议*/
	if(connect(socket_send,(SOCKADDR*)&Server_add,sizeof(SOCKADDR)) == SOCKET_ERROR)
	{
		printf("连接失败!\n");
	}
	
	/*------------------------------------------------------------------*/
	/*----------------------进行聊天--------------------------------*/
	/*------------------------------------------------------------------*/
	while(1)											/*无限循环*/
	{	
		/*---------------发送数据过程---------------*/
		printf("please enter message:");
		scanf("%s",Sendbuf);
		SendLen = send(socket_send,Sendbuf,100,0);			/*发送数据*/
		if(SendLen < 0)
		{
			printf("发送失败!\n");
		}

		/*--------------接收数据过程-----------------*/
		ReceiveLen =recv(socket_send,Receivebuf,100,0);		/*接收数据*/
		if(ReceiveLen<0)
		{
			printf("接收失败\n");
			printf("程序退出\n");
			break;									/*跳出循环*/
		}
		else
		{
			printf("Server say: %s\n",Receivebuf);
		}	
	}

	/*------------------------------------------------------------------*/
	/*-----------------------释放套接字，关闭动态库----------*/
	/*------------------------------------------------------------------*/
	closesocket(socket_send);							/*释放套接字资源*/
	WSACleanup();										/*关闭动态链接库*/
	return 0;
}
```

要实现网络通信，一定先运行服务器端，再运行客户端。注意，在客户端输入lP地址时，计划与哪台计算机通信，就输入哪台计算机的IP地址。

### 16.3.3 基于UDP的网络聊天程序

```c
//网络聊天服务器端的程序
#include<stdio.h>
#include<winsock.h>							/*引入winsock头文件*/

int  main()
{
	/*------------------------------------------------------------------*/
	/*----------------------定义变量--------------------------------*/
	/*------------------------------------------------------------------*/
	char Receivebuf[100];					/*接受数据的缓冲区*/
	int length;

	SOCKET socket_send;					/*定义套接字*/
	SOCKADDR_IN Server_add;				/*服务器地址信息结构*/
	SOCKADDR_IN Client_add;				/*客户端地址信息结构*/

	WORD wVersionRequested;				/*字（word）：unsigned short*/
	WSADATA wsaData;					/*库版本信息结构*/
	int error;							/*表示错误*/

	/*------------------------------------------------------------------*/
	/*-------------------------初始化套接字库---------------------------*/
	/*------------------------------------------------------------------*/
				/*定义版本类型。将两个字节组合成一个字，前面是第字节，后面是高字节*/
	wVersionRequested = MAKEWORD( 2, 2 );	
				/*加载套接字库，初始化Ws2_32.dll动态链接库*/
	error = WSAStartup( wVersionRequested, &wsaData);	
	if(error!=0)
	{
		printf("加载套接字失败！");
		return 0;							/*程序结束*/
	}
				/*判断请求加载的版本号是否符合要求*/
	if ( LOBYTE( wsaData.wVersion ) != 2 ||
		   HIBYTE( wsaData.wVersion ) != 2 ) 
	{	
		WSACleanup( );					/*不符合，关闭套接字库*/
		return 0;							/*程序结束*/
	}

	/*创建套接字*/
	socket_send=socket(AF_INET,SOCK_DGRAM,0);

	/*----------------------设置服务器地址-----------------------*/
	Server_add.sin_family=AF_INET;/*地址家族，对于必须是AF_INET，注意只有它不是网络网络字节顺序*/
	Server_add.sin_addr.S_un.S_addr = htonl(INADDR_ANY);
	Server_add.sin_port=htons(5000);/*端口号*/

	/*绑定套接字*/
	bind(socket_send,(SOCKADDR*)&Server_add,sizeof(SOCKADDR));
	
	length=sizeof(SOCKADDR);

	recvfrom(socket_send,Receivebuf,100,0,(SOCKADDR*)&Client_add,&length);
	
	printf("%s\n",Receivebuf);

	/*------------------------------------------------------------------*/
	/*-----------------------释放套接字，关闭动态库----------*/
	/*------------------------------------------------------------------*/
	closesocket(socket_send);				/*释放套接字资源*/
	WSACleanup();							/*关闭动态链接库*/
	return 0;
}
```

```c
//网络聊天客户端的程序
#include<stdio.h>
#include<winsock.h>							/*引入winsock头文件*/

int  main()
{
	/*------------------------------------------------------------------*/
	/*----------------------定义变量--------------------------------*/
	/*------------------------------------------------------------------*/
	SOCKET socket_client;				/*定义套接字*/
	SOCKADDR_IN Server_add;				/*服务器地址信息结构*/

	WORD wVersionRequested;				/*字（word）：unsigned short*/
	WSADATA wsaData;					/*库版本信息结构*/
	int error;							/*表示错误*/

	/*------------------------------------------------------------------*/
	/*-------------------------初始化套接字库---------------------------*/
	/*------------------------------------------------------------------*/
				/*定义版本类型。将两个字节组合成一个字，前面是第字节，后面是高字节*/
	wVersionRequested = MAKEWORD( 2, 2 );	
				/*加载套接字库，初始化Ws2_32.dll动态链接库*/
	error = WSAStartup( wVersionRequested, &wsaData);	
	if(error!=0)
	{
		printf("加载套接字失败！");
		return 0;							/*程序结束*/
	}
				/*判断请求加载的版本号是否符合要求*/
	if ( LOBYTE( wsaData.wVersion ) != 2 ||
		   HIBYTE( wsaData.wVersion ) != 2 ) 
	{	
		WSACleanup( );					/*不符合，关闭套接字库*/
		return 0;							/*程序结束*/
	}

	/*创建套接字*/
	socket_client=socket(AF_INET,SOCK_DGRAM,0);

	/*----------------------设置服务器地址-----------------------*/
	Server_add.sin_family=AF_INET;/*地址家族，对于必须是AF_INET，注意只有它不是网络网络字节顺序*/
	Server_add.sin_addr.S_un.S_addr = inet_addr("192.168.1.238");
	Server_add.sin_port=htons(5000);/*端口号*/

	sendto(socket_client,"ILoveChina",strlen("ILoveChina")+1,0,(SOCKADDR*)&Server_add,sizeof(SOCKADDR));
	/*------------------------------------------------------------------*/
	/*-----------------------释放套接字，关闭动态库----------*/
	/*------------------------------------------------------------------*/
	closesocket(socket_client);				/*释放套接字资源*/
	WSACleanup();							/*关闭动态链接库*/
	return 0;
}
```