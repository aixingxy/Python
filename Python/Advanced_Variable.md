<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [高级变量](#高级变量)
	- [列表](#列表)
		- [列表常用操作](#列表常用操作)
		- [循环遍历](#循环遍历)
	- [元组](#元组)
		- [元组的定义](#元组的定义)
		- [元组的常用操作](#元组的常用操作)
		- [循环遍历](#循环遍历)
		- [应用场景](#应用场景)

<!-- /TOC -->
# 高级变量
+ 非数字型变量
  - 字符串
  - 列表
  - 元组
  - 字典
+ 在Python中，所有非数字型变量都支持以下特点：
1.都是一个序列sequence，也可以理解为容器
2.取值[]
3.遍历 for in
4.计算长度、最大/最小值、比较、删除
5.链接 + 和重复 *
6.切片

## 列表
+ list（列表）是Python中使用最频繁的数据类型，在其他语言中通常叫做数组
+ 专门用于存储一串信息
+ 列表用 [] 定义，数据之间使用 ， 分隔
+ 列表的索引从 0 开始
  - 索引就是数据在列表中的位置编号，索引又可以被称为下标

```python
In [5]: name_list = ["zhangsan","lisi","wangwu"]

In [6]: name_list
Out[6]: ['zhangsan', 'lisi', 'wangwu']
```

> 从列表中取值时，如果超出索引范围，程序会报错

![list](image/list.png)

### 列表常用操作
+ 在IPython3中定义一个列表，例如：name_list = []
+ 输入name_list.按下TAB键，ipython会提示列表能够使用的方法如下：

```python
In [2]: name_list.
name_list.append   name_list.count    name_list.insert   name_list.reverse
name_list.clear    name_list.extend   name_list.pop      name_list.sort
name_list.copy     name_list.index    name_list.remove
```

|序号|分类|关键字/函数/方法|说明|
|:---|:---|:---|:---|
|1   |增加   |列表.insert(索引，数据)   |在指定位置插入数据   |
|   |   |列表.append(数据)   |在末尾追加数据   |
|   |   |列表.extend(列表2)   |将列表2的数据追加大列表   |
|2   |修改   |列表[索引] = 数据   |修改指定索引的数据   |
|3   |删除   |del 列表[索引]   |删除指定索引的数据   |
|   |   |列表.remove(数据)   |删除第一个出现的指定数据   |
|   |   |列表.pop   |删除末尾数据   |
|   |   |列表.pop(索引)   |删除指定索引数据   |
|   |   |列表.clear   |清空列表   |
|4   |统计   |len(列表)   |列表长度   |
|   |   |列表.count(数据)   |数据在列表中出现的次数   |
|5   |排序   |列表.sort()   |升序排序   |
|   |   |列表.sort(reverse=True)    |降序排序   |
|   |   |列表.reverse()   |逆序、反转   |
```python
  # 定义一个列表
  name_list = ["zhangsan","lisi","wangwu"]
  #  1. 取值和索引
  # list index out of range - 列表超出范围
  print(name_list[2])
  # 知道数据的内容，想确定数据在列表中国的位置
  # 使用index方法需要注意，如果传递的数据不在列表中，程序会报错！
  print(name_list.index("wangwu"))
  # 2. 修改
  name_list[1] = "lisilisi"
  # IndexError: list assignment index out of range
  # 列表指定的索引超出范围，程序会报错
  # name_list[3] = "王二小"

  # 3.增加
  # append 方法可以向列表的末尾追加数据
  name_list.append("wang")
  # insert 方法可以在列表的指定索引位置插入数据
  name_list.insert(1,"小帅哥")
  # extend 方法可以把其他列表中的完整内容追加到当前列表的末尾
  temp_list = ["111","222","333"]
  name_list.extend(temp_list)
  # 4. 删除
  # remove 可以从列表中删除指定的数据
  name_list.remove("wangwu")
  # pop 方法默认可以把列表中最后一个元素删除
  name_list.pop()
  # pop 方法默认可以指定要删除元素的索引
  name_list.pop(3)
  # clear 方法可以清空列表
  name_list.clear()
  print(name_list)
```
```python
	# 定义一个列表
	name_list = ["zhangsan","lisi","wangwu"]
	# 使用del关键字（delete）删除列元素
	# 提示：在日常开发中，要从列表中删除数据，建议使用列表提供的方法
	del name_list[1]

	# del关键字本质上是用来将一个变量从内存中删除
	name = "小明"
	del name
	print(name)
	print(name_list)
```
```python
	# 定义一个列表
	name_list = ["zhangsan","lisi","wangwu"]
	list_len = len(name_list)
	print("列表中包含的%d个元素" % list_len)

	# count方法可以统计列表中某一个数据出现的次数
	count = name_list.count("lisi")
	print("lisi出现了%d次" % count)
	# 从列表中删除第一次出现的数据，如果数据不存在，程序会报错
	name_list.remove("lisi")
	print(name_list)
```
```python
	# 定义一个列表
	name_list = ["zhangsan","lisi","wangwu","wangxiaoer"]
	num_list = [6,8,4,1,10]
	# 升序
	# name_list.sort()
	# num_list.sort()
	# 降序
	# name_list.sort(reverse=True)
	# num_list.sort(reverse=True)
	# 逆序（反转）
	name_list.reverse()
	num_list.reverse()
	print(name_list)
	print(num_list)
```

**关键字、函数和方法**
+ 关键字是Python内置的、具有特殊意义的标识符

```python
In [1]: import keyword

In [2]: print(keyword.kwlist)
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']

In [3]: len(keyword.kwlist)
Out[3]: 33
```
> 关键字后面不需要使用括号

+ 函数封装了独立功能，可以直接调用
> 函数需要死记硬背
+ 方法和函数类似,同样是封装了独立的功能
+ 方法需要通过对象来调用，表示针对这个对象要做的操作

> 在变量后面输入 . ,然后选择针对这个变量要执行的操作

### 循环遍历
+ 遍历就是从头到尾依次从列表中获取数据
	- 在循环体内部针对每一个元素，执行相同的操作
+ 在Python中为了提高列表的遍历效率，专门提供的迭代iteration遍历
+ 使用 for 就能够实现迭代遍历
```python
	name_list = ["zhangsan","lisi","wangwu","wangxiaoer"]
	# 使用迭代遍历列表
	"""
	顺序的从列表中依次获取数据，每一次循环过程中，数据都会保存在my_name
	变量中，在循环体内部可以访问到当前这一次获取到的数据
	"""
	for my_name in name_list:
	    print("my name is %s" % my_name)
```
**应用场景**
+ 尽管Python的列表中可以存储不同类型的数据
+ 但是在开发中，更多应用的场景是
	- 列表存储相同类型的数据
	- 通过迭代遍历，在循环体内部，针对列表中每一项元素，执行相同的操作

## 元组
### 元组的定义
+ Tuple（元组）与列表类似，不同之处在于元组的 **元素不能修改**
	- **元组** 表示多个元素组成的序列
	- 元组在Python开发中，有特定的应用场景
+ 用于存储一串信息、数据之间使用 **,** 分隔
+ 元组用 () 定义
+ 元组的索引从 0 开始
	- 索引就是数据元组中的位置编号

```python
In [1]: info_tuple = ("lisi",18,1.786)
In [2]: type(info_tuple)
Out[2]: tuple
In [3]: info_tuple[1]
Out[3]: 18
```

**创建空元组**
```python
tuple = （）
```
**元组中只包含一个元素时，需要在元素后面添加逗号**
```python
In [8]: single_tuple = (5)
In [9]: type(single_tuple)
Out[9]: int

In [10]: single_tuple = (5,)
In [11]: type(single_tuple)
Out[11]: tuple
```

### 元组的常用操作
+ 在ipyhon中定义一个元组
+ 输入info.按下TAB键，ipython会提示元组能够使用的函数

```python
In [1]: info = ()
In [2]: info.
info.count  info.index  
```
```python
	info_tuple = ("lisi",18,1.786)
	# 1.取值和去索引
	print(info_tuple[0])
	# 已经知道数据的内容，希望知道该数据在元组中的索引
	print(info_tuple.index("lisi"))
	# 2.统计数据
	print(info_tuple.count("lisi"))
	# 统计元组中包含元素的个数
	print(len(info_tuple))
```
### 循环遍历
+ 取值就是从元组中获取存储在指定位置的数据
+ 遍历就是从头到尾依次从元组中获取数据
```python
	info_tuple = ("lisi",18,1.786)
	# 使用迭代遍历元组
	# 使用格式字符串拼接 my_info 这个变量不方便！
	# 因为元组中通常保存的数据类型是不同的
	for my_info in info_tuple:
	    print(my_info)
```
+ 在Python中，可以使用for循环遍历所有非数字类型的变量： **列表、元组、字典以及字符串**
+ 提示：实际开发中，除非能够确认元组中数据类型，否则针对元组的循环遍历需求并不是很多

### 应用场景
+ 函数的参数和返回值：一个函数可以接收任意多个参数，或者以此返回多个数据
+ 格式字符串，格式化字符串后面的（）本质上就是一个元组

```python
	info_tuple = ("lisi",18,1.786)
	# 格式化字符串后面 ’（）‘本质上就是元组
	print("%s %d %f" % ("lisi",20,1.786))
	print("%s %d %f" % info_tuple)
	info_str = "%s %d %f" % info_tuple
	print(info_str)
	# 结果：
	lisi 20 1.786000
	lisi 18 1.786000
	lisi 18 1.786000
```
+ 让列表不可以被修改，以保护数据安全

**元组和列表之间的转换**
+ 使用list函数可以把元组转换成列表
+ 使用tuple函数可以把列表转换成元组

```python
In [1]: num_list = [1,2,3,4]
In [2]: type(num_list)
Out[2]: list
In [3]: num_tuple = tuple(num_list)
In [4]: type(num_tuple)
Out[4]: tuple
In [5]: num2_list = list(num_)
num_list   num_tuple  
In [5]: num2_list = list(num_tuple)
In [6]: type(num2_list)
Out[6]: list
```
