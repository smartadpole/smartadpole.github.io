---
layout: article
title:  "「VIDEO」 关键帧提取资源汇总"
date:   2019-06-12 18:16:40 +0800
key: keyframe-foundation-20190612
aside:
  toc: true
category: [video, key_frame]
tags: 资源
---
<span id='head'></span>
>诸多视频分析技术都是以关键帧提取作为基础，在此就做一个汇总；    
相关资源：[关键帧提取概述](/video/key_frame/2019/08/08/survey.html)    

<!--more-->
`key frame extraction` · `bag of keyframes` · `key frame detection`    
`shot boundary detection` · `key volume mining`     

# 1 综述

# 2 理论

# 3 关键帧提取
1. [Video Key Frame Extraction using Entropy value as Global and Local Feature](http://cn.arxiv.org/abs/1605.08857)   
*2016-05-28* [Paper](https://arxiv.org/abs/1605.08857)   
自注意力机制助力视频字幕提取；    
>摘要不是很好，核心不清晰；   

1. [基于深度学习的视频关键帧提取与视频检索](http://gb.oversea.cnki.net/KCMS/detail/detail.aspx?filename=JZDF201905027&dbcode=CJFD&dbname=DKFXTEMP)     
*2019* 梁建胜,温贺平 [paper](http://gb.oversea.cnki.net/KCMS/detail/detail.aspx?filename=JZDF201905027&dbcode=CJFD&dbname=DKFXTEMP)    


# 4 镜头边界检测
1. [Histogram Based Split and Merge Framework for Shot Boundary Detection](https://www.researchgate.net/profile/Mohammed_Suhil/publication/260984201_Histogram_Based_Split_and_Merge_Framework_for_Shot_Boundary_Detection/links/00b4953b3bf98863a8000000/Histogram-Based-Split-and-Merge-Framework-for-Shot-Boundary-Detection.pdf)     
*2013* [paper](https://www.researchgate.net/profile/Mohammed_Suhil/publication/260984201_Histogram_Based_Split_and_Merge_Framework_for_Shot_Boundary_Detection/links/00b4953b3bf98863a8000000/Histogram-Based-Split-and-Merge-Framework-for-Shot-Boundary-Detection.pdf)    
基于颜色直方图；     


1. [A Novel Approach for Shot Boundary Detection in Videos](http://cn.arxiv.org/abs/1608.06716)    
*2012* [paper](https://arxiv.org/abs/1608.06716)     

1. [Shot boundary detection using convolutional neural networks](http://medialab.sjtu.edu.cn/publications/2016/VCIP2016_XuSongXie.pdf)    
*2016* [paper](http://medialab.sjtu.edu.cn/publications/2016/VCIP2016_XuSongXie.pdf)     
消除假的镜头边界；     

1. [Video shot boundary detection and key-frame extraction using mathematical models](https://tel.archives-ouvertes.fr/tel-01718400/document)     
*2017* [paper](https://tel.archives-ouvertes.fr/tel-01718400/document)      
好长；    

1. [Large-scale, Fast and Accurate Shot Boundary Detection through Convolutional Neural Networks](https://arxiv.org/abs/1705.03281)     
*2017-05-09* [paper](https://arxiv.org/abs/1705.03281) | [home](http://ds.qcri.org/projects/deepsbd/) | [matlab](https://github.com/melgharib/DSBD)-official       
CNN 检测镜头；开放了一个大型数据集；速度快；     

1. [Ridiculously Fast Shot Boundary Detection with Fully Convolutional Neural Networks](http://cn.arxiv.org/abs/1705.08214)     
*2017-05-23* [paper](https://arxiv.org/abs/1705.08214) | [keras](https://github.com/abramjos/Scene-boundary-detection)      
超快    

1. [TransNet: A deep network for fast detection of common shot transitions](http://cn.arxiv.org/abs/1906.03363)   
*2019-06-08* [paper](https://arxiv.org/abs/1906.03363) | [code](https://github.com/soCzech/TransNet)       


# 5 应用
## 5.1  [手势识别](/video/video_classification/2019/05/14/foundation.html#91-手势识别)

1. [Fast and Robust Dynamic Hand Gesture Recognition via Key Frames Extraction and Feature Fusion](http://cn.arxiv.org/abs/1901.04622)   
*2019-01-15* [paper](https://arxiv.org/abs/1901.04622) | [matlab](https://github.com/Ha0Tang/HandGestureRecognition)-official      
基于图像熵和视频聚类提取到视频中的关键帧，一次提高手势识别的准确度；   

## 5.2 [动作识别](/video/video_classification/2019/05/14/foundation.html)

1. [Deep Keyframe Detection in Human Action Videos](http://cn.arxiv.org/abs/1804.10021)   
*2018-04-26* [paper](https://arxiv.org/abs/1804.10021)   
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

1. [A Key Volume Mining Deep Framework for Action Recognition](https://zpascal.net/cvpr2016/Zhu_A_Key_Volume_CVPR_2016_paper.pdf)   
CVPR 2016 *2016* [paper](https://zpascal.net/cvpr2016/Zhu_A_Key_Volume_CVPR_2016_paper.pdf)   
motivation：视频中包含大量静止画面，如果把这些帧送入网络，会对网络的训练起到一个反向的作用；   
做法：将多个帧输入到网络中，只优化对于在目标类中取得最大概率的帧的loss；   
思考：用分类来提取关键帧，类别分数越高，越有可能成为关键帧；   
问题：测试时输入的帧也有可能不含有动作信息，为什么还要将各个帧的得分平均？是不是也可以考虑像训练集那样只考虑关键帧的预测结果；   


## 5.3 [视频摘要](/video/video_summary/2019/05/14/foundation.html)

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

## 5.4 REID


-------------------  
[End](#head)
{:.warning}  


# 附录
## A 参考资料
