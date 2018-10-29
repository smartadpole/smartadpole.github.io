---
layout: article
title:  "「论文解读」DocFace: Matching ID Document Photos to Selfies"
date:   2018-10-29 10:18:40 +0800
key: docFace-20181029
aside:
  toc: true
tags: 人证比对 人脸验证 人脸识别 图像检索 深度学习 计算机视觉 论文解读
---

>论文发表时间：2018年5月  
论文地址：<https://arxiv.org/abs/1805.02283>  
官方代码：<https://github.com/seasonSH/DocFace>（Tensorflow）  


## 一、一句话总结文章  
**第一句**：在[人证比对](#face-verification-id-doc)场景中，「DocFace」比通用人脸验证方案准确度更高——用人脸识别来做匹配；:ghost:  
**第二句**：将迁移学习应用到人脸验证，且为[人证比对](#face-verification-id-doc)问题设计了新的 Loss 函数；:ghost:  

## 二、提出的问题  
人工比对，耗时耗力且容易出错；之前的人证比对方案也都是 2011 年以前了；因此我们使用近年发展迅速的 DNN 来处理人证比对问题；  
1. 与人脸识别面临相同的问题：人脸姿态、光照和表情的变化；  
1. 证件照图像质量低；:ghost:*what*:ghost:  
1. 证件照与自拍照有年龄差距；:ghost:*人脸识别也有面临这个问题吧*:ghost:  
1. 人证比对数据集缺乏；  


## 三、贡献  
针对[人证比对](#face-verification-id-doc)问题：  
- 进行了公开算法的评估；  
- 设计了新的思路——DocFace，和[损失函数](#mps-loss)，效果优异；  

## 四、结论  
由于应用场景不同，所以面临的难题也不同，使得通用人脸验证方法在人证比对问题上效果很差，而本文设计的 DocFace 效果非常好； 另一方面，只要训练集扩大，算法的性能就会稳定提升；  

## 五、基本流程/解决方案
前导知识：`人脸识别`，`CNN`，`深度学习基本知识`；  

第一步：  
第二步：  

## 六、细节
### 1. 概念
<span id="face-verification">**人脸验证/认证**</span>  
给两张人脸图片，判断是否为同一人；　　

<span id="face-verification-id-doc">**人证比对**</span>  
属于[人脸验证](#face-verification)的范畴，只是其中一张人脸图片来源于证件照；　　

<span id="mps-loss">**Max-margin Pairwise Score (MPS) loss**</span>  

### 2. 基本操作

## 七、实验
### 1. 数据集

### 2. 实验结果
TAR：61.14% -> 92.77% at FAR=0.1%  


[^3]:A. Babenko and V. Lempitsky. Aggregating local deep features for image retrieval. In International Conference on Computer Vision (ICCV), December 2015.  
[^11]:Y. Kalantidis, C. Mellina, and S. Osindero. Cross-dimensional weighting for aggregated deep convolutional features. arXiv:1512.04065, 2015.
