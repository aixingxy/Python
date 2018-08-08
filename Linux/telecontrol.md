# 远程管理常用命令

## 关机/重启

|序号|命令|对应英文|作用|
|:---|:---|:---|:---|
|01   |shutdown 选项 时间   |shutdown   | 关机/重新启动   |

### shutdown
+ shutdown 命令可以安全关闭或者重新启动系统

|选项|含义|
|:---|:---|
|-r   |重新启动   |
```
heigou@ubuntu:~$ shutdown
Shutdown scheduled for Wed 2018-08-08 20:12:34 CST, use 'shutdown -c' to cancel.
heigou@ubuntu:~$ shutdown -c
heigou@ubuntu:~$ shutdown -r now
```

**提示:**
+ 不指定选项和参数，默认表示1分钟之后关闭电脑

```
heigou@ubuntu:~$ shutdown
Shutdown scheduled for Wed 2018-08-08 20:12:34 CST, use 'shutdown -c' to cancel.
heigou@ubuntu:~$ shutdown -c
```
+ 远程维护服务器时，最好不要关闭系统，而应该重新启动系统

+ 常用命令示例

```
# 重新启动操作系统，其中 now 表示现在
$ shutdown -r now

# 立刻关机，其中 now 表示现在
$ shutdown now

# 系统在今天的 22:22 会关机
$ shutdown 22:22

# 系统再过十分钟之后会自动关机
$ shutdown +10

#取消之前指定的关机计划（当执行 $ shutdown 时需在一分钟之内执行一下命令）
$ shutdown -c
```

## 查看或配置网卡信息

|序号|命令|对应英文|作用|
|:---|:---|:---|:---|
|01   |ifconfig   |configure a network interface   |查看/配置计算机当前的网卡配置信息   |
|02   |ping ip地址   |ping   |检测到目标ip地址的连接是否正常   |
### 网卡和IP地址
#### 网卡
+ 网卡是一个专门负责网络通讯的硬件设备
+ IP地址是设置在网卡上的地址信息

例如可以把电脑比作电话，网卡相当于SIM卡，IP地址相当于电话号码

**IP地址**
+ 注意：每台电脑的IP地址不能相同，否则会出现IP地址冲突，并且没有办法正常通讯

### ifconfig 查看/配置计算机当前的网卡配置信息
#### 查看网卡配置信息

```
heigou@ubuntu:~$ ifconfig
ens33     Link encap:以太网  硬件地址 00:0c:29:63:eb:6c  
          inet 地址:192.168.74.128  广播:192.168.74.255  掩码:255.255.255.0
          inet6 地址: fe80::e52c:745:50a0:40e6/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  跃点数:1
          接收数据包:154 错误:0 丢弃:0 过载:0 帧数:0
          发送数据包:145 错误:0 丢弃:0 过载:0 载波:0
          碰撞:0 发送队列长度:1000
          接收字节:141690 (141.6 KB)  发送字节:16286 (16.2 KB)

lo        Link encap:本地环回  
          inet 地址:127.0.0.1  掩码:255.0.0.0
          inet6 地址: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  跃点数:1
          接收数据包:218 错误:0 丢弃:0 过载:0 帧数:0
          发送数据包:218 错误:0 丢弃:0 过载:0 载波:0
          碰撞:0 发送队列长度:1000
          接收字节:17801 (17.8 KB)  发送字节:17801 (17.8 KB)
```
#### 查看网卡对应的IP地址
+ 为了快速定位 inet 地址

```
heigou@ubuntu:~$ ifconfig | grep inet
          inet 地址:192.168.74.128  广播:192.168.74.255  掩码:255.255.255.0
          inet6 地址: fe80::e52c:745:50a0:40e6/64 Scope:Link
          inet 地址:127.0.0.1  掩码:255.0.0.0
          inet6 地址: ::1/128 Scope:Host
```
**提示：** 一台计算机中可能会有一个物理网卡和多个虚拟网卡，在Linux中物理网卡的名字通常以 enaXX表示

+ 127.0.0.1 被称为本地回环/环回地址，一般用来测试本机网卡是否正常

### ping

```
# 检测到目标主机是否连接正常
$ ping IP地址

# 检测本地网卡工作正常
$ ping 127.0.0.1

heigou@ubuntu:~$ ping 127.0.0.1
PING 127.0.0.1 (127.0.0.1) 56(84) bytes of data.
64 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.023 ms
64 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.047 ms
64 bytes from 127.0.0.1: icmp_seq=3 ttl=64 time=0.029 ms
64 bytes from 127.0.0.1: icmp_seq=4 ttl=64 time=0.030 ms
64 bytes from 127.0.0.1: icmp_seq=5 ttl=64 time=0.028 ms
64 bytes from 127.0.0.1: icmp_seq=6 ttl=64 time=0.036 ms
64 bytes from 127.0.0.1: icmp_seq=7 ttl=64 time=0.029 ms
64 bytes from 127.0.0.1: icmp_seq=8 ttl=64 time=0.028 ms
^C
--- 127.0.0.1 ping statistics ---
8 packets transmitted, 8 received, 0% packet loss, time 7149ms
rtt min/avg/max/mdev = 0.023/0.031/0.047/0.007 ms
```

+ ping 一般用于检测当前计算机到目标计算机之间的网络是否通畅，数值越大，速度越大
+ ping 的工作原理与潜水艇的声纳相似，ping这个命令就是取自声纳的声音
+ 网络管理员之间也常将 ping 做动词

**原理：网络上的机器都有唯一确定的IP地址，我们给目标IP地址发送一个数据包，对方就要返回一个数据包，根据返回的数据包以及时间，我们可以确定目标主机的存在**

**提示：**在Linux中，想要终止一个终端程序的执行，绝大多数都可以使用
**ctrl+c**
