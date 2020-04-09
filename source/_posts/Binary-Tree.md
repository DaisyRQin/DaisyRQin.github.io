---
title: Binary Tree
date: 2020-04-09 10:00:54
tags:
- Algorithm
- Geekbang Course
- Interview Preparation
categories:
- Coding
- Algorithm
summary: Brief notes on Tree and Binary Search Tree
toc: true
mathjax: true
---

## Tree

链表是特殊化的树，树是特殊化的图

对比链表，树是一种二维的结构

Root; Parent Node; Child Node

Binary Tree

递归树

## 树的遍历

$O(n)$ 的算法复杂度

前序 ( Pre-order) ：根-左-右

中序 (In-order) ：左-根-右

后序 (Post-order) ：左-右-根

基于递归遍历，因为没法有效地循环

## Binary Search Tree

Also called as Ordered Binary Tree, Sorted Binary Tree.

空树也是二叉搜索树

Defined as:

- 左子树的 **所有结点** 的值小于它的根节点的值
- 右子树的 **所有结点** 的值大于它的根节点的值

左、右子树也分别为二叉查找树（所谓 重复性）

中序遍历：升序排列

#### 查询

$O(\log n)$

每次都可以筛掉一半的结点

#### 插入

$O(\log n)$

查询没有找到的话，最后到达的位置就是这个结点应该在的位置，所以和查询有着相同的时间复杂度。

#### 创建

不断调用插入操作

#### 删除

$O(\log n)$

如果是叶子结点：则直接删除即可

若删除的是根结点或者是某一个重要结点：找一个和根结点最接近的作为根结点，把它替换。常用是找第一个大于它的结点，用来替换。

#### 特殊情况

树退化成了一个链表，则时间复杂度变高。

### 中序遍历

递归算法：左-根-右；分别递归调用不同的结点。

递归本身没有效率差别问题，只要算法复杂度没有问题就可。