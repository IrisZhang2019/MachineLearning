PCA

[ref](https://www.bilibili.com/video/BV14a4y1a7Gd/)

为了让数据在某个向量空间的方差最大（=最分散）  
所以求法就是假设一组向量空间，求在该向量空间下数据投影后的方差。找到一组正交的向量空间使得方差最大。  
中途用了不太懂的拉格朗日乘除法求最值问题，但是求后转化为固有值问题。

求法：
1. 将所有数据去中心化，减去平均值
2. 求数据的协方差矩阵
3. 求协方差矩阵的特征值和特征向量
4. 将特征值从大的开始排序，选前k个特征值对应的特征向量组成变换矩阵
