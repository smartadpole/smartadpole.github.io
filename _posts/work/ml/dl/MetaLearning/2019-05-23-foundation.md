---
layout: article
title:  "「DL」 元学习资源汇总"
date:   2019-05-23 12:00:40 +0800
key: meta-learning-foundation-20190523
aside:
  toc: true
category: [DL, meta_learning]
tags: 资源
---
<span id='head'></span>  

<!--more-->

# 1 综述

# 2 理论
1. [A Neural-Symbolic Architecture for Inverse Graphics Improved by Lifelong Meta-Learning](http://cn.arxiv.org/abs/1905.08910)   
*2019-05-22* [paper](https://arxiv.org/abs/1905.08910)    

1. [Embedded Meta-Learning: Toward more flexible deep-learning models](http://cn.arxiv.org/abs/1905.09950)   
*2019-05-23* [paper](https://arxiv.org/abs/1905.09950)   


# 3 小样本学习
## 3.1 基于度量的
1. [Prototypical Networks for Few-shot Learning](http://cn.arxiv.org/abs/1703.05175)   
NIPS 2017 *2017-03-15* [paper](https://arxiv.org/abs/1703.05175) | [openreview](https://openreview.net/forum?id=B1-Hhnslg)       

## 3.2 基于模型的
1. [Task-Agnostic Meta-Learning for Few-shotLearning](http://cn.arxiv.org/abs/1805.07722)    
*2018-05-20* [paper](https://arxiv.org/abs/1805.07722) | [reddit](https://www.reddit.com/r/MachineLearning/comments/8m70um/r_taskagnostic_metalearning_for_fewshot_learning/)       

## 3.3 基于优化的
1. [Optimization as a model for few-shot learning](https://openreview.net/pdf?id=rJY0-Kcll)    
ICLR 2017 [paper](https://openreview.net/pdf?id=rJY0-Kcll) | [openreview](https://openreview.net/forum?id=rJY0-Kcll) | [iclr_notes](https://pdfs.semanticscholar.org/14e2/57bd91af4366d79effac149f03b95f1eaf74.pdf)     

1. [Learning to Compare: Relation Network for Few-Shot Learning](http://cn.arxiv.org/abs/1711.06025)   
CVPR 2018 *2017-11-16* [paper](https://arxiv.org/abs/1711.06025) | [pytorch](https://github.com/floodsung/LearningToCompare_FSL)    
文章探讨了这个为什么会有论文中的 idea；提出了一种基于度量（metric-based）的方法，只不过不是人为度量，而是让网络去度量；    

## 3.4 其他
1. [Attentive Task-Agnostic Meta-Learning for Few-Shot Text Classification](http://metalearning.ml/2018/papers/metalearn2018_paper23.pdf)   
[paper](http://metalearning.ml/2018/papers/metalearn2018_paper23.pdf) | [openreview](https://openreview.net/forum?id=SyxMWh09KX)    

1. [Learning Classifier Synthesis for Generalized Few-Shot Learning](http://cn.arxiv.org/abs/1906.02944)   
*2019-06-07* [paper](https://arxiv.org/abs/1906.02944)    

1. [Meta-Learning with Domain Adaptation for Few-Shot Learning under Domain Shift](https://openreview.net/pdf?id=ByGOuo0cYm)    
ICLR 2019 [paper](https://openreview.net/pdf?id=ByGOuo0cYm) | [openreview](https://openreview.net/forum?id=ByGOuo0cYm)   

1. [Learning to Propagate Labels: Transductive Propagation Network for Few-shot Learning](http://cn.arxiv.org/abs/1805.10002)   
*2018-05-25* [paper](https://arxiv.org/abs/1805.10002) | [tensorflow](https://github.com/csyanbin/TPN)-offical | [pytorch](https://github.com/csyanbin/TPN-pytorch)-offical | [openreview](https://openreview.net/forum?id=SyVuRiC5K7)          

1. [Adaptive Posterior Learning: few-shot learning with a surprise-based memory module](http://cn.arxiv.org/abs/1902.02527)    
ICLR 2019 *2019-02-07* [paper](https://arxiv.org/abs/1902.02527) | [openreview](https://openreview.net/forum?id=ByeSdsC9Km) [pytorch](https://github.com/cogentlabs/apl)      


# 4 单样本学习
## 4.1 基于度量的
1. [Matching Networks for One Shot Learning](http://cn.arxiv.org/abs/1606.04080)   
NIPS 2016 *2016-06-13* [paper](https://arxiv.org/abs/1606.04080)    

## 4.2 基于模型的


## 4.3 基于优化的


# 5 零样本学习
1. [Discriminative Learning of Latent Features for Zero-Shot Recognition](http://cn.arxiv.org/abs/1803.06731)   
*2019-06-25* [paper](https://arxiv.org/abs/1803.06731)   

1. [Transductive Unbiased Embedding for Zero-Shot Learning](http://cn.arxiv.org/abs/1803.11320)   
CVPR 2018 *2018-03-30* 阿里 [paper](https://arxiv.org/abs/1803.11320)

1. [Visual Space Optimization for Zero-shot Learning](http://cn.arxiv.org/abs/1907.00330)   
*2019-06-30* [paper](https://arxiv.org/abs/1907.00330)    
>设计了一个新的 loss；   


# 6 强化学习
1. [Sample-efficient policy learning in multi-agent Reinforcement Learning via meta-learning](http://cn.arxiv.org/abs/1805.12375)   
ICML 2019 *2018-05-31* [paper](https://arxiv.org/abs/1805.12375) | [openreview](https://openreview.net/forum?id=r1fiFs09YX)    



# 7 元学习

## 7.1 基于度量的


## 7.2 基于模型的
1. [Model-Agnostic Meta-Learning for Fast Adaptation of Deep Networks](http://cn.arxiv.org/abs/1703.03400)   
ICML 2017 *2017-03-09* 伯克利 [paper](https://arxiv.org/abs/1703.03400) | [tensorflow](https://github.com/cbfinn/maml)-offical | [project](https://sites.google.com/view/maml)-offical | [blog](https://bair.berkeley.edu/blog/2017/07/18/learning-to-learn/)-offical       


## 7.3 基于优化的

## 7.4 其他
1. [Amortized Bayesian Meta-Learning](https://openreview.net/pdf?id=rkgpy3C5tX)   
ICLR 2019 [paper](https://openreview.net/pdf?id=rkgpy3C5tX) | [openreview](https://openreview.net/forum?id=rkgpy3C5tX)     

1. [Learning to Learn with Conditional Class Dependencies](https://openreview.net/pdf?id=BJfOXnActQ)   
ICLR 2019 [paper](https://openreview.net/pdf?id=BJfOXnActQ) | [openreview](https://openreview.net/forum?id=BJfOXnActQ)    


-------------------  
[End](#head)
{:.warning}  

# 附录
## A 推荐资料
1. [paper-with-code/元学习](https://paperswithcode.com/task/meta-learning/codeless?page=9)    
1. [paper-with-code/少样本学习](https://paperswithcode.com/task/few-shot-image-classification)    
