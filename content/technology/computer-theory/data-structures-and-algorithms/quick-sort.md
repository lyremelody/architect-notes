---
title: '快速排序'
linkTitle: '快速排序'
type: 'docs'
weight: 141104
bookFlatSection: true
bookHidden: false
date: 2023-09-13
isCJKLanguage: true
params:
  author: lyremelody
---

​快速排序基于分治模式的就地排序。

## 基本过程

过程一般是这样的，比如序列A，从左至右排列

1. 选最右一个元素x作为基准
2. 设置最左边为标记位，从左往右开始比较
3. 将小于等于这个基准元素的元素与标记位的元素互换位置，标记位右移
4. 当所有元素都完成比较后，将基准元素(最右)的元素与标记位元素互换
5. 这样基准元素x将序列A分成了左边的序列B和右边的序列C，即A = B, x, C。序列B的元素都小于等于x，序列C的元素都大于x
6. 按照1～5分别再对B和C进行这样排序，迭代下去就能实现排序了 

看一个例子，比如

> **A = 2，8，7，1，3，5，6，4**

1. 选最右元素4作为基准
2. 设置标记位0（即2所在的位置）
3. 比较2与4，2<=4，互换2与标记位0的元素（同一个元素），标记位右移为1（8所在位置）
   1. 比较8与4，8>4，忽略，比较下一个
   2. 比较7与4，忽略，比较下一个
   3. 比较1与4，1<=4，互换1与标记位1的元素(8)，标记位右移为2（7所在位置）。序列A = 2，1，7，8，3，5，6，4
4. 按照3比较所有元素后，A = 2，1，3，8，7，5，6，4，标记位为3（8所在位置）。可以看出标记位左边的元素都是 <=4 的
5. 互换基准元素4与标记位3的元素，A = 2，1，3，4，7，5，6，8
6. 按照1～5再对B = 2，1，3和C = 7，5，6，8进行排序，迭代下去就能实现排序了

从上面的过程来看，快速排序会有两步，第一步实现以最右元素的值将原始序列拆分为两个部分，一部分小于等于这个值，一部分大于这个值。

对于第一步，会采用一个标记位，标记位是划分序列为两部分的界限，通过交换和移动标记位，使得标记位左边是不小于最右元素（基准元素），标记位及右边均大于基准元素；最后将基准元素与标记位交换。

第二步再递归（使用同样方法）将这两部分进行拆分，最终实现排序。

## 随机化

上面的过程，我们选的基准为最右元素。

在随机化版本中，会多出两步，即：

1. 通过随机函数选一个基准
2. 将基准元素与最右元素位置互换

后面的做法与上面的过程一致。

## 应用场景

大概就是排序了。适合大量随机序列的排序。

对于n个元素的序列，快速排序的时间复杂度：

* 最坏运行时间是 O(n²)
* 随机化版本的期望运行时间是 O(n lgn)

所以一般采用随机化的快速排序。
