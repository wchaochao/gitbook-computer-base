# 字符编码

标签（空格分隔）： 计算机基础

---

将字符转换为二进制

* 字符集：已编号字符的有序集合
* 字符编码：在字符集与二进制序列之间建立映射关系，同一字符集可以有多种字符编码

## 字符编码模型

* 抽象字符表：明确字符的范围，如封闭的ASCII字符、开放的Unicode字符
* 编号字符集：用数字给字符编号，如ASCII字符集、Unicode字符集
* 字符编码方式：将数字编号编码为二进制序列，如UTF-8、UTF-16、UTF-32
* 字符编码模式：将二进制序列映射为字节序列，如大端序模式、小端序模式
* 传输编码语法：对字节序列作进一步适应性编码处理，如压缩

## 字符编码演变

* ASCII编码方案
* ANSI编码方案
* Unicode/UCS编码方案

## ASCII编码方案

American Standard Code for Information Interchange, 美国信息交换标准代码，用于显示现代英语

### 字符集

* 0~31: 不可显示不可打印的控制字符
* 32：空格字符
* 33~126：可显示可打印的字符，包括英文字母、阿拉伯数字、符号
* 127：不可显示不可打印字符的控制字符DEL

![ASCII字符集](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/ASCII.jpg)

### 编码

* 使用七位二进制表示一个字符，共128个字符
* 采用单字节表示时，第一位固定为0

## ISO/IEC 8859编码方案

ASCII的扩展编码，用闲置的最高位编码新的字符，用于显示欧洲语言

### 字符集

包括15个字符集，即ISO/IEC 8859-n，n=1、2、3...15、16（12未定义）

* ISO/IEC 8859-1：收录了西欧常用字符，目前使用得最为普遍，别名Latin1
* ISO/IEC 8859-2: 收录了东欧字符，别名Latin-2
* ISO/IEC 8859-3: 收录了南欧字符，别名Latin-3
* ISO/IEC 8859-4: 收录了北欧字符，别名Latin-4
* ISO/IEC 8859-5: 收录了斯拉夫语系字符，别名Cyrillic
* ISO/IEC 8859-6: 收录了阿拉伯语系字符，别名Arabic
* ISO/IEC 8859-7: 收录了希腊字符，别名Greek
* ISO/IEC 8859-8: 收录了希伯莱(犹太人)字符，别名Hebrew
* ISO/IEC 8859-9: 收录了土耳其字符，别名Latin-5
* ISO/IEC 8859-10: 收录了斯堪地那维亚半岛字符，别名Latin-6
* ISO/IEC 8859-11: 收录了泰国字符，别名Thai
* ISO/IEC 8859-12: 未定义
* ISO/IEC 8859-13: 收录了波罗的海字符，别名Latin-7
* ISO/IEC 8859-14: 收录了塞尔特字符，别名Latin-8
* ISO/IEC 8859-15: 将Latin-1中较少用到的符号删除，换成当初遗漏的法文和芬兰字母，别名Latin-9
* ISO/IEC 8859-16: 收录了东南欧国家语言字符，别名Latin-10

![Latin1字符集](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/Latin1.png)

### 编码

* 0x00~0x7F仍对应ASCII字符
* 0xA0~0xFF对应补充扩展的字符
* 0x80~0x9F未定义字符

## GB系列编码方案

国标系列编码，用于显示汉字

### GB2312

收录的汉字不足一万个，基本能满足日常使用需求

#### 字符集

分成94个区，每区有94个位

* 01~09区：包括拉丁字母、希腊字母、日文平假名及片假名字母、俄语西里尔字母在内容的682个全角字符
* 10~15区：空区
* 16~55区：3755个常用汉字(也称一级汉字)，按拼音排序
* 56~87区：3008个非常用汉字(也称二级汉字)，按部首/笔画排序
* 88~94区：空区，留待扩展

*英文输入法下半角字符宽度为全角的一半*

![GB2312字符集](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/GB2312.png)

#### 编码

* ASCII字符仍用ASCII码表示
* GB2312字符用机内码表示
 * 区码、位码各用一个字节表示
 * 区位码分别加+32得到国标码，避开ASCII中不可显示的字符
 * 国标码加128得到机内码，避开ASCII码

![GB2312编码](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/GB2312-encode.jpg)

### GBK

GB2312的扩展，利用GB2312未使用的码点空间，收录生僻字、繁体字等

#### 字符集

* GBK/1：增补字符
* GBK/2：GB2312的中文
* GBK/3：CJK（中日韩统一表意文字）字符
* GBK/4：CJK字符和增补字符
* GBK/5：非中文字符
* UDC：用户自定义字符

![GBK字符集](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/GBK.png)

#### 编码

* 字节值为0~127，对应ASCII字符
* 字节值为128~255，与下一个字节组成汉字

### GB18030

GBK的扩展，使用两个字节或四个字节表示中文

### GB13000

与上述GB系列不兼容，与国际标准ISO/IEC10646及Unicode标准在基本平面上基本保持一致

![GB13000](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/GB13000.png)

### Big5

繁体汉字编码方案，使用两个字节表示一个繁体汉字

* 高位字节在0x81~0xFE之间
* 低位字节在0x40~0x7E及0xA1~0xFE之间

### 输入码

汉字输入用的编码，往往会出现重码，需要选择编号

* 数字编码：区位码等
* 拼音编码：全拼、双拼等
* 字形编码：五笔码

### 输出码

使用n*n的点阵显示汉字，笔划经过的方格值为1，未经过的为0

* 存储一个汉字的字节数=点阵行数×(点阵列数/8)
* 使用字库存储所有汉字的字形信息，以字体文件的形式存在

## ANSI编码方案

各个国家和地区所独立制定的既兼容ASCII又互相之间不兼容的字符编码统称，默认为系统Locale对应的编码

* 简体中文操作系统中ANSI编码默认为GB系列编码
* 繁体中文操作系统中ANSI编码默认为Big5编码
* 日文操作系统中ANSI编码默认为Shift JIS编码

### 代码页

各编码方案在计算机中的具体编码实现，字符-字节映射表

![编码处理](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/encode-process.jpg)

## Unicode编码方案

全球统一字符编码方案

### Unicode字符集

全球统一的通用字符集，目标是涵盖目前人类使用的所有字符，并为每个字符分配唯一的字符编号

* 按照使用上的频繁度划分为了17个平面，每个平面上的编号空间有2^16=65536个码点
* 使用U+十六进制编号表示一个码点，对应一个字符
* 第0个平面BMP：基本平面，基本涵盖了当今世界上正在使用中的常用字符
 * 兼容Latin1：U+0000 ~ U+00FF与Latin1一致
 * 专用区：U+E000 ~ U+F8FF，被保留位私用
 * 代理区：U+D800 ~ U+DFFF，使用其中的两个码点代理辅助平面的字符
* 其他增补平面SP：辅助平面，要么用来表示一些非常特殊的字符，要么被留作扩展之用

![Unicode字符集](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/Unicode.png)

### UCS字符集

Universal Character Set，通用字符集，ISO及IEC联合发布的全球统一的通用字符集，与Unicode字符集基本保持一致

* `UCS-2`：使用两字节表示，对应Unicode的基本平面
* `UCS-4`：使用四字节表示，对应Unicode字符集

### UTF-8

8-bit Unicode/UCS Transformation Format，采用单字节码元编码，不需要考虑字节序，最优设计的UTF

* ASCII字符使用一个码元表示，以0开头，完全兼容ASCII
* 非ASCII字符使用多个码元表示，第一个码元指示有几个码元（前n位为1，第n+1位为0），其他码元以10开头

```
Unicode符号范围       | UTF-8编码方式
(十六进制)            | (二进制)
----------------------+---------------------------------------------
0000 0000 - 0000 007F | 0xxxxxxx
0000 0080 - 0000 07FF | 110xxxxx 10xxxxxx
0000 0800 - 0000 FFFF | 1110xxxx 10xxxxxx 10xxxxxx
0001 0000 - 0010 FFFF | 11110xxx 10xxxxxx 10xxxxxx 10xxxxxx
```

### UTF-16

16-bit Unicode/UCS Transformation Format，采用双字节码元编码，需要考虑字节序，最早推出的UTF

* 基本平面的字符使用一个码元表示，兼容UCS-2
* 辅助平面的字符使用两个在代理区的码元表示，第一个码元为高位，在U+D800到U+DBFF之间，第二个码元为低位，在U+DC00到U+DFFF之间

```
// 将大于U+FFFF的字符，从Unicode转为UTF-16
H = Math.floor((C - 0x10000) / 0x400) + 0xD800
L = (C - 0x10000) % 0x400 + 0xDC00

// 将大于U+FFFF的字符，从UTF-16转为Unicode
C = (H - 0xD800) * 0x400 + L - 0xDC00 + 0x10000
```

![UTF-16](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/UTF-16.png)

### UTF-32

32-bit Unicode/UCS Transformation Format，采用四字节码元编码，需要考虑字节序

* 所有字符都用一个码元表示

![UTF-32](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/UTF-32.jpg)

## 字节序

多字节的数据类型在计算机中存储、读取时其各个字节的排列顺序

* 大端序：Big-Endian，高位在前，如Mac
* 小端序：Little-Endian，低位在前，如x86

![大端序](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/big-endian.png)

![小端序](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/little-endian.png)

### BOM

Byte-Order Mark，字节顺序标记，字符U+FEFF的别名

* 出现在字节流的开头：标识字节流的字节序
 * UTF-16中，FE FF为大端序，FF FE为小端序
 * UTF-32中，00 00 FE FF为大端序，FF FE 00 00为小端序
 * UTF-8中，不需使用BOM，但Windows中使用EF BB BF（BOM的UTF-8表示）表明编码为UTF-8
* 出现在字节流的中间：零宽度非换行空格，Unicode3.2后被舍弃，使用U+2060来表示零宽度非换行空格

## 传输编码

对传输的字节流进行编码，如转换、压缩、加密

### Quoted-printable编码

对可打印ASCII字符外的所有其他字节编码

* 转换为3个ASCII字符，第一个字符为=，后两个字符为字节的十六进制表示
* =也需转换

```
字符    十六进制    编码
=       0x3D        =3D
```

### Base64编码

使用64个字符对字节编码

#### 字符集

* 0~25：大写字母A-Z
* 26~51：小写字母a-z
* 52-61：数字0-9
* 62： +
* 63： /

#### 编码

* 将每三个字节按六位划分为四组，每组前面加两个0，扩展为四个字节，按照字符集得到四个字节对应的字符
* 剩下两个字节时按六位划分为三组，最后一组后面也加上两个0，末尾补充一个=号扩展为四个字节
* 剩下一个字节时按六位划分为两组，最后一组后面也加上四个0，末尾补充两个=号扩展为四个字节

![base64示例](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/base64-example.png)

## 参考资料

* [刨根究底字符编码系列](https://zhuanlan.zhihu.com/paogenjiudi)
