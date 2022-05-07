### 【程序改错1】
**题目：列程序的功能为：已知圆锥半径r和高h，计算圆锥体积v。请纠正程序中存在错误，使程序实现其功能。**
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
### 【程序改错1】
**题目：下列程序的功能为：按下列公式计算并输出x的值。其中a和b的值由键盘输入。请纠正程序中存在的错误，使程序实现其功能。公式： x=2ab/(a+b)^2(平方)**
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

### 【程序改错1】
**功能：输入一个圆的半径，计算圆的周长和面积并输出。**
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

### 【程序改错1】
**功能：写计算级数 ex=1+x+x^2/2!+x^3/3!+ ...+x^n/n! 的值。**
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

### 【程序改错1】
**功能：以下程序能求出1\*1+2\*2+......+n\*n<=1000中满足条件的最大的n,输出格式如n=37。**
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

### 【程序改错1】
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

### 【程序改错1】
**功能：求二分之一的圆面积，函数通过形参得到圆的半径，函数返回二分之一的圆面积。**

**例如：输入圆的半径值：19.527 输出为：s = 598.950017。**
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

### 【程序改错1】
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

### 【程序改错1】
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
### 【程序改错1】
**调用优化的sort函数，完成对数组a的冒泡降序排序。下面给定的程序存在错误，请改正。**

**注意：不得增行或删行，也不得更改程序的结构。**

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

### 【程序改错1】
**在主函数中从键盘输入若干个数放入数组中，用0结束输入并放在最后一个元素中。下列给定程序中，函数fun()的功能是计算数组元素中值为负数的平均值（不包括0）。

**例如：数组中元素的值依次为43，-47，-21，53，-8，12，0，则程序的运行结果为-25.333333。**

**请改正程序中的错误，使它能得到正确结果。**

**注意：不要改动main函数，不得增行或删行，也不得更改程序的结构。**

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
