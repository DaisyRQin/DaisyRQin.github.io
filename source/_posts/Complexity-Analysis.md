---
title: Comlexity Analysis
date: 2020-04-07 10:24:19
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

## 时间复杂度 | Time Analysis

### Big $O$ notation

$O(1)$: Constant complexity

$O(\log n)$: Logarithmic complexity

$O(n)$: Linear complexity

$O(n^2)$: $n$ square complexity

$O(n^3)$: $n$ cubic complexity

$O(2^n)$: Exponential complexity

$O(n!)$: Factorial

Note: we only care about the most complex calculation

 

小技巧：直接看这段函数，或者看这段代码根据 $n$ 的不同情况运行了多少次



### 例题



Calculation: $1+2+\dots+n$



#### sum up with iteration

```python sum up with iteration
y = 0
for i in range(n):
		y = y + 1
```

This block of code has the time complexity of $O(n)$.

#### sum up with the formula

$$
y = \frac{n(n+1)}{2}
$$

This block of code has the time complexity of $O(1)$, because this line of code will only be executed once.



## 递归

找出递归状态的递归树。

### 例题



Fib: $0, 1, 1, 2, 3, 5, 8, 13, 21, \dots$

$F(n) = F(n-1) + F(n-2)$. 

Calculation: Find $F(n)$



#### 直接用递归

```java using recursion directly
int fib(int n){
	if(n < 2) return n
	return fib(n - 1) + fib(n - 2)
}
```

Analysis: take $n=6$, find out how this code execute.

每展开一层，下面的节点树是下面的两倍

可以看出来状态数中有很多节点被重复计算。

直接用递归的时间复杂度为 $O(2^n)$

建议：用缓存存中间结果，或者直接用循环



### Mater Theorem 主定理

用来计算递归的时间复杂度

#### Binary search

二分查找，一个数列本身有序，一分为二，只查一边 

$O(\log n)$

#### Binary tree traversal

二叉树遍历，每次一分为二，每一遍时间复杂度相等

二叉树遍历，每个节点都访问一次，且仅访问一次

$O(n)$

#### Optimal sorted matrix search

在排好序的二维矩阵中进行二分查找

$O(n)$

#### Merge sort

归并排序

所有排序最优的办法就是 $O(n\log n)$

### 常见复杂度问题

#### 二叉树遍历：前序，中序，后序时间复杂度是多少

$O(n)$

每个二叉树节点仅访问一次，时间复杂度线性于节点总数。

#### 图的遍历

$O(n)$

每个图节点仅访问一次，时间复杂度线性于图节点数

#### 搜索算法：DFS，BFS的时间复杂度

DFS: 深度优先； BFS: 广度优先

$O(n)$

因为访问的节点只有一次。$n$ 是搜索空间中的节点总数。



## 空间复杂度

主要看数组的长度，和递归的深度。



## 总结

时间复杂度：看在 $n$ 的不同情况下，一段主要代码被运行了多少次，或看节点被访问了多少次。

空间复杂度：看数组的长度，和递归的深度。