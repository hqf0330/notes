---
title: bitmap--the killer of User Profile System
draft: false
tags:
    - dataware
    - bitmap
---
# 什么是bitmap

Bit-Map算法又名位图算法，其原理是，使用下标代替数值或特定的意义，使用这个位为0或者1代表特性是否存在
Bit-Map算法具有效率高，节省空间的特点，适用于对大量数据进行去重，查询等

> [!NOTE]
> 对于某个标签，给出一个长度为n的数组，初始化都为0，如果来了一个用户或者一个用户符合当
> 前标签，我们就将这个数组的某个位置置为1。基于当前标签进行统计某些值的时候就很快

# 从案例来理解bitmap

1. 建立用户名和id的映射关系

现在有标签宽表如下：

|Name|Sex|Age|Occupation|Phone|
|:---:|:---:|:---:|:---:|:---:|
|A|male|90s|Dev|iPhone|
|B|male|90s|dev|San|
|C|female|00s|student|mi|

构建映射关系之后

|ID|Name|
|:---:|:---:|
|1|A|
|2|B|
|3|C|

2. 将标签宽表使用bitmap进行拆分


|Sex|bitmap|
|:---|:---|
|male|1, 2|
|female|3|

|Age|bitmap|
|:---:|:---|
|90s|1, 2|
|00s|3|

|Occupation|bitmap|
|:---|:---|
|Dev|1, 2|
|student|3|

And so on~

3. 使用bitmap进行查询












