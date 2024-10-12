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


shell 自动化处理的工具
创建shell文件   vim run.sh
#!/bin/bash      //开头
中间   往里面写自动化东西  终端的命令可以写
最后   保存退出

！！！赋权 chmow +x run.sh  //现在run.sh会变成绿色

运行  ./run.sh  source run.sh  sh run.sh  三选一

保留小数点数字
	cout<<fixed<<setprecision(2);

	//判断闰年的标准  能被400整除　或者　能被4整除但不能被100整除 这两个有一个可以，就是闰年
	n % 400 == 0 || (n % 4 == 0 && n % 100 != 0) 


//[0] [1] [2]
//数组的下标从0开始
// 水果 h[20];					   0  1  2  3  4  位置 
// int a[10];      a[2]=4;  a---> [] [] [] [] []
									    4  

										// int a[3];    // [][][]
	// int b[3][3];        //[1][2][3]   b[0][0];
	                    //[4][5][]   
						//[][][9]
	// int k=1;
	// for(int i=0;i<3;i++)
	// {
	// 	for(int j=0;j<3;j++)
	// 	{
	// 		b[i][j]=k;
	// 		k++;
	// 		cout<<b[i][j];
	// 	}
	// 	cout<<endl;
	// }

	倒序输出
	string si;
	cin>>si;
	 string::reverse_iterator riter = s1.rbegin();
    for( ; riter < s1.rend() ; riter++)
    {
        cout<<*riter;
    }
    cout<<endl;
	排序
	    sort(si.begin(),si.end());
	获得长度
		si.length()



	存好多数字字符

	string a;
	cin>>a;

    开平方
	sqrt(a);

	如果能被除了1和它本身的数整除，就不是素数

	 alt+shift+f自动对齐





git 学习	
