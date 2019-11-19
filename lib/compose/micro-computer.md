# 计算机

标签（空格分隔）： 计算机基础

---

## 结构

* CPU：解释执行程序
* 内存：存储程序
* I/O：存储与周边设备进行交互的数据
* 总线：连接到 CPU 中数据引脚、地址引脚、控制引脚上的电路的统称
* 时钟发生器：为CPU、I/O提供时钟信号
* 电源：将220V交流电转换为5V直流电，为各元件提供电源

![计算机硬件组成](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/hardware-composition.png)

## 硬件信息

![微型计算机元件图](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/host-system.png)

### CPU信息

* CPU种类：决定如何解释机器语言
* 时钟信号频率：1s内电信号变换的周期数

### 内存信息

* 地址空间：内存的每一个数据存储单元的地址

### I/O信息

* I/O种类：决定如何连接周边设备
* 地址空间：I/O的每个寄存器的地址，每个寄存器的功能不同
* 连接的周边设备：输入、输出设备

## 工作原理

* CPU在时钟信号的控制下解释、执行内存中存储的程序
* 按照程序中的指令从内存或I/O中把数据输入到CPU中，在CPU内部进行运算，再把运算结果输出到内存或I/O中

## 三大原则

* 计算机是执行输入、运算、输出的机器
* 程序是指令和数据的集合
* 信息使用数字来表达
