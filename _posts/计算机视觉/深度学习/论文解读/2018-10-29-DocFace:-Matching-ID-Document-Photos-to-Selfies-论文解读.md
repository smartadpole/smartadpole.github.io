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


## 一、一句话总结  
**第一句**：在[人证比对](#face-verification-id-doc)场景中，「DocFace」比通用人脸验证方案准确度更高——用人脸识别来做匹配；:ghost:  
**第二句**：将迁移学习应用到人脸验证，且为[人证比对](#face-verification-id-doc)问题设计了新的 Loss 函数；:ghost:  

## 二、Q&A  
人工比对，耗时耗力且容易出错；之前的人证比对方案也都是 2011 年以前了；因此我们使用近年发展迅速的 DNN 来处理人证比对问题；  

1.证件照图像质量低；**`what`{:.warning}**  证件照与自拍照有年龄差距；**`人脸识别也有面临这个问题吧`{:.warning}**    
{:.warning}  
DocFace，[MPS 损失函数](#mps-loss)；  

2.人证比对数据集缺乏；  
{:.warning}  
使用**迁移学习**：先在通用的大型人脸识别数据集上训练出模型；然后，使用此模型在小型人证比对数据集上微调；

3.与人脸识别面临相同的问题：人脸姿态、光照和表情的变化
{:.warning}  
论文中并未就此展开讨论，但是数据集 [ID-Selfie-B](#ID-Selfie-B) 却涵盖了这些挑战；且他们本就是人脸识别也需处理的问题，所以博主认为，这一问题应该放在「基础模型」部分，也就是人脸识别部分做处理；

## 三、贡献  
针对[人证比对](#face-verification-id-doc)问题：  
- 进行了公开算法的评估；  
- 设计了新的思路——DocFace，和[MPS 损失函数](#mps-loss)，效果优异；  
- 设计了两个专门的人证比对数据集（但是并未公开）；  

## 四、结论  
- 由于应用场景不同，所以面临的难题也不同，这使得通用人脸验证方法在人证比对问题上效果很差，而本文设计的 DocFace 效果非常好；  
- 只要训练集扩大，算法的性能就会稳定提升；  

## 五、基本流程/解决方案——DocFace  
前导知识：`人脸识别`，`CNN`，`深度学习基本知识`；  
![](/assets/images/cv/dl/paper_reading/DocFace/DocFace.png)  
**第一步** Train on source domain：**在源数据集上训练出基础模型**   
[MA-Celeb-1M](#MS-Celeb-1M)：Face-ResNet[^Deepvisage] + [AM-Softmax](#AM-Softmax)损失函数；  

**第二步** Train on target domain：**在目标数据集上训练出最终模型**  
[ID-Selfie-A](#ID-Selfie-A)：基础模型（迁移学习/微调）+ [MPS 损失函数](#mps-loss) + [孪生网络](#sibling_net)；  
将数据集中的证件照和自拍照分别送入两个网络；  

## 六、实验  
数据准备：使用 MTCNN 检测并裁剪出人脸，并利用关键点对齐，resize 到 96*112；  

### （一）数据集
<span id="MS-Celeb-1M">**1. MS-Celeb-1M**[^Ms-celeb-1m]</span>  
人脸识别数据集，数据集中存在错误标注；

| 数据 | 训练集（张） | 测试集（张） |  
| -- | -- | -- |  
|原数据集| 8,456,240|99,892|  
|清洗后|5,041,527|98,687|  

`下载地址`{:.warning}  

<span id="ID-Selfie-A">**2. ID-Selfie-A**</span>  
由证件照及对应的自拍照组成，共 10,000 对；能够进行人脸对齐的共 9,915 对，也就是 19,830 张图像；  

<span id="ID-Selfie-B">**3. ID-Selfie-B**</span>  
由证件照及对应的自拍照组成，共 547 组，10,844 张；进行人脸对齐及清洗后，还有 537 组，10,806 张；  
相比 ID-Selfie-A，本数据集中的自拍照，无约束程度更强；  

### （二）实验结果   
- 基础模型  
  速度：1080Ti GPU，11G 显存，前向传播一张图 3ms；  
  准确度：FAR 为 0.1% 的条件下，基础模型在 LFW 上是 99.67%，BLUFR 上是 99.6%；  

**1. 探索实验**  
使用数据集：[MA-Celeb-1M](#MS-Celeb-1M)，[ID-Selfie-A](#ID-Selfie-A)  
![](/assets/images/cv/dl/paper_reading/DocFace/result_explore.png)  
**FS**：从零开始训练  **BM**：基础模型，未经过微调的  **TL**：经过微调的模型  **VR**：验证准确率  **-**：没有训练，这一项就为空   

**2. 对比实验**  
使用数据集：[MA-Celeb-1M](#MS-Celeb-1M)，[ID-Selfie-A](#ID-Selfie-A)，LFW  
![](/assets/images/cv/dl/paper_reading/DocFace/result_compare_a.png)  
**DocFace**：微调 + MPS   

使用数据集：[ID-Selfie-B](#ID-Selfie-B)
![](/assets/images/cv/dl/paper_reading/DocFace/result_compare_b.png)  

## 七、细节
### （一）概念

<span id="mps-loss">**Max-margin Pairwise Score (MPS) loss**</span>  
**`待补充`{:.warning}**  
![](/assets/images/cv/dl/paper_reading/DocFace/mps_loss.png)  

<span id="sibling_net">**孪生网络**</span>  
网络结构相同，但是独立更新参数的模型的两个网络；**`待确认`{:.warning}**    

## 附录  
### （一）基本概念  
<span id="face-verification">**人脸验证/认证**</span>  
给两张人脸图片，判断是否为同一人；　　

<span id="face-verification-id-doc">**人证比对**</span>  
属于[人脸验证](#face-verification)的范畴，只是其中一张人脸图片来源于证件照；　　

### （二）损失函数  
<span id="AM-Softmax">**AM-Softmax**[^AM-Softmax]-[^ArcFace]-[^Cosface]</span>  
**`待补充`{:.warning}**  
![](/assets/images/cv/dl/paper_reading/DocFace/AM-Softmax.png)  

[^Deepvisage]:A. Hasnat, J. Bohné, J. Milgram, S. Gentric, and L. Chen. Deepvisage: Making face recognition simple yet with powerful generalization skills. arXiv:1703.08388, 2017.  
[^ArcFace]:J. Deng, J. Guo, and S. Zafeiriou. Arcface: Additive angular margin loss for deep face recognition. arXiv:1801.07698, 2018.  
[^AM-Softmax]:F. Wang, W. Liu, H. Liu, and J. Cheng. Additive margin softmax for face verification. arXiv:1801.05599, 2018.  
[^Cosface]:H. Wang, Y. Wang, Z. Zhou, X. Ji, Z. Li, D. Gong, J. Zhou, and W. Liu. Cosface: Large margin cosine loss for deep face recognition. arXiv:1801.09414, 2018.  
[^Ms-celeb-1m]:Y. Guo, L. Zhang, Y. Hu, X. He, and J. Gao. Ms-celeb-1m: A dataset and benchmark for large scale face recognition. In ECCV, 2016.  
