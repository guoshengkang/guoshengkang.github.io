### C Programming Experiments
## **Chapter 6**
#### 【2020/**/**】用带参数的main( )函数实现两个字符串的连接。
```c
#include <stdio.h>
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