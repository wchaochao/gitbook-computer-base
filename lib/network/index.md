# 网络

标签（空格分隔）： 计算机基础

---

通过连接多台计算机所组成的、可用于交换信息的系统

## 类型

* `LAN`: Local Area Network，局域网
* `WAN`: Wide Area Network，广域网，由多个LAN组成，如互联网

## 连接

* 安装到每台计算机上的网卡（NIC，Network Interface Card），如以太网（Ethernet）网卡
* 插到网卡上的网线
* 把网线汇集起来连接到一处的集线器
* 把多个LAN连接起来的路由器

![网络连接](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/network-connect.png)

### 数据发送

* 目的地在LAN内，直接发送数据
* 目的地在LAN外，通过路由器转发

## 地址

用于定位网络中的计算机

### MAC地址

Media Access Control，硬件地址，烧录在网卡中，由48位二进制数组成

* 前24位：组织唯一标志符，用于区分厂家
* 后24位：扩展标识符，用于区分同一厂家的网卡

![MAC地址](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/mac-address.png)

### IP地址

网络协议地址，用于将网络内的计算机分组

* 由32位二进制数组成，每8位一组，用十进制表示并用圆点分隔

![IP地址](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/ip-address.png)

组成

* 网络地址：表示分组（即LAN）的部分
* 主机地址：表示各台计算机（即主机）的部分

```bash
# 查看网络配置信息
ipconfig \all
```

### 子网掩码

用于标志网络地址部分

* 值为1的那些位对应着IP地址中的网络地址，后面值为0的那些位则对应着主机地址

计算网络地址

* IP地址 & 子网掩码 = 网络地址
* IP地址 & (~子网掩码) = 主机地址

## 硬件

### 路由器

把多个LAN连接起来

* 决定数据传输路径的设备
* 路由表中记录了通往与之相邻的路由器的路径

```bash
# 查看路由表
route print

# 查看路由过程
tracert {domain | ip}
```

### DHCP服务器

Dynamic Host Configuration Protocol，动态主机设置协议，用于动态分配IP

* 记录着可以被分配到LAN内计算机的IP地址范围和子网掩码的值

### DNS服务器

Domain Name System，域名系统，用于查询域名对应的ip

* 记录着FQDN（Fully Qualified Domain Name，完整限定域名，主机名+LAN域名）和IP地址的对应关系表

```bash
# 查看主机名
hostname

# 进入域名解析环境
nslookup
```

## 网络协议

对信息发送方式的规定或约束

### CSMA/CD

Career Sense Multiple Access with Collision Detection，带冲突检测的载波监听多路访问，以太网的运行机制

* 载波监听：监听（Sense）表示网络是否正在使用的电信号（Career）
* 多路复用：多个（Multiple）设备可以同时访问（Access）传输介质
* 带冲突检测：检测（Detection）因同一时刻的传输而导致的电信号冲突（Collision）

![CSMA机制](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/ethernet-CSMA.png)

![CD机制](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/ethernet-CD.png)

### ARP协议

Address Resolution Protocol，地址解析协议，用于实现由IP地址到MAC地址的转换

* 向LAN内所有计算机广播，询问已知IP地址的MAC地址
* 得到结果后会将结果缓存到内存中，称作ARP缓存表

```bash
# 显示ARP缓存表
arp -a
```

### IP协议

Internet Protocol，网际协议，

* 用于指定数据发送目的地的IP地址以及通过路由器转发数据

### TCP协议

Transmission Control Protocol，传输控制协议

* 把原始的大数据分割成以包（Packet）为单位的数据单元发送
* 用于通过数据发送者和接收者相互回应对方发来的确认信号，可靠地传输数据

![包](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/packet.png)

![网络层级](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/network-level.png)
