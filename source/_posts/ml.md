---
title: "【ML】反向传播算法"
date: 2020-11-14T06:00:00Z
tags:
- 机器学习
categories: ''

---

> 首先附上B站链接🔗

吴恩达机器学习
[https://www.bilibili.com/video/BV164411b7dx?p=51](https://www.bilibili.com/video/BV164411b7dx?p=51)￼
吴恩达机器学习里反向传播算法的数学推导
[https://www.bilibili.com/video/BV1GK4y1s76c](https://www.bilibili.com/video/BV1GK4y1s76c)￼

这里面的细节讲得也很清楚
[https://www.bilibili.com/video/BV1Y7411d7Ys?p=4](https://www.bilibili.com/video/BV1Y7411d7Ys?p=4)￼

### 线性模型

![drawing](https://cdn.sparkling.land/christy/images/1C5948C3-A27E-4BB7-BF7F-6AFC7560E221.jpg)￼

![image](https://cdn.sparkling.land/christy/images/47255AEE-1FE4-45EE-9006-27E3381DE6D3.jpg)￼

![drawing](https://cdn.sparkling.land/christy/images/1D89373E-CD2C-487D-BAE0-901472FD818E.jpg)￼

### 为什么需要反向传播

嵌套非常多的复合函数，如果在这里写解析式的话，就会变的相当的复杂。
把网络看成一张图，在图上传播梯度，根据链式法则求出梯度；这种算法就叫做反向传播算法，BP

### 🌰一个两层的网络

![drawing](https://cdn.sparkling.land/christy/images/80634E14-D541-440B-9EB9-A541356D0B9122.jpg)￼
以上，没有用激活函数，展开会发现，不管多少层，都是一个线性变换；所以要对每一层的输出，都加一个激活函数，也就是非线性单元。

![image](https://cdn.sparkling.land/christy/images/F2599DF3-61BC-4FCA-AE71-42DBCB5C90D5.jpg)￼

### 链式法则

![image](https://cdn.sparkling.land/christy/images/F4D7D09C-51BE-4BFA-829F-4774EBD2170E.jpg)￼

### 链式求导

创建计算图，前馈运算，反向传播
![image](https://cdn.sparkling.land/christy/images/56490478-9A4E-40D6-8375-754441DD5C8D.jpg)￼
![image](https://cdn.sparkling.land/christy/images/3B6FE363-B6D2-4D7B-80D1-FD0223BBC5C8.jpg)￼

## 解释吴恩达机器学习课程中的反向传播

![image](https://cdn.sparkling.land/christy/images/DF02A442-83E8-4475-8C37-57F242A4F3A8.jpg)￼

**代价函数**

* 二分类：输出0或1
* 多分类：输出one-hot向量
  ![image](https://cdn.sparkling.land/christy/images/4C5CC8EF-8AF6-4BDE-87D8-822553737AA6.jpg)￼

反向传播算法里，很重要的一步是，计算这些偏导项。
![image](https://cdn.sparkling.land/christy/images/B24A9AD6-BEB4-4957-BB2C-7C200134B020.jpg)￼
![image](https://cdn.sparkling.land/christy/images/CA88173B-AFA9-4B27-BDEF-C89E1C24644E.jpg)￼
这里的δ更准确的说是，J对θ的偏导数。

对于这里面如何推导出来的，建议看最前面附上的第二个视频链接，讲得很清楚。

![image](https://cdn.sparkling.land/christy/images/1F78B3A3-8A9B-4659-9BBD-97A65C2FBDBD.jpg)￼
![image](https://cdn.sparkling.land/christy/images/430BC1AC-9FA0-476F-90B3-A5D0F5B05F05.jpg)￼

## 理解反向传播在神经网络训练过程中的作用

正向传播，计算代价函数；

在一次反向传播之后，计算出所有待更新参数的梯度之后，进行更新（对于任意参数ω ，更新参数的公式都是ω = ω + Δω）
然后再正向传播，计算代价函数；再反向传播计算梯度，更新......；一直到结束（一般是参数基本不再更新，loss不再下降等）