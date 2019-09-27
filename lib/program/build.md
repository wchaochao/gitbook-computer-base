# 程序构建

标签（空格分隔）： 计算机基础

---

将源文件转换为可执行文件的过程

## 代码

* 源代码：用编程语言编写的程序
* 本地代码：CPU能解释执行的机器语言程序

![代码](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/code.png)

## 编译器

在运行前将源代码转换为本地代码，生成目标文件的程序

* 与编程语言种类、CPU种类、操作系统有关

![编译器](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/compiler.png)

### 解释器

在运行时将源代码转换为本地代码的程序

## 链接器

将多个目标文件结合生成可执行文件的程序

### 库文件

将多个目标文件集成保存到一个文件中

* 静态链接库：存储目标文件的实体
* 导入库：存储操作系统的库文件链接，执行时动态调用

![链接](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/build-link.png)

## 加载

* 在可执行文件的开头，记录了本地代码全局变量和函数的相对内存地址
* 根据再配置信息将变量组和函数组复制到内存中

![加载](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/build-load.png)

## 运行

程序运行时申请分配栈和堆两个组

* 栈：存储函数的参数和局部变量，函数执行完成时自动销毁
* 堆：存储程序运行时产生的数据，数据不再需要时要进行回收

![运行](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/build-run.png)

## 垃圾回收

对不再需要的堆空间数据进行清理，释放内存空间

* C、C++等语言需要手动回收
* Java、C#等语言会自动回收
