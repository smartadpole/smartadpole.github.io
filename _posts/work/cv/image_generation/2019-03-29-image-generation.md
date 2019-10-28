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
<span id='head'></span>  

<!--more-->

# 1 综述

# 2 理论

# 3 图像修复
>修补图像中少量的缺失；    

`Image inpainting`    

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


1. [Image inpainting for irregular holes using partial convolutions](http://cn.arxiv.org/abs/1804.07723)    
ECCV 2018 *2018-04-20* [paper](https://arxiv.org/abs/1804.07723) | [pytorch](https://github.com/NVIDIA/partialconv)-official       


1.  [Free-Form Image Inpainting with Gated Convolution](http://cn.arxiv.org/abs/1806.03589)  
[Project](http://jiahuiyu.com/deepfill2)  [YouTube](https://youtu.be/uZkEi9Y2dj4)   

1.  [EdgeConnect: Generative Image Inpainting with Adversarial Edge Learning](http://cn.arxiv.org/abs/1901.00212)  
[Code](https://github.com/knazeri/edge-connect)  

1. [PEPSI++: Fast and Lightweight Network for Image Inpainting](http://cn.arxiv.org/abs/1905.09010)    
*2019-05-22* [paper](https://arxiv.org/abs/1905.09010)    

## 3.1 应用
### 3.1.1 [人脸](/cv/human/facial_inpaint/2019/05/14/foundation.html)

# 4 图像补全
>比图像修复更进一步，能从一个图像片段“推断”出外延的部分，补全成整个画面；是斯坦福大学 CS230 课程中 Mark Sabini 的期末作品；     

`Image outpainting`     

1. Globally and Locally consistent image completion     
*2017* [torch](https://github.com/satoshiiizuka/siggraph2017_inpainting)-official       

1. [Painting Outside the Box: Image Outpainting with GANs](http://cn.arxiv.org/abs/1808.08483)    
*2018-08-25* [paper](https://arxiv.org/abs/1808.08483) | [note](https://cs230.stanford.edu/projects_spring_2018/posters/8265861.pdf) | [keras](https://github.com/bendangnuksung/Image-OutPainting) | [blog](https://www.itcodemonkey.com/article/6793.html)    

1. [Multimodal Image Outpainting With Regularized Normalized Diversification](http://cn.arxiv.org/abs/1910.11481)   
*2019-10-25* [paper](https://arxiv.org/abs/1910.11481)    
提出新的正则化方法处理多样的输入；并使用特征金字塔提高生成图像的质量；     



# 5 风格迁移
## 5.1 美颜

## 5.2 艺术
1. [Multi-Source Domain Adaptation and Semi-Supervised Domain Adaptation with Focus on Visual Domain Adaptation Challenge 2019](https://arxiv.org/abs/1910.03548)     
VisDA-2019 *2019-10-08* [paper](https://arxiv.org/abs/1910.03548) | [pytorch](https://github.com/Panda-Peter/visda2019-multisource)-多源-official | [pytorch](https://github.com/Panda-Peter/visda2019-semisupervised)-半监督-official     

# 6 图像编辑
>替换掉图像中的某些物件或部位；    

## 6.1 [人脸编辑](/cv/human/facial_attribute_editing/2019/10/09/foundation.html)

## 6.2 去遮挡
`跟图像修复有啥区别`{:.warning}   
1.  [Robust LSTM-Autoencoders for Face De-Occlusion in the Wild](http://cn.arxiv.org/abs/1612.08534)   
*2016-11-25* [paper](https://arxiv.org/abs/1612.08534) | [caffe](https://github.com/zhaofang0627/face-deocc-lstm)        

# 7 图像生成
## 7.1 序列
## 7.2 跨模态
### 7.2.1 文本
1. [Text2Shape: Generating Shapes from Natural Language by Learning Joint Embeddings](http://cn.arxiv.org/abs/1803.08495)   
2018 [Paper](https://arxiv.org/abs/1803.08495) | [Tensorflow](https://github.com/kchen92/text2shape/)-Offical WGAN | [Project](http://text2shape.stanford.edu/)      
根据文本生成彩色三维图像，使用了 Wasserstein GAN；  


## 7.3 3D

## 7.4 应用
### 7.4.1 [人脸](/cv/human/face_generation/2019/10/09/foundation.html)
### 7.4.2 场景生成

### 7.4.3 纹理生成
1.  [Precomputed real-time texture synthesis with markovian generative adversarial networks](http://cn.arxiv.org/abs/1604.04382)  
ECCV 2016 *2016-04-15* [paper](https://arxiv.org/abs/1604.04382) | [torch](https://github.com/chuanli11/MGANs)  


-------------------  
[End](#head)
{:.warning}  


# 附录
## A 参考资料
[1]. dragonlong. Trending in 3D Vision[EB/OL]. <https://github.com/dragonlong/Trending-in-3D-Vision>. -/2019-03-28.    
[2]. timzhang641. 3D-Machine-Learning[EB/OL]. <https://github.com/timzhang642/3D-Machine-Learning>. -/2019-03-28.    
