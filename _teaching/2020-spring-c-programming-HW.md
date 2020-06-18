### C Programming Homework and Answer
## **Chapter 1**
#### 【2020/02/24】请编程输出“我的第一个C语言程序"
```c
#include <stdio.h>
int main( )
{	
    printf("这是我的第一个C语言程序\n");
    return 0;
} 
```
## **Chapter 2**
#### 【2020/02/28】 编程输出：1、88和125的和; 2、任意输入两个整数，求两数的差。
```c
#include <stdio.h>
int main( )
{	
	int a,b;
	printf("88+125=%d\n",88+125);
    printf("请输入两个整数：");
	scanf("%d %d",&a,&b);
	printf("%d-%d=%d\n",a,b,a-b);
    return 0;
} 
```
#### 【2020/03/05】任意输入一位3位正整数，输出它的逆序数，如输入264，输出462（提示可以用/，%两个运算符）
```c
#include <stdio.h>
int main( )
{	
	int n,gewei,shiwei,baiwei,r;
    printf("请输入一个三位正整数：");
	scanf("%d",&n);
	baiwei=n/100;
	shiwei=n%100/10;
	gewei=n%10;
	r=gewei*100+shiwei*10+baiwei;
	printf("%d逆序数为：%d\n",n,r);
    return 0;
} 
```
## **Chapter 3**
#### 【2020/03/09】请模拟实现一个简单的四则运算计算器的功能。即输入一个两个数的运算式，根据不同的运算符得到不同的结果(分别用if和switch结构实现)。提示：1、四则运算指加减乘除;2、有除法运算结果会有小数，考虑变量的数据类型设什么合适
```c
#include <stdio.h>
main( )
{	float x,y;
	char op;
	printf("Please input Expression:");
	scanf("%f%c%f",&x,&op,&y);
	switch(op)
	{	case '+':
		printf("%g%c%g=%g\n", x,op,y,x+y);
			break;
		case '-':
			printf("%g%c%g=%g\n",x,op,y,x-y);
			break;
		case '*':
			printf("%g%c%g=%g\n",x,op,y,x*y);
			break;
		case '/':
			if ((y>=-1e-6) && (y<=1e-6))
				printf("Division Error!\n");
			else
				printf("%g%c%g=%g\n",x,op,y,x/y);
			break;
		default:printf("Expression Error!\n");
	}
}
```
#### 【2020/03/16】编程打印出所有的“水仙花数”。所谓水仙花数：是指一个三位数，其各位数字的立方之和等于该数。 
```c
#include <stdio.h>
int main( )
{ 
	int n,a,b,c; 
	for(n=100; n<1000; n++)
	{
		a=n/100; 
		b=n/10%10; 
		c=n%10; 
		if(a*a*a+b*b*b+c*c*c==n)
			printf("水仙花数有：%5d\n",n);
	}
	return 0;
}
```
## **Chapter 4**
#### 【2020/03/20】编程实现从键盘输入一整数，如果该整数为素数，则返回1，否则返回0。要求单独编写一个求素数的自定义函数。
```c
#include <stdio.h>
int fun(int x)
{
	int n;
	for(n=2; n<x; n++)
		if(x%n==0)  
			return 0;
	return  1;
}
int main(void)
{
	int x;
	printf("input a number:");
	scanf("%d", &x);
	if(fun(x))
		printf("%d is a prime number!\n",x);
	else 
	printf("%d is not a prime number!\n",x);
    return 0;
} 

```
#### 【2020/03/23】试用递归的方法编写一个返回长整型的函数，以计算斐波纳契数列的前20项。该数列满足：F(0)=1，F(1)=1，F(n)=F(n-1)+F(n-2)  （n>2）。
```c
#include <stdio.h>
long int Fibonacci (int n)
{
	long int p;
	if(n==0||n==1)
		p=n;
	else
		p= Fibonacci (n-1)+ Fibonacci (n-2);
	return  p;
}
int  main(void)
{
	int n;
	for(n=1; n<=20; n++)
	{
		printf("%-8d", Fibonacci (n));
		if((n)%5==0)
			printf("\n");
	}
    return 0;
} 
```
#### 【2020/03/27】编写一函数change(x，r)，将十进制整数x转换成r（1<r<10）进制后输出。(建议在main函数中调用进行测试)
```c
#include<stdio.h>
#include<math.h>
int change(int x,int r)
{
	int temp, result=0,count=0;
	do
	{
		temp=x%r;
		result=result+temp*pow(10,count++);
		x=x/r;
	}while(x);
	return result;
}
int  main(void)
{
	int x,r;
	printf("请输入一个正整数x:");
	scanf("%d", &x);
	printf("请输入一个正整数r(1<r<10):");
	scanf("%d", &r);
	printf("%d转化为%d进制为:%d\n",x,r,change(x,r));
    return 0;
} 
```
#### 【2020/03/30】如果一个数等于其所有真因子（不包括其本身）之和，则该数为完数，例如：6的因子有1、2、3，且6=1+2+3，故6为完数，求2\~1000中的所有完数。（要求：定义一个函数判断一个数是否为完数，并在main函数中调用，输出2\~1000中的所有完数）
```c
#include <stdio.h>
int IsWanshu(int n)
{
	int k, s=0;
	for(k=1; k<n; k++)
		if(n%k==0)
			s=s+k;
		if(s==n)
			return 1;
		else
			return 0;
}
int  main(void)
{
	int i, j=0;
	for(i=2; i<=1000; i++)
	{
		if(IsWanshu(i))  
		{
			printf("%5d", i);
			j=j+1; 
			if(j%5==0)
				printf("\n");
		}
	}
	printf("\n");
	return 0;
}
```
## **Chapter 5**
#### 【2020/04/03】编一程序用简单选择排序方法对10个整数排序（从大到小）。排序思路为：首先从n个整数中选出值最大的整数，将它交换到第一个元素位置，再从剩余的n-1个整数中选出值次大的整数，将它交换到第二个元素位置，重复上述操作n次后，排序结束。
```c
#include <stdio.h>
#define N 10
int  main(void)
{
	int i,j,max,temp,a[N]={29,37,12,30,45,47,27,39,16,72};
	for(i=0; i<N-1; i++)
	{
		max=i;
		for(j=i+1;j<N;j++)
			if(a[j]>a[max])
				max=j;
		temp=a[i];
		a[i]=a[max];
		a[max]=temp;
	}
	for(i=0;i<N;i++)
		printf("%d ",a[i]);
	printf("\n");
	return 0;
}
```
#### 【2020/04/10】若有说明：int a[3][4]＝{{1,2,3,4 },{5,6,7,8},{9,10,11,12}}；现要将a的行和列的元素互换后存到另一个二维数组b中，并分别将ａ和b按矩阵形式输出。试编程。
```c
#include <stdio.h>
#define M 3
#define N 4
int main()
{
	int i,j,a[M][N]={{1,2,3,4},{5,6,7,8},{9,10,11,12}},b[N][M];
	printf("初始的数组为: \n");
	for(i=0;i<M;i++)
	{
		for(j=0;j<N;j++)
		{
			printf("%-6d ",a[i][j]);
			b[j][i]=a[i][j];
		}
		printf("\n");
	}
	printf("互换后的数组为: \n");
	for(i=0;i<N;i++)
	{
		for(j=0;j<M;j++)
			printf("%-6d ",b[i][j]);
		printf("\n");
	}
	return 0;
}
```
#### 【2020/04/13】试用一维数组计算出Fibonacci数列的前20项并输出。Fibonacci数列定义如下：第1项f(1)=1,第2项f(2)=1,...,第n项f(n)=f(n-1)+f(n-2),(n>2)。
```c
#include<stdio.h>
#define N 20
int main()
{
	int i,a[N];
	a[0]=a[1]=1;
	for(i=2;i<N;i++)
		a[i]=a[i-1]+a[i-2];
	for(i=0;i<N;i++)
	{
		printf("%-d\t",a[i]);
		if((i+1)%5==0)
			printf("\n"); // or putchar('\n');
	}
	return 0;
}
```
## **Chapter 6**
#### 【2020/04/17】输入一个字符串，按相反次序输出其中的所有字符。
```c
// Solution 1
#include<stdio.h>
#define N 100
int main()
{
	char str[N+1],*p;
	int i;
	for(i=0;i<N;i++)
	{
		str[i]=getchar();
		if(str[i]=='\n')
			break;
	}
	p=str;
	while(--i>=0)
		putchar(*(p+i));
	putchar('\n');
	return 0;
}
```
```c
// Solution 2
#include<stdio.h>
#include<string.h>
int main()
{
	char a[2]; // even it seems more flexible, it is still not recommended!
	int i,L;
	gets(a);  // but not scanf("%s",a); it will exceed the length of the array.
	L=strlen(a);
	for(i=L-1;i>=0;i--)
		printf("%c",a[i]);
	printf("\n");
	return 0;
}
```
```c
// Solution 3
#include<stdio.h>
#include<string.h>
int main()
{
	char a[100],*p;
	printf("please input a string:\n");
	gets(a);
	p=a+strlen(a);
	while(--p>=a)
		putchar(*p);
	putchar('\n');
	return 0;
}
```
#### 【2020/04/20】输入或初始化2个字符串，将其连接后输出。
```c
#include<stdio.h>
#define N 100
strlink(char * str1, char *str2)
{
	while((*str1)!='\0')
		str1++;
	while((*str2)!='\0')
	{
		*str1=*str2;
		str1++;
		str2++;
	}
	*str1='\0';
}
int main()
{
	char s1[N]="Very",s2[N]=" Good!";
	strlink(s1,s2);
	printf("%s\n",s1);
	return 0;
}
```
#### 【2020/04/24】编一程序，将字符串中的第m个字符开始的全部字符复制到另一个字符串。要求在主函数中输入字符串及m的值并输出复制结果，在被调用函数中完成复制。
```c
#include <stdio.h>
#include <string.h>
copystr(char * str2,char * str1, int m)
{
	int n=0;
	while(n<m-1)
	{
		str1++;
		n++;
	}
	while(*str1!='\0')
	{
		*str2=*str1;
		str2++;
		str1++;
	}
	*str2='\0';
}
int main()
{
	int m;
	char s1[50],s2[50];
	printf("请输入一个字符串s1=");
	gets(s1);
	printf("请输入复制的起始位置m=");
	scanf("%d",&m);
	if(strlen(s1)<m)
		printf("输入有误!\n");
	else
	{
		copystr(s2,s1,m);
		printf("复制的结果是s2=%s\n",s2);
	}
	return 0;
}
```
#### 【2020/04/27】编写一个密码检测程序，程序执行时，要求用户输入密码（标准密码预先设定），然后通过字符串比较函数比较输入密码和标准密码是否相等．若相等，则显示“口令正确”并转去执行后继程序；若不相等，重新输入，三次都不相等则终止程序的执行。
```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
int strcompare(char *str1,char *str2)
{
	while(*str1==*str2 && *str1!=0 && *str2!=0)
	{
		str1++;
		str2++;
	}
	return *str1-*str2;
}
int main()
{
	char password[20]="Hello World";
	char input_pass[20];
	int i=0;
	while(1)
	{
		printf("请输入密码\n");
		gets(input_pass);
		if(strcompare(input_pass,password)!=0)
			printf("口令错误,按回车键继续!!!\n");
		else
		{
			printf("口令正确!!!\n");
			break;
		}
		getchar();
		i++;
		if(i==3)
		{
			printf("口令错误已达3次,请重新启动程序!!!\n");
			exit(0);
		}
	}
	return 0;
}
```
#### 【2020/05/07】编写一个程序，用于统计从键盘输入的字符串中元音字母的(a,A,e,E,i,I,o,O,u,U)个数。
```c
#include <stdio.h>
int fun(char *s)
{
	char a[]="aAeEiIoOuU",*p;
	int n=0;
	while(*s)
	{
		for(p=a;*p;p++)
			if(*p==*s)
			{
				n++;
				break;
			}
		s++;
	}
	return n;
}
int main()
{
	char str[255];
	printf("请输入一个字符串:");
	gets(str);
	printf("该字符串中元音字母的个数为:%d\n",fun(str));
	return 0;
}
```
## **补充作业**
#### 【2020/05/08】从键盘输入一个年份，判断改年是否为闰年。闰年的判断必须满足两个条件之一:(1)年份能被4整除，但不能被100整除;(2)年份能被400整除。
```c
#include <stdio.h>
int main()
{
	int year;
	scanf("%d",&year);
	if( (year%4==0 && year%100!=0) || (year%400==0) )
		printf("%d is a leap year\n",year);
	else
	printf("%d is not a leap year\n",year);
	return 0;
} 
```
#### 【2020/05/14】从键盘输入一个年份和月份，输出该月对应的天数。
```c
#include <stdio.h>
int main()
{
	int year,month,days;
	scanf("%d%d",&year,&month);
	switch(month)
	{
		case 1: case 3: case 5: case 7:
		case 8: case 10: case 12: days=31; break;

		case 4: case 6: case 9: case 11:days=30; break;

		case 2:
			if((year%4==0 && year%100!=0) || (year%400==0))
				days=29;
			else 
				days=28;
			break;

		default: days=0;
	}
	if(days!=0)
		printf("days=%d\n",days);
	else
		printf("Data Error\n");
	return 0;
} 
```
#### 【2020/05/15】用递归函数求s=1/(1\*2)+1/(2\*3)+...+1/(n\*(n+1))。
```c
#include <stdio.h>
float fun(int n)
{   
	float s;
	if(n==1)
		s=0.5;
	else
		s=fun(n-1)+1.0/(n*(n+1));
	return  s;
}

int  main(void)
{  
	int n;
	scanf("%d",&n);
	printf("fun(%d)=%f\n",n,fun(n));
    return 0;
}
```