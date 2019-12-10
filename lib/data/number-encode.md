# 数字编码

标签（空格分隔）： 计算机基础

---

将数字转换为二进制

## 整数

二进制能准确表示整数

### 无符号n位整数

* 最高位不表示符号，全为正数
* 表示范围[0, 2^n - 1]

### 有符号n位整数

* 最高位表示符号，0为正、1为负
* 表示范围[-2^(n - 1), 2^(n - 1) - 1]
* 负数为正数取反加一，补码表示

```javascript
1 = 0000 0001
-1 = 1111 1111
```

## 小数

二进制表示的小数是离散的小数，有些小数只能近似表示

### 浮点数

* 用符号、尾数、基数、指数表示小数
* 小数点位置不定

```
0.75 = 0.75 * 10^0
0.75 = 7.5 * 10^1
0.75 = 75 * 10^2
```

### IEEE浮点数

```
V = (-1)^S*M*(2^E)
```

* 符号S：0为正、1为负
* 尾数M：1≤M<2，小数点前的1默认省略
* 基数：2
* 指数E：需要加上偏移量（指数部分表示范围的中间值），使得负数不需要使用符号位来表示

十进制转换为IEEE浮点数

```
十进制 -125.125
转换为二进制表示：-1111101.001
科学计数法表示：-1.111101001 * 2^6

数符S：1
尾数M：11110100 10000000 00000000 00000000 00000000 00000000 0000
阶码E：000 00000110 (阶码真值) + 011 11111111 (偏移量) = 1  00 00000101
最终值：1 + 100 00000101 + 11110100 10000000 00000000 00000000 00000000 00000000 0000
```

IEEE浮点数转换为十进制

* E不全为0且不全为1，E减去偏移量，M加上1
* E全为0，E减去偏移量再加1，M不加1，表示±0和接近0的数
* E全为1，M全为0，表示±无穷大，M不全为0，表示非数字

### 单精度浮点数

32位二进制表示小数

* 符号位：1位
* 指数位：8位，偏移量127，表示范围[-127, 128]
* 尾数位：23位

### 双精度浮点数

64位二进制表示小数

* 符号位：1位
* 指数位：11位，偏移量1023，表示范围[-1023, 1024]
* 尾数位：52位

### 计算误差

* 有些小数无法准确表示，造成计算误差
* 可通过将小数转换为整数或使用BCD（四位二进制表示0-9）避免误差