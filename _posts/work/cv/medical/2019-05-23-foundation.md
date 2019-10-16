---
layout: article
title:  "「CV」 医疗图像分析资源汇总"
date:   2019-05-23 11:18:40 +0800
key: medical-foundation-20190523
aside:
  toc: true
category: [CV, medical]
tags: 资源
---
<span id='head'></span>  
>[通用物体分割资源](/cv/segmentation/2019/05/05/foundation.html)   

<!--more-->

# 1 论文
## 1.1 综述
1. [Medical Image Analysis using Convolutional Neural Networks: A Review](http://cn.arxiv.org/abs/1709.02250)   
*2017-09-04* [paper](https://arxiv.org/abs/1709.02250)   

## 1.2 理论

## 1.3 分割
### 1.3.1 肺结核
1. [Dual-branch residual network for lung nodule segmentation](http://cn.arxiv.org/abs/1905.08413)   
*2019-05-21* [paper](https://arxiv.org/abs/1905.08413)   

1. [Lung nodule segmentation via level set machine learning](http://cn.arxiv.org/abs/1910.03191)    
*2019-10-08* [paper](https://arxiv.org/abs/1910.03191)    
基于 CT；     

### 1.3.2 白细胞
1. [A novel algorithm for segmentation of leukocytes in peripheral blood](http://cn.arxiv.org/abs/1905.08416)   
*2019-05-21* [paper](https://arxiv.org/abs/1905.08416)   

### 1.3.3 手术器械
1. [RASNet: Segmentation for Tracking Surgical Instruments in Surgical Videos Using Refined Attention Segmentation Network](http://cn.arxiv.org/abs/1905.08663)   
*2019-05-21* [paper](https://arxiv.org/abs/1905.08663)   

1. [Learning Where to Look While Tracking Instruments in Robot-assisted Surgery](http://cn.arxiv.org/abs/1907.00214)   
MICCAI 2019 *2019-06-29* [paper](https://arxiv.org/abs/1907.00214)    

### 1.3.4 头部 CT
1. [Improved ICH classification using task-dependent learning](http://cn.arxiv.org/abs/1907.00148)   
*2019-06-29* [paper](https://arxiv.org/abs/1907.00148)   
分割、分类双任务同时进行，最后的 loss 有借鉴意义；    

### 1.3.5 骨骼
1. [Permutohedral Attention Module for Efficient Non-Local Neural Networks](http://cn.arxiv.org/abs/1907.00641)   
MICCAI 2019 *2019-07-01* [paper](https://arxiv.org/abs/1907.00641)   
椎骨分割，用了注意力；   

### 1.3.6 皮肤
1. [MobileGAN: Skin Lesion Segmentation Using a Lightweight Generative Adversarial Network](http://cn.arxiv.org/abs/1907.00856)   
*2019-07-01* [paper](https://arxiv.org/abs/1907.00856)   
使用 GAN 进行分割；    

### 1.3.7 肿瘤
1. [An Efficient Solution for Breast Tumor Segmentation and Classification in Ultrasound Images Using Deep Adversarial Learning](https://arxiv.org/abs/1907.00887)   
*2019-07-01* [paper](https://arxiv.org/abs/1907.00887)    
使用了对抗学习；   

### 1.3.7 器官
1. [End-to-End Adversarial Shape Learning for Abdomen Organ Deep Segmentation](http://cn.arxiv.org/abs/1910.06474)     
*2019-10-15* [paper](https://arxiv.org/abs/1910.06474)     
GAN 分割腹部器官——肝、胰和脾；     

### 1.3.8 其他
1. [Task Decomposition and Synchronization for Semantic Biomedical Image Segmentation](http://cn.arxiv.org/abs/1905.08720)   
*2019-05-21* [paper](https://arxiv.org/abs/1905.08720)   

1. [Multi-scale guided attention for medical image segmentation](http://cn.arxiv.org/abs/1906.02849)   
*2019-06-07* [paper](https://arxiv.org/abs/1906.02849) | [pytorch](https://github.com/sinAshish/Multi-Scale-Attention)-offical    
差不多的低层特征在多个尺度上重复提取，我们就设计了一个注意力，来重复利用这些特征；并在腹部磁共振成像（MRI）上进行了实验；    


## 1.4 MRI
1. [Reducing Uncertainty in Undersampled MRI Reconstruction with Active Acquisition](http://cn.arxiv.org/abs/1902.03051)    
CVPR 2019 *2019-02-08* facebook [paper](https://arxiv.org/abs/1902.03051) | [keras](https://github.com/Corey-Zumar/MRI-Reconstruction)    

1. [DUAL-GLOW: Conditional Flow-Based Generative Model for Modality Transfer](http://cn.arxiv.org/abs/1908.08074)    
ICCV 2019 *2019-08-21* [paper](https://arxiv.org/abs/1908.08074)    
用 MRI 合成 PET 图像；    


-------------------  
[End](#head)   
{:.warning}  
