---
layout: article
title:  "「CV」 物体分类资源汇总"
date:   2019-05-15 18:00:40 +0800
key: object-classify-foundation-20190515
aside:
  toc: true
category: [AI, CV, classification]
tags: 资源
---
<span id='head'></span>  
>[CNN](/ai/dl/cnn/2019/05/21/foundation.html)     


<!--more-->  

# 1 综述


# 2 理论

1. [Optimizing Shallow Networks for Binary Classification](http://cn.arxiv.org/abs/1905.10161)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10161)   

1. [NICO: A Dataset Towards Non-I.I.D. Image Classification](http://cn.arxiv.org/abs/1906.02899)   
*2019-06-07* [paper](https://arxiv.org/abs/1906.02899)    

1. [Transferability and Hardness of Supervised Classification Tasks](http://cn.arxiv.org/abs/1908.08142)    
ICCV 2019 *2019-08-21* [paper](https://arxiv.org/abs/1908.08142)    
无需训练，使用条件熵来衡量两个任务之间迁移的难易程度；     

# 3 经典论文

1. [Rethinking ImageNet Pretraining](http://cn.arxiv.org/abs/1811.08883)   
*2018-11-21* 何恺明 [Paper](https://arxiv.org/abs/1811.08883)   

# 4 one-hot
1. [Dynamic Mode Decomposition based feature for Image Classification](http://cn.arxiv.org/abs/1910.03188)    
*2019-10-08* [paper](https://arxiv.org/abs/1910.03188)     
动态模式分解 + SVM；对数据量要求不那么高；      

# 5 多标签
1. [Learning a Deep ConvNet for Multi-label Classification with Partial Labels](http://cn.arxiv.org/abs/1902.09720)   
CVPR 2019 *2019-02-26* [paper](https://arxiv.org/abs/1902.09720)    
降低多标签任务的标注成本；     


# 6 应用
## 6.1 [OCR](/ai/cv/ocr/2019/07/27/foundation.html#3-字符识别)

## 6.2 金融
`股票预测`    

1. [Convolutional Feature Extraction and Neural Arithmetic Logic Units for Stock Prediction](http://cn.arxiv.org/abs/1905.07581)   
ICACDS 2019 *2019-05-18* [paper](https://arxiv.org/abs/1905.07581)   


## 6.3 交通
### 6.3.1 [车辆识别](/ai/cv/vehicle/vehicle_recognition/2019/07/12/foundation.html)
### 6.3.2 [交通信号识别](/ai/cv/traffic/traffic_signals_recognition/2019/10/11/foundation.html)

## 6.4 自然
### 6.4.1 叶片分类
1. [A 1d convolutional network for leaf and time series classification](http://cn.arxiv.org/abs/1907.00069)   
*2019-06-28* [paper](https://arxiv.org/abs/1907.00069) | [Tensorflow](https://github.com/dykuang/Leaf_Project)-offical     
1 维卷积在轮廓分类问题中的使用；    

## 6.5 农业

## 6.6 智能家居
### 6.6.1 家居机器人
`烹饪状态识别`   

1. [VGG Fine-tuning for Cooking State Recognition](http://cn.arxiv.org/abs/1905.08606)   
*2019-05-13* [paper](https://arxiv.org/abs/1905.08606)   

## 6.7 医学
### 6.7.1 皮肤病

1. [TopoResNet: A hybrid deep learning architecture and its application to skin lesion classification](https://arxiv.org/abs/1905.08607)   
*2019-05-13* [paper](https://arxiv.org/abs/1905.08607)   

1. [Skin Cancer Recognition using Deep Residual Network](https://arxiv.org/abs/1905.08610)   
*2019-05-14* [paper](https://arxiv.org/abs/1905.08610)    

1. [Skin Lesion Classification Using Ensembles of Multi-Resolution EfficientNets with Meta Data](http://cn.arxiv.org/abs/1910.03910)     
ISIC 2019 *2019-10-09* [paper](https://arxiv.org/abs/1910.03910) | [ISIC 2019](https://challenge2019.isic-archive.com/leaderboard.html)       
对输入图像的分辨率做了处理；似乎还用了模型集成；


### 6.7.2 肾小球病变
1. [Classification of glomerular hypercellularity using convolutional features and support vector machine](http://cn.arxiv.org/abs/1907.00028)   
*2019-06-28* [paper](https://arxiv.org/abs/1907.00028)    
>为啥要用深度特征+SVM 啊，直接用全连接+softmax 不好吗；   

### 6.7.3 青光眼
1. [REFUGE Challenge: A Unified Framework for Evaluating Automated Methods for Glaucoma Assessment from Fundus Photographs](http://cn.arxiv.org/abs/1910.03667)       
*2019-10-08* [paper](https://arxiv.org/abs/1910.03667)    

### 6.7.4 罕见疾病诊断
1. [Difficulty-aware Meta-Learning for Rare Disease Diagnosis](http://cn.arxiv.org/abs/1907.00354)   
*2019-06-30* [paper](https://arxiv.org/abs/1907.00354)    
零样本学习解决罕见疾病诊断；   

### 6.8.5 肿瘤存活率
1. [Semi-Supervised Variational Autoencoder for Survival Prediction](http://cn.arxiv.org/abs/1910.04488)    
*2019-10-10* [paper](https://arxiv.org/abs/1910.04488)     
弱监督分类，根据脑肿瘤分割结果预测其存活率；   

## 6.8 建筑
1. [Tour the World: Building a Web-Scale Landmark Recognition Engine](http://www.cs.bilkent.edu.tr/~cansin/projects/cs554-vision/landmark-recognition/landmark-recognition-presentation.pdf)   
CVPR 2009 *2009-12* [ppt](http://www.cs.bilkent.edu.tr/~cansin/projects/cs554-vision/landmark-recognition/landmark-recognition-presentation.pdf)   

1. [Landmark Recognition: State-of-the-Art Methods in a Large-Scale Scenario?](http://ceur-ws.org/Vol-1226/paper05.pdf)   
*2014-09-08* [paper](http://ceur-ws.org/Vol-1226/paper05.pdf)   

1. [Tiny-Inception-ResNet-v2: Using Deep Learning for Eliminating Bonded Labors of Brick Kilns in South Asia](http://cn.arxiv.org/abs/1907.05552)   
CVPR 2019 *2019-07-12* [paper](https://arxiv.org/abs/1907.05552)   

## 6.9 人
### 6.9.1 [人脸识别](/ai/cv/human/face_recognization/2019/05/14/foundation.html)
### 6.9.2 [步态识别](/ai/cv/human/gait_recognition/2019/05/21/foundation.html)
### 6.9.3 指纹识别
1. [A Novel Approach for Partial Fingerprint Identification to Mitigate MasterPrint Generation](http://cn.arxiv.org/abs/1911.03052)      
*2019-11-08* [paper](https://arxiv.org/abs/1911.03052)     


# 7 [训练](/ai/dl/foundation/2019/05/20/foundation.html#311-分类)

# 8 数据集
1. [Places : A 10 milLion image database for scene recognition](http://places2.csail.mit.edu/PAMI_places.pdf)     
*2017* [paper](http://places2.csail.mit.edu/PAMI_places.pdf)    



-------------------  
[End](#head)
{:.warning}  


# 附录
## A 参考资料
1. [CVPR 2018 地标建筑物识别](https://landmarksworkshop.github.io/CVPRW2018/)     
1. [图像验证码和大规模图像识别技术](https://www.infoq.cn/article/CAPTCHA-image-recognition/?itm_source=infoq&itm_campaign=user_page&itm_medium=link)     
