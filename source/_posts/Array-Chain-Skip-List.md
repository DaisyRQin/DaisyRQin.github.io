---
title: 'Array, Chain, Skip List'
date: 2020-04-08 20:28:30
tags:
- Algorithm
- Geekbang Course
- Interview Preparation
categories:
- Coding
- Algorithm
summary:
toc: true
mathjax: true
---

## Array

泛型：任何一个单元类型都可以放进去。

数组：在内存中开辟了一段连续的地址。访问第一个和其中任何一个元素的时间复杂度都是一样的 $O(1)$，数组访问速度比较快。

 Inserting：插入元素平均要挪动一半的元素位置，$O(n)$ 的时间复杂度。

Deleting：删除一处元素后要清理内存（自动 or 手动管理）

Look up：$O(1)$.

## Linked List / Chain

对于添加删除操作比较频繁的情况下，比较好用。

每一个元素用 class 来定义，被称为 Node。

每一个 Node 有 Value 和 Next Pointer。单链表 / 双向链表。

头指针：head

尾指针：tail

如果 tail 的 next 指针指向 head，则为循环列表。

Inserting：New Node; 更改 next 指针。$O(1)$ 的操作。

Deleting：前驱 next 指针指向后继 Node。

难以访问，必须从头节点挪到某个特殊节点，$O(n)$ 的操作。

## Skip List

在链表的基础上发展而来。

**只能用于元素有序的情况**，对标的是平衡树和二分查找，是一种 插入/删除/搜索 都是 $O(\log n)$ 的数据结构。

添加第一级索引 —— 增加一个维度，索引指向 next+1 的元素。

可以再增加第二级索引。等等多级索引。

$O(\log n)$ 的查询时间复杂度: 索引的高度为 $\log(n)$. 每层索引遍历的结点个数为 $3$。

维护成本高，增加或者删除都会更改索引。

空间复杂度：$O(n)$

## 题目解析

### 步骤

1. 5-10 分钟，读题和思考
2. 有思路：自己开始写代码；不然，马上看题解
3. 默写背诵题解，到熟练
4. 之后开始自己写，闭卷写

### Move-zeros

 #### 题目

给定一个数组 ```nums```，编写一个函数将所有 $0$ 移动到数组的末尾，同时保持非零元素的相对顺序。

#### 示例

```tex
输入: [0,1,0,3,12]
输出: [1,3,12,0,0]
```

#### 说明

1. 必须在原数组上操作，不能拷贝额外的数据
2. 尽量减少操作次数

#### 解题过程与思路

1. Loop, count the number of zero
2. new array, loop, 两个指针，非零往前放，0往后放
3. 直接在数组中进行 index 操作，loop 中记录非零元素的位置
4. 注意测试特殊情况
5. 五遍刷题法
6. 看别人的解法

