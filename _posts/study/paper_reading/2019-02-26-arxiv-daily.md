---
layout: article
title:  "「论文阅读」 每日 arXiv · 2019-02-26"
date:   2019-02-26 16:10:40 +0800
key: arXiv-20190226
aside:
  toc: true
tags: arXiv
categories: [PaperReading]
articles:
  excerpt_type: html
---

><https://arxiv.org/list/cs/new>  

## 计算机视觉
#### 1. DoPaNet: 域分区网络  
发表时间：2019-02-21   
标签：GAN  

<!--more-->

>Csaba, B., Boukhayma, A., Kulharia, V., Horváth, A., & Torr, P. H. S. (2019). Domain Partitioning Network. [arXiv:1902.08134](https://arxiv.org/abs/1902.08134)    

**背景**：标准对抗生成网络（GAN）是用一个生成器和一个判别器进行优化；  
**问题**：陷入模式崩溃时，虽然模型收敛情况稳定，但生成器可能并没有完整覆盖到整个数据分布；  
**方案**：「DOPaNet」使用多个判别器，来配合生成器生成目标数据中不同部分的数据；为了确保生成器生成的各部分数据不会相互重叠，我们引入了一个分类器；由这个分类器决定，针对当前样本应该用哪一个判别器去配合（生成器）训练；    
**实验**：在 CIFAR-10 和 CelebA 数据集上做了对比实验；  
**结论**：  
  1. 生成器和判别器不一定要具有同样的收敛能力，这也就意味着可以用多个（弱）判别器来指导生成器生成不同分布的数据；  
  2.  实验证明，DoPaNet 可以更好的覆盖实际的数据分布；    
  3. 一个生成器可以应对多种数据分布；  

#### 2. 基于 CNN 的漫画书对话框检测与分割  
发表时间：2019-02-21   
标签：检测，分割    
（很有意思的应用）    
>Dubray, D., & Laubrock, J. (2019). Deep CNN-based Speech Balloon Detection and Segmentation for Comic Books. [arXiv:1902.08137](http://arxiv.org/abs/1902.08137)  

基于 VGG-16 和 UNet 进行了改进，使用了全卷积网络；F1 达到 0.94； 召回率 0.94，比当前最佳方案高出了 8 个百分点；  
分割效果很好，能够分割出虚线框及框上的箭头；    

BOWDA-Net: 前列腺磁共振图像分割的边界加权域自适应神经网络
发表时间：2019-02-21   
标签：分割，MR，FCN，DenseNet，ResNet，迁移学习，挛生网络  
>Zhu, Q., Du, B., & Yan, P. (2019). Boundary-weighted Domain Adaptive Neural Network for Prostate MR Image Segmentation. [arXiv:1902.08128](http://arxiv.org/abs/1902.08128)  

#### 3. BOWDA-Net: 前列腺磁共振图像分割的边界加权域自适应神经网络  
**背景**：三维磁共振图像的前列腺分割仍面临着一些挑战，例如，前列腺边界模糊，背景纹理复杂，前列腺形状、大小和清晰程度变化较大；  
**挑战**：大量标注医学图像很困难；  
**解决**：「BOWDA-Net」   
  1. 为了加强分割时对于边界的感知，引入了边界加权分割损失函数（boundary-weighted segmentation loss ，BWL）；
  2. 针对小型医学图像数据集，我们使用了迁移学习；
**数据集**：MICCAI 2012 Prostate MR Image Segmentation (PROMISE12) 挑战赛数据集；<https://promise12.grand-challenge.org/>  
**结论**：边界分割效果很好，优于其他最先进的方法；
