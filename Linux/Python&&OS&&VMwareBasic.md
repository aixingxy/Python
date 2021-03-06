<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Python&&OS&&VMwareBasic](#pythonosvmwarebasic)
	- [Python基本体验](#python基本体验)
	- [操作系统（Operation System， OS）](#操作系统operation-system-os)
		- [操作系统接口示意图](#操作系统接口示意图)
		- [OS的作用](#os的作用)
		- [不同应用领域的操作系统](#不同应用领域的操作系统)
	- [虚拟机](#虚拟机)
	- [操作系统的发展史](#操作系统的发展史)

<!-- /TOC -->
# Python&&OS&&VMwareBasic
## Python基本体验

Python中使用基本的平方、加法、乘法：

![12](https://github.com/Renwoxin/Python/blob/master/image/12.png)

## 操作系统（Operation System， OS）

### 操作系统接口示意图

![13](https://github.com/Renwoxin/Python/blob/master/image/13.png)

**没有安装操作系统的计算机，通常被称为裸机**
（1）如果想在裸机上运行自己所编写的程序，就必须用机器语言（011010001）书写程序

（2）如果计算机上安装了操作系统，就可以在操作系统上安装支持的高级语言环境，用高级语言开发程序

### OS的作用
**管理硬件设备**

1）直接控制各个不同的硬件进行工作

（1）由OS给CPU命令

（2）由OS查找内存数据

（3）由OS查找硬盘数据

等等

2）把操作硬件的方法封装为不同的系统调用，供其他成员调用

**播放音乐的事例**

![14](https://github.com/Renwoxin/Python/blob/master/image/14.png)

### 不同应用领域的操作系统
1）桌面操作系统：

（1）Windows系列（用户群体大，安全性和稳定性不好）

（2）macOS（适合于开发人员）

（3）Linux（应用软件少）

2）服务器操作系统

（1）Linux（安全、稳定、免费；占有率高）

（2）Windows Server（付费，占有率低）

3）嵌入式操作系统

   Linux

4）移动设备操作系统

（1）iOS

（2）Android（基于Linux）

## 虚拟机

**虚拟机（Virtual Machine）指通过软件模拟具有完整硬件系统功能的、运行在一个完全隔离环境中的完整计算机系统**

（1）虚拟系统通过生成现有OS的全新虚拟镜像，具有真实操作系统完全一样的功能

（2）进入虚拟系统后，所有操作都是在这个全新的独立的虚拟系统里面进行，可以独立安装运行软件，保存数据，拥有自己的独立桌面，不会对真正的系统产生任何影响

（3）可以在虚拟和现实之间灵活切换

## 操作系统的发展史

（1）操作系统的发展历史

   Unix——（多用户Unix）多用户能够在同一时间登录到同一个电脑上使用的操作系统

（2）Minix

  Minix——小型Unix

（3）Linux
