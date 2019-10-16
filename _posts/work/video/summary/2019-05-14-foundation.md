---
layout: article
title:  "「VIDEO」 视频摘要资源汇总"
date:   2019-05-14 10:06:40 +0800
key: video-summary-foundation-20190514
aside:
  toc: true
category: [video, video_summary]
tags: 资源
---
<span id='head'></span>
`shot detection` · `video summary` · `video synopsis` · `video key clip extraction` · `video summarization` · `key frame Detection`   

>又称视频浓缩，是对视频内容的一个简单概括；       
相关资源：[视频摘要概述](/video/video_summary/2019/06/10/survey.html)、[关键帧提取概述](/video/key_frame/2019/08/08/survey.html)、[关键帧提取资源汇总](/video/key_frame/2019/06/12/foundation.html)     


<!--more-->

>先通过运动目标分析，提取到运动目标及其轨迹；然后将不同的目标拼接到同一个背景中，也可以拼接；视频摘要在视频分析和基于内容的视频检索中扮演着重要角色；    



# 1 传统方法
## 1.1 基于镜头边界

## 1.2 基于运动分析

## 1.3 基于视觉内容

## 1.4 基于聚类


# 2 机器学习方法

## 2.1 基于回归
>通过机器学习算法对每帧图像进行打分，取最高分为关键帧；   

## 2.2 视频摘要

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

1. [Person Identification with Visual Summary for a Safe Access to a Smart Home](http://cn.arxiv.org/abs/1904.01178)   
*2019-04-02* [Paper](https://arxiv.org/abs/1904.01178)   

1. [Attention is all you need for Videos: Self-attention based Video Summarization using Universal Transformers](http://cn.arxiv.org/abs/1906.02792)   
*2019-06-06* [paper](https://arxiv.org/abs/1906.02792)    


## 2.3 [静态摘要](/video/key_frame/2019/06/12/foundation.html)

# 3 扩展技术
## 3.1 关键帧
>[关键帧资源](/video/key_frame/2019/06/12/foundation.html)    

1. [Video Summarization with LongShort-term Memory](http://cn.arxiv.org/abs/1605.08110)    
ECCV 2016 *2016-05-26* [paper](https://arxiv.org/abs/1605.08110) | [blog](https://blog.csdn.net/nana13628679472/article/details/82826592) | [theano](https://github.com/kezhang-cs/Video-Summarization-with-LSTM)              
用 LSTM 提取关键帧序列；     

1. [Unsupervised Video Summarization with Adversarial LSTM Networks](http://web.engr.oregonstate.edu/~sinisa/research/publications/cvpr17_summarization.pdf)     
CVPR 2017 *2017* [paper](http://web.engr.oregonstate.edu/~sinisa/research/publications/cvpr17_summarization.pdf)    
**先验**：关键帧的分布应该与原序列的分布一直（去除冗余信息）；  
**正规化**：关键帧的个数应该尽可能的少；关键帧的信息尽可能离散；   
**做法**：    
- slstm：输出每一帧的得分，与原来帧加权后得到新的特征；      
- elstm：对于lstm得到的特征编码，得到一个特征；      
- dlstm：对elstm得到的特征解码，恢复出原来的特征；      
- clstm：判断dlstm得到的特征是否还是原来的特征；      

**处理**：根据每一帧的得分选出关键帧     
- 将视频分成不重叠的几个clip；      
- 每个clip的得分是这个clip中所有帧的得分的平均，对clip排序；      
- 高得分的clip中的帧按照分数排序，选出最高的几帧；      



-------------------  
[End](#head)
{:.warning}  


# 附录
## A 参考资料
1. [paper with code](https://paperswithcode.com/task/video-summarization/codeless)    
