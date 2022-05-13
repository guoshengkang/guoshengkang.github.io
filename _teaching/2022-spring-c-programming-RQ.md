## 输入/输出语句

**【程序填空】题目：下列程序从键盘输入所需数据，求出z的值并输出，要求输出结果保留2位小数。**

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

**【程序改错】题目：列程序的功能为：已知圆锥半径r和高h，计算圆锥体积v。请纠正程序中存在错误，使程序实现其功能。**
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
### 
**【程序改错】题目：下列程序的功能为：按下列公式计算并输出x的值。其中a和b的值由键盘输入。请纠正程序中存在的错误，使程序实现其功能。公式： x=2ab/(a+b)^2(平方)**
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

**【程序改错】功能：输入一个圆的半径，计算圆的周长和面积并输出。**
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


---------------------------------------------------------

**【程序设计】题目：求华氏温度 150°F 对应的摄氏温度。计算公式：c = (5/9)\*f-(5/9)\*32，式中：c表示摄氏温度，f表示华氏温度。**

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

## 控制结构

**【程序填空】功能：将字母转换成密码，转换规则是将当前字母变成其后的第四个字母，但W变成A、X变成B、Y变成C、Z变成D。小写字母的转换规则同样。**
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
**【程序填空】**题目：输入x、y两个整数，按先大后小的顺序输出x、y。**
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

**【程序改错】功能：写计算级数 ex=1+x+x^2/2!+x^3/3!+ ...+x^n/n! 的值。**
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

**【程序改错】功能：以下程序能求出1\*1+2\*2+......+n\*n<=1000中满足条件的最大的n,输出格式如n=37。**
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

**【程序设计】题目：输入正整数m和n（设100≤m≤n≤999），输出m到n之间满足下列条件的三位数：它的个位数的立方加十位数的平方再加上百位数等于该数的本身（例如135＝1＋3\*3＋5\*5\*5）。**

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

**【程序设计】题目：从键盘输入实数x，按照所示的公式计算并输出y值：**
https://latex.codecogs.com/svg.image?y=\left\{\begin{matrix}&space;2&plus;\sqrt{x}&&space;x>7&space;\\5&plus;3x&space;&&space;-7\leqslant&space;x\leqslant&space;7&space;\\&space;3x^{2}&&space;x<&space;-7&space;\\\end{matrix}\right.
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

## 函数
### 【程序改错6】
**功能：输入两个实数，按代数值由小到大输出它们,并在fun()函数中输出。（输出的数据都保留2位小数）**
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

### 【程序改错7】
**功能：求1到10的阶乘的和。**
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

### 【程序改错8】
**题目：函数fun的功能是：求1到20的阶乘的和。请改正程序中的错误，使它能得出正确的结果。**

注意：不可以增加或删除程序行，也不可以更改程序的结构。

```c   
fun()
{ 
  int n,j;
  float s=0.0,t=1.0;
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

### 【程序改错9】
**功能：求二分之一的圆面积，函数通过形参得到圆的半径，函数返回二分之一的圆面积。**

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

### 【程序改错10】
**功能：根据整型形参m，计算如下公式的值：y=1/2＋1/8＋1/18＋...＋1/(2m\*m)**
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
     y=+1.0/(2*i*i); 
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

### 【程序改错11】
**题目：下列给定程序中函数fun的功能是：计算函数F(x，y，z)＝(x＋y)/(x－y)＋(z＋y)/(z－y)的值。其中x和y的值不相等，z和y的值不相等。**

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
## 数组
### 【程序改错12】
**功能：在一个一维整型数组中找出其中最大的数及其下标。**
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

### 【程序改错13】
**功能：利用二维数组输出如图所示的图形。**

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
### 【程序改错14】
**调用优化的sort函数，完成对数组a的冒泡降序排序。下面给定的程序存在错误，请改正。**

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

### 【程序改错15】
**在主函数中从键盘输入若干个数放入数组中，用0结束输入并放在最后一个元素中。下列给定程序中，函数fun()的功能是计算数组元素中值为负数的平均值（不包括0）。**

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

### 【程序改错16】
**题目：fun函数的功能是：先从键盘上输入一个3行3列矩阵的各个元素的值，然后输出主对角线上的元素之和sum。请改正程序中的错误，使它能得出正确的结果。**

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

### 【程序改错17】
**题目：fun函数的功能是：在任意给定的N个正整数中，从左到右依次逐个取三个数作为一组，按值大小找出该组数的中值，用该中值替换与该组数对应的原三个数中的中间位置的数。处理后原数列中首尾2个数不变。处理后数列在主函数中输出。**

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

### 【程序改错18】
**功能：输入一个字符串，过滤此串，滤掉字母字符，并统计新生成串中包含的字符个数。**

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
