---
title: "【ML】机器学习的系统设计"
date: 2020-11-16T07:00:00Z
tags:
- 机器学习
categories: ''

---
> 吴恩达机器学习

## 确定执行的优先级

### 建立垃圾邮件分类器

构建特征向量x
![image](https://cdn.sparkling.land/christy/images/FBFDBDFE-C66E-434D-BEF4-7B1CF0A88F0C.jpg)￼

![image](https://cdn.sparkling.land/christy/images/E95C38F0-C941-4676-A213-BED1936A6DC3.jpg)￼

## 误差分析

### 一种推荐做法

1. 快速、简单实现：面对一个机器学习的问题时，用一种简单的算法快速实现，并在交叉验证集上测试。
2. 画出学习曲线：根据学习曲线来**帮助判断**是需要更多的数据，还是更多的特征等；相当于是一种指导作用。
3. 误差分析：**观察**交叉验证集里经常被错误分类的输入，有什么共同的特征和规律；这可能对设计特征有所启发，或者根据现有系统的优缺点进行指导改进。

### 误差分析

![image](https://cdn.sparkling.land/christy/images/56D9DFD0-F6FD-4632-A872-95C0971D48CE.jpg)￼

### 数值评价指标

![image](https://cdn.sparkling.land/christy/images/CBFAE3D3-D1A4-4046-8FA5-9E732B2B96C8.jpg)￼

Note：
**在交叉验证集上做误差分析，而不是在测试集上做误差分析。**

## 不对称性分类的误差评估

### 斜偏类

使用一个合适的误差度量，有助于解决**斜偏类问题**。

🌰
![image](https://cdn.sparkling.land/christy/images/9885B79C-A8D3-43F5-916A-9BA7EB82E798.jpg)￼

问题发生在：正例与负例的比例非常接近于一个极端情况。
本🌰中，正样本数量很少很少，负样本数量很多很多。

思考：
accuracy从99.2%提高到99.5%，意义大吗？

### 精确率、召回率

![image](https://cdn.sparkling.land/christy/images/EB189A76-BDE2-42A3-8303-4F66CCBFDC4F.jpg)￼

**精确率和召回率均越高越好。**

## 精确率和召回率的权衡

![image](https://cdn.sparkling.land/christy/images/1E442B58-1DD0-4C96-96A0-3804424D10AF.jpg)￼

### F1分数

![image](https://cdn.sparkling.land/christy/images/EFEBDC12-C924-44EC-8B7E-B1961539F1A7.jpg)￼

F1会考虑一部分P和R的平均值，但会给值较低的一方更高的权重。

## 机器学习数据

![image](https://cdn.sparkling.land/christy/images/E3F793F3-512F-4E15-AC1F-DE1D308503B8.jpg)￼
![image](https://cdn.sparkling.land/christy/images/22452C27-0238-4D38-AD6C-6456AECDFC37.jpg)￼
![image](https://cdn.sparkling.land/christy/images/4F53074E-4A03-468F-84BD-7139C8714E59.jpg)￼