---
layout: article
title:  "「VIDEO」 视频摘要入门"
date:   2019-05-14 10:06:40 +0800
key: key-frame-extraction-foundation-20190514
aside:
  toc: true
category: [video, KeyFrame]
tags: 资源
---
`video key frame extraction` · `video key clip extraction` · `video summarization` · `key frame Detection`   
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
1. [Video Summarization with Attention-Based Encoder-Decoder Networks](http://cn.arxiv.org/abs/1708.09545)   
*2017-08-31* [Paper](https://arxiv.org/abs/1708.09545)   

1. [Video Summarization by Learning from Unpaired Data](http://cn.arxiv.org/abs/1805.12174)
CVPR 2019 *2018-03-30* [Paper](https://arxiv.org/abs/1805.12174)   

1. [DTR-GAN: Dilated Temporal Relational Adversarial Network for Video Summarization](http://cn.arxiv.org/abs/1804.11228)   
*2018-04-30* [Paper](https://arxiv.org/abs/1804.11228)   

1. [Query-Conditioned Three-Player Adversarial Network for Video Summarization](http://cn.arxiv.org/abs/1807.06677)   
BMVC 2018 *2018-07-17* [Paper](https://arxiv.org/abs/1807.06677)   

1. [Discriminative Feature Learning for Unsupervised Video Summarization](http://cn.arxiv.org/abs/1811.09791)   
*2018-11-24* [Paper](https://arxiv.org/abs/1811.09791)    

1. [Hierarchical Recurrent Neural Network for Video Summarization](http://cn.arxiv.org/abs/1904.12251)   
*2019-04-28* [Paper](https://arxiv.org/abs/1904.12251)   

1. Unsupervised Video Summarization with Adversarial LSTM Networks   
先验：关键帧的分布应该与原序列的分布一直（去除冗余信息）；  
正规化：关键帧的个数应该尽可能的少；关键帧的信息尽可能离散；   

1. [Person Identification with Visual Summary for a Safe Access to a Smart Home](http://cn.arxiv.org/abs/1904.01178)   
*2019-04-02* [Paper](https://arxiv.org/abs/1904.01178)   

### 1.2.3 关键帧提取
1. [Video Key Frame Extraction using Entropy value as Global and Local Feature](http://cn.arxiv.org/abs/1605.08857)   
*2016-05-28* [Paper](https://arxiv.org/abs/1605.08857)   

## 1.3 应用
### 1.3.1  [在手势识别中的应用](/cv/human/gesturerecognition/2019/05/14/foundation.html#12-基于关键帧)

### 1.3.2 [在动作识别中的应用](/cv/human/poseestimation/2019/05/14/foundation.html#12-关键帧提取)



-------------------  
 [End](/video/keyframe/2019/05/14/foundation.html#1-paper)
{:.warning}  


# 附录
## A 参考资料
