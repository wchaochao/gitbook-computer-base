# 算法

标签（空格分隔）： 计算机基础

---

## 介绍

把解决问题的步骤无一遗漏地用文字或图表示出来

* 步骤必须是明确的并且步骤数必须是有限的
* 计算机不靠直觉而是机械地解决问题
* 了解并应用典型算法
* 利用计算机的处理速度
* 使用编程技巧提升程序执行速度
* 找出数字间的规律
* 先在纸上考虑算法

## 用流程图表示

* 先从整体上考虑程序的粗略流程：初始化处理 → 循环处理 → 收尾处理
* 再考虑程序各个部分细节的流程

## 典型算法

| 名称 | 用途 |
| --- | --- |
| 辗转相除法 | 求解最大公约数 |
| 埃拉托斯特尼筛法 | 判定素数 |
| 顺序查找 | 检索数据 |
| 二分查找 | 检索数据 |
| 哈希查找 | 检索数据 |
| 冒泡排序 | 数据排序 |
| 快速排序 | 数据排序 |

### 辗转相除法

求解最大公约数

```javascript
/**
 * a > b时，最大公约(a, b) = 最大公约(bk + c, b) = 最大公约(c, b)
 */
function getMaxCommonDivisor (a, b) {
  if (a === b) {
    return a
  } else if (a > b) {
    return getMaxCommonDivisor(a % b, b)
  } else {
    return getMaxCommonDivisor(a, b % a)
  }
}
```

### 埃拉托斯特尼筛法

判定素数

```javascript
/**
 * 判断x能否被2到根号x的整数整除
 */
function IsPrime (x) {
  for (let i = 2; i <= Math.pow(x, 0.5); i++) {
    if (x % i === 0) {
      return false
    }
  }

  return true
}
```

### 顺序查找

检索数据

```javascript
/**
 * 遍历数组，查找符合条件的元素
 */
function sequentialSearch (arr, condition) {
  for (let i = 0; i < arr.length; i++) {
    if (condition(arr[i])) {
      return i
    }
  }

  return -1
}
```

### 二分查找

检索数据

### 哈希查找

检索数据

### 冒泡排序

数据排序

```javascript
/**
 * 通过不断交互相邻的数，将本轮循环中最大的数往后沉淀
 */
function bubbleSort (arr) {
  for (let i = arr.length - 1; i > 0; i++) {
    let done = true
    for (let j = 0; j < i; j++) {
      if (arr[j] > arr[j + 1]) {
        let temp = arr[j]
        arr[j] = arr[j + 1]
        arr[j + 1] = temp
        done = false
      }
    }

    if (done) {
      break
    }
  }

  return arr
}
```

### 快速排序

数据排序
