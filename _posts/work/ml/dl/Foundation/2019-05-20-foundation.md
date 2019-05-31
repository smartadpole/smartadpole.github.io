---
layout: article
title:  "「DL」 深度学习基本技能资源汇总"
date:   2019-05-20 18:08:40 +0800
key: dl-foundation-20190520
aside:
  toc: true
category: [DL, foundation]
tags: 资源
---
<span id='head'></span>  

<!--more-->


# 1 综述

# 2 训练
## 2.1 训练方法
1. [Sequential training algorithm for neural networks](https://arxiv.org/abs/1905.07490)   
*2019-05-17* [paper](https://arxiv.org/abs/1905.07490)    
$\bullet \bullet$   
网络逐层单独训练，最终融合在一起；虽然效果不如整体训练好，但是对于算力有限情况下的大型网络训练很有帮助；   

## 2.2 过拟合
1. [One-Step or Two-Step Optimization and the Overfitting Phenomenon: A Case Study on Time Series Classification](http://cn.arxiv.org/abs/1407.4364)   
*2014-07-16* [paper](https://arxiv.org/abs/1407.4364)   

1. [How much does your data exploration overfit? Controlling bias via information usage](http://cn.arxiv.org/abs/1511.05219)   
*2015-11-16* [paper](https://arxiv.org/abs/1511.05219)   

1. [Detecting Overfitting of Deep Generative Networks via Latent Recovery](http://cn.arxiv.org/abs/1901.03396)   
*2019-01-09* [paper](https://arxiv.org/abs/1901.03396)   

1. [Overfitting Mechanism and Avoidance in Deep Neural Networks](http://cn.arxiv.org/abs/1901.06566)   
*2019-01-19* [paper](https://arxiv.org/abs/1901.06566)   

1. [GradMask: Reduce Overfitting by Regularizing Saliency](http://cn.arxiv.org/abs/1904.07478)   
*2019-04-16* [paper](https://arxiv.org/abs/1904.07478)   

1. [Overfitting in Synthesis: Theory and Practice](http://cn.arxiv.org/abs/1905.07457)   
*2019-05-17* [paper](https://arxiv.org/abs/1905.07457)   

1. [Overfitting in Synthesis: Theory and Practice](http://cn.arxiv.org/abs/1905.07457)   
*2019-05-17* [paper](https://arxiv.org/abs/1905.07457)   
$\bullet \bullet$    

1. [The advantages of multiple classes for reducing overfitting from test set reuse](http://cn.arxiv.org/abs/1905.10360)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10360)   

## 2.3 欠拟合

## 2.4 模型检验
>验证模型相关性，并检验过拟合和欠拟合；    

1. [Perturbed Model Validation: A New Framework to Validate Model Relevance](http://cn.arxiv.org/abs/1905.10201)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10201)   


## 2.5 梯度爆炸
1. [On the difficulty of training Recurrent Neural Networks](http://cn.arxiv.org/abs/1211.5063)  
*2012-11-21* [paper](https://arxiv.org/abs/1211.5063)   

1. [Which Neural Net Architectures Give Rise To Exploding and Vanishing Gradients?](http://cn.arxiv.org/abs/1801.03744)   
NIPS 2018 *2018-01-11* [paper](https://arxiv.org/abs/1801.03744)     

1. [Products of Many Large Random Matrices and Gradients in Deep Neural Networks](http://cn.arxiv.org/abs/1812.05994)   
*2018-12-14* [paper](https://arxiv.org/abs/1812.05994)   
RELU 梯度问题测量；    

## 2.6 初始化
1. [How to start training: The effect of initialization and architecture](http://cn.arxiv.org/abs/1803.01719)    
NIPS 2018 *2018-03-05* [paper](https://arxiv.org/abs/1803.01719)   



# 3 优化
## 3.1 SGD
1. [The Impact of Neural Network Overparameterization on Gradient Confusion and Stochastic Gradient Descent](https://arxiv.org/abs/1904.06963)   
*2019-04-15* [paper](https://arxiv.org/abs/1904.06963)   
SGD 对于模型收敛的影响，及相应网络结构的探索；   

1. [Time-Smoothed Gradients for Online Forecasting](http://cn.arxiv.org/abs/1905.08850)   
ICML 2019 *2019-05-21* [paper](https://arxiv.org/abs/1905.08850)   
PTS-SGD: 对学习率不敏感；计算快速；    

1. [Fine-grained Optimization of Deep Neural Networks](http://cn.arxiv.org/abs/1905.09054)   
*2019-05-22* [paper](https://arxiv.org/abs/1905.09054)   
FG-SGD:细粒度优化，确保收敛到最小值；   

1. [Momentum-Based Variance Reduction in Non-Convex SGD](http://cn.arxiv.org/abs/1905.10018)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10018)   


# 4 归一化
1. [Self-Normalizing Neural Networks](https://arxiv.org/abs/1706.02515)   
*2017-06-08* [Paper](https://arxiv.org/abs/1706.02515) | [tensorflow](https://github.com/bioinf-jku/SNNs) | [zhihu](https://www.zhihu.com/question/60910412) | [reddit](https://www.reddit.com/r/MachineLearning/comments/6g5tg1/r_selfnormalizing_neural_networks_improved_elu/dio0qac/)      

1. [Fixup Initialization: Residual Learning Without Normalization](http://cn.arxiv.org/abs/1901.09321)   
ICLR 2019 *2019-01-27* [paper](https://arxiv.org/abs/1901.09321) | [openreview](https://openreview.net/forum?id=H1gsz30cKX)   
归一化的理论和有效性的探讨；   

1. [ROI Regularization for Semi-supervised and Supervised Learning](http://cn.arxiv.org/abs/1905.08615)   
*2019-05-15* [paper](https://arxiv.org/abs/1905.08615)  

# 5 激活函数
1. [Neurons Activation Visualization and Information Theoretic Analysis](http://cn.arxiv.org/abs/1905.08618)   
*2019-05-14* [paper](https://arxiv.org/abs/1905.08618)   

# 6 模型可解释性
1. [Explainable Machine Learning for Scientific Insights and Discoveries](http://cn.arxiv.org/abs/1905.08883)   
*2019-05-21* [paper](https://arxiv.org/abs/1905.08883)   

1. [On the Learning Dynamics of Two-layer Nonlinear Convolutional Neural Networks](http://cn.arxiv.org/abs/1905.10157)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10157)   

# 7 神经网络
## 7.1 神经网络
1. [Mean Field Limit of the Learning Dynamics of Multilayer Neural Networks](http://cn.arxiv.org/abs/1902.02880)   
*2019-02-07* [paper](https://arxiv.org/abs/1902.02880)   

1. [Loss Surface Modality of Feed-Forward Neural Network Architectures](http://cn.arxiv.org/abs/1905.10268)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10268)   

1. [What Can ResNet Learn Efficiently, Going Beyond Kernels?](http://cn.arxiv.org/abs/1905.10337)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10337)   

## 7.2 反向传播
1. [Memorized Sparse Backpropagation](http://cn.arxiv.org/abs/1905.10194)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10194)    

-------------------  
[End](#head)
{:.warning}  
