### C语言综合测试
- **[输入/输出语句](#输入/输出语句)**
- **[控制结构](#控制结构)**
- **[函数](#函数)**
- **[数组](#数组)**
- **[指针](#指针)**
#### 答题说明
* **【题目-1】【程序填空】**：在“\*\*\*\*SPACE\*\*\*\*”语句的下一行完成程序填空，首先将填空标志【?】删除，然后填入正确答案
* **【题目-1】【程序改错】**：在“\*\*\*\*FOUND\*\*\*\*”语句的下一行修改程序，注意：不可以增加或删除程序行，也不可以更改程序的结构
* **【题目-1】【程序设计】**：在“\*\*\*\*Program\*\*\*\*”和“\*\*\*\*End\*\*\*\*”范围内编写程序

****

### <span id="输入/输出语句">输入/输出语句</span>  

**【题目-1】【程序填空】题目：下列程序从键盘输入所需数据，求出z的值并输出，要求输出结果保留2位小数。**

```c
#include <stdio.h>
/***********SPACE***********/
    【?】      
    main()
        {  int x;
double y,z;
/***********SPACE***********/
           scanf("【?】",&x,&y);
           z=2*x*sqrt(y);
/***********SPACE***********/
           printf("z=【?】",z);
        }
```
> **答案**  
> #include<math.h>  
> %d%lf  
> %.2lf  

**【题目-2】【程序改错】题目：列程序的功能为：已知圆锥半径r和高h，计算圆锥体积v。请纠正程序中存在错误，使程序实现其功能。**
```c
#include <stdio.h>
main()
{ 
/***********FOUND***********/
float r=10,h=5;
/***********FOUND***********/
v=1/3*3.14159*r2*h;
/***********FOUND***********/
printf("v=%d\n",v);
}
```
> **答案**  
> float r=10,h=5, v;  
> v=1/3\*3.14159\*r2\*h;-->v=1.0/3\* 3.14159\*r\*r\*h;  
> printf("v=%f\n",v);  

**【题目-3】【程序改错】题目：下列程序的功能为：按下列公式计算并输出x的值。其中a和b的值由键盘输入。请纠正程序中存在的错误，使程序实现其功能。公式： x=2ab/(a+b)^2(平方)**
```c
#include <stdio.h>
 main()
{ 
    int a,b;
    double x;
/***********FOUND***********/
    scanf("%d,%d",a,b);
/***********FOUND***********/
    x=2ab/(a＋b)(a＋b);
/***********FOUND***********/
     printf("x=%d＼n",x);
}
```
> **答案**  
> scanf("%d,%d",&a,&b);  
> x=2\*a\*b/((a＋b)\*(a＋b));  
> printf("x=%f＼n",x);  

**【题目-4】【程序改错】功能：输入一个圆的半径，计算圆的周长和面积并输出。**
```c
#include<stdio.h>
#define PI 3.1415926
/**********FOUND**********/
void maie()
{
  double r,l,s;
  /**********FOUND**********/
  scanf("%lf",r); 
  l=2*PI*r;
  s=PI*r*r;
  printf("%6.2f,%6.2f\n",l,s);
}
```
> **答案**  
> void main()  
> scanf("%lf",&r);  

**【题目-5】【程序设计】题目：求华氏温度 150°F 对应的摄氏温度。计算公式：c = (5/9)\*f-(5/9)\*32，式中：c表示摄氏温度，f表示华氏温度。**

输入输出示例：fahr = 150, celsius = 65

```c
#include <stdio.h>
void main()
{
    int celsius, fahr;  

    /**********Program**********/



    /**********  End  **********/

    printf("fahr = %d, celsius = %d\n", fahr, celsius); 
}
```
> **答案**  
> fahr=150;  
> celsius= 5.0/9.0*(fahr-32);

### <span id="控制结构">控制结构</span> 

**【题目-6】【程序填空】功能：输出Fibonacci数列的前15项，要求每行输出5项。Fibonacci数列：1,1,2,3,5,8,13...........**

```c
#include <stdio.h>

main()
{
  /***********SPACE***********/
  int 【?】[14],i;                                
  fib[0]=1;fib[1]=1;
  for (i=2;i<15;i++)
    /***********SPACE***********/
    fib[i]=【?】;                                        
  for(i=0;i<15;i++)
  {
    printf("%d\t",fib[i]);
    /***********SPACE***********/
    if ( 【?】 ) printf("\n");                        
  }
}
```
> **答案**  
> fib  
> fib[i-1]+fib[i-2]  
> (i+1)%5==0  

**【题目-7】【程序填空】功能：将字母转换成密码，转换规则是将当前字母变成其后的第四个字母，但W变成A、X变成B、Y变成C、Z变成D。小写字母的转换规则同样。**
```c
#include <stdio.h>
main()
{
  char c;
  /***********SPACE***********/
  while((c=【?】)!='\n')
  {
    /***********SPACE***********/
    if((c>='a'&&c<='z')||(c>='A'&&c<='Z'))【?】;
    /***********SPACE***********/
    if((c>'Z'【?】c<='Z'+4)||c>'z') c-=26;
    printf("%c",c);
  }
}
```
> **答案**  
> getchar()  
> c=c+4  
> &&  

**【题目-8】【程序填空】题目：输入x、y两个整数，按先大后小的顺序输出x、y。**
```c
#include <stdio.h>
void main( )
{  int x,y, t ;
   scanf("%d %d",&x,&y);
    if(x<y)
/***********SPACE***********/
     {  【?】 ;
/***********SPACE***********/
        【?】 ;   
/***********SPACE***********/
        【?】 ;  }
    printf("x=%d,y=%d\n",x,y); 
}
```

**【题目-9】【程序填空】题目：函数fun的功能是：统计长整数n的各位上出现数字1、2、3的次数，并用外部(全局)变量c1、c2、c3返回主函数。**

例如：当n＝123114350时，结果应该为：c1＝3  c2＝1  c3＝2。

```c
#include <stdio.h>

int c1, c2, c3;

void fun(long n)
{
        c1=c2=c3=0;
        while(n)
        {
/***********SPACE***********/
                switch(【?】)
                {
                        case 1:
/***********SPACE***********/
                                c1++;【?】;
                        case 2:
/***********SPACE***********/
                                c2++;【?】;
                        case 3: 
                                c3++;
                }
                n/=10;
        }
}

main()
{
        long n=123114350L;
        fun(n);
        printf("\nThe result: \n");
        printf("n=%ld c1=%d c2=%d c3=%d\n",n,c1,c2,c3); 
}
```

**【题目-10】【程序填空】功能：计算并输出high以内最大的10个素数之和，high由主函数传给fun函数，若high的值为100，则函数的值为732。**
```c
#include <conio.h>
#include <stdio.h>
#include <math.h>
int fun( int  high )
{ 
  int sum = 0,  n=0,  j,  yes;
  /***********SPACE***********/
  while ((high >= 2) && (【?】))
  {  
    yes = 1;
    for (j=2; j<=high/2; j++ )
      /***********SPACE***********/
      if (【?】)
      {
        yes=0;
        break;
      }
      if (yes)
      {
        sum +=high; 
        n++; 
      }
     high--;
  }
  /***********SPACE***********/
  【?】;
}

main ( )
{  
   printf("%d\n", fun (100));
}
```

**【题目-11】【程序填空】题目：下列给定程序中，函数fun的功能是：找出100～999之间(含100和999)所有整数中各位上数字之和为x(x为正整数)的整数，并输出；符合条件的整数个数作为函数值返回。**

例如：当x值为5时，100～999之间各位上数字之和为5的整数有：104、113、122、131、140、203、212、221、230、302、311、320、401、410、500，共有15个。

当x值为27时，各位数字之和为27的整数是：999，只有1个。

```c
#include  <stdio.h>

int fun(int  x)
{ 
        int  n, s1, s2, s3, t;
        n=0;
        t=100;
/***********SPACE***********/
        while(t<=【?】)
        {
                s1=t%10;
/***********SPACE***********/
                s2=(【?】)%10; 
                s3=t/100;
/***********SPACE***********/
                if(s1+s2+s3==【?】)
                { 
                        printf("%d ",t);
                        n++;
                }
                t++;
        }
        return  n;
}
main()
{ 
        int x=-1;
        while(x<0)
        {
                printf("Please input(x>0): "); 
                scanf("%d",&x);
        }
        printf("\nThe result is: %d\n",fun(x));
}
```


**【题目-12】【程序填空】功能：输入一个整数，计算它可能是哪两个整数的平方和，并打印结果数据。**

如：34是5和3或3和5的平方和。

```c
#include  <stdio.h>           /* for i/O functions        */
#include  <stdlib.h>          /* for atoi()               */
#include  <math.h>            /* for sqrt()               */

void  main(void)
{
  int  given;              /* the given number         */
  int  row, column;        /* row and column indicators*/
  int  count;              /* number of solutions      */
  char line[100];
  printf("\nRepresenting a Given Number as the Sum of Two Squares");
  printf("\n=====================================================\n");
  printf("\nAn integer Please ---> ");
  gets(line);
  given = atoi(line);
  printf("\nCount      X      Y");
  printf("\n-----  -----  -----");
  row    = 1;              /* starts from far enough   */
  column = (int) (sqrt((double) given) + 0.5);
  count  = 0;              /* so solution yet          */
  while (row <= given && column > 0)  /* scan down...  */
    if (row*row + column*column == given) 
    {
      /***********SPACE***********/
      【?】;                                        
      printf("\n%5d%7d%7d", count, row, column);
      row++;
      column--;
    }
    else if (row*row + column*column > given)
      /***********SPACE***********/
      【?】;                                        
    else
      /***********SPACE***********/
      【?】;                                        
  if (count == 0)
    printf("\n\nSorry, NO ANSWER found.");
  else
    printf("\n\nThere are %d possible answers.",count);
}
```


**【题目-13】【程序填空】题目：函数fun的功能是：计算公式的前n项之和。若x＝2.5，n＝15时，函数值为17914。**  

<center><a href="images/image2.jpg"  title=""><img src="images/image2.jpg" width="200"/></a></center>

```c
#include    <stdio.h>
#include    <math.h>

double fun(double  x, int  n)
{  
        double  f, t;   
        int  i;
/***********SPACE***********/
        f = 【?】;
        t = -1;
        for (i=1; i<n; i++)
        {
/***********SPACE***********/
                t *= (【?】)*x/i;
/***********SPACE***********/
                f += 【?】;
        }
        return  f;
}
main()
{  
        double  x, y;
        x=2.5;
        y = fun(x, 15);
        printf("\nThe result is :\n");
        printf("x=%-12.6f    y=%-12.6f\n", x, y);
}
```


**【题目-14】【程序填空】功能：用等分法在有序的循环数组中，找到最小元素的位置。**

```c
#include  <stdio.h>
int  cyclic_min(int  x[], int n)
{
  int  left  = 0;
  int  right = n - 1;
  int  mid;
  /***********SPACE***********/
  while (【?】) 
  {                        
    mid = (left + right)/2;
    if (x[mid] < x[right])
      /***********SPACE***********/
       【?】;                        
    else
      /***********SPACE***********/
      【?】;                        
  }
  return left;
}

#include  <stdio.h>
void  main(void)
{
     int  x[] = { 20, 23, 28, 35, 39, 40, 42, 8, 10, 15, 17, 19};
     int  n   = sizeof(x)/sizeof(int);
     int  loc, i;

     printf("\nFind Cyclic Minimum");
     printf("\n===================");
     printf("\n\nGiven Array Sorted in Cyclic Fashion :\n");
     for (i = 0; i < n; i++)
          printf("%3d", x[i]);
     loc = cyclic_min(x, n);
     printf("\n\nMinimum is located at x[%d] = %d", loc, x[loc]);
}
```

**【题目-15】【程序改错】功能：写计算级数 ex=1+x+x^2/2!+x^3/3!+ ...+x^n/n! 的值。**
```c
#include<stdio.h>
main()
{
  int m,n;
  float x,term,ex1,ex2;
  printf("x,m=");
  scanf("%f %d",&x,&m);
  /**********FOUND**********/
  ex1==ex2=1;
  term=1;
  for(n=1;n<=m;n++)
  {
    /**********FOUND**********/
    term*=x%n;
    ex1+=term;
  }
  ex2=term;
  /**********FOUND**********/
  for (n=m;n>1; n--)
  {
    term*=n/x;
    ex2+=term;
  }
  printf("exforward=%f exbackrard=%f\n",ex1,ex2);
}
```


**【题目-16】【程序改错】功能：以下程序能求出1\*1+2\*2+......+n\*n<=1000中满足条件的最大的n,输出格式如n=37。**
```c     
#include <stdio.h>
#include "string.h"
main()
{
  int n,s;
  /**********FOUND**********/
  s==n=0;
  /**********FOUND**********/
  while(s>1000)
  {
    ++n;
    s+=n*n;
  }
  /**********FOUND**********/
  printf("n=%d\n",&n-1);
}
```


**【题目-17】【程序设计】题目：下面的公式可以用来计算圆周率PI的近似值: pi/8=1/（1\*3）+1/（5\*7）+1/（9\*11）+…… 请编程序计算公式的前15项，并输出pi值。**

要求：循环控制变量用i，中间项存于变量p中，若使用其他变量用n。

```c
#include <stdio.h>
void main()
{

/**********Program**********/




/**********  End  **********/

}
```


**【题目-18】【程序设计】题目：输入正整数m和n（设100≤m≤n≤999），输出m到n之间满足下列条件的三位数：它的个位数的立方加十位数的平方再加上百位数等于该数的本身（例如135＝1＋3\*3＋5\*5\*5）。**

如输入：135  600

则输出：135  175  518  598

```c   
#include <stdio.h>
main()
{
    int  m,n;
/**********Program**********/




/**********  End  **********/
}
```  


**【题目-19】【程序设计】题目：从键盘输入实数x，按照所示的公式计算并输出y值：**

<center><a href="images/imagepg"  title=""><img src="images/imagepg" width="200"/></a></center>

```c   
#include <stdio.h>
#include<math.h>
main()
{  
   double x,y;

/**********Program**********/





/**********  End  **********/
   printf("y=%f\n",y);
}
```

### <span id="函数">函数</span>  

**【题目-20】【程序改错】功能：输入两个实数，按代数值由小到大输出它们,并在fun()函数中输出。（输出的数据都保留2位小数）**
```c   
#include <stdio.h>

fun()
{
  /**********FOUND**********/
  float t
  float a, b ;
  scanf("%f %f",&a,&b);
  /**********FOUND**********/
  if(a<b)
  {
    t=a;
    a=b;
    b=t;
  }
  /**********FOUND**********/
  printf("%5.2f,%5.2f\n",&a,&b);
}

main()
{
  fun();
}
```

**【题目-21】【程序改错】功能：求1到10的阶乘的和。**
```c  
#include <stdio.h>
main()
{
  int i;
  float s=0;
  float fac(int n);
  /**********FOUND**********/
  for(i=1;i<10;i++)
    /**********FOUND**********/
    s=fac(i);
  printf("%f\n",s);
}
float fac(int n)
{
/**********FOUND**********/
  int  y=1;
  int i;
  for(i=1 ;i<=n;i++)
    y=y*i;
  /**********FOUND**********/
  return;
}
```

**【题目-22】【程序改错】题目：函数fun的功能是：求1到20的阶乘的和。请改正程序中的错误，使它能得出正确的结果。**

注意：不可以增加或删除程序行，也不可以更改程序的结构。

```c   
fun()
{ 
  int n,j;
  float s=0.0,t=;
  for(n=1;n<=20;n++)
   {        
        t=1;
   for(j=1;j<=n;j++)
    t=t*j;
/**********FOUND**********/
    s+t=s;
    }
/**********FOUND**********/
 printf("jiecheng=%d\n",s);
}
main()
{
 fun();
}
```

**【题目-23】【程序改错】功能：求二分之一的圆面积，函数通过形参得到圆的半径，函数返回二分之一的圆面积。**

例如：输入圆的半径值：19.527 输出为：s = 598.950017。
```c
#include <stdio.h>
#include <conio.h>

/**********FOUND**********/
double fun( r)
{
  double s;
  /**********FOUND**********/
  s=1/2*3.14159* r * r;
  /**********FOUND**********/
  return r;
}

main()
{
  float x;
  printf ( "Enter x: ");
  scanf ( "%f", &x );
  printf (" s = %f\n ", fun ( x ) );
}
```

**【题目-24】【程序改错】功能：根据整型形参m，计算如下公式的值：y=1/2＋1/8＋1/18＋...＋1/(2m\*m)**
```c
#include <stdio.h>

double fun(int m)   
{
  /**********FOUND**********/
  double y=0
  int i;
  /**********FOUND**********/
  for(i=1; i<m; i++)
  {
    /**********FOUND**********/
     y=+/(2*i*i); 
  }
  return(y);
}

main()   
{
  int n;   
  printf("Enter n: ");   
  scanf("%d", &n);   
  printf("\nThe result is %1f\n", fun(n)); 
}
```

**【题目-25】【程序改错】题目：下列给定程序中函数fun的功能是：计算函数F(x，y，z)＝(x＋y)/(x－y)＋(z＋y)/(z－y)的值。其中x和y的值不相等，z和y的值不相等。**

例如：当x的值为9，y的值为11，z的值为15时，函数值为-3.50。

```c
#include <stdio.h>
#include <math.h>
#include <stdlib.h>

/***********FOUND***********/
#define FU(m,n) ((m/n))

float fun(float a,float b,float c)
{  
        float  value;
        value=FU(a+b,a-b)+FU(c+b,c-b);
/***********FOUND***********/
        Rteurn(Value);
}
main()
{  
        float  x,y,z,sum;
        printf("Input  x  y  z:  ");
        scanf("%f%f%f",&x,&y,&z);
        printf("x=%f,y=%f,z=%f\n",x,y,z);
        if (x==y||y==z)
        {
                printf("Data error!\n");
                exit(0);
        }
        sum=fun(x,y,z);
        printf("The result is : %5.2f\n",sum);
}
```

**【题目-26】【程序设计】功能：编写函数fun求sum=d+dd+ddd+……+dd...d(n个d)，其中d为1-9的数字。**

例如：3+33+333+3333+33333(此时d=3,n=5)，d和n在主函数中输入。

```c
#include <stdio.h>

long int fun(int d,int n)
{
  /**********Program**********/
  
  
  /**********  End  **********/
}

main()
{ 
  int d,n;
  long sum,fun();
  printf("d=");
  scanf("%d",&d);
  printf("n=");
  scanf("%d",&n);
  sum=fun(d,n);
  printf("sum=%ld\n",sum);
 }
```

**【题目-27】【程序设计】功能：计算并输出给定整数n的所有因子之和（不包括1与自身）。注意：n的值不大于1000。**

例如：n的值为855时，应输出704。

```c
#include <stdio.h>
   
int fun(int n)
{
/**********Program**********/




 
/**********  End  **********/  
}

void main()
{
        printf("s=%d\n",fun(855));
}
```

**【题目-28】【程序设计】请编写函数sum，其功能是：用for循环语句求1到n之间所有偶数之和（若n为偶数包括n），并将结果返回给主函数。（n值由主函数传入）**

运行程序后若输入：10，则输出为：sum=30。

```c
#include <stdio.h>

int sum(int n)
 {
    /**********Program**********/

  
  
  
  
    /**********  End  **********/    
 }
void main()
{ 
    int n,s;
    scanf("%d",&n);
    s=sum(n);
    printf("sum=%d\n",s);
  
}
```


**【题目-29】【程序设计】题目：编写函数fun，w是一个大于10的无符号整数，若w是n(n≥2)位的整数，则函数求出w的后n－1位的数作为函数值返回。**

例如：w值为5923，则函数返回923；若w值为923，则函数返回23。

注意：请勿改动main函数和其他函数中的任何内容，仅在函数fun的花括号中填入你编写的若干语句。

```c
#include<conio.h>
#include<stdio.h>
#include<stdlib.h>

unsigned fun(unsigned w)
{
/**********Program**********/





/**********  End  **********/
}
void main()
{ 
  
        unsigned x;
        printf("Enter a unsigned integer number: ");
        scanf ("%u",&x);
        printf("The original data is:%u\n",x);
        if(x<10) 
                printf("Data error! ");
        else 
                printf ("The result :%u\n", fun(x));

}
```

**【题目-30】【程序设计】题目：公式e=1+1/1!+1/2!+1/3!+......,求 e 的近似值，精度为10的-6次方。**
  
```c
#include <stdio.h>

//函数功能：计算e,精度为f;
double fun(double f)
{
        double e=1;
        double jc=1;//求阶乘，并存入jc中
        /**********Program**********/





        /**********  End  **********/
        return e;
}

void main()
{
        printf("e=%f\n",fun(10e-6));
}
```

### <span id="数组">数组</span>  


**【题目-31】【程序填空】题目：下列给定程序中，函数fun的功能是：把形参a所指数组中的奇数按原顺序依次存放到a[0]、a[1]、a[2]、……中，把偶数从数组中删除，奇数个数通过函数值返回。**

例如：若a所指数组中的数据最初排列为：9、1、4、2、3、6、5、8、7，删除偶数后a所指数组中的数据为：9、1、3、5、7，返回值为5。
```c
#include    <stdio.h>
#define    N    9

int fun(int  a[], int  n)
{        
        int  i,j;
        j = 0;
        for (i=0; i<n; i++)
/***********SPACE***********/
                if (a[i]%2==【?】)
                {
/***********SPACE***********/
                        a[j] = a[i]; 【?】;
                }
/***********SPACE***********/
        return 【?】;
}
main()
{  
        int  b[N]={9,1,4,2,3,6,5,8,7}, i, n;
        printf("\nThe original data  :\n");
        for (i=0; i<N; i++)  printf("%4d ", b[i]);
        printf("\n");
        n = fun(b, N);
        printf("\nThe number of odd  : %d \n", n);
        printf("\nThe odd number  :\n");
        for (i=0; i<n; i++)  printf("%4d ", b[i]);
        printf("\n");
}
```

**【题目-32】【程序填空】题目：给定程序中，函数fun的作用是：统计整型变量m中各数字出现的次数，并存放到数组a中，其中：a[0]存放0出现的次数，a[1]存放1出现的次数，…… a[9]存放9   出现的次数。**  

例如：若m为14579233，则输出结果应为：0,1,1,2,1,1,0,1,0,1,   

```c
#include  <stdio.h>

void fun( int  m, int  a[10])
{  
        int  i;
        for (i=0; i<10; i++)
/***********SPACE***********/
                【?】= 0;
        while (m > 0)
        {
/***********SPACE***********/
                i = 【?】;
                a[i]++;
/***********SPACE***********/
                m = 【?】;
        }
}
main()
{  
        int  m,  a[10],i;
        printf("请输入一个整数 :  ");  
        scanf("%d", &m);
        fun(m, a);
        for (i=0; i<10; i++) 
                printf("%d,",a[i]); 
        printf("\n");
}
```


**【题目-33】【程序填空】题目：给定程序中，函数fun的功能是：在任意给定的9个正整数中找出按升序排列时处于中间的数，将原数据序列中比该中间数小的数用该中间数替换，位置不变，在  主函数中输出处理后的数据序列，并将中间数作为函数值返回。**

例如：有9个正整数：1  5  7  23  87  5  8  21  45   按升序排列时的中间数为：8

     处理后主函数中输出的数列为：8  8  8  23  87  8  8  21  45

```c
#include  <stdio.h>
#define    N    9

int fun(int  x[])
{  
        int  i,j,k,t,mid,b[N];
        for(i=0;i<N;i++)
                b[i]=x[i];
        for(i=0;i<=N/2;i++)
        {  
                k=i;
                for(j=i+1;j<N;j++)
                        if(b[k]>b[j])  
                                k=j;
                if(k != i )
                {  
                        t=b[i]; 
/***********SPACE***********/
                        b[i]=【?】; 
                        b[k]=t;
                }
        }
/***********SPACE***********/
        mid=b[【?】];
        for(i=0; i<N; i++)
/***********SPACE***********/
                if(x[i] 【?】 mid) 
                        x[i]=mid;
        return  mid;
}
main()
{ 
        int  i, x[N]={1,5,7,23,87,5,8,21,45};
        for(i=0; i<N; i++) 
                printf("%d ",x[i]);
        printf("\nThe mid data is: %d\n",fun(x));
        for(i=0; i<N; i++)  
                printf("%d ",x[i]);
        printf("\n");
}
```


**【题目-34】【程序填空】题目：求数组a[5]中相邻元素的最大公约数，并保存到数组b[5]中(a[4]与a[0]看作相邻元素)。**

例如：a[5]={18,66,38,87,15}    b[5]={6,2,1,3,3}
      
注意：除要求填空的位置之外，请勿改动程序中的其他内容。且不能使用C语言的库函数

```c
#include <stdio.h>
#define  M  5

void Calculate(int a[],int n,int b[])
{
    int i,x,y,r;
    for(i=0;i<n;i++)
    {
        x=a[i];
/***********SPACE***********/
        y=a[【?】];
        do
        { 
/***********SPACE***********/
            【?】;
            x=y;
            y=r;
        }while(r);
        b[i]=x;
    }
}
void  main()
{
    int  i,n=5,a[5]={18,66,38,87,15},b[5]={0};
    Calculate(a,n,b);
    for(i=0;i<n;i++)
        printf("%3d、%3d的最大公约数：%3d\n",a[i],a[(i+1)%n],b[i]);
}
```


**【题目-35】【程序填空】题目：以下程序的功能是打印以下图形。**

        *****
         ***** 
          *****  
           *****   
            *****
    
```c 
main ( )
{
static char a[5][9];
 int i,j;
 for (i=0;i<5;i++)
/***********SPACE***********/
   for(j=i; 【?】;j++)
     a[i][j]='*';
 for(i=0;i<5;i++)
   {
    for(j=0;j<9;j++)
/***********SPACE***********/
    printf("%c", 【?】 );
/***********SPACE***********/
   【?】;
   }
 }

 ```
 

**【题目-36】【程序填空】题目：输入一字符串，检查字符串是否满足以下条件：**

（1）字符串s中左括号“(”的个数与右括号“)”的个数相同；

（2）从字符串s的首字符起顺序查找右括号“)”的个数在任何时候均不超过所遇到的左括号“(”的个数。若字符串同时满足上述两个条件，函数返回1，否则返回0。

注意：请勿改动主函数main()中的其他内容。
```c
#include<stdio.h>
#include<string.h>
void main()
{
    int fun(char s[]);
    char s[80];
    int c;
    printf("Please input the string:");
    gets(s);
    c=fun(s);
    printf("c=%d\n",c);
}
int fun(char s[])
{
    int c1,c2,i;
    i=c1=c2=0;
    while(s[i]!='\0')
    {
        if(s[i]=='(') c1++;
        else if(s[i]==')')
        { 
            c2++;
/***********SPACE***********/
            if(【?】) return(0);
        }
        i++;
    }
/***********SPACE***********/
    return(【?】);
}
```

**【题目-37】【程序改错】功能：在一个一维整型数组中找出其中最大的数及其下标。**
```c
#include <stdio.h>
#define N 10
/**********FOUND**********/
float fun(int *a,int *b,int n)
{
  int *c,max=*a;
  for(c=a+1;c<a+n;c++)
    if(*c>max)
    {
      max=*c;
      /**********FOUND**********/
      b=c-a;
    }
  return max;
}

void main()
{
  int a[N],i,max,p=0;
  printf("please enter 10 integers:\n");
  for(i=0;i<N;i++)
    /**********FOUND**********/
    get("%d",a[i]);
  /**********FOUND**********/
  m=fun(a,p,N);
  printf("max=%d,position=%d",max,p);
}
```

**【题目-38】【程序改错】功能：利用二维数组输出如图所示的图形。**

        *******
         *****
          ***
           *
          ***
         *****
        *******
        
```c
#include <stdio.h>
#include <conio.h>
/**********FOUND**********/
#define N= 7
main()
{
  char a[N][N];
  int i,j,z;
  for(i=0;i<N;i++)
    for(j=0;j<N;j++)
      /**********FOUND**********/
      a[i][j]=;
  z=0;
  for(i=0;i<(N+1)/2;i++)
  {  
    for(j=z;j<N-z;j++)
      a[i][j]='*';
    z=z+1;
  }
  /**********FOUND**********/
  z=0;
  for(i=(N+1)/2;i<N;i++)
  {
    z=z-1;
    for(j=z;j<N-z;j++)
    a[i][j]='*';
  }
  for(i=0;i<N;i++)
  { 
    for(j=0;j<N;j++)
      /**********FOUND**********/
      printf("%d",a[i][j]);
    printf("\n");
  }
}
```

**【题目-39】【程序改错】调用优化的sort函数，完成对数组a的冒泡降序排序。下面给定的程序存在错误，请改正。**

注意：不得增行或删行，也不得更改程序的结构。

```c
#include<stdio.h>
void sort(int [ ],int );
int main()
{
        int  i, a[ ]={6,0,-3,9,4,-5,18,20};
        int n=sizeof(a)/sizeof(a[0]);
/***********FOUND***********/
        sort(n ,a[n]);
        for(i=0;i<n;i++)
                printf("%d\t",a[i]);
        printf("\n");
        return 0;
}
void sort(int a[ ],int n)
{
        int i,j,k,swap;
        for(i=0;i<n-1;i++)
        {
                swap=0;
        /***********FOUND***********/
                for(j=n-1;j>i;j++)
                        if(a[j]>a[j-1])
                                k=a[j],a[j]=a[j-1],a[j-1]=k,swap=1;
        /***********FOUND***********/
                if(swap)break;
        }
}
```


**【题目-40】【程序改错】在主函数中从键盘输入若干个数放入数组中，用0结束输入并放在最后一个元素中。下列给定程序中，函数fun()的功能是计算数组元素中值为负数的平均值（不包括0）。**

例如：数组中元素的值依次为43，-47，-21，53，-8，12，0，则程序的运行结果为-25.333333。

请改正程序中的错误，使它能得到正确结果。

注意：不要改动main函数，不得增行或删行，也不得更改程序的结构。

```c
#include <stdlib.h>
#include <conio.h>
#include <stdio.h>
double  fun(int   x[ ])
{
    double sum = 0.0;
    int  c = 0, i = 0;
/***********FOUND***********/
    while(x[i]==0)
    {
        if(x[i]<0)
        { 
            sum=sum+x[i];
            c++;
        }
        i++;
     }
/***********FOUND***********/
    sum=sum\c;
    return  sum;
}
void main()
{
    int  x[1000];  
    int  i=0;
    system("CLS");
    printf("\nPlease enter some data(end with 0) :");
    do
    {
        scanf("%d",&x[i]);
    }   
    while(x[i++]!=0);
    printf("%f\n",fun(x));
}
```


**【题目-41】【程序改错】题目：fun函数的功能是：先从键盘上输入一个3行3列矩阵的各个元素的值，然后输出主对角线上的元素之和sum。请改正程序中的错误，使它能得出正确的结果。**

注意：不可以增加或删除程序行，也不可以更改程序的结构。

```c
#include "stdio.h"
int fun()
{
  int a[3][3],sum;
  int i,j;
  sum=0;
  for(i=0;i<3;i++)
    for(j=0;j<3;j++)
      scanf("%d",&a[i][j]);
  for(i=0;i<3;i++)
/**********FOUND**********/
    sum=sum+a[i][j];
/**********FOUND**********/
  printf("sum=%f\n",sum);
}
main()
{
 fun();
}
```


**【题目-42】【程序改错】题目：fun函数的功能是：在任意给定的N个正整数中，从左到右依次逐个取三个数作为一组，按值大小找出该组数的中值，用该中值替换与该组数对应的原三个数中的中间位置的数。处理后原数列中首尾2个数不变。处理后数列在主函数中输出。**

例如：有10个正整数如下：初始数列为：6 5 7 23 18 5 8 21 45 38 第1组数为：6 5 7  

      中值为：6   替换后的数列为：6 6 7 23 18 5 8 21 45 38 第2组数为：5 7 23 
      
      中值为：7   替换后的数列为：6 6 7 23 18 5 8 21 45 38第3组数为：7 23 18  
      
      中值为：18  替换后的数列为：6 6 7 18 18 5 8 21 45 38第4组数为：23 18 5 
      
      中值为：18  替换后的数列为：6 6 7 18 18 5 8 21 45 38第5组数为：18 5 8  
      
      中值为：8   替换后的数列为：6 6 7 18 18 8 8 21 45 38第6组数为：5 8 21  
      
      中值为：8   替换后的数列为：6 6 7 18 18 8 8 21 45 38第7组数为：8 21 45  
      
      中值为：21  替换后的数列为：6 6 7 18 18 8 8 21 45 38第8组数为：21 45 38 
      
      中值为：38  替换后的数列为：6 6 7 18 18 8 8 21 38 38        
      
      最终结果为：6 6 7 18 18 8 8 21 38 38 
```c
#include  <stdio.h>
#define   N   10

int findmid(int  a, int  b, int  c)
{  
        int  t;
        t = (a>b)?(b>c?b:(a>c?c:a)):((a>c)?a:((b>c)?c:b));
/***********FOUND***********/
        return  b;
}
void fun(int  x[])
{  
        int  i,a,b,c,t[N];
        /***********FOUND***********/
        for(i=0;i<N;i++) t[i]=x[i]
        for(i=0;i<N-2;i++)
        {  
                a=t[i];
                b=t[i+1];
                c=t[i+2];
        /***********FOUND***********/
                t[i+1]=findmid(a,b,c);
        }
}
main()
{  
        int  i, x[N]={6,5,7,23,18,5,8,21,45,38};
        for(i=0; i<N; i++)  
                printf("%d ",x[i]);
        printf("\n");
        fun(x);
        for(i=0; i<N; i++) 
                printf("%d ",x[i]);
        printf("\n");
}
```


**【题目-43】【程序改错】功能：输入一个字符串，过滤此串，滤掉字母字符，并统计新生成串中包含的字符个数。**

例如：输入的字符串为ab234$df4，则输出为：

      The new string is 234$4 
      
      There are 5 char in the new string.。

```c
#include <stdio.h>
#include <conio.h>
#define N 80

int fun(char *ptr)
{
  int i,j;
  /**********FOUND**********/
  for(i=0,j=0;*(ptr+i)!="\\0";i++)
    /**********FOUND**********/
    if(*(ptr+i)>'z'|| *(ptr+i)<'a'||*(ptr+i)>'Z' || *(ptr+i)<'A')
    {
      /**********FOUND**********/
      (ptr+j)=(ptr+i);
      j++;
    }
  *(ptr+j)='\0';
  return(j);
}

main()
{
  char str[N];
  int s;
  printf("input a string:");gets(str);
  printf("The original string is :"); puts(str);
  s=fun(str);
  printf("The new string is :");puts(str);
  printf("There are %d char in the new string.",s);
}

```

**【题目-44】【程序填空】功能：统计一个字符串中的字母、数字、空格和其它字符的个数。**

```c
#include <stdio.h>
main ()
{
  char s1[80];int a[4]={0};
  int k;
  /***********SPACE***********/
  【?】;
  gets(s1);
  /***********SPACE***********/
  【?】;
  puts(s1);
  for(k=0;k<4;k++)
    printf("%4d",a[k]);
}

void fun(char s[],int b[])
{
  int i;
  for (i=0;s[i]!='\0';i++)
  if ('a'<=s[i]&&s[i]<='z'||'A'<=s[i]&&s[i]<='Z') 
    b[0]++;
  /***********SPACE***********/
  else if (【?】) 
    b[1]++;
  /***********SPACE***********/
  else if (【?】 ) 
    b[2]++;
  else
    b[3]++;
}
```


**【题目-45】【程序设计】题目：（一维数组）将1－200中所有11的倍数存放到一个一维数组中，并输出。**
```c
#include <stdio.h>
void main()
{        
        int i,j=0,a[100];

       
       /**********Program**********/







       /**********  End  **********/

       for(i=0;i<j;i++)
                printf("%d ",a[i]);
        printf("\n");
}
```


**【题目-46】【程序设计】题目：（一维数组）有n个已经按由小到大排好序的整数，再输入一个整数，将其插入到这批数据中，要求插入该元素后仍然按由小到大的顺序排列。**
```c
#include <stdio.h>
#define N 11
void main()
{
        int a[N],x,p;
        int i;
        printf("Please input %d numbers:",N-1);
        for(i=0;i<=N-2;i++)
                scanf("%d",&a[i]);
        printf("Please input x to be intert:");
                scanf("%d",&x);

        /**********Program**********/



        /**********  End  **********/

        for(i=0;i<=N-1;i++)//结果
                printf("%5d",a[i]);
        printf("\n");
}
```

**【题目-47】【程序设计】题目：请编写函数fun，该函数的功能是：求出二维数组周边元素之和，作为函数值返回。二维数组中的值在主函数中赋予。**

例如：若二维数组中的值为： 

1　3　5　7　9

2　9　9　9　4 

6　9　9　9　8

1　3　5　7　0

则函数值为61。

注意：请勿改主动函数main和其他函数中的任何内容，仅在函数fun的花括号中填入你编写的若干语句。

```c
#include<conio.h>
#include<stdio.h>
#include<stdlib.h>
#define  M  4
#define  N  5

int fun( int a [M][N])
{
/**********Program**********/



/**********  End  **********/
}
void main()
{
        
        int aa[M][N]={{1,3,5,7,9},{2,9,9,9,4},{6,9,9,9,8},{1,3,5,7,0}};
        int i, j, y;
        system("CLS");
        printf ("The original data is :\n ");
        for(i=0; i<M;i++)
        {
                for (j=0; j<N;j++) 
                        printf("%6d ",aa[i][j]);
                printf("\n ");
        }
        y=fun(aa);
        printf("\nThe sun: %d\n ",y);
        printf("\n ");
}
```

**【题目-48】【程序设计】题目：输入一个正整数 repeat (0<repeat<10)，做 repeat 次下列运算：输入一个正整数 n，输出 2/1＋3/2＋5/3＋8/5＋……前n项之和，保留2位小数。(该序列从第2项起，每一项的分子是前一项分子与分母的和，分母是前一项的分子)**

输入输出示例：括号内是说明

输入

3        (repeat=3) 

1        (n=1) 

5        (n=5) 

20       (n=20) 

输出

sum = 2.00           (第1项是2.00)

sum = 8.39           (前5项的和是8.39)

sum = 32.66          (前20项的和是32.66)

```c
#include <stdio.h>
void main( )
{
    int i, n;
    int repeat, ri;
    double denominator, numerator, sum, temp;

    scanf("%d", &repeat);
    for(ri = 1; ri <= repeat; ri++)
    {
        scanf("%d", &n);

        /**********Program**********/



        /**********  End  **********/

             printf("sum = %.2f\n",sum);
   }
}
```


**【题目-49】【程序设计】题目：编程从键盘输入一个字符串和一个字符，统计该字符串中指定字符出现的次数。**
```c
#include <stdio.h>
#include <string.h>
void main()
{        
        char str[100],c;
        int i=0,count=0;
        printf("请输入一个字符串：");
        gets(str);
        printf("请输入指定的查找字符：");
        scanf("%c",&c);

       /**********Program**********/



       /**********  End  **********/

        printf("%d\n",count);
}
```


**【题目-50】【程序设计】题目：主函数main()中字符串a，b为测试数据，字符串a中字符已按ASCII码值降序排列，将字符串b中ASCII码为偶数的字符依次插入到字符串a中，使字符串a中字符仍按ASCII码值降序排列。再删除字符串a中的重复字符，使相同字符只出现一次。**

编写程序：

1、编写void insert(char a[],char b[])函数，按上述规则将字符串b中字符插入到字符串a中。

2、编写 void del(char a[])函数，删除字符串a中的重复字符，使相同字符只出现一次。

注意：请勿改动主函数main()中的任何语句。
```c
#include<stdio.h>
#include<stdlib.h>
#include<conio.h>
#include<ctype.h>
#include<math.h>
void insert(char a[],char b[])
{
/**********Program**********/



 
/**********  End  **********/
}

void del(char a[])
{
/**********Program**********/



 
/**********  End  **********/
}

void main(){
    char a[30]="9777532";
    char b[10]= "987645231";
    FILE *fp;
    if((fp=fopen("data.txt","w"))==NULL)
    {
        printf("File open error\n");
        exit(0);
    }
    insert(a,b);
    fprintf(fp,"After insterting:");
    printf("After insterting:");
    fprintf(fp,"%s\n",a);
    printf("%s\n",a);
    del(a);
    fprintf(fp,"After deleting:");
    printf("After deleting:");
    fprintf(fp,"%s\n",a);
    printf("%s\n",a);
    fclose(fp);
}
```

### <span id="指针">指针</span>  

**【题目-51】【程序填空】题目：使用指向变量的指针编写交换两个变量值函数，按主调函数的调用形式编写。**
```c
void swap();
void main()
{  int x,y;
   printf("输入两个整数 x,y \n");
   scanf("%d%d",&x,&y);
   swap(&x,&y);
   printf("x=%dy=%d",x,y);  }
void swap( int *p , int *q  )
{  int t;
   t=*p;
/***********SPACE***********/
       【?】; 
/***********SPACE***********/
       【?】 ;  }
```


**【题目-52】【程序填空】题目：给定程序中，函数fun的功能是：调用随机函数产生20个互不相同的整数放在形参a所指数组中(此数组在主函数中已置0)。**
```c
#include  <stdlib.h>
#include  <stdio.h>
#define   N  20

void  fun( int  *a)
{ 
        int  i, x, j=0;
        x=rand()%20;
/***********SPACE***********/
        while (j<【?】)
        {  
                for(i=0; i<j; i++ )
                        if( x==a[i] ) 
/***********SPACE***********/
                                【?】;
/***********SPACE***********/
                if( i==【?】)
                { 
                        a[j]=x; 
                        j++; 
                }
                x=rand()%20;
        }
}
main()
{ 
        int  x[N]={0} ,i;
        fun( x );
        printf("The result :  \n");
        for( i=0; i<N; i++ )
        {
                printf("%4d",x[i]);
                if((i+1)%5==0)
                        printf("\n");
        }
        printf("\n\n");
}
```


**【题目-53】【程序改错】功能：输入一个字符串，过滤此串，滤掉字母字符，并统计新生成串中包含的字符个数。**

例如：输入的字符串为ab234$df4，则输出为： 

The new string is 234$4  

There are 5 char in the new string.
```c
#include <stdio.h>
#include <conio.h>
#define N 80

int fun(char *ptr)
{
  int i,j;
  /**********FOUND**********/
  for(i=0,j=0;*(ptr+i)!="\\0";i++)
    /**********FOUND**********/
    if(*(ptr+i)>'z'|| *(ptr+i)<'a'||*(ptr+i)>'Z' || *(ptr+i)<'A')
    {
      /**********FOUND**********/
      (ptr+j)=(ptr+i);
      j++;
    }
  *(ptr+j)='\0';
  return(j);
}

main()
{
  char str[N];
  int s;
  printf("input a string:");gets(str);
  printf("The original string is :"); puts(str);
  s=fun(str);
  printf("The new string is :");puts(str);
  printf("There are %d char in the new string.",s);
}
```


**【题目-54】【程序设计】题目：编写函数fun,其功能是：将a、b两个两位正整数合并成一个新的整数放在c中。合并的方式是：将a中的十位和个位数依次放在变量c的千位和十位上,b中的十     位和个位数依次放在变量c的个位和百位上。**

例如：当a=45,b=12,调用该函数后c=4251。  
注意：请勿改动主函数main和其它函数中的任何内容，仅在函数fun的花括号中填入你编写的若干语句。

```c
#include <stdio.h>

void fun(int a, int b, long *c)
{
/**********Program**********/


/**********  End  **********/
}
void main()
{  
        int  a,b; long  c;
        printf("Input a, b:");
        scanf("%d%d", &a, &b);
        fun(a, b, &c);
        printf("The result is: %ld\n", c);
}
```
