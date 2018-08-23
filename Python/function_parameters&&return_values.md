## 函数参数和返回值的作用
函数根据有没有参数 以及有没有返回值，可以相互结合：
1. 无参数，无返回值
2. 无参数，有返回值
3. 有参数，无返回值
4. 有参数，有返回值

![parameter_and_return](image/parameter_and_return.png)

> 定义函数，是否接收参数，或者是否返回结果，是根据实际的功能需求来决定的！
1. 如果函数内部处理的数据不确定，就可以将外界的数据以参数传递到内部
2. 如果希望一个函数执行完成后，向外界汇报执行结果，就可以增加函数的返回值

## 函数的返回值
+ 在程序开发中，希望一个函数执行结束后，告诉调用者一个解雇，以便调用者针对具体的结果做后续的处理
+ **返回值** 是函数完成工作后，最后给调用者一个结果
+ 在函数中使用 return 关键之可以返回结果
+ 调用函数一方，可以使用变量来接收函数的返回值

**示例**
+ 假设开发一个函数能够同时返回当前温度和湿度
+ 先返回温度的功能如下：
```python
  def measure():
      """测量温度和湿度"""
      print("开始测量...")
      temp = 10
      wetness = 50
      print("测量结束...")
      return temp
  result = measure()
  print(result)
  # 结果
  开始测量...
  测量结束...
  10
```
+ 利用元组在返回温度的同时，也能够返回湿度
+ 改造如下：
```python
  def measure():
      """测量温度和湿度"""
      print("开始测量...")
      temp = 10
      wetness = 50
      print("测量结束...")
      # 元组-可以包含多个数据，因此可以使用元组让函数一次返回多个值
      # 如果函数返回的类型是元组，小括号可以省略
      # return (temp,wetness)
      return temp,wetness
  result = measure()
  print(result)
  # 结果
  开始测量...
  测量结束...
  (10, 50)
```
```python
  def measure():
      """测量温度和湿度"""
      print("开始测量...")
      temp = 10
      wetness = 50
      print("测量结束...")
      # 元组-可以包含多个数据，因此可以使用元组让函数一次返回多个值
      # 如果函数返回的类型是元组，小括号可以省略
      # return (temp,wetness)
      return temp,wetness
  # 元组
  result = measure()
  print(result)
  # 需要单独处理温度或者湿度 -- 不方便
  print(result[0])
  print(result[1])
  # 如果函数返回的类型是元组，同时希望单独的处理元组中的元素
  # 可以使用多个变量，一次接收函数的返回结果
  # 注意：使用多个变量接收结果时，变量的个数应该和元组中元素的个数保持一致
  gl_temp,gl_wetness = measure()
  print(gl_temp)
  print(gl_wetness)
  # 结果
  开始测量...
  测量结束...
  (10, 50)
  10
  50
  开始测量...
  测量结束...
  10
  50
```
## 面试题 -- 交换两个数字
**题目要求**
1. 有两个整数变量 a = 6，b = 100
2. 不使用其他变量，交换两个变量的值

```python
  a = 6
  b = 99

  # 解法1： 使用其他变量
  # c = a
  # a = b
  # b = c
  # 解法2：不使用其他变量
  # a = a + b
  # b = a - b
  # a = a - b
  # 解法3：Python专有
  # a,b = (b,a)
  # 等号右边是元组，只是把小括号省略了
  a,b = b,a
  print(a)
  print(b)
  # 结果
  99
  6
```
## 函数的参数
### 不可变和可变的参数
> 问题1：在函数内部，针对参数使用赋值语句，会不会影响到调用函数时传递的实参变量？ -- 不会

+ 无论传递的参数是可变还是不可变
  - 只要针对参数使用赋值语句，会在函数内部修改局部变量的引用，不会影响到外部变量的引用

```python
  def demo(num,num_list):
      print("函数内部的代码")

      # 在函数内部，针对参数使用赋值语句,不会修改到外部的实参变量
      num = 100
      num_list = [1,2,3]
      print(num)
      print(num_list)
      print("函数执行完成")


  gl_num = 99
  gl_list = [4,5,6]
  demo(gl_num,gl_list)
  print(gl_num)
  print(gl_list)
  # 结果
  函数内部的代码
  100
  [1, 2, 3]
  函数执行完成
  99
  [4, 5, 6]
```