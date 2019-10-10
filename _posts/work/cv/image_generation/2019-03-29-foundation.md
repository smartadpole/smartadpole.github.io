---
layout: article
title:  "「CV」 图像生成资源汇总"
date:   2019-03-29 11:06:40 +0800
key: image-generation-foundation-20190329
aside:
  toc: true
category: [CV, image_generation]
tags: 资源
---
<!--more-->  

# 1 综述

# 2 理论

# 3 图像修复
## 3.1 人脸修复

# 4 风格迁移
## 4.1 美颜

## 4.2 艺术
1. [Multi-Source Domain Adaptation and Semi-Supervised Domain Adaptation with Focus on Visual Domain Adaptation Challenge 2019](https://arxiv.org/abs/1910.03548)     
VisDA-2019 *2019-10-08* [paper](https://arxiv.org/abs/1910.03548) | [pytorch](https://github.com/Panda-Peter/visda2019-multisource)-多源-official | [pytorch](https://github.com/Panda-Peter/visda2019-semisupervised)-半监督-official     

# 5 图像编辑
## 5.1 人脸编辑

## 5.2 去模糊

## 5.3 去遮挡
`跟图像修复有啥区别`{:.warning}   
1.  [Robust LSTM-Autoencoders for Face De-Occlusion in the Wild](http://cn.arxiv.org/abs/1612.08534)   
*2016-11-25* [paper](https://arxiv.org/abs/1612.08534) | [caffe](https://github.com/zhaofang0627/face-deocc-lstm)        

# 6 图像修复

1.  [Semantic Image Inpainting with Perceptual and Contextual Losses](http://cn.arxiv.org/abs/1607.07539)  
[Code](https://github.com/bamos/dcgan-completion.tensorflow)  
CVPR 2017  

1.  [Context Encoders: Feature Learning by Inpainting](http://cn.arxiv.org/abs/1604.07379)  
[Code](https://github.com/jazzsaxmafia/Inpainting)   

1.  [Semi-Supervised Learning with Context-Conditional Generative Adversarial Networks](http://cn.arxiv.org/abs/1611.06430v1)    

1.  [Generative face completion](https://drive.google.com/file/d/0B8_MZ8a8aoSeenVrYkpCdnFRVms/edit)  
[Code](https://github.com/Yijunmaverick/GenerativeFaceCompletion)  
CVPR 2017

1.  [Globally and Locally Consistent Image Completion](http://iizuka.cs.tsukuba.ac.jp/projects/completion/data/completion_sig2017.pdf)   
[MainPAGE](http://hi.cs.waseda.ac.jp/~iizuka/projects/completion/en/)  [Code](https://github.com/satoshiiizuka/siggraph2017_inpainting)    
SIGGRAPH 2017

1.  [High-Resolution Image Inpainting using Multi-Scale Neural Patch Synthesis](http://cn.arxiv.org/abs/1611.09969)   
[Code](https://github.com/leehomyc/Faster-High-Res-Neural-Inpainting)  
CVPR 2017  

1.  [Eye In-Painting with Exemplar Generative Adversarial Networks](http://cn.arxiv.org/abs/1711.03999)   
[Introduction](https://github.com/bdol/exemplar_gans) [Tensorflow code](https://github.com/zhangqianhui/Exemplar_GAN_Eye_Inpainting)   
CVPR 2018

1.  [Generative Image Inpainting with Contextual Attention](http://cn.arxiv.org/abs/1801.07892)   
[Project](http://jiahuiyu.com/deepfill)  [Demo](http://jiahuiyu.com/deepfill)[[YouTube]](https://youtu.be/xz1ZvcdhgQ0)  [Code](https://github.com/JiahuiYu/generative_inpainting)    
CVPR 2018

1.  [Free-Form Image Inpainting with Gated Convolution](http://cn.arxiv.org/abs/1806.03589)  
[Project](http://jiahuiyu.com/deepfill2)  [YouTube](https://youtu.be/uZkEi9Y2dj4)   

1.  [EdgeConnect: Generative Image Inpainting with Adversarial Edge Learning](http://cn.arxiv.org/abs/1901.00212)  
[Code](https://github.com/knazeri/edge-connect)  

1. [PEPSI++: Fast and Lightweight Network for Image Inpainting](http://cn.arxiv.org/abs/1905.09010)    
*2019-05-22* [paper](https://arxiv.org/abs/1905.09010)    


# 7 图像生成
## 7.1 人脸生成

## 7.2 场景生成

## 7.3 纹理生成

1.  [Precomputed real-time texture synthesis with markovian generative adversarial networks](http://cn.arxiv.org/abs/1604.04382)  
ECCV 2016 *2016-04-15* [paper](https://arxiv.org/abs/1604.04382) | [torch](https://github.com/chuanli11/MGANs)  


# 8 3D
## 8.1 人脸生成
1. [Semi-supervised Adversarial Learning to Generate Photorealistic Face Images of New Identities from 3D Morphable Model](http://cn.arxiv.org/abs/1804.03675)    
ECCV 2018 *2018-04-10* [Paper](https://arxiv.org/abs/1804.03675) | [Tensorflow](https://github.com/barisgecer/facegan)    
*`半监督` · `GAN` · `3D face`*   
对比了 DCGAN、BEGAN 和 GAN-CLS；    

1. [Generating 3D faces using Convolutional Mesh Autoencoders](http://cn.arxiv.org/abs/1807.10267)   
ECCV 2018 *2018-07-26* [Paper](https://arxiv.org/abs/1807.10267) | [Tensorflow](https://github.com/anuragranj/coma)  
自编码网络；    

# 9 跨模态
## 9.1 文本
1. [Text2Shape: Generating Shapes from Natural Language by Learning Joint Embeddings](http://cn.arxiv.org/abs/1803.08495)   
2018 [Paper](https://arxiv.org/abs/1803.08495) | [Tensorflow](https://github.com/kchen92/text2shape/)-Offical WGAN | [Project](http://text2shape.stanford.edu/)      
根据文本生成彩色三维图像，使用了 Wasserstein GAN；  

# 10 序列
1. [Unaligned Image-to-Sequence Transformation with Loop Consistency](http://cn.arxiv.org/abs/1910.04149)     
*2019-10-09* [paper](https://arxiv.org/abs/1910.04149)   
季节和人脸衰老的生成；     

-------------------  
 End
{:.warning}  


# 附录
## A 参考资料
[1]. dragonlong. Trending in 3D Vision[EB/OL]. <https://github.com/dragonlong/Trending-in-3D-Vision>. -/2019-03-28.    
[2]. timzhang641. 3D-Machine-Learning[EB/OL]. <https://github.com/timzhang642/3D-Machine-Learning>. -/2019-03-28.    
