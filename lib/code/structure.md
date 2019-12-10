# 数据结构

标签（空格分隔）： 计算机基础

---

## 变量

按照变量所存储数据的大小被分配到的一块内存空间

* 程序中数据存储的最小单位
* 每个变量都对应着一块物理上的内存空间

## 结构体

若干数据项的集合

## 数组

为了存储多个数据而在内存上集中分配出的一块内存空间，并且为这块空间整体赋予了一个名字

* 数据结构的基础
* 可通过遍历数组处理数组中的数据

## 典型数据结构

通过程序从逻辑上改变了内存的物理结构

### 栈

LIFO（Last In First Out，后进先出），最后被存入的数据是最先被处理

```javascript
class Stack {
  constructor () {
    this.items = []
  }

  push (data) {
    this.items.push(data)
  }

  pop () {
    return this.items.pop()
  }
}
```

### 队列

FIFO（First In First Out，先进先出），最先被存入的数据也是最先被处理

```javascript
class Queue {
  constructor () {
    this.items = []
  }

  enqueue (data) {
    this.items.unshift(data)
  }

  dequeue () {
    return this.items.pop()
  }
}
```

### 链表

相当于一条链路

* 每个链表元素中含有指向下一个链表元素的指针
* 可任意改变链表的顺序，用于追加或删除数组元素

```javascript
class Node {
  constructor (data) {
    this.data = data
    this.next = null
  }
}

class LinkedList {
  constructor () {
    this.head = null
    this.tail = null
  }

  push (data) {
    const node = new Node(data)

    if (this.head === null) {
      this.head = node
      this.tail = node
      return
    }

    this.tail.next = node
    this.tail = node
  }
}
```

### 二叉树

相当于一棵树，但每次都只会分为两杈

* 特殊类型的链表，每个链表元素中含有指向下两个链表元素的指针
* 用于二分查找

```javascript
class Node {
  constructor (data) {
    this.value = data
    this.left = null
    this.right = null
  }
}

class BST {
  constructor () {
    this.root = null
  }

  insertValue (value) {
    let newNode = new Node(value)

    if (!this.root) {
      this.root = newNode
    } else {
      this.insertNode(this.root, newNode)
    }
  }

  insertNode (root, newNode) {
    if (newNode.value < root.value) {
      if (!root.left) {
        root.left = newNode
      } else {
        this.insertNode(root.left, value)
      }
    } else {
      if (!root.right) {
        root.right = newNode
      } else {
        this.insertNode(root.right, value)
      }
    }
  }
}
```
