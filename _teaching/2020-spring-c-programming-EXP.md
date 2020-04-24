### C Programming Experiments
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
## **Chapter 6**
#### 【实验】用带参数的main()函数实现两个字符串的连接。
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