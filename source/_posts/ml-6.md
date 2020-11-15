---
title: "【ML】诊断偏差与方差"
date: 2020-11-15T00:00:00Z
tags:
- 机器学习
categories: ''

---

在运行算法效果不佳的时候，多半是两种情况：一种是欠拟合（高偏差），一种是过拟合（高方差）。
弄清楚是哪种情况，便于找到解决问题的方法。


#### 偏差/方差
![image](https://cdn.sparkling.land/christy/images/CE76FB14-1068-46E2-868D-F02224E22D6F.jpg)￼

#### 训练误差/交叉验证误差
横轴是多项式次数d
![image](https://cdn.sparkling.land/christy/images/760AE4B8-7C49-4787-9179-7500B1B79AC0.jpg)￼

#### 诊断偏差与方差
![image](https://cdn.sparkling.land/christy/images/931F25FD-37B9-4BD8-859B-5875C03F93CC.jpg)￼
高偏差：图中左边，训练误差很高，交叉验证的误差也很高，与训练误差接近；此时是欠拟合
高方差：图中右边，训练误差很低，交叉验证的误差远大于训练误差；此时是过拟合。