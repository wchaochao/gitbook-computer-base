# C语言

标签（空格分隔）： 计算机基础

---

## 变量

表示数据

* 全局变量：函数模块外定义的变量，所有函数都可访问
* 局部变量：函数内定义的变量，只能在函数内访问

### 数据类型

预先被定义过的位数和精度

| 名称 | 描述 |
| --- | --- |
| char | 8位有符号整数 |
| short | 16位有符号整数 |
| int/long | 32位有符号整数 |
| float | 32位单精度浮点数 |
| double | 64位双精度浮点数 |

### 变量声明

声明变量的数据类型，变量要先声明后使用

```c
int a;
a = 123;
```

## 函数

表示指令

* 参数：传入函数的值
* 返回值：函数返回的值

### 标准函数库

系统提供的通用功能函数，被包含在头文件中

```c
#include <stdio.h>
```

### 函数调用

程序从main函数开始启动，main函数又可调用其他函数

```c
#include <stdio.h>

int average (int, int)

void main (void) {
  int a, b, ave;
  scanf("%d", &a);
  scanf("%d", &b);
  ave = average(a, b);
  printf("%d\n", ave);
}

int average (int a, int b) {
  return (a + b) / 2
}
```
