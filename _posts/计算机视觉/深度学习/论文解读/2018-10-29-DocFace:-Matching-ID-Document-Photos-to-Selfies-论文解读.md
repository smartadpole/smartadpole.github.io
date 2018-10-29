---
layout: article
title:  "DocFace: Matching ID Document Photos to Selfies 论文解读"
date:   2018-10-29 10:18:40 +0800
key: DocFace-20181029
aside:
  toc: true
tags: 人脸验证 图像检索 深度学习 计算机视觉 论文解读
---

>论文发表时间：2018年5月  
论文地址：<https://arxiv.org/abs/1805.02283>  
官方代码：<https://github.com/seasonSH/DocFace>（Tensorflow）  


## 一、一句话总结文章  
**第一句**：「DocFace」证件照和自拍照的匹配，比通用人脸识别来做匹配的方案好；  
**第二句**：迁移学习在人脸验证中的应用，且设计了新的 Loss 函数；  

## 二、贡献  
- 身份认证领域中，公开的人脸比对算法的评估；  
- 从两个人脸模型中学习人脸验证特征，自己设计的损失函数；  
- 特定领域的匹配方法——DocFace；   

## 三、提出的问题

## 四、结论  
本文针对人脸验证问题，使用迁移学习微调网络，并结合自定义的损失函数，效果远优于将通用人脸识别应用于人脸验证问题的方案；
数据集扩大，本文的算法性能会稳定提升；  

## 五、基本流程/解决方案
前导知识：`CNN`，`深度学习基本知识`，`图像检索的基本知识`；  

第一步：  
第二步：  

## 六、细节
### 1. 概念


### 2. 基本操作

## 七、实验
### 1. 数据集

### 2. 实验结果
TAR：61.14% -> 92.77% at FAR=0.1%  


[^3]:A. Babenko and V. Lempitsky. Aggregating local deep features for image retrieval. In International Conference on Computer Vision (ICCV), December 2015.  
[^11]:Y. Kalantidis, C. Mellina, and S. Osindero. Cross-dimensional weighting for aggregated deep convolutional features. arXiv:1512.04065, 2015.
