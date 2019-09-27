# 运行环境

标签（空格分隔）： 计算机基础

---

程序的运行环境 = 硬件 + 操作系统

## 硬件

* CPU影响机器语言的执行
* 内存影响指令和数据的存储
* I/O影响外围设备的驱动

## 操作系统

管理计算机软件和硬件资源的控制程序

* 内核：管理软件活动和驱动硬件
* 系统调用：提供给应用调用的API

### 发展

操作系统的原型：监控程序

![操作系统的原型](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/operate-system-prototype.png)

初期操作系统：监控程序 + 基本输入输出程序

![初期操作系统](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/operate-system-simple.png)

现代操作系统：多个实用程序的几何体

![现代操作系统](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/operate-system-current.png)

### Windows操作系统

* 32位或64位操作系统
* 通过时钟分割技术实现多任务功能
* 提供网络功能及数据库功能
* GUI用户界面
* 所见即所得实现打印输出
* 即插即用实现设备驱动
* 通过API函数集来提供系统调用

### 其他操作系统

可通过虚拟机安装其他操作系统

* MS-DOS: Microsoft Disk Operating System
* Mac
* Unix
* Linux

### Java虚拟机

提供Java字节代码的运行环境

![Java虚拟机](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/java-virtual-machine.png)

### BIOS

Basic Input/Output System，基本输入输出系统，预先内置在计算机ROM中的程序

* 开机自检程序：从CMOS中读写系统设置的具体信息，对硬件部分进行检测
* 系统自启动程序：启动引导程序并由引导程序加载操作系统
* 基本输入输出程序：进入BIOS界面进行操作

## 应用

* 运行在操作系统之上的程序
* 通过系统调用使用操作系统的功能，间接控制硬件

![应用程序](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/application.png)
