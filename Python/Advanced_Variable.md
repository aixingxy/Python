<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [高级变量](#高级变量)
	- [列表](#列表)
		- [列表常用操作](#列表常用操作)

<!-- /TOC -->
# 高级变量
+ 非数字型变量
  - 字符串
  - 列表
  - 元组
  - 字典
+ 在Python中，所有非数字型变量都支持以下特点：
1. 都是一个序列sequence，也可以理解为容器
2. 取值[]
3. 遍历 for in
4. 计算长度、最大/最小值、比较、删除
5. 链接 + 和重复 *
6. 切片

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
