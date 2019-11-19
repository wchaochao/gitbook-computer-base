# I/O

标签（空格分隔）： 计算机基础

---

Input/Output, 输入输出，用于与周边设备交互

## 结构

![I/O结构](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/io-port.png)

### I/O地址

连接到计算机的周边设备地址，也称为端口

### I/O引脚

* 地址总线引脚：I/O中的寄存器地址
* 数据总线引脚：I/O的读写数据
* 输入输出引脚：从外部设备读取数据或向外部设备写入数据
* 控制引脚
 * 激活引脚：在电路中激活I/O，用于控制CPU的读写位置
 * 读写操作引脚：读或写I/O的数据
 * 时钟引脚：接收时钟信号
 * 同步引脚：同步时钟
 * 中断引脚：向CPU发出中断请求

## 交互

### IRQ

Interrupt Request, 中断请求

* 周边设备发出中断请求，暂停当前正在运行的程序，跳转到中断处理程序，运行完后再返回原来的程序

![IRQ](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/io-irq.png)

### DMA

Direct Memory Access, 直接内存访问

* 周边设备发出DMA通道信号，在不通过CPU的情况下，直接对内存进行数据传输，如加载磁盘中的程序

![DMA](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/io-dma.png)
