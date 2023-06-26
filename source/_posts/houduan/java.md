---
title: JAVA
tags:
  - Java
---
**本文作者** [fllow_wind](https://blog.csdn.net/fllow_wind?type=blog)

笔记参考来源狂神说Java视频[https://www.bilibili.com/video/BV12J41137hu](https://www.bilibili.com/video/BV12J41137hu)  
本篇笔记有点长，可以根据目录定位，建议配合视频学习。

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)预科
=============================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)什么是计算机
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1.  名称：Computer，全称电子计算机，俗称电脑。
2.  定义：能够按照程序运行，自动、高速处理海量数据的现代化智能电子设备。
3.  组成：由硬件和软件组成。
4.  形式：常见显示有台式计算机、笔记本计算机、大型计算机等。
5.  应用：科学计算、数据处理、自动控制、计算机辅助设计、人工智能、网络等领域。

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)硬件及冯诺依曼结构
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)计算机硬件

组成：cpu，主板，内存，电源，主机箱，硬盘，显卡，键盘、鼠标，显示器。

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)冯诺依曼结构

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427081055529.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)软件及软件开发
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)计算机软件

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Windows常用快捷键
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Alt+f4关闭窗口 Shift+Delete永久删除 ctrl+w自动保存

死机：任务管理器结束进程

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)基本的Dos命令
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

打开CMD的方式

1.  开始+系统+命令提示符
2.  win键+R+输入cmd (推荐使用)
3.  在任意的文件夹下，按住Shift键+鼠标右击，打开命令行窗口
4.  在资源管理器地址栏路径前面加 “cmd ”
5.  管理员运行方式：命令提示符右键以管理员身份运行（最高权限运行）

常用的Dos命令

```
# 盘符切换 E:
# 查看当前目录下所有文件 dir
# 切换目录 cd /d E:\idea
# 返回上一级目录 cd ..
# 进入同级目录下的下一级目录 cd tmp(该目录下的文件名)
# 清屏 cls (clear screen)
# 退出终端 exit
# 查看电脑当前IP地址 ipconfig

# 打开计算器 calc
# 打开画图 mspaint
# 新建记事本 notepad

# 在当前目录新建文件夹 md test(文件夹名)
# 新建文件 cd> a.txt(文件名)
# 删除文件 del a.txt(文件名)
# 删除目录 rd test(目录名)

# ping命令(复制链接进入Dos直接单击鼠标右键粘贴)
	ping www.baidu.com

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)计算机语言发展史
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   第一代语言：机器语言
*   第二代语言：汇编语言
*   第三代语言：高级语言

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)高级语言

C、C++、Java、C#、Python、PHP、JavaScript …

大体上分为：**面向过程**与**面向对象**两大类

*   C语言是典型的**面向过程**的语言，C++，Java是典型的**面向对象**的语言

* * *

* * *

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Java入门
=================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Java帝国的诞生
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427081209316.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427081218160.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Java特性与优势
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   简单性
*   面对对象
*   可移植性
*   高性能
*   分布式
*   多态性
*   多线程
*   安全性
*   健壮性

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Java三大版本
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   Write Once，Run Anywhere

*   **JavaSE**: 标准版 (桌面程序，控制台开发…)
*   JavaME: 嵌入式开发 (手机，小家电…)，已经凉了
*   **JavaEE**: E企业级开发 (Web端，服务端开发…)，JavaSE为基础

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)JDK JRE JVM
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   JDK：Java Development Kit (Java开发者工具，包括 JRE，JVM)
*   JRE：Java Runtime Environment (Java运行时环境)
*   JVM：Java Virtual Machine (Java虚拟机，跨平台核心)

![](https://img-blog.csdnimg.cn/20210427081317290.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)安装开发环境
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)卸载JDk

1.  删除Java安装目录
2.  删除环境变量JAVA\_HOME
3.  删除path下关于JAVA的目录
4.  Java -version

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)安装JDK

1.  百度搜索JDK8，找到下载地址
2.  同意协议，下载电脑对应的版本，如64位操作系统下载 jdk-8u281-windows-x64.exe
3.  双击安装JDK
4.  记住安装路径
5.  配置环境变量
    1.  我的电脑-》属性-》系统高级设置-》环境变量
    2.  系统变量 新建–> JAVA\_HOME 输入对应的jdk安装路径
    3.  path变量–>% JAVA\_HOME%\\bin
6.  测试是否成功 cmd–>Java -version

* * *

* * *

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Java基础
=================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)注释
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1.  单行注释 //
2.  多行注释 /\* \*/
3.  文档注释 /\*\* \*/

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)标识符和关键字
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   Java 所有的组成部分都需要名字。类名、变量名、方法名都被称为**标识符**

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)关键字

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042708142877.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)标识符注意点

*   所有标识符都应该以 字母、$(美元符)、\_(下划线) 开头
*   首字母之后可以是 字母、$、\_ 或数字任何字符组合
*   **关键字不能作为变量名或方法名**
*   标识符**大小写敏感**
*   **可以用中文命名，但不建议使用**，即使用拼音命名也Low

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)数据类型
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   **强类型语言**
    
    *   要求变量的使用要严格符合规定，所有变量都必须先定义后才能使用
*   弱类型语言：JavaScript，Python
    
*   Java的数据类型分为两大类
    
    *   **基本类型**（primitive type），有8大基本类型，此外都是引用类型
    *   **引用类型**（reference type）

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427081748164.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

```
//整数
int num1 = 10; //最常用，只要别超过21亿（2^31-1）
byte num2 = 20; //-128~127
short num3 = 30;
long num4 = 30L; //long类型数字后面要加个L(尽量用大写，小写l容易与1搞混)

```
```
//小数：浮点数
float num5 = 50.1F; //float类型数字后面要加个F
double num6 = 3.141592653589793238;

```
```
//字符
char name = '国';
//字符串, String不是关键字，是类
//String namea = "薛之谦";

```
```
//布尔值：是非
boolean flag = true

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)什么是字节

*   位(bit)：是计算机内部数据存储的最小单位，11001100是一个八位二进制数
*   字节(byte, B)：是计算机中 数据处理 的基本单位，习惯上用大写B表示
*   1B(byte) = 8bit，1字节等于8位
*   字符：指计算机中使用的字母，数字，字和符号
    *   1bit表示1位
    *   1Byte表示一个字节 1B=8b
    *   1024B = 1KB, 1024KB = 1M, 1024M = 1G

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)扩展及面试题

```
//整数扩展： 二进制0b		八进制0		十进制		十六进制0x
int i = 10;
int i2 = 010; //八进制 8
int i3 = 0x10; //十六进制 16

```
```
//浮点数扩展：
//面试题：银行业务字母怎么表示钱? BigDecimal(数学工具类)
//float double是有问题的，最好避免使用浮点数进行比较
float f = 0.1f; 	//0.1
double d = 1.0/10;  //0.1
System.out.println(f==d); //false
//浮点数 位有限，舍入误差，大约
//最好避免使用浮点数进行比较
float f1 = 23131313131f;
float f2 = f1+1;
System.out.println(f1==f2); //true

```
```
//字符扩展：所有字符本质还是数字
char c1 = 'a';
char c2 = '中';

System.out.println(c1);		//a
System.out.println((int)c1);//强制类型转换,97
System.out.println(c2);		//中
System.out.println((int)c2);//强制类型转换,20013

//编码 Unicode表（97=a,65=A）2字节 0-65536
//U000~UFFFF 十六进制（u0061=a,相当于十进制的97）
System.out.println('\u0061');  //a '\'是转义字符

```
```
//布尔值扩展
boolean flag = true;
if(flag==true){} //新手
if(flag){}	//老手这样写 Less is More(代码要精简易读)

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)类型转换
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   由于Java是强类型语言，所以要进行有些运算的时候，需要用到类型转换。
    
*   容量高–>低：  
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427081848182.png)
    
*   运算中，不同类型的数据先转化位同一类型，再进行运算。
    
    *   强制转换，（类型）变量名，容量由高到低
    *   自动转换，容量由低到高

```
//强制转换 （类型）变量名 高--低
//自动转换 低--高
int i = 128;
byte b = (byte)i; //强制转换 内存溢出 -128~127
double d =i; //自动转换

System.out.println(i); //128
System.out.println(b); //-128
System.out.println(d); //128.0
/*
   注意点：
   1.不能对布尔值进行转换
   2.不能把对象类型转换为不相干的类型
   3.在把高容器转换到低容量的时候，强制转换
   4.可能存在内存溢出，或者精度问题
 * */
System.out.println((int)23.7); //23 丢失精度
char c = 'a';
int n = c+1;
System.out.println(n); //98
System.out.println((char)n); //b

```
```
//当操作数比较大时，注意溢出问题
//JDK7新特性，数字之间可以用下划线分割
int money = 10_0000_0000; //10亿，下划线不会被打印出来
System.out.println(money); //1000000000
int years = 20;

int total = money*years;  //数据大，溢出
System.out.println(total); //-1474836480

long total2 = money*years; //默认是int，转换前就有溢出问题
System.out.println(total2); //-1474836480

long total3 = money*(long)years; //先把一个数转Long
System.out.println(total3); //20000000000

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)变量、常量、作用域
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   变量是什么：就是可以变化的量
*   Java是一种强类型语言，每个变量都必须声明其类型
*   Java变量是程序中最基本的存储单元，要素包括变量名，变量类型和作用域

```
//数据类型 变量名 = 值;
type varName [=value][{,varName[=value]}];
//可以使用逗号隔开同多个类型的变量，但不建议在一行定义多个变量

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)变量作用域

*   类变量（static）
*   实例变量
*   局部变量

```
public class Variable{
    static int 	allClicks = 0; //类变量
    String str = "hello world"; //实例变量
    public void method(){
        int i=0; //局部变量
    }
}

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)常量

*   常量：初始化后不能再改变的值，不会变动的值。
*   可以理解为一种特殊的变量，其值被设定后，在程序运行过程不允许被更改。

```
//常量一般用大写字符
final 常量名=值;
final double PI=3.14;

```
```
//修饰符 不存在先后顺序，static可以写final后面
static final doube PI=3.14; //类变量，该类下的全局范围

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)变量的命名规范

*   所有变量、方法、类名：**见名知意**
*   类成员变量：首字母小写+驼峰原则：lastName
*   局部变量：首字母小写+驼峰原则
*   常量：大写字母和下划线：MAX\_VALUE
*   类名：首字母大写+驼峰原则：Man，GoodMan
*   方法名：首字母小写+驼峰原则：run()，fastRun()

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)运算符
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427081956511.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

```
int a=10;
int b=20;
System.out.println(a/b); //0
System.out.println((double)a/b); //0.5

long c=12300000000;
System.out.println(a+b); //int
System.out.println(a+c); //long 自动转换式子中容量大的数据类型

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)自增自减运算符

```
// ++自增 --自减 单目运算符
int a = 3;
int b = a++; //b=a,a=a+1 先赋值 即b=3 a=4
int c = ++a; //a=a+1,c=a 先自增 即a=5 c=5

System.out.println(a); //5
System.out.println(b); //3
System.out.println(c); //5

```
```
//幂运算 2^3 2*2*2=8
double pow = Math.pow(2,3); // (底数，指数)double型
System.out.println(pow); //8.0

```
```
//扩展：笔试题 i=5 s=(i++)+(++i)+(i--)+(--i) s=?
int i=5;
int s=(i++)+(++i)+(i--)+(--i);
System.out.println(s); //24

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)逻辑运算符

*   && 逻辑与运算：两个变量都为真，结果为true
*   || 逻辑与运算：两个变量有一个为真，结果为true
*   ! 取反，真变为假，假变为真

```
// 与(snd) 或(or) 非(取反)
boolean a = true;
boolean b = false;

System.out.println(a&&b); // false
System.out.println(a||b); // true
System.out.println(!(a&&b)); // true

int c=5;
boolean d = (c<5)&&(c++<5); //第一个值为false，后面就不进行判定了
System.out.println(d); //false
System.out.println(c); //5 c++未执行

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)位运算

```
/*
    A = 0011 1100
    B = 0000 1101

    A&B 0000 1101 按位与
    A|B 0011 1101 按位或
    A^B 0011 0001 异或
    ~B  1111 0010 非

    面试题：2*8 怎么算最快？ 2<<3
    <<左移  *2 效率极高！！
    >>右移  /2
   */
System.out.println(2<<3); // 16

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)三元运算符

```
int a = 10;
int b = 20;

a+=b; // a = a+b
a-=b; // a = a-b

System.out.println(a); //10
//字符串连接符 + ，转化为String类型,然后拼接    注意！！
System.out.println(""+a+b); //1020
System.out.println(a+b+""); //30 先进行运算，再转为String拼接
System.out.println(a+b+"str"); //30str

```
```
// x ? y : z
//如果x为真，则结果为y,否则为z
//if(x) y; else z;
int score = 80;
String type = score<60?"及格":"不及格";
System.out.println(type); //及格

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)包机制
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   为了更好地组织类，Java提供了包机制，由于区分类名的命名空间
*   包的语法格式：

```
package pkg1[.pkg2[.pkg3...]];

```

*   一般利用公司域名倒置作为包名；com.kuangstudy.www
    
*   为了能够使用一个包的成员，需要在Java程序中导入该包
    

```
import package1[.package2...].(className|*); //通配符* 导入包下所有的类

```

*   参考：阿里巴巴Java开发手册

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)JavaDoc生成文档
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   javadoc命令是用来生成自己API文档的
    
*   参数信息
    
    *   @author 作者名
    *   @version 版本号
    *   @since 指明最早用的jdk版本
    *   @param 参数名
    *   @return 返回值情况
    *   @throws 异常抛出情况
*   API文档：[https://docs.oracle.com/javase/8/docs/api/](https://docs.oracle.com/javase/8/docs/api/)
    

```
/**
 * @author Kuangshen
 * @version 1.0
 * @since 1.8
 */
public class Demo05 {
    String name;

    /**
     * @author kuangshen
     * @param name
     * @return
     * @throws Exception
     */
    public String test(String name) throws Exception{
        return name;
    }
    
}

```

1.  打开某个类所在文件夹下的cmd命令行
2.  输入：javadoc -encoding UTF-8 -charset UTF-8 Doc(类名).java
3.  会自动生成该类有关的API文档，查看文件夹发现多了一些文件
4.  打开 index.html（首页）查看文档注释

* * *

* * *

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Java流程控制
===================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)用户交互Scanner
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   之前我们学的基本语法并没有实现**程序和人的交互**，Java给我们提供了一个工具类，可以获取用户的输入java.util.Scanner是Java5的新特征，我们通过Scanner类来获取用户的输入。
*   基本语法

```
Scanner s = new Scanner(System.in);

```

*   通过Scanner类的 next()与 nextLine()方法获取用户的字符串，读取前一般用hasNext()与hasNextLine()判断是否还有输入的数据。

```
//创建一个扫描器对象
Scanner scanner = new Scanner(System.in);

System.out.println("使用next方式接收");
//判断用户有没有输入字符串
if(scanner.hasNext()){  //使用hasNextLie()会接收一行 "hello word"
    //使用next方式接收
    String str = scanner.next(); 
    System.out.println("输入的内容为："+str);
    //input: hello word
    //输入的内容为：hello
}
//凡是属于IO流的类如果不关闭会一直占用资源
scanner.close();

```

#### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)next()

1.  一定要读取到有效字符才可以结束输入
2.  对输入有效字符之前遇到的空白，next()方法会将其去掉
3.  只有输入有效字符后才将其后面输入的**空白作为结束符**
4.  **next()不能得到带有空格的字符串**

#### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)nextLine()

1.  以**Enter作为结束符**，即返回输入回车之前所有的字符
2.  **nextLine()可以获取空白**

```
//从键盘接收数据
Scanner scanner = new Scanner(System.in);
System.out.println("请输入数据：");

String str = scanner.nextLine();
System.out.println("输入的内容为："+str);
scanner.close();

```
```
System.out.println("请输入整数：");
if(scanner.hasNextInt()){
    int i=scanner.nextInt();
    System.out.println("输入的整数为："+i);
}else {
    System.out.println("输入的不是整数数据");
}

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)顺序结构
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   Java的基本结构就是顺序结构，除非特别指明，否则就按语句一条一条执行。
*   顺序结构是最简单的算法结构。
*   语句语句之间是按从上到下执行的，它是由若干个依次执行的处理步骤组成的，它是如何一种算法都离不开的一种基本算法结构。

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)选择结构

*   if单选择结构 if( )
*   if双选择结构 if( ){ }else{ }
*   if多选择结构 if( ){ }else if{ }else{}
*   嵌套的if结构 if( ){ if( ) }

```
int a = 80;
if(a>60){
    System.out.println("及格");
    if(a>80) System.out.println("且优秀");
}else if(a>0){
    System.out.println("不及格");
}else {
    System.out.println("缺考");
}

```

#### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)switch多选择结构

```
char grade = 'C'; //JDK新特性 可以是字符串(字符本质还是数字)
switch (grade){
    case 'A':
        System.out.println("优秀");
        break; //可选，跳出当前结构
    case 'B':
        System.out.println("良好");
        break;
    case 'C':
        System.out.println("合格");
        break;
    default: //默认，以上值没匹配到
        System.out.println("不及格");
        break;
}

```

IDEA反编译之后.class文件与源代码对比

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427082240517.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)循环结构
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   **while循环**

```
//计算1+2+3+...+100
int i=0;
int sum=0;
while(i<100){
    i++;
    sum+=i;
}
System.out.println(sum); //5050

```

*   do…while循环

```
//先执行后判断，至少执行一次
do{
    i++;
    sum+=i;
}while(i<100) //跟上面效果一样

```

*   **for循环**

```
//（初始化;条件判断;迭代）
for(int i=0;i<100;i++){
    i++;
    sum+=i;
}
for(; ; ){...} //死循环

```
```
//练习：输出1-1000能被5整除的数，每行输出3个
for (int i = 1; i <= 1000; i++) {
    if(i%5==0){
        System.out.print(i+"\t"); //输出完不换行
    }
    if(i%(3*5)==0){
        System.out.println();
    }
}

```
```
//练习2：输出九九乘法表
for(int i=1;i<=9;i++){
    for(int j=1;j<=i;j++){
        System.out.print(j+"*"+i+"="+i*j+"\t");
    }
    System.out.println();
}

```

#### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)增强for循环

```
int [] numbers = {10,20,30,40,50}; //定义一个数组
for (int x:numbers){
    System.out.println(x); //遍历数组的元素 10 20 30 40 50
}
//相当于
for(int i=0;i<5;i++){
    System.out.println(numbers[i]);
}

```

#### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)break & continue

*   break可用在任何循环的主体部分，由于**强行退出循环**，也可以用在switch语句。
*   continue用于循环语句中，**终止某次循环过程**，跳过剩余语句，之间进行下一次循环条件判断。
*   标签：后面跟一个冒号的标识符 label:

```
//打印101-150之间所有的质数
int count = 0;
outer:for(int i=101;i<=150;i++){
    for (int j=2;j<i/2;j++){
        if(i%j==0)
            continue outer; //不建议使用标签
    }
    System.out.print(i+" ");
}

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)流程控制练习
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

```
//打印等腰空心三角形
/*  例如：输入为4时
          *
         * *
        *   *
       * * * *
*/
Scanner scanner = new Scanner(System.in);
int n = scanner.nextInt(); //n为三角形高
for(int i=1;i<=n;i++){
    for(int j=1;j<=2*n-1;j++){
        if(i!=n){ //若不为最后一行
            if(i+j==n+1)
                System.out.print("*"); //三角形左腰边
            else if(i+j==n+2*i-1)
                System.out.print("*"); //三角形右腰边
            else System.out.print(" ");
        }
        else if(j%2!=0){  //最后一行，底边
            System.out.print("*");
        }else {
            System.out.print(" ");
        }
    }
    System.out.println(); //换行
}

```

* * *

* * *

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Java方法
=================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)方法的定义
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   Java的方法类似与其他语言的函数，是**一段用来完成特定功能的代码片段**。
*   **方法包含一个方法头和一个方法体**。
    *   **修饰符**：可选，定义了方法的访问类型，告诉编译器如何调用该方法。
    *   **返回值类型**：方法可能会返回值。returnValueType是方法返回值的数据类型。有些方法没有返回值，则returnValueType为关键字void。
    *   **方法名**：是方法的实际名称，方法名与参数表共同构成方法签名。
    *   **参数类型**：像一个占位符。方法被调用时，传递值给参数，该值称为实参或变量。参数列表是指方法的参数类型、顺序和参数个数。参数是可选的，方法可以不包含任何参数。
        *   形式参数：在方法被调用时用于接收外界输入的数据。
        *   实参：调用方法时实际传给方法的数据。
    *   **方法体**：方法体包含具体的语句，定义该方法的功能。

```
修饰符 返回值类型 方法名（参数类型 参数名,...）{
   方法体...
   return 返回值；
}

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)方法的调用
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   调用方法：对象名.方法名(实参列表)。
*   Java支持两种调用方法的方式，根据方法是否返回值来选择。
*   **当方法返回一个值的时候，方法调用通常被当成一个值**。

```
int larger = max(30,40);

```

*   如果方法返回值是void，方法调用一定是一条语句。
    
*   扩展：值传递和引用传递 ( **Java都是值传递**)。
    
*   **调用其他类的方法，除非是static静态方法，不然必须实例化这个类(new)**
    

```
public class Demo01 {
   
    public static void main(String[] args) {
        int add = Demo01.add(1,2); // 通过类名直接调用静态方法
        System.out.println(add); // 3
    }
	// static静态方法，否则就要new实例化来调用
    public static int add(int a,int b){
        return a+b;
    }
}

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)值传递 &引用传递

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427082403886.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

* * *

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427082454225.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)方法的重载
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   重载是在一个类中，有相同的方法名，参数列表不同的方法。
    
*   方法重载的规则：
    
    *   **方法名称必须相同**
    *   **参数列表必须不同**（个数、参数类型、或排序不同）
    *   返回类型可以相同也可以不相同
    *   仅仅返回类型不同不足以成为方法的重载
*   实现理论
    
    *   方法名称相同时，编译器会根据调用方法的参数个数、参数类型等去逐个匹配，以选择对应的方法，如果匹配失败，则编译器报错。

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)命令行传参
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   有时候你希望运行一个程序时候传递给它消息，这要靠传递命令行参数给main()函数实现。

```
public static void main(String[] args) {
    //args.length 数组长度
    for (int i = 0; i < args.length; i++) {
        System.out.println("args["+i+"]: "+args[i]);
    }
}

```

找到当前类的文件夹，打开cmd.

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427082556110.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)可变参数
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   Jdk1.5开始，Java支持传递同类型的可变参数给一个方法。
*   在方法声明中，在指定参数类型后加一个省略号 (…)。
*   一个方法中只能指定一个可变参数，它必须是方法的最后一个参数。

```
//打印最大值
public static void printMax(int... num){
    if(num.length==0){
        System.out.println("没有值传入");
        return;
    }
    int result = num[0];
    for (int i = 1; i < num.length; i++) {
        if(num[i] > result){
            result = num[i];
        }
    }
    System.out.println("最大值是："+result);
}
public static void main(String[] args) {
    printMax(1,2,3,4); //最大值是：4
    printMax(new int[]{1,2,3,4,5}); //最大值是：5
}

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)递归
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   递归就是：A方法调用A方法，自己调用自己！
    
*   递归策略只需少量的代码可描述解题过程中多次重复计算，大大减少了程序的代码量。递归的能力在于用有限的语句来定义对象的无限集合。
    
*   递归结构
    
    *   **递归头**：什么时候不调用自身方法，没有头 将陷入死循环。
    *   **递归体**：什么时候需要调用自身方法。

```
//阶乘 n! n*(n-1)*...*2*1
public static int f(int n){
    if(n==1) return 1;
    return n*f(n-1); //递归：调用自身
}
public static void main(String[] args) {
    System.out.println(f(5)); //5!= 120
}

```

* * *

* * *

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Java数组
=================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)数组的定义
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   数组是相同类型数据的有序集合
*   数组描述的是相同类型的若干数据，按照一定先后次序排序组合而成
*   其中，每一个数据称作一个数组元素，每个数组元素可以通过下标访问它们

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)数组的声明创建

*   首先必须声明数组变量，才能在程序中使用数组。

```
dataType[] arrayRefVar; //首选
dataType arrayRefVar[]; //效果相同,但不是首选

```

*   Java语言使用new操作符来创建数组，语法如下

```
dataType[] arrayRefVar = new dataType[arraySize]; //int[] nums=new int[10]

```

*   数组的元素是通过索引访问的，数组索引从0开始
*   获取数组长度：**arrays.length**

```
int[] nums; //1.声明一个数组
nums = new int[3]; //2.创建一个数组
//3.给数组元素赋值
nums[0]=1;
nums[1]=2;
nums[2]=3;
for (int num : nums) { //打印数组所有元素
    System.out.println(num);
}

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)内存分析

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427082623150.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

* * *

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427082639964.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

* * *

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)数组的三种初始化

*   静态初始化

```
//静态初始化：创建+赋值
int[] a={1,2,3};
Man[] mans={new Man(1,1),new Man(2,2)}

```

*   动态初始化

```
//包含默认初始化
int[] a=new int[2]; //默认值为0
a[0]=1;
a[1]=2;

```

*   默认初始化
    *   数组是引用类型，它的元素相当于类的实例变量，因此数组一经分配空间，其中的每个元素也被按照实例变量同样的方式被隐式初始化。

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)数组的基本特点

1.  其长度是确定的，数组一旦被创建，它的大小就是不可改变的。
    
2.  其元素必须是相同类型，不允许出现混合类型。
    
3.  数组中的元素可以是任何数据类型，包括基本类型和引用类型。
    
4.  数组变量属于引用类型，数组也可以看作对象，其中每个元素相当于该对象的成员变量。
    
    数组本身就是对象，Java中对象是在堆中的，因此数组无论保存原始类型还是其他对象类型，
    
    **数组本身是在堆中的**。
    

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)数组边界

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427082726194.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)数组的使用
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   **For-Each循环**

```
int[] arrays = {1,2,3,4,5};
//打印全部的数组元素 JDK1.5 没有下标
for (int array : arrays) {
    System.out.println(array);
}

```

*   **数组作方法入参**

```
//打印数组元素
public static void printArray(int[] a){
    for (int i = 0; i < a.length; i++) {
        System.out.print(a[i]+" ");
    }
}

```

*   **数组作返回值**

```
//反转数组
public static int[] reverse(int[] arrays){
    int[] result = new int[arrays.length];
    //反转的操作
    for (int i = 0; i < arrays.length; i++) {
        result[i] = arrays[arrays.length-i-1];
    }
    return result;
}

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)多维数组
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   多维数组可以看成数组的数组，比如二维数组就是一个特殊的数组，其每一个元素都是一个一维数组。

```
int arr[][] = new int[3][2]; //二维数组,三行两列

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427082746289.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

```
int[][] array = {{1,2},{3,4},{5,6}};
//打印二维数组所有元素
for (int i = 0; i < array.length; i++) { //arrays.length=3
    for (int j = 0; j < array[i].length; j++) {
        System.out.print(array[i][j]+" ");
    }
    System.out.println();
}

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Arrays类
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   数组的工具类java.util.Arrays
*   由于数组对象本身并没有什么方法可以供我们使用，但API提供了一个工具类Arrays供我们使用。
*   Array类中的方法都是static修饰的静态方法，使用时直接使用类名进行调用，可以不用对象调用。
*   常用功能
    *   给数组赋值：fill方法。
    *   排序：sort方法，升序。
    *   比较数组：equals方法比较数组中元素值是否相等。
    *   查找数组元素：binarySearch对排序好的数组进行二分查找法操作。

```
int[] a = {1,2,3,4,9000,32145,451,21};
System.out.println(a); // [I@28d93b30 (hashcode)

//Arrays.toString 打印数组元素
System.out.println(Arrays.toString(a)); //[1, 2, 3, 4, 9000, 32145, 451, 21]

//二分法查找某值 返回下标
System.out.println(Arrays.binarySearch(a, 9000)); // 4

//填充
Arrays.fill(a,2,4,0); //数组[a[2]~a[4])之间填充0
System.out.println(Arrays.toString(a)); //[1, 2, 0, 0, 9000, 32145, 451, 21]

//升序排序
Arrays.sort(a);

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)**冒泡排序**
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   冒泡排序是八大排序最出名的排序算法。
*   代码：两层循环，外层冒泡轮数，里层依次比较。
*   当我们看到嵌套循环，应该立马就可以得出这个算法的**时间复杂度为O(n2)**。

```
//冒泡排序
//1.比较数组中两个相邻的元素，如果第一个数大于第二个数，交换它们位置
//2.每一次比较，都会产生一个最大或最小的数字(升序为最大数)
//3.下一轮则可以少一次排序
//4.依次循环，直到结束
public static int[] sort(int[] array){
    int temp=0;
    //外层循环，次数length-1
    for (int i = 0; i < array.length-1; i++) {
        //内层循环：如果第一个数大于第二个数，交换它们位置
        for (int j = 0; j < array.length-1-i; j++) {
            if(array[j]>array[j+1]){
                temp=array[j];
                array[j]=array[j+1];
                array[j+1]=temp;
            }
        }
    }
    return array;
}

public static void main(String[] args) {
    int[] a={8,1,35,47,19,-2};
    int[] sort = sort(a);
    System.out.println(Arrays.toString(sort)); //[-2, 1, 8, 19, 35, 47]
}

```

*   思考：如何优化？

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)稀疏数组
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427082948815.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

* * *

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083015623.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

* * *

```
//创建一个二维数组 11*11  0：没有棋子，1：黑棋  2：白棋
int[][] array1 = new int[11][11];
array1[1][2] = 1;
array1[2][3] = 2;
//输出原始的数组
System.out.println("原始的数组：");
for (int[] array : array1) {
    for (int i : array) {
        System.out.print(i+"\t");
    }
    System.out.println();
}

//转换为稀疏数组保存
//1.有效值的个数
int sum = 0; //有效值总数
for (int i = 0; i < 11; i++) {
    for (int j = 0; j < 11; j++) {
        if(array1[i][j]!=0){
            sum++;
        }
    }
}
//2.创建一个稀疏数组
int[][] array2 = new int[sum+1][3];
array2[0][0] = 11;
array2[0][1] = 11;
array2[0][2] = sum;

//3.遍历二维数组，将有效值存放到稀疏数组
int count = 0;
for (int i = 0; i < array1.length; i++) {
    for (int j = 0; j < array1[i].length; j++) {
        if(array1[i][j]!=0){
            count++;
            array2[count][0] = i;
            array2[count][1] = j;
            array2[count][2] = array1[i][j];
        }
    }
}

//4.输出稀疏数组
System.out.println("稀疏数组：");
for (int i = 0; i < array2.length; i++) {
    for (int j = 0; j < array2[i].length; j++) {
        System.out.print(array2[i][j]+"\t");
    }
    System.out.println();
}
/* 结果：
输出原始的数组
0	0	0	0	0	0	0	0	0	0	0	
0	0	1	0	0	0	0	0	0	0	0	
0	0	0	2	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	0	
稀疏数组
11	11	2	
1	2	1	
2	3	2	
*/

```

* * *

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)面向对象
===============================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)初识面向对象
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)面向过程&面向对象

*   **面向过程思想**
    *   步骤清晰简单，第一步做什么，第二部做什么…
    *   面向过程适合处理一些较为简单的问题
*   **面向对象思想**
    *   物以类聚，分类的思维模式，思考问题首先会解决问题需要哪些分类，然后对这些分类进行单独思考。最后，才对某个分类下的细节进行面向过程的思索。
    *   面向对象适合处理复杂的问题，适合处理需要多人协作的问题！
*   **对于描述复杂的事物，为了从宏观上把握、从整体上合理分析，我们需要使用面向对象来分析整个系统。但是，具体到微观操作，仍然需要面向过程的思路去处理。**

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)什么是面向对象

*   面向对象编程（Object-Oriented Programming, OOP）
*   本质：以类的方式组织代码，以对象的组织(封装)数据。
*   **抽象**
*   三大特性
    *   封装
    *   继承
    *   多态
*   从认识论的角度考虑是先有对象后有类。**对象是具体的事物**，类是对象的抽象。
*   从代码运行角度考虑是先有类后有对象。**类是对象的模板**。

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)类与对象的关系

*   类是一种抽象的数据类型，它是对某一类事物整体描述/定义，但并不能代表某一个具体的事物。
    *   动物、植物、手机、电脑…
    *   Person类、Pet类、Cat类等，都是用来描述/定义某一具体的事物应该具备的特点和行为。
*   对象是抽象概念的具体实例，如张三是人的一个具体实例、张三家里的狗旺财就是狗的一个具体实例。

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)创建与初始化对象
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   使用new来创建对象。
*   使用new关键字创建的时候，除了分配内存之外，还会给创建好的对象进行默认的初始化，以及对类中构造器的调用。
*   类中的**构造器**也被称为构造方法，创建对象时必须要调用。有以下特点：
    *   **必须和类的名字相同**
    *   **没有返回类型，也不能写void**
*   一个类即使什么都不写，也会存在一个默认的构造方法

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)构造器

```
public class Person {
    //一个类即使什么都不写，也会存在一个默认的无参构造方法
    //显示地定义构造器
    String name;
    
    //作用：1. 使用new关键字，本质是在调用构造器
    //2. 用来初始化对象的值
    public Person(){} //无参构造
    
    //有参构造 3.一旦定义了有参构造，无参就必须显示定义
    public Person(String name){
        this.name=name;
    }
	//Alt+insert 快捷键插入构造方法
}

```

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)内存分析

```
//定义一个宠物类
public class Pet {
    public String name; //默认 null
    public int age; 	//默认 0
    //无参构造

    public void shout(){
        System.out.println("叫了一声");
    }
}

```
```
//应用类，创建调用对象
public class Application {
    public static void main(String[] args) {
        
        Pet dog = new Pet();

        dog.name = "旺财";
        dog.age = 3;
        dog.shout();
    }
}

```

*   **对象通过引用类型来操作：栈 - - ->堆**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083120326.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083125469.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)封装
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   该露的露，该藏的藏
    *   我们程序设计要追求“**高内聚，低耦合**”。高内聚就是类的内部数据细节由自己完成，不允许外部干涉；低耦合：仅暴露少量的方法给外部使用。
*   封装（数据的隐藏）
    *   通常，应禁止直接访问一个对象中数据的实际表示，而应通过操作接口来访问，称为信息隐藏。
*   作用
    1.  提高程序的安全性，保护数据
    2.  隐藏代码的实现细节
    3.  统一接口
    4.  系统可维护性增加了

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083157156.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)继承
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   继承的本质是对某一批类的抽象，从而实现对世界更好地建模。
    
*   **extends**的意思是”扩展“。子类是父类的扩展，使用关键字extends来表示。
    
*   **Java中类只有单继承**，没有多继承！一个类只能继承一个父类。
    
*   继承是**类与类之间的一种关系**，此外还有依赖、组合、聚合等。
    
*   继承关系的两个类，一个为**子类（派生类）**，一个为\*\*父类（基类）\*\*子类继承父类。
    
*   子类和父类之间，从意义上讲应该具有”is a“的关系。
    

```
//学生类(子类)继承 人类(父类)
public class Student extends Person{ /*Person extends Object*/
    ...
}

```

*   子类继承了父类，就会拥有父类的全部方法，而private**私有属性及方法无法继承**。
*   在Java中，所有类，都默认直接或间接继承**Object**类 (Ctrl+H 可以查看类关系)
*   **被final修饰的类**，无法被继承（断子绝孙）。

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)super & this

1.  super()调用父类的构造方法，必须在构造方法的第一个
2.  super必须只能出现在子类的方法或构造方法中
3.  \*\*super()**和**this()\*\*不能同时调用构造方法，因为this也必须写在第一行

*   **super与this的区别**：super代表**父类对象的引用，只能在继承条件下使用**；this调用自身对象，没有继承也可以使用。

```
super(); //隐藏代码，默认调用了父类的无参构造，要写只能写第一行

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083247265.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

* * *

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083318162.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)方法的重写

*   重写：子类的方法必须与父类方法必须一致，方法体不同。
    
*   重写是方法的重写，与属性无关
    
*   重写方法只与非静态方法有关，与静态方法无关（静态方法不能被重写）
    

```
public class B {
    public static void test(){ //静态方法
        System.out.println("B==>test()");
    }
}

```
```
public class A extends B{ //继承
    public static void test(){
        System.out.println("A==>test()");
    }
}

```
```
public class Application {
    public static void main(String[] args) {
        //方法的调用之和左边定义的类型有关
        A a = new A();
        a.test(); //打印 A==>test()

        //父类的引用指向了子类，但静态方法没有被重写
        B b = new A();
        b.test(); //打印 B==>test()
    }
}

```

**修改A.java, B.java**

```
public class B {
    public void test(){ //非静态方法
        System.out.println("B==>test()");
    }
}
public class A extends B{
    @Override //重写了B的方法
    public void test() {
        System.out.println("A==>test()");
    }
}

```
```
//父类的引用指向了子类
B b = new A(); //子类重写了父类的方法，执行子类的方法
b.test(); //打印变成了 A==>test()
/* 
静态方法是类的方法，非静态方法是对象的方法
有static时，b调用了B类的方法，因为b是b类定义的
没有static时，b调用的是对象的方法，而b是A类new出来的对象，调用A的方法
*/

```

*   静态方法属于类，非静态方法属于对象
*   注意点：

1.  方法名、参数列表必须相同
2.  修饰符范围可以扩大，不能缩小（public>protect>private）
3.  抛出的异常 范围可以被缩小，不能扩大
4.  被\*\*static(属于类，不属于实例)，final(常量方法)，private(私有)\*\*修饰的方法不能重写

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)多态
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   动态编译：类型
    
*   **即同一方法可以根据发送对象的不同而采用不同的行为方式**
    
*   一个对象的实际类型是确定的，但可以指向对象的引用可以有很多
    
*   多态存在条件
    
    *   有继承关系
    *   子类重写父类方法
    *   父类引用指向子类对象

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042708335834.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

* * *

*   注意点：
    1.  **多态是方法的多态，没有属性的多态**
    2.  父类和子类，有联系 类型转换异常: ClassCastException
    3.  存在条件：继承关系，方法需要重写，父类引用指向子类对象！

### [](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)instanceof和类型转换

*   **instanceof 引用类型比较**，判断一个对象是什么类型

```
public static void main(String[] args) {

    // Object > String
    // Objest > Person > Student
    // Objest > Person > Teacher
    Object object = new Student();
	// X instanceof Y，X引用指向的对象是不是Y的子类
    System.out.println(object instanceof Student); //true
    System.out.println(object instanceof Person); //true
    System.out.println(object instanceof Teacher); //false
    System.out.println(object instanceof Object); //true
    System.out.println(object instanceof String); //false
	
    //类型之间的转化：父-子（高-低）,低可以转换为高
    Person obj = new Syudent(); //只能用Person方法（重写了用子类重写过的方法）
    (Syudent)obj.go(); //强转之后可以用Student方法(Student->go())
}

```

**类型转换**

1.  父类引用指向子类的对象
2.  把子类转换为父类，向上转型，会丢失自己原来的一些方法
3.  把父类转换为子类，向下转型，强制转换，才调用子类方法
4.  方便方法的调用(转型)，减少重复的代码，简洁。

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)Static
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   静态变量可以直接用类名访问，也称类变量。
*   静态变量(或方法)对于类，所有对象（实例）所共享。
*   静态区代码 加载类时一起被初始化，最早执行且只执行一次（第一次new）。
*   Math->随机数:

```
//静态导入包
import static java.lang.Math.random;

public class Application {
    public static void main(String[] args) {

        //第一种随机数，不用导包
        System.out.println(Math.random()); //0.7562202902634543

        //第二种随机数，静态导入包
        System.out.println(random()); //0.5391606223844663
    }
}

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)抽象类(abstract)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   abstract修饰的类就是抽象类，修饰的方法就是抽象方法。
*   抽象类中可以没有抽象方法，但有抽象方法的类一定要声明为抽象类。
*   抽象类不能使用new来创建对象，它是用来让子类继承的。
*   **抽象方法只有方法的声明，没有实现**，让其子类实现。
*   子类继承抽象类，**必须实现抽象类的所有方法**，否则该子类也要声明为抽象类。

```
//abstract 抽象类 类只能单继承（接口可以多继承）
public abstract class Action {

    //约束~有人帮我们实现~
    //抽象方法只有方法名，没有方法的实现
    public abstract void doSth();

    //1.不能new抽象类，只能靠子类去实现它，仅作为一个约束
    //2.抽象方法只能出现在抽象类中，抽象类可以有普通方法
    //3.抽象类有构造器，可以派生子类
    //4.抽象类的意义：约束，提高开发效率。但是类只能单继承，所以有局限 用的不多
}

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)接口(interface)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   普通类：只有具体实现
*   抽象类：具体实现和规范(抽象方法)都有
*   接口：**只有规范，没有方法实现**，专业的约束！约束与实现分离：面向接口编程~

*   接口就是规范，定义的是一组规则，"你是什么…必须做什么…"的思想。
*   **接口的本质是约束**，就像人间法律一样，制定好大家都遵守。

```
//interface接口,接口都要有继承类
//实现类（implements 可以继承多个接口）
//多继承，利用接口实现多继承
public interface UserService {
    //定义的属性都是常量,默认修饰 public static final
    public static final int AGE = 99; //一般不用
    //所有的定义的方法都是抽象的 默认public abstract
    public abstract void run();
    void add();
    void query();
    void delete();
}

```

注意点

*   接口没有构造方法，不能被实例化
*   实现类必须要重写接口中的方法
*   实现类（implements） 可以实现多个接口

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)内部类
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   内部类就是在一个类的内部再定义一个类，比如A类中定义了一个B类，那么B就是A的内部类，而A相对B来说就是外部类
    1.  成员内部类：**可以操作外部类的私有属性及方法**
    2.  静态内部类：static修饰，不能访问外部类私有属性
    3.  局部内部类：外部类的方法里定义的类
    4.  匿名内部类：没有名字初始化类

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083429180.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

* * *

* * *

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)异常
=============================================================================================================================================================================================================================================================================================================================================================================================================================================

*   软件程序在运行过程中，经常可能遇到异常问题，异常英文(**Exception**)，意思是例外，这些例外情况需要我们写程序做出合理的处理，而不至于让程序崩溃。
    
*   异常指程序运行中出现的不期而至的各种状况：文件找不到，网络连接错误，非法参数等。
    
*   异常发生在程序运行期间，它影响了正常的执行流程。
    

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083507444.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)简单分类
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   **检查型异常**：最具代表性异常是用户错误或问题引起的异常，这是程序员无法预见的。例如用户要打开一个不存在的文件时引发的异常，这些异常在编译时不能被简单地忽略。
*   **运行时异常**：是可能被程序员避免的异常，与检查性异常相反，运行时异常可以在编译时忽略。
*   **错误Error**：错误不是异常，而是脱离程序员控制的问题。错误在代码经常被忽略。例如当栈溢出，一个异常就发生了，它们在编译也检查不到。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083535592.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083557330.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042708360855.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)异常处理机制
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   **抛出异常**
*   **捕获异常**
*   异常处理关键字：**try、catch、finally、throw、throws**

```
public static void main(String[] args) {
    int a = 1;
    int b = 0;

    try { //try监控区域
        System.out.println(a/b);
    }catch (ArithmeticException e){ //catch 捕获异常
        System.out.println("程序出现异常，变量b不能为0");
    }catch (Exception e){
        e.printStackTrace();
    }finally { //一定会执行，处理善后工作，如关闭资源
        System.out.println("finally");
    }
    
    if(b==0){ //抛出异常一般在方法中使用
        throw new ArithmeticException(); //主动抛出异常
    }
}
//Ctrl+Alt+T 快捷键插入 try-catch

```

[](https://blog.csdn.net/fllow_wind/article/details/116174854?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137275416781432913237%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137275416781432913237&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-116174854.142^v9^control,157^v4^control&utm_term=java%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)自定义异常
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083645704.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042708372149.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083725235.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210427083739287.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZsbG93X3dpbmQ=,size_16,color_FFFFFF,t_70)  
如果本篇文章对你有帮助，不妨点个赞再走吧！

 

[

![](https://img-blog.csdnimg.cn/fce44ffe4f1f493b84f6e057060c9c93.png)

创作打卡挑战赛 ![](https://csdnimg.cn/release/blogv2/dist/components/img/iconArrowLeftWhite.png)

赢取流量/现金/CSDN周边激励大奖



](https://mp.csdn.net/clock?utm_campaign=marketingcard&utm_source=fllow_wind&utm_content=116174854)

 