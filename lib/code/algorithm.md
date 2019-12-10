# 算法

标签（空格分隔）： 计算机基础

---

保证特定计算过程正确执行的一系列步骤

* 步骤必须是明确的并且步骤数必须是有限的
* 步骤可以用文字、流程图、伪代码表示

## 时间复杂度

算法所花的时间与数据量的关系

* 常数阶O(1): 不受数据量影响，如普通语句
* 对数阶O(logn): 与数据量的对数成正比，如二分策略
* 线性阶O(n): 与数据量成正比，如循环
* 线性对数阶O(nlogn)：与数据量的nlogn成正比，如分治
* 平方阶O(n²)：与数据量的平方成正比，如双层循环
* 指数阶O(2^n)：指数级增长，如穷举可能性

![时间复杂度](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/time-complexity.png)

## 数学算法

### 辗转相除法

求解最大公约数

```javascript
/**
 * a > b时，最大公约(a, b) = 最大公约(bk + c, b) = 最大公约(c, b)
 */
function getMaxCommonDivisor (a, b) {
  if (a !== Math.floor(a) || b !== Math.floor(b)) {
    console.error('参数不是整数')
    return
  }

  a = Math.abs(a)
  b = Math.abs(b)
  if (a === 0 && b === 0) {
    console.error('参数不能全为0')
    return
  }

  let max = Math.max(a, b)
  let min = Math.min(a, b)
  if (min === 0) {
    return max
  }

  let n = max % min
  while (n !== 0) {
    max = Math.max(n, min)
    min = Math.min(n, min)
    n = max % min
  }

  return min
}
```

### 埃拉托斯特尼筛法

判定素数

```javascript
/**
 * 判断x能否被2到根号x的整数整除
 */
function IsPrime (x) {
  if (x <= 1 || x !== Math.floor(x)) {
    console.error('无效参数')
    return
  }

  for (let i = 2; i <= Math.pow(x, 0.5); i++) {
    if (x % i === 0) {
      return false
    }
  }

  return true
}
```

## 查找算法

### 顺序查找

```javascript
/**
 * 遍历数组，查找符合条件的元素
 */
function sequentialSearch (arr, callback) {
  for (let i = 0; i < arr.length; i++) {
    if (callback(arr[i])) {
      return i
    }
  }

  return -1
}
```

### 二分查找

```javascript
/**
 * 按照二分法搜索已排序的数组
 */
function binarySearch (arr, callback) {
  let min = 0
  let max = arr.length - 1

  while (min <= max) {
    let mid = Math.floor((min + max + 1) / 2)
    let number = callback(arr[mid])

    if (number === 0) {
      return mid
    } else if (number > 0) {
      max = mid - 1
    } else {
      min = mid + 1
    }
  }

  return -1
}
```

## 排序算法

### 冒泡排序

```javascript
/**
 * 每轮循环时依次比较相邻的元素，不符合排序规则时交换，将最大或最小的数向后沉淀
 */
function bubbleSort (arr) {
  let len = arr.length

  for (let i = len - 1; i > 0; i--) {
    for (let j = 0; j < i; j++) {
      if (arr[j] > arr[j + 1]) {
        swap(arr, j, j + 1)
      }
    }
  }

  return arr
}

function swap (arr, i, j) {
  let temp = arr[i]
  arr[i] = arr[j]
  arr[j] = temp
}
```

### 选择排序

```javascript
/**
 * 每轮循环时在剩下的数中找到最大或最小值，放在正确的位置
 */
function selectionSort (arr) {
  let len = arr.length

  for (let i = 0; i < len - 1; i++) {
    let min = i
    for (let j = i + 1; j < len; j++) {
      if (arr[j] < arr[min]) {
        min = j
      }
    }

    if (i !== min) {
      swap(arr, i, min)
    }

  }

  return arr
}

function swap (arr, i, j) {
  let temp = arr[i]
  arr[i] = arr[j]
  arr[j] = temp
}
```

### 插入排序

```javascript
/**
 * 将未排序的元素插入到已排序的元素中
 */
function insertionSort (arr) {
  let len = arr.length
  let i, j, value

  for (i = 1; i < len; i++) {
    value = arr[i]
    for (j = i - 1; j >= 0 && arr[j] > value; j--) {
      arr[j + 1] = arr[j]
    }
    arr[j + 1] = value
  }

  return arr
}
```

### 合并排序

```javascript
/**
 * 将数组不断的拆两半，直至只有1个或0个元素，再不断的两两合并
 */
function merge (left, right) {
  let result = []
  let il = 0
  let ir = 0

  while (il < left.length && ir < right.length) {
    if (left[il] < right[ir]) {
      result.push(left[il++])
    } else {
      result.push(right[ir++])
    }
  }

  return result.concat(left.slice(il)).concat(right.slice(ir))
}

function mergeSort (arr) {
  let len = arr.length
  if (len < 2) {
    return arr
  }

  let mid = Math.floor(len / 2)
  let left = arr.slice(0, mid)
  let right = arr.slice(mid)
  let params = merge(mergeSort(left), mergeSort(right))

  arr.splice(0, len, ...params)

  return arr
}
```

### 快速排序

```javascript
/**
 * 选择一个元素作为基准，小于基准的元素移到基准的左边，大于的移到右边
 */
function swap (arr, i, j) {
  let temp = arr[i]
  arr[i] = arr[j]
  arr[j] = temp
}

function partition (arr, left, right) {
  let mid = Math.floor((left + right) / 2)
  let i = left
  let j = right
  let privot = arr[mid]

  while (i <= j) {
    while (arr[i] < privot) {
      i++
    }

    while(arr[j] > privot) {
      j--
    }

    if (i <= j) {
      swap(arr, i, j)
      i++;
      j--;
    }
  }
  return i
}

function quickSort (arr, left, right) {
  let len = arr.length
  if (arr.length < 2) {
    return arr
  }

  left = left || 0
  right = right || (len - 1)

  let index = partition(arr, left, right)
  if (left < index - 1) {
    quickSort(arr, left, index - 1)
  }
  if (index < right) {
    quickSort(arr, index, right)
  }

  return arr
}
```
