# 运行环境

标签（空格分隔）： 计算机基础

---

程序的运行环境 = 硬件 + 操作系统

## 硬件

* CPU影响机器语言的执行
* 内存影响指令和数据的存储
* I/O影响外围设备的驱动

## 操作系统

屏蔽各种硬件的不同，提供统一的硬件接口

* 内核：管理所有活动和驱动硬件
* 系统调用层：提供一组的API供应用程序调用

![操作系统](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/operate-system.png)

### 常见

* MS-DOS系列: Microsoft Disk Operating System
* Windows系列
* Mac系列
* Unix系列
* Linux系列

### 虚拟机

* 通过虚拟机安装其他操作系统
* Java虚拟机：提供Java字节代码的运行环境

![Java虚拟机](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/java-virtual-machine.png)

## 应用程序

运行在操作系统之上的程序，对操作系统有依赖

## BIOS

Basic Input/Output System，存储在ROM中，预先内置在计算机内部的程序

* 检查硬件是否运行正常
* 启动引导程序，把操作系统加载到内存中运行
