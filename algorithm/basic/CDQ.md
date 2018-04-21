# CDQ 分治

## 引入
CDQ分治的基本思想十分简单。如下：
我们要解决一系列问题，这些问题一般包含修改和查询操作，可以把这些问题排成一个序列，用一个区间[L,R]表示。
   * 分：递归处理左边区间[L,M]和右边区间[M+1,R]的问题。
   * 治：合并两个子问题，同时考虑到[L,M]内的修改对[M+1,R]内的查询产生的影响。即，用左边的子问题帮助解决右边的子问题。

和普通分治不同的地方在于，普通分治在合并两个子问题的过程中，[L,M]内的问题不会对[M+1,R]内的问题产生影响。
## 性质
### 对于动态查询转换为静态查询
我们记过程DivideConquer(l,r)表示处理完[l,r]内的修改对查询的影响 

此时我们引入分治思想,将操作序列划分为[l,mid],[mid+1,r]两个区间 

这两个区间内部的修改对区间内部的查询的影响是完全相同的子问题,我们递归处理 

处理完之后剩下来只要考虑[l,mid]中的修改对[mid+1,r]中的查询的影响 

这时我们发现这其实已经变成了一个静态查询问题,因为所有的查询都发生在修改之后,我们只需要考虑静态查询的问题如何处理即可
### 对于降维
通过规定用[L,MID]更新[MID+1,R]，使得在满足上一维顺序的同时可以对这一维进行排序来满足这一维的顺序
如二维偏序问题，我们在拿到所有有序对(a,b)的时候，先把a元素从小到大排序。这时候问题就变成了“求顺序对”，因为a元素已经有序，可以忽略a元素带来的影响，和“求逆序对”的问题是一样的
## 应用
1. 降维
   [BZOJ 4237](http://www.lydsy.com/JudgeOnline/problem.php?id=4237) [题解](/BZOJ/p4237.md) 
2. 动态询问转换为静态询问


**参考资料：**

[CDQ分治与整体二分]个人对CDQ分治与整体二分的理解:[ http://blog.csdn.net/hbhcy98/article/details/50642773](http://blog.csdn.net/hbhcy98/article/details/50642773)

【教程】简易CDQ分治教程&学习笔记:[http://www.cnblogs.com/mlystdcall/p/6219421.html](http://www.cnblogs.com/mlystdcall/p/6219421.html)