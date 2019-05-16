---
layout: article
title:  "「VIDEO」 视频理解资源汇总"
date:   2019-05-14 11:06:40 +0800
key: video-classify-foundation-20190514
aside:
  toc: true
category: [Video, VideoClassification]
tags: 资源
---
`video understanding` · `video classification` · `action recognition`   
>知道这段视频在做什么：行为识别就是对时域预先分割好的序列判定其所属行为动作的类型，即“读懂行为”；   

<!--more-->

# 1 数据集

| 数据集 | 来源 | 视频数 | 动作数 | 说明 |
| --- | --- | --- | --- | --- |
| UCF-101 | YouTube | 13320 | 101 | |
| HMDB51 | YouTube | 7000 | 51 | |
| Kinetics | YouTube | 300K | 400 | |
| activity-net |  | 10024+4926+5044 | 200 | |
| 1M sport |  | 1.2 million | 487 | 每类 1k-3k 个视频 |

# 2 Paper
## 2.1 综述
1. [The THUMOS Challenge on Action Recognition for Videos](http://cn.arxiv.org/abs/1604.06182)   
*2016-04-21* [Paper](https://arxiv.org/abs/1604.06182)   

1. [Deep Learning for Video Classification and Captioning](http://cn.arxiv.org/abs/1609.06782)   
*2016-09-22* [Paper](https://arxiv.org/abs/1609.06782)   

1. [A Survey on Deep Learning Based Approaches for Action and Gesture Recognition in Image Sequences](https://hal.inria.fr/hal-01678006/file/deep_learning_action.pdf)   
*2018-01-08* [Paper](https://hal.inria.fr/hal-01678006/file/deep_learning_action.pdf)    

1. [A Survey of Video Based Action Recognition in Sports](https://pdfs.semanticscholar.org/2bb7/6926af1af556e3fd1c32c6dd557826b8ee2a.pdf?_ga=2.53757928.1506702602.1557989902-129004075.1557370518)   
*2018-09* [Paper](https://pdfs.semanticscholar.org/2bb7/6926af1af556e3fd1c32c6dd557826b8ee2a.pdf?_ga=2.53757928.1506702602.1557989902-129004075.1557370518)    

## 2.2 经典论文

## 2.3 通用视频分析

1. [Non-local Neural Networks](http://cn.arxiv.org/abs/1711.07971)   
CVPR 2018 *2017-11-21* [Paper](https://arxiv.org/abs/1711.07971) [caffe2](https://github.com/facebookresearch/video-nonlocal-net) | [zhihu](https://www.zhihu.com/question/68473183)       

1. [ECO: Efficient Convolutional Network for Online Video Understanding](http://cn.arxiv.org/abs/1804.09066)   
ECCV 2018 *2018-04-24* [Paper](https://arxiv.org/abs/1804.09066) | [caffe](https://github.com/mzolfaghari/ECO-efficient-video-understanding) | [pytorch](https://github.com/mzolfaghari/ECO-pytorch) | [林天威](https://zhuanlan.zhihu.com/p/36795554)        

1. [$A^2$ -Nets: Double Attention Networks](http://cn.arxiv.org/abs/1810.11579)   
NIPS 2018 *2018-10-27* [Paper](https://arxiv.org/abs/1810.11579) | [Kivee123](https://blog.csdn.net/qq_37014750/article/details/83989334) | [zhihu](https://www.zhihu.com/question/321294274)

1. [StNet: Local and Global Spatial-Temporal Modeling for Action Recognition](http://cn.arxiv.org/abs/1811.01549)    
AAAI 2019 *2018-11-05* 百度 MIT [Paper](https://arxiv.org/abs/1811.01549) | [pytorch](https://github.com/hyperfraise/Pytorch-StNet) | [机器之心](https://zhuanlan.zhihu.com/p/55901502)

1. [Temporal Shift Module for Efficient Video Understanding](http://cn.arxiv.org/abs/1811.08383)   
*2018-11-20* [Paper](https://arxiv.org/abs/1811.08383) | [pytorch](https://github.com/MIT-HAN-LAB/temporal-shift-module)-offical | [pytorch](https://github.com/Pika7ma/Temporal-Shift-Module) | [琪瑞](https://zhuanlan.zhihu.com/p/64525610)        

1. [Convolutional sparse coding for capturing high speed video content](http://cn.arxiv.org/abs/1806.04935)   
*2018-06-13* [Paper](https://arxiv.org/abs/1806.04935)   

## 2.4 视频分类
1. [Large-scale video classification with convolutional neural networks](https://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/42455.pdf)   
CVPR 2014 *2014* 李飞飞 [Paper](https://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/42455.pdf) | [夏洛的网](https://blog.csdn.net/liuxiao214/article/details/78134319)     

1. [Efficient Large Scale Video Classification](https://arxiv.org/abs/1505.06250)   
*2015-05-22* [Paper](https://arxiv.org/abs/1505.06250)   

1. [Adversarial Perturbations Against Real-Time Video Classification Systems](http://cn.arxiv.org/abs/1807.00458)   
*2018-07-02* [Paper](https://arxiv.org/abs/1807.00458)   

1. [Adaptive Temporal Encoding Network for Video Instance-level Human Parsing](http://cn.arxiv.org/abs/1808.00661)   
ACM MM 2018 *2018-08-02* [Paper](https://arxiv.org/abs/1808.00661) | [Keras](https://github.com/HCPLab-SYSU/ATEN) | [LIP-Dataset](http://sysu-hcp.net/lip/)    
视频人物分割；   

1. [Semantic Adversarial Network with Multi-scale Pyramid Attention for Video Classification](http://cn.arxiv.org/abs/1902.02155)   
*2019-03-06* [Paper](https://arxiv.org/abs/1902.02155)   
仅基于 RGB 的双流网络；   

## 2.5 动作识别
又叫行为识别；   

### 2.5.1 传统方法
1. [Dense Trajectories and Motion Boundary Descriptors for Action Recognition](https://hal.inria.fr/hal-00725627v2/document)   
*2013-01-25* [Paper](https://hal.inria.fr/hal-00725627v2/document)   
iDT   

1. [Action recognition with improved trajectories](https://hal.inria.fr/hal-00873267v2/document)    
ICCV 2013 *2013-10-16* [Paper](https://hal.inria.fr/hal-00873267v2/document)    
传统方法，密集轨迹算法(DT算法) iDT；     

### 2.5.2 单帧 CNN

### 2.5.3 扩展 CNN

### 2.5.4 双流法

1. [Two-Stream Convolutional Networks for Action Recognition in Videos](http://cn.arxiv.org/abs/1406.2199)   
NIPS 2014 *2014-06-09* VGG 团队 [Paper](https://arxiv.org/abs/1406.2199) | [pytorch](https://github.com/jeffreyhuang1/two-stream-action-recognition) | [陈泰红](https://zhuanlan.zhihu.com/p/31841417)   
TSC    

1. [Convolutional Two-Stream Network Fusion for Video Action Recognition](http://cn.arxiv.org/abs/1604.06573)   
CVPR 2016 *2016-04-22* [Paper](https://arxiv.org/abs/1604.06573) | [pytorch](https://github.com/tomar840/two-stream-fusion-for-action-recognition-in-videos) | [牛牛存](https://blog.csdn.net/weixin_42164269/article/details/80689653)    

1. [Temporal Segment Networks: Towards Good Practices for Deep Action Recognition](http://cn.arxiv.org/abs/1608.00859)   
ECCV 2016 *2016-08-02* [Paper](https://arxiv.org/abs/1608.00859) | [caffe](https://github.com/yjxiong/temporal-segment-networks) | [pytorch](https://github.com/yjxiong/tsn-pytorch) | [pytorch](https://github.com/jeffreyhuang1/two-stream-action-recognition) | [AI之路](https://blog.csdn.net/u014380165/article/details/79029309)   
TSN     

1. [Spatiotemporal Residual Networks for Video Action Recognition](http://cn.arxiv.org/abs/1611.02155)   
NIPS 2016 *2016-11-07* [Paper](https://arxiv.org/abs/1611.02155) | [matlab](https://github.com/feichtenhofer/st-resnet)   

1. [Spatiotemporal Multiplier Networks for Video Action Recognition](http://openaccess.thecvf.com/content_cvpr_2017/papers/Feichtenhofer_Spatiotemporal_Multiplier_Networks_CVPR_2017_paper.pdf)   
CVPR 2017 *2017* [Paper](http://openaccess.thecvf.com/content_cvpr_2017/papers/Feichtenhofer_Spatiotemporal_Multiplier_Networks_CVPR_2017_paper.pdf) | [matlab](https://github.com/feichtenhofer/st-resnet) | [BojackHorseman](https://blog.csdn.net/bojackhosreman/article/details/78654753)    

1. [Temporal Segment Networks for Action Recognition in Videos](http://cn.arxiv.org/abs/1705.02953)   
*2017-05-08* [Paper](https://arxiv.org/abs/1705.02953) | [caffe](https://github.com/yjxiong/temporal-segment-networks) | [pytorch](https://github.com/tomar840/two-stream-fusion-for-action-recognition-in-videos)     

1. [A Closer Look at Spatiotemporal Convolutions for Action Recognition](http://cn.arxiv.org/abs/1711.11248)   
*2017-11-30* facebook [Paper](https://arxiv.org/abs/1711.11248) | [S3D-G_pytorch](https://github.com/MRzzm/action-recognition-models-pytorch) | [张智勐SDU](https://blog.csdn.net/zzmshuai/article/details/85143711)   

1. [Rethinking Spatiotemporal Feature Learning For Video Understanding](http://cn.arxiv.org/abs/1712.04851)     
ECCV 2018 *2017-12-13* google [Paper](https://arxiv.org/abs/1712.04851) | [S3D-G_pytorch](https://github.com/MRzzm/action-recognition-models-pytorch) | [张智勐SDU](https://blog.csdn.net/zzmshuai/article/details/85235239)   

1. [DMC-Net: Generating Discriminative Motion Cues for Fast Compressed Video Action Recognition](http://cn.arxiv.org/abs/1901.03460)   
CVPR 2019 *2019-01-11* [Paper](https://arxiv.org/abs/1901.03460)   


### 2.5.5 C3D
1. [3D Convolutional Neural Networks for Human Action Recognition](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.442.8617&rep=rep1&type=pdf)   
*2013* [Paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.442.8617&rep=rep1&type=pdf) | [陈泰红](https://zhuanlan.zhihu.com/p/31841353)   

1. [C3D: Generic Features for Video Analysis](http://cn.arxiv.org/abs/1412.0767)     
ICCV 2015 *2014-12-02* facebook [Paper](https://arxiv.org/abs/1412.0767) [project](http://vlg.cs.dartmouth.edu/c3d/) | [caffe](https://github.com/facebook/C3D)-offical | [tensorflow](https://github.com/hx173149/C3D-tensorflow) | [极市平台](https://zhuanlan.zhihu.com/p/25912625)      
*Learning spatiotemporal features with 3d convolutional networks*     

### 2.5.6 RNN
1. [A Torch Library for Action Recognition and Detection Using CNNs and LSTMs](http://cs231n.stanford.edu/reports/2016/pdfs/221_Report.pdf)  
*2016* [Paper](http://cs231n.stanford.edu/reports/2016/pdfs/221_Report.pdf)    

1. [Delving Deeper into Convolutional Networks for Learning Video Representations](http://cn.arxiv.org/abs/1511.06432)   
ICLR 2016 *2015-11-19* [Paper](https://arxiv.org/abs/1511.06432)   
GRU   

1. [RPAN：An End-to-End Recurrent Pose-Attention Network for Action Recognition in Videos]()    
ICCV 2017 oral 中科院深圳先进·院乔宇   
与传统的 Video-level category 训练 RNN 不同，这篇文章还提出了 Pose-attention 的机制；  
贡献：   
- 不同于之前的pose-related action recognition，这篇文章是端到端的RNN，而且是 spatial-temporal evolutionos of human pose；   
- 不同于独立的学习关节点特征(human-joint features)，这篇文章引入的pose-attention机制通过不同语义相关的关节点(semantically-related human joints)分享attention参数，然后将这些通过human-part pooling层联合起来    
- 视频姿态估计，通过文章的方法可以给视频进行粗糙的姿态标记；   

1. [TS-LSTM and Temporal-Inception: Exploiting Spatiotemporal Dynamics for Activity Recognition](http://cn.arxiv.org/abs/1702.10667)   
*2017-03-30* [Paper](https://arxiv.org/abs/1702.10667) | [pytorch](https://github.com/jeffreyhuang1/two-stream-action-recognition) | [torch](https://github.com/olivesgatech/TS-LSTM-and-Temporal-Inception)-lua | [torch](https://github.com/chihyaoma/Activity-Recognition-with-CNN-and-RNN)-lua      


### 2.5.7 其他
1. [Action Recognition with Trajectory-Pooled Deep-Convolutional Descriptors](http://cn.arxiv.org/abs/1505.04868)   
CVPR 2015 *2015-05-19* [Paper](https://arxiv.org/abs/1505.04868) | [caffe](https://github.com/wanglimin/TDD)-matlab      

1. [A Key Volume Mining Deep Framework for Action Recognition](https://zpascal.net/cvpr2016/Zhu_A_Key_Volume_CVPR_2016_paper.pdf)   
CVPR 2016 *2015* [Paper](https://zpascal.net/cvpr2016/Zhu_A_Key_Volume_CVPR_2016_paper.pdf)   
Key Volume Mining；    

1. [Deep Multi Scale Video Prediction Beyond Mean Square Error](http://cn.arxiv.org/abs/1511.05440)   
*2015-11-17* [Paper](https://arxiv.org/abs/1511.05440)   

1. [Long-term temporal convolutions for action recognition](https://arxiv.org/abs/1604.04494)   
PAMI 2018 *2016-01-15* [Paper](https://arxiv.org/abs/1604.04494) | [project](https://www.di.ens.fr/willow/research/ltc/) | [torch](https://github.com/gulvarol/ltc)-lua | [BojackHorseman](https://blog.csdn.net/bojackhosreman/article/details/78261097)   
LTC  

1. [Trajectory Convolution for Action Recognition](https://papers.nips.cc/paper/7489-trajectory-convolution-for-action-recognition.pdf)   
NIPS 2018 [Paper](https://papers.nips.cc/paper/7489-trajectory-convolution-for-action-recognition.pdf) | [zhihu](https://www.zhihu.com/question/304696640/answer/546086974)      
TrajectoryNet：轨迹卷积网络   

1. [Deep Adaptive Temporal Pooling for Activity Recognition](http://cn.arxiv.org/abs/1808.07272)   
ACM Multimedia 2018 *2018-08-22* [Paper](https://arxiv.org/abs/1808.07272)    


# 4 渔
- 牛人   
[David Forsyth](http://luthuli.cs.uiuc.edu/~daf/)   
[Michal Irani](http://www.weizmann.ac.il/math/irani/)   
- 总结   
[MVision](https://github.com/Ewenwan/MVision/blob/master/CNN/Action_Recognition/readme.md)    
[Christoph Feichtenhofer](https://feichtenhofer.github.io/)   

-------------------  
 [End]()
{:.warning}  


# 附录
