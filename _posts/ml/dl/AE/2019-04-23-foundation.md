---
layout: article
title:  "「DL」 自编码入门"
date:   2019-04-23 16:08:40 +0800
key: autoencoder-foundation-20190423
aside:
  toc: true
category: [DL, Autoencoder]
---


<!--more-->


# 1 参考资料
## 1.1 书籍


## 1.2 报告


## 1.3 课程

## 1.4 资源
### 1.4.1 论文

### 1.4.2 代码


## 1.5 Paper
### 1.5.1 基础论文


### 1.5.2 综述


### 1.5.3 其他
1. [GRAINS: Generative Recursive Autoencoders for INdoor Scenes](http://cn.arxiv.org/abs/1807.09193)    
*2018-07-24* [Paper](https://arxiv.org/abs/1807.09193)    
使用递归变分自编码网络进行三维室内场景生成； VAE 主要负责 2D 转 3D；`RNN 在里边干啥了`{:.warning}    

1. [An Alarm System For Segmentation Algorithm Based On Shape Model](http://cn.arxiv.org/abs/1903.10645)    
*2019-03-26* [Paper](https://arxiv.org/abs/1903.10645)    
使用 VAE 网络自动评估分割算法的效果；对于测试数据来说，因为缺乏标签，人工检查费时费力，本文提出一个报警系统，基本思路是用 VAE 把分割结果映射到低维空间，然后使用分类或回归的方式来评判分割的质量；本文用的是分割结果的形状信息；算法在三维医疗分割任务上做了评估，比其他方法效果都好；      

1. [Variational AutoEncoder For Regression: Application to Brain Aging Analysis](http://cn.arxiv.org/abs/1904.05948)   
*2019-04-11* [Paper](https://arxiv.org/abs/1904.05948)    

## 1.6 渔

-------------------  
End
{:.warning}  
