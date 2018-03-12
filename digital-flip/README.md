# [843. 数字翻转](http://www.lintcode.com/zh-cn/problem/digital-flip/)

## 描述

给你一个01构成的数组。请你找出最小翻转步数，使得数组满足以下规则：
1的后面可以是1或者0，但是0的后面必须是0。

> 注意事项
> * 输入的数组长度n <= 100000。

### 样例
给出 array = [1,0,0,1,1,1] , 返回2。
> 解释：  
把两个0翻转成1。  

给出 array = [1,0,1,0,1,0] , 返回2。
> 解释：  
把第二个1和第三个1都翻转成0。

## 思路

### 一

最坏的情况是全部 1 都翻转；
遍历数字，如果是 1 则计算前面的 0 都翻成 1 后面的 1 都翻成 0 的情况，比较之前的最坏的情况和这种情况，选次数最少的。

### 二

由于 0 之后只能是 0，1 之后能是 1 或 0，从最后开始翻转同时统计需要翻转成 0 和 1 的次数；
如果数是 1，翻成 0 的最少次数是后面翻成 0 的次数 + 1，翻成 1 的次数是后面翻成 0 或 1 次数的最小值；
如果数是 0，翻成 0 的最少次数是后面翻成 0 的次数，翻成 1 的次数是后面翻成 0 或 1 最小次数 + 1；