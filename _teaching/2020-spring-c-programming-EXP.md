### C Programming Experiments
## **Chapter 2**
#### 【实验】对求一元二次方程通解的程序用单步执行方式来调试，查找逻辑错误。比如测试案例:输入“2 5 3”,则应得到x1=-1,x2=-1.5。
```c
#include <stdio.h>
#include <math.h>
int main()
{
	double a,b,c,delt,x1,x2;
	scanf("%lf%lf%lf",&a,&b,&c);
	delt=b*b-4*a*c;
	x1=(-b+sqrt(delt))/(2*a);
	x2=(-b-sqrt(delt))/(2*a);
	printf("x1=%g\n",x1);
	printf("x2=%g\n",x1);
	return 0;
}
```
**修正**：  
```c
printf("x2=%g\n",x1); --> printf("x2=%g\n",x2);
```
## **Chapter 3**
#### 【实验】跟踪调试以下程序，注意函数调用过程中形参和实参的关系。
```c
#include<stdio.h>
int main()
{
	int t,x=2,y=5;
	void swap(int,int);
	printf("(1) in main:x=%d,y=%d\n",x,y);
	swap(x,y);
	printf("(4) in main:x=%d,y=%d\n",x,y);
	return 0;
}

void swap(int a,int b)
{
	int t;
	printf("(2) in swap:a=%d,b=%d\n",a,b);
	t=a;a=b;b=t;
	printf("(3) in swap:a=%d,b=%d\n",a,b);
}
```
#### 【实验】将4~100中的偶数分解成两个素数之和，每个数只取一种分解结果。如100可分解为3和97、或为11和89、或为17和83等，但我们只取第一种分解即可。
```c
#include <stdio.h>
int main()
{
	int x,k,a,b,count=0;
	for(x=4; x<=100; x=x+2)
	{   
		for(a=2; a<=(x/2); a++)
		{
			for(k=2; k<a; k++)
				if(a%k==0)
					break;
			if(a==k) //a为素数
			{
				b=x-a;
				for(k=2; k<b; k++)
					if(b%k==0)
						break;
				if(b==k) //b为素数
				{
					printf("%3d=%3d+%3d\t",x,a,b);
					count++;
					if (count%3==0)
						printf("\n");
					break;
				}
			}
		}
	}
} 
```
## **Chapter 4**
#### 【实验】求1000以内的亲密数对。亲密数对的定义为：若正整数a的所有因子（不包括a本身）之和为b，b的所有因子（不包括b本身）之和为a，且a≠b，则称a与b为亲密数对。
```c
#include <stdio.h>
int fun(int x)
{   
	int n,s=0;
	for(n=1; n<x; n++)
		if(x%n==0)
			s=s+n;
	return  s;
}

int  main(void)
{   int a, b;
	for(a=1; a<=1000; a++)
	{   
		b=fun(a);
		if(fun(b)==a&&a!=b&&b<=1000&&b>a)  
			printf("%d,%d\n",a,b);
	}
    return 0;
}
```
#### 【实验】以下程序中函数的功能是求s=1/(1\*2)+1/(2\*3)+...+1/(n\*(n+1))。请使用单步执行方式来调试，查找逻辑错误。比如测试案例:输入“1”,则应输出“fun(1)=0.500000”;输入“2”,则应输出“fun(2)=0.666667”。
```c
#include<stdio.h>
int fun(int n)
{
	float s=0;
	int i;
	for(i=1;i<=n;i++) // 注:C++编译器可写成for(int i=1;i<=n;i++),但C编译器不可以
		s=s+1/(i*(i+1));
	return s;
}
int main(void)
{
	int n;
	printf("请输入一个大于0的整数:");
	scanf("%d",&n);
	printf("fun(%d)=%f",n,fun(n));
}
```
**修正**：  
```c
s=s+1/(x*(x+1)); --> s=s+1.0/(x*(x+1));
int fun(int n) --> float fun(int n)
```
#### 【实验】用递归函数方法计算学生的年龄。已知第一位学生的年龄最小为10岁，其余学生一个比一个大2岁，求第5位学生的年龄。
```c
#include<stdio.h>
int age(int n)
{
	int c;
	if(n==1)
		c=10;
	else
		c=age(n-1)+2;
	return c;
}
int main(void)
{
	int n=5;
	printf("age=%d\n",age(n));
	return 0;
}
```
#### 【实验】从键盘输入"ABCDEFG?",分析下述程序的运行结果，然后上机验证。
```c
#include<stdio.h>
void string()
{
	char ch;
	ch=getchar();
	if(ch!='?')
		string();
	putchar(ch);
}
int main(void)
{
	string();
	putchar('\n');
	return 0;
}
```
#### 【实验】分别求下列程序的运行结果(注:先思考预期的运行结果,再上机测试验证)
```c
//程序一
#include<stdio.h>
int main()
{
	void fun(void);
	int i=1;
	printf("In main, first i=%d\n",i);
	{
		int i=8;
		printf("In main, second i=%d\n",i);
	}
	fun();
	printf("In main, third i=%d\n",i);
	fun();
	return 0;
}
void fun(void)
{
	int i=9;
	i++;
	printf("In fun, i=%d\n",i);
}

//输出：
//In main, first i=1
//In main, second i=8
//In fun, i=10
//In main, third i=1
//In fun, i=10
```
```c
//程序二
#include<stdio.h>
void num()
{
	extern int x,y;
	int a=15,b=10;
	x=a-b;
	y=a+b;
}
int x,y;
int main()
{
	int a=7,b=5;
	x=a+b;
	y=a-b;
	num();
	printf("%d,%d\n",x,y);
	return 0;
}

//输出：
//5,25
```
```c
//程序三
#include<stdio.h>
int d=1;
int fun(int p)
{
	static int d=5;
	d+=5;
	printf("%d\n",d);
	return d;
}
int main()
{
	int a=3;
	printf("%d\n",fun(a+fun(d)));
}

//输出：
//10
//15
//15
```
#### 【实验】分别求下列程序的运行结果(注:先思考预期的运行结果,再上机测试验证)
```c
//程序一
# define N 10
# define s(x) x*x
# define f(x) (x*x)
int main()
{
	int i1,i2;
	i1=1000/s(N);
	i2=1000/f(N);
	printf("%d %d\n",i1,i2);
	return 0;
}
//输出：
//1000 10
```
```c
//程序二
程序头文件type1.h的内容是
# define N 5
# define M1 N*3
程序如下：
# include<stdio.h>
# include"type1.h"
# define M2 N*2
int main()
{
	int i;
	i=M1+M2;
	printf("%d\n",i);
}
```
## **Chapter 5**
#### 【实验】编写一个把字符串(由数字字符、小数点、正号或负号组成)转换成浮点数的函数，并在main函数中调用测试。
```c
#include <stdio.h>
#include <string.h>
double StrToDouble(char s[])
{
	int flag=0,i=0,decimal=0;
	double n,n1=0,n2=0,m=0.1;
	for(;s[i]!='\0';i++)
	{
		if(s[i]=='-')
			flag=1;
		else if(s[i]=='+')
			flag=1;
		else if(s[i]=='.')
			decimal=1;
		else if(decimal==0)
			n1=n1*10+(s[i]-'0');
		else
			{
				n2=n2+(s[i]-'0')*m;
				m=m/10;
			}
	}
	n=n1+n2;
	if(flag==1)
		n=-n;
	return(n);
}
int main()
{
	double num;
	char str[]="-432.9238";
	num=StrToDouble(str);
	printf("有字符串\"%s\"转换成的浮点数为%f\n",str,num);
	return 0;
}
```
#### 【实验】输入5个整数,并存放在一维数组中,找出最大数与最小数所在的下标位置,并把两者对调,然后输出调整后的5个数。
```c
#include<stdio.h>
# define N 5
int main()
{
	int k,arr[N],max,min,temp;
	for(k=0;k<N;k++)		//输入整数数组
		scanf("%d",&arr[k]);
	max=min=0;				//查找最大数和最小数的下标
	for(k=1;k<N;k++)
	{
		if(arr[k]>arr[max])
			max=k;
		if(arr[k]<arr[min])
			min=k;
	}
	temp=arr[max];		//交换最大数和最小数
	arr[max]=arr[min];
	arr[min]=temp;
	for(k=0;k<N;k++)	 //输入整数数组
		printf("%d\t",arr[k]);
	printf("\n") ;
}
```
#### 【实验】编写一个程序,用简单选择排序方法对5个字符串{"abc","aabdfg","abbd","dcdbe","cd"}进行排序(从大到小),并输出排序后的结果。
```c
#include<stdio.h>
#include<string.h>
# define N 5
int main()
{
	char *p[N]={"abc","aabdfg","abbd","dcdbe","cd"},*q;
	int i,j,max;
	for(i=0;i<N-1;i++)
	{
		max=i;
		for(j=i+1;j<N;j++)
			if(strcmp(p[max],p[j])<0)
				max=j;
		q=p[i];
		p[i]=p[max];
		p[max]=q;
	}
	for(i=0;i<N;i++)
		printf("%s\n",p[i]);
}
```
## **Chapter 6**
#### 【实验】用带参数的main()函数实现两个字符串的连接。
```c
#include <stdio.h>
#include <string.h>
int main(int argc, char *argv[])
{
   if(argc==3)
   {
      printf("第0个参数(命令名)为：%s\n",argv[0]);
      printf("第1个参数(字符串1)为：%s\n",argv[1]);
      printf("第2个参数(字符串2)为：%s\n",argv[2]);
      printf("字符串1和字符串2相连后的结果为：%s\n",strcat(argv[1],argv[2]));
   }
   else
      printf("错误!请输入两个参数(字符串)!");
   return 0;
}
```
### 方法一：在命令行运行
将上面的源程序取名为strlink.c，将其编译连接成可执行文件strlink.exe并存放在d:\xds目录中，若在d:\xds目录下执行命令：`d:\xds>strlink  First_string  Second_string`  
则得到的输出结果如下：  
> 第0个参数(命令名)为：d:\xds\strlink.exe  
> 第1个参数(字符串1)为：First_string  
> 第2个参数(字符串2)为：Second_string  
> 字符串1和字符串2相连后的结果为：First_stringSecond_string
### 方法二：在VC中运行
程序要想在VC中直接调试运行，可以先在“工程｜设置｜Debug｜Program arguments”项中填入参数“First_string  Second_string”，然后运行即可得到与上面相同的结果。
#### 【实验】求下列程序的运行结果(注:先思考预期的运行结果,再上机测试验证)
```c
int fa(int x)
{return x*x;}
int fb(int x)
{return x*x*x;}
int f(int (*f1)(),int (*f2)(),int x)
{return f2(x)-f1(x);}
int main()
{
	int i;
	i=f(fa,fb,2);
	printf("%d\n",i);
}
//输出：
//4
```