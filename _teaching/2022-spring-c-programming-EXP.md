### C 语言实验
## **Chapter 2**
#### 【实验1】 编程输出：1、88和125的和; 2、任意输入两个整数，求两数的差。
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
#### 【实验2】对求一元二次方程通解的程序用单步执行方式来调试，查找逻辑错误。比如测试案例:输入“2 5 3”,则应得到x1=-1,x2=-1.5。
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
#### 【实验3】跟踪调试以下程序，注意函数调用过程中形参和实参的关系。
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
#### 【实验4】将4~100中的偶数分解成两个素数之和，每个数只取一种分解结果。如100可分解为3和97、或为11和89、或为17和83等，但我们只取第一种分解即可。
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
#### 【实验5】从键盘输入一个年份，判断改年是否为闰年。闰年的判断必须满足两个条件之一:(1)年份能被4整除，但不能被100整除;(2)年份能被400整除。
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
#### 【实验6】请模拟实现一个简单的四则运算计算器的功能。即输入一个两个数的运算式，根据不同的运算符得到不同的结果(分别用if和switch结构实现)。提示：1、四则运算指加减乘除;2、有除法运算结果会有小数，考虑变量的数据类型设什么合适
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
#### 【实验7】从键盘输入一个年份和月份，输出该月对应的天数。
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
#### 【实验8】编程打印出所有的“水仙花数”。所谓水仙花数：是指一个三位数，其各位数字的立方之和等于该数。 
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
#### 【实验9】求1000以内的亲密数对。亲密数对的定义为：若正整数a的所有因子（不包括a本身）之和为b，b的所有因子（不包括b本身）之和为a，且a≠b，则称a与b为亲密数对。
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
{
	int a, b;
	for(a=1; a<=1000; a++)
	{ 
		b=fun(a);
		if(fun(b)==a&&a!=b&&b<=1000&&b>a)  
			printf("%d,%d\n",a,b);
	}
	return 0;
}
```
#### 【实验10】以下程序中函数的功能是求s=1/(1\*2)+1/(2\*3)+...+1/(n\*(n+1))。请使用单步执行方式来调试，查找逻辑错误。比如测试案例:输入“1”,则应输出“fun(1)=0.500000”;输入“2”,则应输出“fun(2)=0.666667”。
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
#### 【实验11】用递归函数方法计算学生的年龄。已知第一位学生的年龄最小为10岁，其余学生一个比一个大2岁，求第5位学生的年龄。
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
#### 【实验12】从键盘输入"ABCDEFG?",分析下述程序的运行结果，然后上机验证。
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
#### 【实验13】分别求下列程序的运行结果(注:先思考预期的运行结果,再上机测试验证)
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
#### 【实验14】分别求下列程序的运行结果(注:先思考预期的运行结果,再上机测试验证)
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
#### 【实验15】编程实现从键盘输入一整数，如果该整数为素数，则返回1，否则返回0。要求单独编写一个求素数的自定义函数。
```c
#include <stdio.h>
int fun(int x)
{
	int n;
	for(n=2; n<x; n++)
		if(x%n==0) 
			return 0;
	return 1;
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
#### 【实验16】试用递归的方法编写一个返回长整型的函数，以计算斐波纳契数列的前20项。该数列满足：F(0)=1，F(1)=1，F(n)=F(n-1)+F(n-2) （n>2）。
```c
#include <stdio.h>
long int Fibonacci (int n)
{
	long int p;
	if(n==0||n==1)
		p=n;
	else
		p= Fibonacci (n-1)+ Fibonacci (n-2);
	return p;
}
int main(void)
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
#### 【实验17】用递归函数求s=1/(1\*2)+1/(2\*3)+...+1/(n\*(n+1))。
```c
#include <stdio.h>
float fun(int n)
{ 
	float s;
	if(n==1)
		s=0.5;
	else
		s=fun(n-1)+1.0/(n*(n+1));
	return s;
}

int main(void)
{ 
	int n;
	scanf("%d",&n);
	printf("fun(%d)=%f\n",n,fun(n));
	return 0;
}
```
#### 【实验18】编写一函数change(x，r)，将十进制整数x转换成r（1<r<10）进制后输出。(建议在main函数中调用进行测试)
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
int main(void)
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
#### 【实验19】如果一个数等于其所有真因子（不包括其本身）之和，则该数为完数，例如：6的因子有1、2、3，且6=1+2+3，故6为完数，求2\~1000中的所有完数。（要求：定义一个函数判断一个数是否为完数，并在main函数中调用，输出2\~1000中的所有完数）
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
int main(void)
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
#### 【实验20】编写一个把字符串(由数字字符、小数点、正号或负号组成)转换成浮点数的函数，并在main函数中调用测试。
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
#### 【实验21】输入5个整数,并存放在一维数组中,找出最大数与最小数所在的下标位置,并把两者对调,然后输出调整后的5个数。
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
#### 【实验22】编写一个程序,用简单选择排序方法对5个字符串{"abc","aabdfg","abbd","dcdbe","cd"}进行排序(从大到小),并输出排序后的结果。
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
#### 【实验23】编一程序用简单选择排序方法对10个整数排序（从大到小）。排序思路为：首先从n个整数中选出值最大的整数，将它交换到第一个元素位置，再从剩余的n-1个整数中选出值次大的整数，将它交换到第二个元素位置，重复上述操作n次后，排序结束。
```c
#include <stdio.h>
#define N 10
int main(void)
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
#### 【实验24】若有说明：int a[3][4]＝{{1,2,3,4 },{5,6,7,8},{9,10,11,12}}；现要将a的行和列的元素互换后存到另一个二维数组b中，并分别将ａ和b按矩阵形式输出。试编程。
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
#### 【实验25】试用一维数组计算出Fibonacci数列的前20项并输出。Fibonacci数列定义如下：第1项f(1)=1,第2项f(2)=1,...,第n项f(n)=f(n-1)+f(n-2),(n>2)。
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
#### 【实验26】输入一个字符串，按相反次序输出其中的所有字符。
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
	gets(a); // but not scanf("%s",a); it will exceed the length of the array.
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
#### 【实验27】输入或初始化2个字符串，将其连接后输出。
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
#### 【实验28】编一程序，将字符串中的第m个字符开始的全部字符复制到另一个字符串。要求在主函数中输入字符串及m的值并输出复制结果，在被调用函数中完成复制。
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
#### 【实验29】编写一个密码检测程序，程序执行时，要求用户输入密码（标准密码预先设定），然后通过字符串比较函数比较输入密码和标准密码是否相等．若相等，则显示“口令正确”并转去执行后继程序；若不相等，重新输入，三次都不相等则终止程序的执行。
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
#### 【实验30】编写一个程序，用于统计从键盘输入的字符串中元音字母的(a,A,e,E,i,I,o,O,u,U)个数。
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

#### 【实验31】用带参数的main()函数实现两个字符串的连接。
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
#### 【实验32】求下列程序的运行结果(注:先思考预期的运行结果,再上机测试验证)
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