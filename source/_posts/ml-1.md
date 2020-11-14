---
title: "【ML】梯度检验"
date: 2020-11-14T07:00:00Z
tags:
- 机器学习
categories: ''

---
# 梯度检验
### 为什么要进行梯度检验？
为了保证反向传播算法实现的正确性。
![image](https://cdn.sparkling.land/christy/images/105A04B2-83E3-4F4B-8F43-6F7F9A5FED1F.jpg)￼

![image](https://cdn.sparkling.land/christy/images/A6D83E40-90AD-485C-A694-36BC3A446B5E.jpg)￼

ε通常取10^-4，再小会出一些问题

![image](https://cdn.sparkling.land/christy/images/7D35FA77-911B-42A1-ADFD-CDC65B264363.jpg)￼

检验：比较计算得到的结果，与反向传播中的导数是否相等or非常相近

### 数值上的梯度检验步骤
1.	反向传播计算Dvec
2.	数值上的梯度检验计算gradApprox
3.	比较Dvec与gradApprox，确保两者的数值相近
4.	在反向传播学习（训练）之前要关掉梯度检验：因为梯度检验计算导数的开销很大，而且很慢

### 小结
在训练之前一定要关掉梯度检验，如果每次梯度下降里都进行数值上的梯度检验，会变得很慢。
反向传播是高性能的，梯度检验比反向传播要慢很多。
在数值上验证反向传播算法实现的正确之后，一定要记得在训练时候禁用梯度检验。