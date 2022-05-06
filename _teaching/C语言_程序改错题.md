### 【程序改错1】
**题目：列程序的功能为：已知圆锥半径r和高h，计算圆锥体积v。请纠正程序中存在错误，
      使程序实现其功能。**
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
**题目：下列程序的功能为：按下列公式计算并输出x的值。其中a和b的值由键盘输入。
      请纠正程序中存在的错误，使程序实现其功能。公式： x=2ab/(a+b)^2(平方)**
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
**功能：以下程序能求出1\*1+2\*2+......+n\*n<=1000中满足条件的
      最大的n,输出格式如n=37。**
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

