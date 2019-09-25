# 文件

标签（空格分隔）： 计算机基础

---

以字节为单位存储

## 分类

* 文本文件：存储文字
* EXE文件：存储可执行程序
* 图像文件：存储图像
 * BMP: bitmap，未压缩
 * JPEG：数码图像，不可逆压缩
 * gif: 256色

## 压缩

* 可逆压缩：能还原到压缩前的状态，如文本文件压缩、EXE文件压缩
* 不可逆压缩：不能还原到压缩前的状态，如图像压缩

![压缩](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/compress.png)

### RLE算法

Run Length Encoding，行程长度编码

* 使用数据*重复次数的形式压缩文件
* 经常被用于压缩传真的图像，不适合压缩数据不连续出现的文件，如文本文件

![RLE算法](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/compress-REL.png)

### 哈夫曼算法

为压缩对象构造最佳的编码体系，并以该编码体系为基础来进行压缩

![哈夫曼压缩](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/compress-HFM.png)

通过哈夫曼树构建编码体系，频率高的数据用最少的二进制位表示

![哈夫曼树](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/compress-HFM-tree.png)
