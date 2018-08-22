# 变量的进阶
## 变量的引用
> + 变量和数据都是保存在内存中的
> + 在Python中函数的参数传递以及返回值都是靠引用传递的

### 引用的概念
在Python中
+ 变量和数据是分开存储的
+ 数据保存在内存中的一个位置
+ 变量中保存着数据在内存中的地址
+ 变量中记录数据的地址，就叫做引用
+ 使用id()函数可以查看变量中保存数据所在的内存地址

> 注意： 如果变量已经被定义，当给一个变量赋值时，本质上是修改了数据的引用
> + 变量不再对之前的数据引用
> + 变量改为对新赋值数据的引用

```python
In [1]: a = 1
In [2]: id(a)
Out[2]: 10919424
In [3]: id(1)
Out[3]: 10919424
In [4]: b = a
In [5]: id(b)
Out[5]: 10919424
In [6]: a = 2
In [7]: id(a)
Out[7]: 10919456
In [8]: id(b)
Out[8]: 10919424
In [9]: b = a
In [10]: id(b)
Out[10]: 10919456
```
### 函数的参数和返回值的传递
在Python中，函数的实参/返回值都是靠引用传递来的
```python
  def test(num):
    print("在函数内部 %d 对应的内存地址是%d " %(num,id(num)))
    # >1 定义一个字符串变量
    result = "hello"
    print("函数要返回数据的内存地址是%d" % id(result))
    # >2 将字符串变量返回,函数返回的是数据的引用，而不是数据本身
    return result
  # 1.定义一个数字的变量
  a = 10
  # 数据的地址本质上就是一个数字
  print("a变量保存数据的内存地址是%d" %id(a))
  # 2.调用test函数，本质上传递的是实参保存数据的引用，而不是实参保存的数据！
  # 注意：如果函数有返回值，但是没有定义变量接收
  # 程序不会报错，但是无法获得返回结果
  r = test(a)
  print("%s的内存地址是%d" %(r,id(r)))
```
## 可变和不可变型
+ 不可变型，内存中的数据不允许被修改:
  - 数字类型 int，bool，float，complex，long（2，x）
  - 字符串 str
  - 元组 tuple
+ 可变类型，内存中的数据不允许被修改：
  - 列表 list
  - 字典 dict


```python
In [1]: # 列表
In [2]: a = [1,2,3]
In [3]: id(a)
Out[3]: 139929865061768
In [4]: a.append(888)
In [5]: a
Out[5]: [1, 2, 3, 888]
In [6]: id(a)
Out[6]: 139929865061768
In [7]: a.remove(2)
In [8]: a
Out[8]: [1, 3, 888]
In [9]: id(a)
Out[9]: 139929865061768
In [10]: a.clear
Out[10]: <function list.clear>
In [11]: a.clear()
In [12]: id(a)
Out[12]: 139929865061768
In [13]: a
Out[13]: []
In [14]: a = []
In [15]: id(a)
Out[15]: 139929865098696
In [16]: # 字典
In [17]: d = {"name":"xiaoming"}
In [18]: d
Out[18]: {'name': 'xiaoming'}
In [19]: d["age"] = 18
In [20]: d
Out[20]: {'name': 'xiaoming', 'age': 18}
In [21]: id(d)
Out[21]: 139929865101256
In [22]: d.pop("age")
Out[22]: 18
In [23]: d
Out[23]: {'name': 'xiaoming'}
In [24]: id(d)
Out[24]: 139929865101256
In [25]: d.clear()
In [26]: id(d)
Out[26]: 139929865101256
In [27]: d = {}
In [28]: id(d)
Out[28]: 139929865052680
```
> 注意：字典的key只能使用不可变类型的数据

**注意**
1. 可变类型的数变化，是通过方法来实现的
2. 如果给一个可变类型的变量，赋值了一个新的数据，引用会修改
  + 变量不再对之前的数据引用
  + 变量改为对新赋值的数据引用

**哈希（hash）**
+ python中内置有一个hash（o）函数
  - 接收一个不可变类型的数据作为函数
  - 返回结果是一个整数
+ 哈希是一种算法，其作用就是提取数据类型的特征码（类似于指纹）
  - 相同的内容得到相同的结果
  - 不同的内容得到不同的结果
+ 在python中，设置字典的键值对时，首先对key进行hash已决定如何在内存中保存字典的数据，以方便后续对字典的操作:增、删、改、查
  - 键值对的key必须是不可变类型数据
  - 键值对的value可以是任意类型的数据

```python
In [1]: d = {}
In [2]: d["name"] = "xiaoming"
In [3]: d["1"] = "整数"
In [4]: d
Out[4]: {'name': 'xiaoming', '1': '整数'}
In [5]: d[(1,)] = "整数"
In [6]: d[[1,2,3]] = "列表"
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-6-184ccaf06b98> in <module>()
----> 1 d[[1,2,3]] = "列表"

TypeError: unhashable type: 'list'

In [7]: d[{"n":"xxx"}] = "字典"
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-7-397e5cf0ea61> in <module>()
----> 1 d[{"n":"xxx"}] = "字典"

TypeError: unhashable type: 'dict'

In [8]: hash(1)
Out[8]: 1
In [10]: hash("hello")
Out[10]: -4504525527338452810
In [11]: hash("hello")
Out[11]: -4504525527338452810
In [12]: hash("hello1")
Out[12]: -8420205507634319855
In [13]: hash((1,))
Out[13]: 3430019387558
In [14]: hash([])
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-14-6420c1e61a67> in <module>()
----> 1 hash([])

TypeError: unhashable type: 'list'

In [15]: hash({})
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-15-c8fd4c7a4881> in <module>()
----> 1 hash({})

TypeError: unhashable type: 'dict'
```
