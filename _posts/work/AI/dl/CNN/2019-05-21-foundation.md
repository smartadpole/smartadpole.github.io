---
layout: article
title:  "「DL」 卷积网络资源汇总"
date:   2019-05-21 14:18:40 +0800
key: cnn-foundation-20190521
aside:
  toc: true
category: [DL, CNN]
tags: 资源
---
<span id='head'></span>  
<!--more-->

# 1 综述

# 2 理论
1. [Notes on Convolutional Neural Networks](http://cogprints.org/5869/1/cnn_tutorial.pdf)   
*2006-11-22* [Paper](http://cogprints.org/5869/1/cnn_tutorial.pdf) | [亦轩Dhc](https://www.cnblogs.com/daihengchen/p/5646526.html)   
$\bullet \bullet$   
主要讲了 CNN 前向和反向传播，包括卷积层和池化的反向传播的推导的讲解；    

1. [Optimizing Shallow Networks for Binary Classification](http://cn.arxiv.org/abs/1905.10161)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10161)   

1. [NICO: A Dataset Towards Non-I.I.D. Image Classification](http://cn.arxiv.org/abs/1906.02899)   
*2019-06-07* [paper](https://arxiv.org/abs/1906.02899)    


# 2 二维
## 2.1 经典网络
1. [ImageNet classification with deep convolutional neural networks](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)     
*2012* [paper](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf) | [tensorflow](https://github.com/Abhisek-/AlexNet)    
AlexNet；     

1. [Very deep convolutional networks for large-scale image recognition](http://cn.arxiv.org/abs/1409.1556)    
ICLR 2015 oral *2014-09-04* [paper](https://arxiv.org/abs/1409.1556) | [tensorflow](https://github.com/Abhisek-/VGG)       
VGG:    

1. [Going deeper with convolutions](http://cn.arxiv.org/abs/1409.4842)     
CVPR 2015 *2014-09-17* [paper]https://arxiv.org/abs/1409.4842     
GoogLeNet;     

1. [Deep residual learning for image recognition](http://cn.arxiv.org/abs/1512.03385)     
CVPR 2016 *2015-12-10* [paper](https://arxiv.org/abs/1512.03385)     
ResNet;    

1. [Squeeze-and-Excitation Networks](http://cn.arxiv.org/abs/1709.01507)   
*2017-09-05* [Paper](https://arxiv.org/abs/1709.01507)   
SENet   

## 2.2 轻量级网络
1. [Aggregated Residual Transformations for Deep Neural Networks](http://cn.arxiv.org/abs/1611.05431)     
CVPR 2017 *2016-11-16* [paper](https://arxiv.org/abs/1611.05431)     
ResNeXt;     

1. [SqueezeNet: AlexNet-level accuracy with 50x fewer parameters and <0.5MB model size](http://cn.arxiv.org/abs/1602.07360)    
ICLR 2017 *2016-02-24* 伯克利&斯坦福 [paper](https://arxiv.org/abs/1602.07360)    
SqueezeNet     

1. [Xception: Deep Learning with Depthwise Separable Convolutions](http://cn.arxiv.org/abs/1610.02357)    
*2016-10-07* Google [paper](https://arxiv.org/abs/1610.02357)    
Xception     

1. [MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications](http://cn.arxiv.org/abs/1704.04861)    
CVPR 2017 *2017-04-17* [paper](https://arxiv.org/abs/1704.04861) | [ncnn](https://github.com/Revo-Future/ncnn_mobileNet)-[Blog](https://blog.csdn.net/computerme/article/details/77876633) | [caffe](https://github.com/shicai/MobileNet-Caffe)      
MobileNet     

1. [ShuffleNet: An Extremely Efficient Convolutional Neural Network for Mobile Devices](http://cn.arxiv.org/abs/1707.01083)     
CVPR 2017 *2017-07-04* Face++ [paper](https://arxiv.org/abs/1707.01083)     
ShuffleNet     

1. [Interleaved Group Convolutions for Deep Neural Networks](http://cn.arxiv.org/abs/1707.02725)     
ICCV 2017 *2017-07-10* 微软 [paper](https://arxiv.org/abs/1707.02725)    
IGCV     

1. [MobileNetV2: Inverted Residuals and Linear Bottlenecks](http://cn.arxiv.org/abs/1801.04381)     
*2018-01-13* [paper](https://arxiv.org/abs/1801.04381) | [mxnet](https://github.com/liangfu/mxnet-mobilenet-v2) | [caffe](https://github.com/shicai/MobileNet-Caffe)    
MobileNetV2      

1. [IGCV2: Interleaved Structured Sparse Convolutional Neural Networks](http://cn.arxiv.org/abs/1804.06202)     
*2018-04-17* 微软 [paper](https://arxiv.org/abs/1804.06202)     
IGCV2     

1. [IGCV3: Interleaved Low-Rank Group Convolutions for Efficient Deep Neural Networks](http://cn.arxiv.org/abs/1806.00178)     
BMVC 2018 *2018-06-01* 微软 [paper](https://arxiv.org/abs/1806.00178) | [mxnet](https://github.com/homles11/IGCV3) | [pytorch](https://github.com/xxradon/IGCV3-pytorch)              
IGCV3     

1. [ShuffleNet V2: Practical Guidelines for Efficient CNN Architecture Design](http://cn.arxiv.org/abs/1807.11164v1)     
*2018-07-30* [paper](https://arxiv.org/abs/1807.11164v1)    
ShuffleNetV2    

1. [Searching for MobileNetV3](http://cn.arxiv.org/abs/1905.02244)   
*2019-05-06* google [paper](https://arxiv.org/abs/1905.02244) | [pytorch](https://github.com/xiaolai-sqlai/mobilenetv3) | [pytorch](https://github.com/shanglianlm0525/MobileNetV3-Pytorch) | [我爱计算机视觉](https://www.jiqizhixin.com/articles/2019-05-09-2)   
MobileNetV3:    

1. [MoGA: Searching Beyond MobileNetV3](http://cn.arxiv.org/abs/1908.01314)     
*2019-08-04* [paper](https://arxiv.org/abs/1908.01314) | [pytorch](https://github.com/xiaomi-automl/MoGA)-official          

## 2.3 提升泛化能力
1. [Learning to Find Correlated Features by Maximizing Information Flow in Convolutional Neural Networks](http://cn.arxiv.org/abs/1907.00348)   
*2019-06-30*  [paper](https://arxiv.org/abs/1907.00348)    
设计了新的 loss 来指导网络学习更多的相关特征，以应对未见过的数据；    


## 2.4 其他
1.[Invertible Residual Networks](https://arxiv.org/abs/1811.00995)   
ICML 2019 *2018-11-02* [paper](https://arxiv.org/abs/1811.00995)  


# 3 三维
1. [3D Dense Separated Convolution Module for Volumetric Image Analysis](http://cn.arxiv.org/abs/1905.08608)   
*2019-05-14* [paper](https://arxiv.org/abs/1905.08608)   

1. [A review on deep learning techniques for 3D sensed data classification](http://cn.arxiv.org/abs/1907.04444)    
*2019-07-09* [paper](https://arxiv.org/abs/1907.04444)    



# 6 应用
## 6.1 针对嵌入式设备提速
1. [Closing the Accuracy Gap in an Event-Based Visual Recognition Task](http://cn.arxiv.org/abs/1906.08859)    
*2019-05-06* [paper](https://arxiv.org/abs/1906.08859)    

-------------------  
[End](#head)
{:.warning}  
