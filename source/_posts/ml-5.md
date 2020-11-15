---
title: "【ML】模型的选择问题+数据集的划分"
date: 2020-11-15T11:00:00Z
tags:
- 机器学习
categories: ''

---

![image](https://cdn.sparkling.land/christy/images/C59348C4-0008-49F1-A0F6-08E662F509C62.jpg)￼
__当我们用训练集去拟合参数θ_0，θ _1等等，拟合后的模型在训练集上的效果是不能预测出假设函数对于新样本的泛化能力的，因为这些参数能够拟合训练集，在训练集上表现的效果很好，但对于其他新样本就不一定那么好了。__
### 模型的选择问题

![image](https://cdn.sparkling.land/christy/images/14520E7A-B74D-4EBD-A17C-80F04CCC99AC2.jpg)￼

首先选择第一个模型，然后最小化训练误差，就会得到一个参数θ(1)
选择第二个模型，最小化训练误差，就会得到一个参数θ(2)
...
选择第10个模型，最小化训练误差，就会得到一个参数θ(10)

相应地，可以计算出J_test(θ(1)),  J_test(θ(2)), ... J_test(θ(10))
再观察，根据哪个模型有更小的测试误差来选择

假设d=5的这种情况下J_test最小。
这样并不能公平的知道模型的泛化能力，因为给了一个额外的参数d，用测试集拟合得到了d。意思是，这个多项式的次数d，是让J_test最小，是偏向于测试集的。

__在训练集上拟合θ之后，又通过拟合测试集得到参数d；这意味着，假设函数在测试集上的效果并不能用来公正的来估计对于新样本的效果。
__
> 上面两处划线部分可以联合起来看。

为了解决这个问题，可以采取如下的办法来评估假设函数。
将数据集划分为3部分，而不是之前的2部分。

### 数据集的划分
数据集划分为三部分：训练集、（交叉）验证集（cross validation）、测试集
划分比例为6：2：2。
![image](https://cdn.sparkling.land/christy/images/4E155879-3A48-4BCF-B6A0-D01EC769AE5A23.jpg)￼


![image](https://cdn.sparkling.land/christy/images/C1214608-7814-404E-831B-897C716D9F1C2.jpg)￼

![image](https://cdn.sparkling.land/christy/images/0354AD0C-EC24-4064-93A4-E5FA99A4CD582.jpg)￼

我们使用验证集来选择模型，而不是原来的测试集。
选择模型方法与上一小节的方法相同，只是将测试集换成了验证集。

留出测试集来估计选出的模型的泛化误差。