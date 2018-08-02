# ubuntu安装教程

## 准备工作
下载Vmware
下载ubuntu-16.04.4-desktop-amd64.iso（网址：http://releases.ubuntu.com/16.04.4/）
两者安装好即可

## 设置语言环境

（1）进入System Setting（系统设置）

（2）打开Language Support（语言支持）

（3）通过Install/Remove Language（安装/删除语言）添加Chinese（simplified）（简体中文）

（4）选择汉语（中国）

![1](https://github.com/Renwoxin/Python/blob/master/image/1.png)

（5）重启系统

![2](https://github.com/Renwoxin/Python/blob/master/image/2.png)
![3](https://github.com/Renwoxin/Python/blob/master/image/3.png)

（6）不修改文件夹的名称（Ubuntu终端不能有汉语的存在）

![4](https://github.com/Renwoxin/Python/blob/master/image/4.png)

结果

![5](https://github.com/Renwoxin/Python/blob/master/image/5.png)

## 常用软件安装

### 1.设置服务器镜像源

**Ubuntu中大部分的软件安装/更新都是利用apt命令，从Ubuntu的服务器直接安装的**

**Ubuntu官方服务器在国外，为了提高软件安装/更新速度，Ubuntu提供了选择服务器的功能——>因此产生了镜像服务器**

（1）进入系统设置

（2）打开软件和更新

（3）设置下载自其它站点

![6](https://github.com/Renwoxin/Python/blob/master/image/6.png)

（4）通过选择最佳服务器选择速度最快的镜像源

![7](https://github.com/Renwoxin/Python/blob/master/image/7.png)

![8](https://github.com/Renwoxin/Python/blob/master/image/8.png)

### 2.在启动栏添加终端

Ubuntu的启动栏类似于Windows的 任务栏

（1）通过最上方的搜索按钮可以搜索并启动程序

（2）点击锁定到启动器，完成保留常用软件图标在启动栏，并且可以进行拖拽移动图标

### 3.apt终端命令

apt 是Ubuntu下的安装包管理工具

大部分软件安装/更新/卸载都是利用apt命令来实现

常用命令：

（1）安装软件

	sudo apt install 软件名

（2）卸载软件

	sudo apt remove 软件名

（3）更新可用软件包列表

	sudo apt update

（4）更新已安装的包

	sudo apt upgrade

**apt是apt-get格式的增强版**
## deb格式及谷歌浏览器的安装
deb是Bebian Linux的安装格式（类似于exe），在Ubuntu中同样可以使用，需要安装deb安装包，需要使用dpkg终端命令：

	sudo dpkg -i<pakege.deb>

（1）下载谷歌浏览器安装包

（2）输入安装命令

	dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
	sudo apt install libappindicator1 libindicator7
	sudo dpkg -i google-chrome-stable_current_amd64.deb
	sudo apt -f install
**sudo apt -f install解决已经安装好的软件的依赖关系的修复**
## 搜狗输入法的安装设置分辨率

fcitx被称小企鹅输入法，优点是，短小精悍、和程序的兼容性比较好！
（1）打开系统设置->语言支持->将键盘输入法系统改为fcitx

![9](/home/heigou/Desktop/Python/image/9.png)

（2）下载搜狗输入法安装包 [网址]（http://pinyin.sogou.com/linux）

（3）输入安装命令：

	sudo dpkg -i sogoupinyin_2.2.0.0108_amd64.deb

![10](/home/heigou/Desktop/Python/image/10.png)

（4）安装完成之后会有报错情况，此时需要使用命令：

	sodu apt -f install
![11](/home/heigou/Desktop/Python/image/11.png)

**解决问题**
