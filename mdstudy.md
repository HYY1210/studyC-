# 文件的创建，编译运行

创建cpp文件：
    vim 文件名.cpp
保存退出；
    先按esc,再:(要在英文模式下),再wq!
编译运行；
    g++ 文件名.cpp -o 新文件名     # -o 后面生成：可执行文件的文件名

#创建文件夹
mkdir 文件夹名
#删除文件夹
rmdir 文件夹名  //前提是此文件夹是空的
#删除单个文件
rm 文件

# shell 自动化处理的工具

创建shell文件   vim run.sh

```shell
#!/bin/bash  
```

​    //开头
中间   往里面写自动化东西  终端的命令可以写
最后   保存退出

```
！！！赋权 chmow +x run.sh  //现在run.sh会变成绿色

运行  ./run.sh  source run.sh  sh run.sh  三选一

保留小数点数字
    cout<<fixed<<setprecision(2);

​    //判断闰年的标准  能被400整除　或者　能被4整除但不能被100整除 这两个有一个可以，就是闰年
​    n % 400 == 0 || (n % 4 == 0 && n % 100 != 0) 

//[0] [1] [2]
//数组的下标从0开始
// 水果 h[20];                       0  1  2  3  4  位置 
// int a[10];      a[2]=4;  a---> [] [] [] [] []
                                        4  

​                                        // int a[3];    // [][][]
​    // int b[3][3];        //[1][2][3]   b[0][0];
​                           //[4][5][]   
​                           //[][][9]
​    // int k=1;
​    // for(int i=0;i<3;i++)
​    // {
​    //  for(int j=0;j<3;j++)
​    //  {
​    //      b[i][j]=k;
​    //      k++;
​    //      cout<<b[i][j];
​    //  }
​    //  cout<<endl;
​    // }

​    倒序输出
​    string si;
​    cin>>si;
​     string::reverse_iterator riter = s1.rbegin();
​    for( ; riter < s1.rend() ; riter++)
​    {
​        cout<<*riter;
​    }
​    cout<<endl;
​    排序
​        sort(si.begin(),si.end());
​    获得长度
​        si.length()



​    存好多数字字符

​    string a;
​    cin>>a;

​    开平方
​    sqrt(a);

​    如果能被除了1和它本身的数整除，就不是素数

​     alt+shift+f自动对齐
```





# git 学习  

git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/HYY1210/studyC-.git
git push -u origin main



# 排序

setfill('0')单引号里面是填充的内容

setw(6)括号里面是有几位数字

 cout << setfill('0') << setw(6) << b[i] << endl;

# 进入阅读模式

网站前面加上read:

# 斐波那契数列

**从第三项开始，每一项都等于前两项之和**。

每对兔子每个月可以生一对小兔，而小兔经过一个月生长后也可每月生一对小兔。这种增长模式符合斐波那契数列的定义：

- 第一个月有1对兔子；
- 第二个月有1对兔子；
- 从第三个月开始，每个月的兔子对数等于前两个月兔子对数的和。

斐波那契数列的递推公式为：

F(n)=F(n−1)+F(n−2)*F*(*n*)=*F*(*n*−1)+*F*(*n*−2)

其中 F(1)=1*F*(1)=1，F(2)=1*F*(2)=1。

我们需要计算第 x*x* 个月的兔子对数，记作 F(x)*F*(*x*)。



# 数组插入字符

  // cin >> x;   // 插入的位置 

  // cin >> y;   // 插入的元素 

  // x--;   // 插入的位置修改为下标

  

  // for(i = n - 1 ; i >= x ; i--){

  //  a[i + 1] = a[i];

  // }

  

  // a[x] = y;

  

  // n++;

  

  // for(i = 0 ; i < n ; i++){

  //  cout << a[i] << " ";

  // }



string s;

getline(cin,s);//输入一个含空格的字符串

string s1,s2;

s1.insert(1,s2);//把s2插到s1的1位置后面

![image-20241114192803091](C:\Users\20747\AppData\Roaming\Typora\typora-user-images\image-20241114192803091.png)





#  set学习

**begin()   　　 ,返回set容器的第一个元素**

**end() 　　　　 ,返回set容器的最后一个元素**

**clear()  　　   ,删除set容器中的所有的元素**

**empty() 　　　,判断set容器是否为空**

**max_size() 　 ,返回set容器可能包含的元素最大个数**

**size() 　　　　 ,返回当前set容器中的元素个数**

**rbegin　　　　 ,返回的值和end()相同**

**rend()　　　　 ,返回的值和rbegin()相同**



# min max

`int` 正无穷： `0x7fffffff` = 2147483647。

`int` 负无穷： `0x80000000` = -2147483648。

一般常用 `0x3f3f3f3f` 表示正无穷。



# 保留小数

cout<<fixed<<setprecision(2)
    printf("%.2lf\n",avrrage);

# **三元运算符 `? :`**：

- 这是一个条件运算符，格式为 `condition ? true_expression : false_expression`。
- 如果 `condition` 为真，则返回 `true_expression` 的值；否则返回 `false_expression` 的值。

**条件部分 `y ? ... : ...`**：

- 这里的条件是 `y`。如果 `y` 不为0，则条件为真；如果 `y` 为0，则条件为假。



# 最大公约数

1. **递归调用 `gcd(y, x % y)`**：
   - 这是递归调用的部分，表示继续计算 `y` 和 `x % y` 的最大公约数。
   - `x % y` 是 `x` 除以 `y` 的余数。
2. **终止条件**：
   - 当 `y` 为0时，递归终止，返回当前的 `x`，因为此时 `x` 就是两个数的最大公约数。

# **`const`**: 

1. 这是一个关键字，用于声明一个常量。一旦被初始化后，这个常量的值就不能被修改。

# 1e3

 是科学计数法的一种表示方式，在 C 语言中常用于表示较大的整数。



#  if (a[i]) // 如果a[i]不为0，表示数字i出现过*

![image-20250117143416501](C:\Users\20747\AppData\Roaming\Typora\typora-user-images\image-20250117143416501.png)

意思是把a[0]到a[a+n]从大到小排序，n以后的顺序不变



# 类型

  int n               ->   printf("%d",&n)

​          long long n    ->  printf("%lld",&n)

​           float a            -> printf("%f",&a)

​           double b        -> printf"%lf",&b)

​           char c              -> printf("%c",&c)

# continue  结束本层循环

break 退出本层循环

符号常量 ：const int N=20  不可更改

![image-20250120095304478](C:\Users\20747\AppData\Roaming\Typora\typora-user-images\image-20250120095304478.png)





# 矩阵阶乘，加速

## 计时代码  

```c++
auto start = std::chrono::high_resolution_clock::now();//计时开始
auto end = std::chrono::high_resolution_clock::now();//计时结束
std::chrono::duration<double> duration = end - start;//计算用了多少时间
std::cout << "Elapsed time: " << duration.count() << " seconds" << std::endl;//输出用了多少时间
```

## 优化加速

	  #pragma GCC optimize(3,"Ofast","inline")//加速
	   
	   
	   for(int i=0;i<n;i++)
		  {
		  for(int j=0;j<n;j++)
		  {
		  int b=0;
		  for(int k=0;k<n;k++)
		  {
	  
	  
	  b+=p[i*n+k]*q[k*n+j];
	
	  }
	  c[i*n+j]=b;
	
	  }
	
	  }
	/****注釋的要更慢，因爲每計算一次就賦值更麻煩
	for(int i=0;i<n;i++)
	{
		for(int j=0;j<n;j++)
		{
			
			for(int k=0;k<n;k++)
			{
	
				c[i*n+j]+=p[i*n+k]*q[k*n+j];
	
			}
		}
	
	}
	*/
	
	

## 宏定义

```c++
在运行的时候，如果没有加上-DDEBUG就不会运行在他们中间的代码
#ifdef DEBUG//DEBUG可以改成任何东西比如hyy 就该在编译的时候加上 —Dhyy
#endif
```



```cpp
#include<bits/stdc++.h>
#include <chrono>
//#pragma GCC optimize(3,"Ofast","inline")//加速
using namespace std;
const int n=1024;
int main()
{
	int *p;
	p=(int *)malloc(n*n*sizeof(int));
	int *q;
	q=(int *)malloc(n*n*sizeof(int));
	int *c;
	c=(int *)malloc(n*n*sizeof(int));
	for(int i=0;i<n;i++)
	{
		for(int j=0;j<n;j++)
		{
			p[i*n+j]=1;
			q[i*n+j]=1;
			c[i*n+j]=0;
		}
	}
	auto start = std::chrono::high_resolution_clock::now();//计时开始

	  for(int i=0;i<n;i++)
	  {
	  for(int j=0;j<n;j++)
	  {
	  int b=0;
	  for(int k=0;k<n;k++)
	  {

	  b+=p[i*n+k]*q[k*n+j];

	  }
	  c[i*n+j]=b;

	  }

	  }
	/****
	for(int i=0;i<n;i++)
	{
		for(int j=0;j<n;j++)
		{
			
			for(int k=0;k<n;k++)
			{

				c[i*n+j]+=p[i*n+k]*q[k*n+j];

			}
			

		}

	}
	*/
	auto end = std::chrono::high_resolution_clock::now();//计时结束
	std::chrono::duration<double> duration = end - start;//计算用了多少时间
#ifdef DEBUG
	for(int i=0;i<8;i++)
	{

		for(int j=0;j<8;j++)
		{
			cout<<c[i*n+j]<<" ";
		}
		cout<<endl;
	}
	std::cout << "Elapsed time: " << duration.count() << " seconds" << std::endl;//输出用了多少时间
#endif
	return 0;
}


```

