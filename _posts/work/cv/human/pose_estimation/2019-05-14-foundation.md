---
layout: article
title:  "「CV」 姿态识别资源汇总"
date:   2019-05-14 14:06:40 +0800
key: pose-estimate-foundation-20190514
aside:
  toc: true
category: [CV, human, pose_estimation]
tags: 资源
---
<span id='head'></span>
`pose estimation` · `action classification`    

>又叫动作识别，给定一幅图像或一段视频，人体姿态识别就是去恢复其中人体关节点位置的过程；   

<!--more-->

# 1 数据集

# 2 论文
## 2.1 综述  
## 2.2 图片
### 2.2.1 头部
1. [Improving Head Pose Estimation with a Combined Loss and Bounding Box Margin Adjustment](https://arxiv.org/abs/1905.08609)    
*2019-05-14* [paper](https://arxiv.org/abs/1905.08609)   

## 2.3 视频
### 2.3.1 关键帧提取
1. [Deep Keyframe Detection in Human Action Videos](http://cn.arxiv.org/abs/1804.10021)   
*2018-04-26* [Paper](https://arxiv.org/abs/1804.10021)   
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

## 2.4 3D 姿态估计
1. [Patch-based 3D Human Pose Refinement](http://cn.arxiv.org/abs/1905.08231)   
CVPR 2019 (Augmented Human) *2019-05-20* [paper](https://arxiv.org/abs/1905.08231)   



-------------------  
[End](#head)
{:.warning}  


# 附录
## A 参考资料
1. 程程. VALSE2017系列之三：人体姿态识别领域年度进展报告[EB/OL]. <https://zhuanlan.zhihu.com/p/27293180>. 2017-06-07/2019-05-14.   
1. lyl-Deepleraing. 深度学习的人体动作识别算法[EB/OL]. <https://zhuanlan.zhihu.com/p/46599638>. 2018-10-12/2019-05-14.   
