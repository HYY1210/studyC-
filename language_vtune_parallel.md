# 更改系统语言

打开设置，搜索语言，把英文更改成中文，再把键盘输入加入中文。

# 循环展开(没加-O3)

```c++
#include<bits/stdc++.h>
using namespace std;
int main()
{
    int sum = 0;
    int count=100000;
    auto start = std::chrono::system_clock::now();
    /***************未循环展开******************/
    for(int i = 0;i < count;i++){  
        sum += i;
    }
    				//71到171ms
     /***************循环展开******************/
     for(int i = 0;i < count;i+=4){  
        sum += i;
		sum+=i+1;
		sum+=i+2;
		sum+=i+3;
    }
    				//39到167ms
    /*********************************/
    auto end = std::chrono::system_clock::now();
    auto dura = std::chrono::duration_cast<std::chrono::microseconds> (end - start);
    cout <<" cost time: "<< dura.count() << " microseconds" << std::endl;
    cout<<sum;
	
	return 0;
}
```

### 原因：

​	1：取数字和写回数字慢

​	2:三级缓存机制

```shell
lscpu:
Caches (sum of all):      
  L1d:                    544 KiB (14 instances)
  L1i:                    704 KiB (14 instances)
  L2:                     11.5 MiB (8 instances)
  L3:                     24 MiB (1 instance)

```



# VTUNE性能分析

### 1.先装oneapi

因为VTUNE包含在oneapi开发套件中，属于开发套间的一个部分。

```shell
wget https://registrationcenter-download.intel.com/akdlm/irc_nas/17769/l_BaseKit_p_2021.2.0.2883.sh
sudo bash l_BaseKit_p_2021.2.0.2883.sh

```

官方网站：

​	https://www.intel.com/content/www/us/en/developer/tools/oneapi/base-toolkit-download.html?packages=oneapi-toolkit&oneapi-toolkit-os=linux&oneapi-lin=online

### 2.存在问题及解决方案

oneapi套件的版本为2021,本地使用的ubuntu是24.04，因此导致无法正常使用。

如何解决:

​	更换oneapi版本为2024，后编译系统需要的内核支持(if 不编译，会出现未知问题)

```shell
cd  /opt/intel/oneapi/vtune/latest/sepdk/src
sudo ./build-driver
```

3.打开

vtune-gui

# Typora

```shell
wget https://download2.typoraio.cn/linux/typora_1.8.10_amd64.deb
sudo dokg -i typora_1.8.10_amd64.deb
git clone https://github.com/hazukieq/Yporaject.git
#1.使用官方脚本安装
 curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

#2.检查cargo是否安装
sudo apt install cargo
 cargo --version
#cargo 1.65.0
# cd Yporaject

#1.编译
 cargo build

#2.查看在target中是否生成：node_inject
# ls target/debug

#3.执行以下命令
 cargo run
 sudo cp target/debug/node_inject /usr/share/typora
 cd /usr/share/typora
 sudo chmod +x node_inject
 sudo ./node_inject
 cd Yporaject/license-gen

#1.编译生成激活码的代码
 cargo build

#2.生成激活码
 cargo run
#output:
#    Finished dev [unoptimized + debuginfo] target(s) in 0.00s
#     Running `target/debug/license-gen`
#License for you: xxxxxx-xxxxxx-xxxxxx-xxxxxx

```

OPENMP

```c++
#include <bits/stdc++.h>
#include <omp.h>
using namespace std;
int main()
{
    omp_set_nested(1);
#pragma omp parallel for
   for(int i=0;i<2;i++)
   {
        int outer_thread=omp_get_thread_num();
        #pragma omp parallel for
        for(int j=0;j<4;j++)
        {
            int inner_thread=omp_get_thread_num();
            printf("Hello(int i=%d j=%d)\n",outer_thread,inner_thread);
        }
   }

    return 0;
}
```

```shell
g++ h.cpp -o h -fopenmp -O3 -DDEBUG
./h
```

