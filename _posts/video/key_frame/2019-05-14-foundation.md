---
layout: article
title:  "「VIDEO」 视频关键帧提取入门"
date:   2019-05-14 10:06:40 +0800
key: key-frame-extraction-foundation-20190514
aside:
  toc: true
category: [Video, KeyFrame]
tags: 资源
---
`video key frame extraction` · `video key clip extraction` · `video summarization` · ` key frame Detection`   
>视频相比图像来说信息更加丰富，但是一个序列里冗余信息太多，如何无监督的提取关键帧对于很多任务都是至关重要的；   

<!--more-->
`关键帧提取和视频摘要的关系`{:.warning}   

# 1 Paper
## 1.1 传统方法
### 1.1.1 基于镜头边界
>将视频分割成多段（镜头），直接取每个镜头的首末帧和中间帧作为关键帧；   
优势是计算量小；   

### 1.1.2 基于运动分析
>即光流计算；通过光流分析运动量，在运动量取局部最小值时即为关键帧，他反映了视频数据的静止部分；   
缺点是计算量巨大，且局部最小值也未必准确；    

### 1.1.3 基于视觉内容
>通过颜色纹理等视觉信息的变化来提取关键帧；当信息变化较大时即可作为关键帧；      

### 1.1.4 基于聚类
>综合考虑镜头内和镜头间的相关性，依据时间和内容上高度相关性将视频划分为不同的类，然后选取最不相关的帧作为关键帧；   
计算高效，可获取变化显著的帧，但不能有效保存镜头内图像帧的时间顺序和动态信息；   


## 1.2 机器学习方法

### 1.2.1 基于回归
>通过机器学习算法对每帧图像进行打分，取最高分为关键帧；   

### 1.2.2 视频摘要
1. [Query-Conditioned Three-Player Adversarial Network for Video Summarization](http://cn.arxiv.org/abs/1807.06677)   
BMVC 2018 *2018-07-17* [Paper](https://arxiv.org/abs/1807.06677)   

1. [Discriminative Feature Learning for Unsupervised Video Summarization](http://cn.arxiv.org/abs/1811.09791)   
*2018-11-24* [Paper](https://arxiv.org/abs/1811.09791)    

1. [Hierarchical Recurrent Neural Network for Video Summarization](http://cn.arxiv.org/abs/1904.12251)   
*2019-04-28* [Paper](https://arxiv.org/abs/1904.12251)   

1. Unsupervised Video Summarization with Adversarial LSTM Networks   
先验：关键帧的分布应该与原序列的分布一直（去除冗余信息）；  
正规化：关键帧的个数应该尽可能的少；关键帧的信息尽可能离散；   

1. Deep Keyframe Detection in Human Action Video  
人体行为关键帧的特点：这些关键帧的类别区分度最强；   
做法：  
- 生成关键帧的label   
    - 利用 Imagenet 预训练的 VGG-16 提取每一帧的特征   
    - 根据每个视频的类别，将同一类别的帧组成 Vc   
    - 对于每一类，利用 LDA 学习一个矩阵，最大化与其他类别的距离    
每一帧的得分为：
- 利用生成的 label，训练一个关键帧得分生成网络   
收获：   
- 关键帧的分布与原序列的分布一致（多样性）  
- 关键帧的信息冗余尽可能少（离散型）  
- 关键帧的个数应该尽可能的少  
- 关键帧能够很容易识别出该 id（判别性）  

1. A Key Volume Mining Deep Framework for Action Recognition   
motivation：视频中包含大量静止画面，如果把这些帧送入网络，会对网络的训练起到一个反向的作用；   
做法：将多个帧输入到网络中，只优化对于在目标类中取得最大概率的帧的loss；   
思考：用分类来提取关键帧，类别分数越高，越有可能成为关键帧；   
问题：测试时输入的帧也有可能不含有动作信息，为什么还要将各个帧的得分平均？是不是也可以考虑像训练集那样只考虑关键帧的预测结果；   

1. [Person Identification with Visual Summary for a Safe Access to a Smart Home](http://cn.arxiv.org/abs/1904.01178)   
*2019-04-02* [Paper](https://arxiv.org/abs/1904.01178)   


### 1.2.3 其他
1. [Fast and Robust Dynamic Hand Gesture Recognition via Key Frames Extraction and Feature Fusion](http://cn.arxiv.org/abs/1901.04622)   
*2019-01-15* [Paper](https://arxiv.org/abs/1901.04622)   
基于图像熵和视频聚类提取到视频中的关键帧，一次提高手势识别的准确度；   
[数据，代码](https://github.com/Ha0Tang/HandGestureRecognition) 待发布；   

-------------------  
 [End]()
{:.warning}  


# 附录
## A 参考资料
