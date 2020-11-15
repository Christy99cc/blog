---
title: "【ML】神经网络流程小结"
date: 2020-11-15T07:00:00Z
tags:
- 机器学习
categories: ''

---
### 选择一种网络架构

指的是，神经元的连接方式（隐层单元的个数，输入单元数，输出单元数量）

### 训练神经网络

1. 构建一个神经网络，并随机初始化权重（很小的值，接近0）
2. 前向传播
3. 计算J代价函数
4. 反向传播，计算偏导k
5. 梯度检验
6. 使用优化算法与BP算法来结合，计算偏导…

![image](https://cdn.sparkling.land/christy/images/BF409FAB-780B-4A34-A26A-1055EC48AA3E.jpg)￼

![image](https://cdn.sparkling.land/christy/images/C2254DF5-DBB0-4EDC-9592-90B8E08AD2DB.jpg)￼

![image](https://cdn.sparkling.land/christy/images/4E6D4BC0-A5D1-4FBF-AA50-DAE0A0603614.jpg)￼
反向传播算法：算出梯度下降的方向
梯度下降：沿着梯度下降的方向一点点下降一直到我们希望得到的点（最优的参数，局部最优点）