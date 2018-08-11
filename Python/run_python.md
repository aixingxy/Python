<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [执行Python程序的三种方式](#执行python程序的三种方式)
	- [Python解释器 Python/Python3](#python解释器-pythonpython3)
- [使用python 2.x解释器](#使用python-2x解释器)
- [使用python 3.x解释器](#使用python-3x解释器)
	- [交互式运行Python程序](#交互式运行python程序)
	- [Python的IDE -- PyCharm](#python的ide-pycharm)

<!-- /TOC -->
# 执行Python程序的三种方式
## Python解释器 Python/Python3
**Python解释器**

```
# 使用python 2.x解释器
$ python xxx.py

#使用python 3.x解释器
$ python3 xxx.py
```
**其他解释器**

**Python解释器** 如今有多个语言的实现，包括：
+ Cpython --官方版本的C语言实现
+ Jpython --可运行在Java品台上
+ IronPython --可以运行在.NET和Mono平台
+ PyPy --Python实现的，支持JIT即时编译

## 交互式运行Python程序
+ 直接在终端中运行解释器，而不输入要执行的文件名
+ 在Python的shell中直接输入Python的代码，会即刻看到程序执行结果

**1）交互式运行的Python优缺点**
+ 优点
  + 适合与学习/验证Python语法或者局部代码
+ 缺点
  + 代码不能保存
  + 不适合运行太大的程序
**2）退出官方解释器**
+ 直接输入exit（）

+ 使用热键退出
在Python解释器中，按热键ctrl+d可以退出解释器

```
heigou@ubuntu:~$ python
Python 2.7.12 (default, Dec  4 2017, 14:50:18)
[GCC 5.4.0 20160609] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> 1.01 ** 356
34.546898707112454
>>> exit()
heigou@ubuntu:~$ python3
Python 3.5.2 (default, Nov 23 2017, 16:37:01)
[GCC 5.4.0 20160609] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
heigou@ubuntu:~$


```
**3）IPython**
+ IPython中的“I”代表交互interactive

**特点**
+ IPython 是一个Python的交互式shell，比默认的python shell更好用
  + 支持自动补全
  + 自动缩进
  + 支持bash shell命令
  + 内置了许多很有用的功能和函数
+ IPython是基于BSD开发的

**版本**
+ Python 2.x使用的解释器是ipython
+ Python 3.x使用的解释器是ipython3
+ 退出解释器可以有以下两种方式：
  + 直接输入exit
  + 使用热键退出
  在Python解释器中，按热键ctrl+d，Ipython会询问是否退出解释器

  ```
  heigou@ubuntu:~$ ipython
  Python 2.7.12 (default, Dec  4 2017, 14:50:18)
  Type "copyright", "credits" or "license" for more information.

  IPython 2.4.1 -- An enhanced Interactive Python.
  ?         -> Introduction and overview of IPython's features.
  %quickref -> Quick reference.
  help      -> Python's own help system.
  object?   -> Details about 'object', use 'object??' for extra details.

  In [1]:
  Do you really want to exit ([y]/n)? y
  ```

## Python的IDE -- PyCharm
**1)集成开发环境（IDE）**
集成开发环境（IDE，Integrated Development Environment）-- 集成了开发软件需要的所有工具，一般包括以下工具：
+ 图形用户界面
+ 代码编辑器（支持自动补全/自动缩进）
+ 编译器/解释器
+ 调试器（断点/单步执行）
+ .......

**2)PyCharm介绍**
+ PyCharm是Python一款非常优秀的集成开发环境
+ PyCharm除了具有一般IDE所必备的功能补全，还可以在Windows、Linux、macOS下使用
+ PyCharm适合开发大型工具
  + 一个项目通常包含很多源文件
  + 每个源文件的代码行数是有限的，通常在几百行之内
  + 每个源文件各司其职，共同完成复杂的业务功能

**3）PyCharm快速体验**

![Pycharm](image/pycharm.png)

+ 文件导航区 能够浏览/定位/打开 项目文件
+ 文件编辑区 能够编辑当前打开的文件
+ 控制台区域能够：
  + 输出程序执行内容
  + 跟踪调试代码的执行
+ 右上角的工具栏能够 **执行（SHFIT +F10）** / **调试（SHIFT+F9）** 代码
