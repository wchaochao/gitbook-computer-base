# 汇编语言

标签（空格分隔）： 计算机基础

---

使用助记符的编程语言

## 语法

把标签、操作码和操作数并排写在一行上，分号结尾，表示一个指令

* 标签：指代当前行的内存地址，可为任意单词
* 操作码：指令，由CPU种类决定
* 操作数：指令对象，多个操作数用逗号分隔

### 操作码

| 操作码 | 操作数 | 功能 |
| --- | --- | --- |
| mov | A, B | 把B的值赋给A |
| inc | A | A的值加一 |
| and | A, B | A、B的值相加，结果赋给A |
| xor | A, B | A、B的值异或，结果赋给A |
| push | A | 把A压入栈 |
| pop | A | 值出栈并赋给A |
| call | A | 调用函数A |
| ret | 无 | 返回到函数的调用源 |
| cmp | A, B | 比较A、B的值（相减），结果自动存入标志寄存器 |
| jmp | A | 无条件跳转到A地址 |
| jle | A | 小于或等于时跳转到A地址 |
| jge | A | 大于或等于时跳转到A地址 |
| in | A, B | 端口B输入的值赋给寄存器A |
| out | B, A | 寄存器A的值输出给端口B |

### 操作数

寄存器、常数、内存地址等

| 操作数 | 描述 |
| --- | --- |
| reg | 寄存器reg |
| num | 数值num，如十进制123、十六进制123H |
| [reg] | 寄存器reg存储的地址 |
| [num] | 值为num的地址 |

## 转换

汇编语言编写的源代码与本地代码一一对应，源文件扩展名为`.asm`

* 汇编：将汇编语言编写的源代码转换为本地代码
* 反汇编：将本地代码转换为汇编语言编写的源代码

![转换](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/assemply-convert.png)

### 伪指令

指示程序的构造

| 伪指令 | 名称 | 描述 |
| --- | --- | --- |
| segment/ends| 段定义 | 一段连续的内存空间，如指令、初始化的全局变量、未初始化的全局变量 |
| group | 组 | 将多个段定义汇总为一个组，如初始化的全局变量和未初始化的全局变量汇总成全局变量组 |
| proc/endp | 过程 | 一个函数 |

![伪指令](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/assemply-pseudo-command.png)

### 函数调用

函数的参数是通过栈来传递，返回值是通过寄存器来返回的

![函数调用](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/assemply-function-call.png)

### 变量

* 全局变量：函数外部定义的变量，保存在全局变量组中，所有函数都可访问
* 局部变量：函数内部定义的变量，临时保存在寄存器或栈中，只能在函数内部访问

![局部变量](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/assemply-local-variable.png)

### 流程控制

通过比较指令和跳转指令实现条件分支、循环等流程
