### 编译原理课程设计之一（简单C编译器设计）

基于龙书附录代码，在此基础上进行添油加醋

- 增添四元式，三元式产生
  
 **本项目报告因为工作量过大因此只提供pdf版本，如有需要请联系我**  
目前而言实现的C语言是if,if-else,if-else if-else,do-while,while,for语句，数组的简单操作，普通语句的表示，以及break语句  


### 进度
2020.4.15 完成龙书代码的整体copy  
2020.4.18 完成Java Servlet的基础学习  
2020.4.19 完成第课设网页主界面的设计以及“C编译器实现”界面的前后端交互      
2020.4.21 开始改编代码，第一个目标:添加四元式的产生，备份代码  
2020.6.21 完成四元式的基本构造  
2020.7.1 修复了一些四元式的bug 
2020.8.1 增添了for语句的编译(递归下降)  
2020.8.10 完成了GUI的实现，并将三地址代码和四元式由控制台输出转为GUI输出  
2020.8.21 修复了若干个已知bug  
2020.8.23 完成了测试样例的设计  
2020.8.24 验收  
2020.8.30 完成报告并提交  
2020.9.5 上传代码  


使用说明:src中为源代码文件，由于时间原因并没有完成网页端的开发，只有使用Java Swing完成的简单GUI  
CParser文件夹中为有功能的源代码，main函数位于Main.java中    
  
本C语言简单编译器仅实现了词法分析，语法分析，语义分析和中间代码产生  
产生中间语言包括三地址代码和四元式，目标代码因为时间关系尚未实现  

输入语言格式  
①for语句，输入格式如下  
for(i=0;i<5;i=i+1)  
也就是第一个不能写成for(int i;...),否则会报语法错误，这个是因为时间原因来不及添加更为详细的语法分析，可以自行拓展  

成功测试样例如下  
① 分支语句  
```
{
int a;
int b;
while(a>0)
{
a=1;	
}
if(a<2) 
{
a=4;
}
do
{
a=5;
}while(a>3);

for(a=2;a<5;a=a+1)
{
a=a+1;
if(a<5)
{
break;
}
else if(a>5)
{
a=2;
}
else{
a=4;
}
}
}
}
}
```

②复杂布尔表达式
```
  {
 int a;
 int b;
 int c;
 a=2; b=4; c=43;
   if(a<b&&a==b&&a<=b&&a>=b&&a>b)
 {
	c=7;
 }
 else {
    c=5;
 }
 }
 }
 ```
 
 ③冒泡排序程序
 ```
 { 
int i;
int j;
int g;
int n;
int temp;
int [15] arr;
n=10;
g=53;
for(i=0;i<n-1;i=i+1)
{
	for(j=i;j<n;j=j+1)
	{
		if(arr[i]>arr[j])
		{
			temp = arr[i];
			arr[i] = arr[j];
			arr[j] = temp;
		}
	}
 }
 }
 }
 
 ```
 
