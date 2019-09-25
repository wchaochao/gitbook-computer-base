# 磁盘

标签（空格分隔）： 计算机基础

---

存储文件

## 结构

磁盘通过将其物理表面划分为多个空间来使用

* 扇区：磁盘读写的最小单位，主要有 512B 与 4KB 两种格式
* 磁道：扇区组成的同心圆
* 柱面：多个盘片的同一磁道组成柱面

## 操作

* 分区：将磁盘分为多个区
* 格式化：使用文件系统对分区格式化
* 挂载：将格式化了的分区挂载到某个目录
* 读写：读写挂载分区的文件

## 加载

* 程序保存在存储设备中，通过有序的读出来实现运行
* 存储在磁盘的程序需要读入到内存后才能运行

![程序加载](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/disk-load.png)

### 磁盘缓存

把从磁盘中读取的数据存储到内存空间，加快磁盘数据的访问速度

![磁盘缓存](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/disk-cache.png)

### 虚拟内存

把磁盘的一部分作为假想的内存使用

* 在内存不足时，将实际内存和虚拟内存进行置换来运行程序

![虚拟内存](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/virtual-memory.png)

### DLL文件

Dynamic Link Library，动态链接文件

* 在程序运行时动态加载Library（函数和数据的集合），实现函数共享

![dll](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/dll.png)
