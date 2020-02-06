---
layout: article
title:  "「DL」 元学习资源汇总"
date:   2019-05-23 12:00:40 +0800
key: meta-learning-foundation-20190523
aside:
  toc: true
category: [AI, DL, meta_learning]
tags: 资源
---
<span id='head'></span>  
>识别从未见过的数据类别，使模型具有知识迁移的能力；        

`zero shot learning`     

<!--more-->

# 1 综述
1. [Learning to Detect Unseen Object Class by Between-Class Attribute Transfer](https://pdfs.semanticscholar.org/0890/89c2051bb4a786dfd79276f5c7a2c3672244.pdf)           
CVPR 2009 *2009* [paper](https://pdfs.semanticscholar.org/0890/89c2051bb4a786dfd79276f5c7a2c3672244.pdf)           
最早提出零样本学习；    
$\bullet \bullet$     

1. [Zero Shot Learning with Semantic Output Codes](https://pdfs.semanticscholar.org/0f69/11bc1e6abee8bbf9dd3f8d54d40466429da7.pdf?_ga=2.4060537.835547854.1580895914-504939339.1571502740)     
NIPS 2009 *2009* [paper](https://pdfs.semanticscholar.org/0f69/11bc1e6abee8bbf9dd3f8d54d40466429da7.pdf?_ga=2.4060537.835547854.1580895914-504939339.1571502740)    
$\bullet \bullet$     

# 2 理论
1. [Learning from one example through shared densities on transforms](https://people.cs.umass.edu/~elm/papers/Miller_congealing.pdf)           
*2000* [paper](https://people.cs.umass.edu/~elm/papers/Miller_congealing.pdf)          
$\bullet \bullet$     
贝叶斯单次学习算法的方法     

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
[paper](http://metalearning.ml/2018/papers/metalearn2018_paper23.pdf)       | [openreview](https://openreview.net/forum?id=SyxMWh09KX)    

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

## 4.2 其他
1. [One-shot learning of object categories](http://vision.stanford.edu/documents/Fei-FeiFergusPerona2006.pdf)           
*2006* [paper](http://vision.stanford.edu/documents/Fei-FeiFergusPerona2006.pdf)           

# 5 零样本学习
1. [Zero-data learning of new tasks](https://www.aaai.org/Papers/AAAI/2008/AAAI08-103.pdf)          
AAAI 2008 *2008* [paper](https://www.aaai.org/Papers/AAAI/2008/AAAI08-103.pdf)          

1. [Zero-shot learning through cross-modal transfer](http://cn.arxiv.org/abs/1301.3666)    
NIPS 2013 *2013-01-16* [paper](https://arxiv.org/abs/1301.3666) | [matlab](https://github.com/mganjoo/zslearning)    


1. [Zero-Shot Learning - A Comprehensive Evaluation of the Good, the Bad and the Ugly](http://cn.arxiv.org/abs/1707.00600)     
*2017-07-03* [paper](https://arxiv.org/abs/1707.00600)     

1. [Discriminative Learning of Latent Features for Zero-Shot Recognition](http://cn.arxiv.org/abs/1803.06731)   
*2019-06-25* [paper](https://arxiv.org/abs/1803.06731)   

1. [Transductive Unbiased Embedding for Zero-Shot Learning](http://cn.arxiv.org/abs/1803.11320)   
CVPR 2018 *2018-03-30* 阿里 [paper](https://arxiv.org/abs/1803.11320)     

1. [Visual Space Optimization for Zero-shot Learning](http://cn.arxiv.org/abs/1907.00330)   
*2019-06-30* [paper](https://arxiv.org/abs/1907.00330)     
>设计了一个新的 loss；   


1. [Generalized Zero- and Few-Shot Learning via Aligned Variational Autoencoders](http://cn.arxiv.org/abs/1812.01784)  
CVPR 2019 *2019* [paper](https://arxiv.org/abs/1812.01784) | [pytorch](https://github.com/edgarschnfld/CADA-VAE-PyTorch)    
$\bullet \bullet$ - CADA-VAE     

1. [Generative Dual Adversarial Network for Generalized Zero-shot Learning](http://cn.arxiv.org/abs/1811.04857)  
CVPR 2019 *2019* [paper](https://arxiv.org/abs/1811.04857) | [pytorch](https://github.com/stevehuanghe/GDAN)     
$\bullet \bullet$ - GDAN     

1. [Hybrid-Attention based Decoupled Metric Learning for Zero-Shot Image Retrieval](http://www.bhchen.cn/paper/cvpr19.pdf)     
CVPR 2019 *2019* [paper](http://www.bhchen.cn/paper/cvpr19.pdf) | [caffe](https://github.com/chenbinghui1/Hybrid-Attention-based-Decoupled-Metric-Learning)    
$\bullet \bullet$ - DeML      

1. [Generalized Zero-Shot Recognition based on Visually Semantic Embedding](http://cn.arxiv.org/abs/1811.07993)  
CVPR 2019 *2019* [paper](https://arxiv.org/abs/1811.07993)     
Gzsl-VSE     

1. [Leveraging the Invariant Side of Generative Zero-Shot Learning](htts://cn.arxiv.org/abs/1904.04092)  
CVPR 2019 *2019* [paper](https://arxiv.org/abs/1904.04092) | [pytorch](https://github.com/lijin118/LisGAN)    
$\bullet \bullet$ - LisGAN     

1. [Rethinking Knowledge Graph Propagation for Zero-Shot Learning](http://cn.arxiv.org/abs/1805.11724)  
CVPR 2019 *2019* [paper](https://arxiv.org/abs/1805.11724) | [pytorch](https://github.com/cyvius96/DGP)    
$\bullet \bullet$ - DGP    

1. [Domain-Aware Generalized Zero-Shot Learning](http://cn.arxiv.org/abs/1812.09903)  
CVPR 2019 *2019* [paper](https://arxiv.org/abs/1812.09903)      
DAZL     

1. [Progressive Ensemble Networks for Zero-Shot Recognition](http://cn.arxiv.org/abs/1805.07473)  
CVPR 2019 *2019* [paper](https://arxiv.org/abs/1805.07473)      
PrEN    

1. [On Zero-Shot Learning of generic objects](http://cn.arxiv.org/abs/1904.04957)  
CVPR 2019 *2019* [paper](https://arxiv.org/abs/1904.04957) | [pytorch](https://github.com/TristHas/GOZ)-official     
$\bullet \bullet$     

1. [Semantically Aligned Bias Reducing Zero Shot Learning](http://cn.arxiv.org/abs/1904.07659)  
CVPR 2019 *2019* [paper](https://arxiv.org/abs/1904.07659)     
SABR-T      

1. [Attentive Region Embedding Network for Zero-shot Learning](http://openaccess.thecvf.com/content_CVPR_2019/papers/Xie_Attentive_Region_Embedding_Network_for_Zero-Shot_Learning_CVPR_2019_paper.pdf)  
CVPR 2019 *2019* [paper](http://openaccess.thecvf.com/content_CVPR_2019/papers/Xie_Attentive_Region_Embedding_Network_for_Zero-Shot_Learning_CVPR_2019_paper.pdf) |  [pytorch](https://github.com/gsx0/Attentive-Region-Embedding-Network-for-Zero-shot-Learning)     
$\bullet \bullet$ - AREN      

1. [Marginalized Latent Semantic Encoder for Zero-Shot Learning](http://openaccess.thecvf.com/content_CVPR_2019/papers/Ding_Marginalized_Latent_Semantic_Encoder_for_Zero-Shot_Learning_CVPR_2019_paper.pdf)  
CVPR 2019 *2019* [paper](http://openaccess.thecvf.com/content_CVPR_2019/papers/Ding_Marginalized_Latent_Semantic_Encoder_for_Zero-Shot_Learning_CVPR_2019_paper.pdf)    

1. [Compressing Unknown Classes with Product Quantizer for Efficient Zero-Shot Classification](http://openaccess.thecvf.com/content_CVPR_2019/papers/Li_Compressing_Unknown_Images_With_Product_Quantizer_for_Efficient_Zero-Shot_Classification_CVPR_2019_paper.pdf)   
CVPR 2019 *2019* [paper](http://openaccess.thecvf.com/content_CVPR_2019/papers/Li_Compressing_Unknown_Images_With_Product_Quantizer_for_Efficient_Zero-Shot_Classification_CVPR_2019_paper.pdf)    
PQZSL    

1. [Gradient Matching Generative Networks for Zero-Shot Learning](http://openaccess.thecvf.com/content_CVPR_2019/papers/Sariyildiz_Gradient_Matching_Generative_Networks_for_Zero-Shot_Learning_CVPR_2019_paper.pdf)  
CVPR 2019 *2019* [paper](http://openaccess.thecvf.com/content_CVPR_2019/papers/Sariyildiz_Gradient_Matching_Generative_Networks_for_Zero-Shot_Learning_CVPR_2019_paper.pdf)    

1. [Hierarchical Disentanglement of Discriminative Latent Features for Zero-shot Learning](http://openaccess.thecvf.com/content_CVPR_2019/papers/Tong_Hierarchical_Disentanglement_of_Discriminative_Latent_Features_for_Zero-Shot_Learning_CVPR_2019_paper.pdf)        
CVPR 2019 *2019* [paper](http://openaccess.thecvf.com/content_CVPR_2019/papers/Tong_Hierarchical_Disentanglement_of_Discriminative_Latent_Features_for_Zero-Shot_Learning_CVPR_2019_paper.pdf)    

1. [Creativity Inspired Zero-Shot Learning](http://openaccess.thecvf.com/content_ICCV_2019/papers/Elhoseiny_Creativity_Inspired_Zero-Shot_Learning_ICCV_2019_paper.pdf)        
ICCV 2019 *2019* [paper](http://openaccess.thecvf.com/content_ICCV_2019/papers/Elhoseiny_Creativity_Inspired_Zero-Shot_Learning_ICCV_2019_paper.pdf)       [pytorch](https://github.com/mhelhoseiny/CIZSL)    
$\bullet \bullet$ - CIZSL     

1. [Attribute Attention for Semantic Disambiguation in Zero-Shot Learning](http://openaccess.thecvf.com/content_ICCV_2019/papers/Liu_Attribute_Attention_for_Semantic_Disambiguation_in_Zero-Shot_Learning_ICCV_2019_paper.pdf)        
ICCV 2019 *2019* [paper](http://openaccess.thecvf.com/content_ICCV_2019/papers/Liu_Attribute_Attention_for_Semantic_Disambiguation_in_Zero-Shot_Learning_ICCV_2019_paper.pdf) | [pytorch](https://github.com/ZJULearning/AttentionZSL)     
$\bullet \bullet$  - LFGAA+SA      

1. [Transferable Contrastive Network for Generalized Zero-Shot Learning](http://openaccess.thecvf.com/content_ICCV_2019/papers/Jiang_Transferable_Contrastive_Network_for_Generalized_Zero-Shot_Learning_ICCV_2019_paper.pdf)        
ICCV 2019 *2019* [paper](http://openaccess.thecvf.com/content_ICCV_2019/papers/Jiang_Transferable_Contrastive_Network_for_Generalized_Zero-Shot_Learning_ICCV_2019_paper.pdf)            
TCN      

1. [Rethinking Zero-Shot Learning: A Conditional Visual Classification Perspective](http://openaccess.thecvf.com/content_ICCV_2019/papers/Li_Rethinking_Zero-Shot_Learning_A_Conditional_Visual_Classification_Perspective_ICCV_2019_paper.pdf)        
ICCV 2019 *2019* [paper](http://openaccess.thecvf.com/content_ICCV_2019/papers/Li_Rethinking_Zero-Shot_Learning_A_Conditional_Visual_Classification_Perspective_ICCV_2019_paper.pdf)          
GXE     

1. [Learning Feature-to-Feature Translator by Alternating Back-Propagation for Generative Zero-Shot Learning](http://openaccess.thecvf.com/content_ICCV_2019/papers/Zhu_Learning_Feature-to-Feature_Translator_by_Alternating_Back-Propagation_for_Generative_Zero-Shot_Learning_ICCV_2019_paper.pdf)        
ICCV 2019 *2019* [paper](http://openaccess.thecvf.com/content_ICCV_2019/papers/Zhu_Learning_Feature-to-Feature_Translator_by_Alternating_Back-Propagation_for_Generative_Zero-Shot_Learning_ICCV_2019_paper.pdf) | [pytorch](https://github.com/EthanZhu90/ZSL_ABP)       
$\bullet \bullet$     


1. [Modeling Inter and Intra-Class Relations in the Triplet Loss for Zero-Shot Learning](http://openaccess.thecvf.com/content_ICCV_2019/papers/Le_Cacheux_Modeling_Inter_and_Intra-Class_Relations_in_the_Triplet_Loss_for_ICCV_2019_paper.pdf)        
ICCV 2019 *2019* [paper](http://openaccess.thecvf.com/content_ICCV_2019/papers/Le_Cacheux_Modeling_Inter_and_Intra-Class_Relations_in_the_Triplet_Loss_for_ICCV_2019_paper.pdf)    

1. [Dual Adversarial Semantics-Consistent Network for Generalized Zero-Shot Learning](http://cn.arxiv.org/abs/1907.05570)    
NIPS 2019 *2019-07-12* [paper](https://arxiv.org/abs/1907.05570)    
双生 GAN；   

1. [Transductive Zero-Shot Learning with Visual Structure Constraint](http://papers.nips.cc/paper/9188-transductive-zero-shot-learning-with-visual-structure-constraint.pdf)          
NIPS 2019 *2019* [paper](http://papers.nips.cc/paper/9188-transductive-zero-shot-learning-with-visual-structure-constraint.pdf) | [pytorch](https://github.com/raywzy/VSC)-official    
$\bullet \bullet$ - VSC     

1. [Zero-shot Learning via Simultaneous Generating and Learning](http://papers.nips.cc/paper/8300-zero-shot-learning-via-simultaneous-generating-and-learning.pdf)          
NIPS 2019 *2019* [paper](http://papers.nips.cc/paper/8300-zero-shot-learning-via-simultaneous-generating-and-learning.pdf)                

1. [Semantic-Guided Multi-Attention Localization for Zero-Shot Learning](http://papers.nips.cc/paper/9632-semantic-guided-multi-attention-localization-for-zero-shot-learning.pdf)          
NIPS 2019 *2019* [paper](http://papers.nips.cc/paper/9632-semantic-guided-multi-attention-localization-for-zero-shot-learning.pdf)    
SGMA

# 6 元学习

## 6.1 基于度量的


## 6.2 基于模型的
1. [Model-Agnostic Meta-Learning for Fast Adaptation of Deep Networks](http://cn.arxiv.org/abs/1703.03400)   
ICML 2017 *2017-03-09* 伯克利 [paper](https://arxiv.org/abs/1703.03400) | [tensorflow](https://github.com/cbfinn/maml)-offical | [project](https://sites.google.com/view/maml)-offical | [blog](https://bair.berkeley.edu/blog/2017/07/18/learning-to-learn/)-offical       


## 6.3 基于优化的

## 6.4 其他
1. [Amortized Bayesian Meta-Learning](https://openreview.net/pdf?id=rkgpy3C5tX)   
ICLR 2019 [paper](https://openreview.net/pdf?id=rkgpy3C5tX) | [openreview](https://openreview.net/forum?id=rkgpy3C5tX)     

1. [Learning to Learn with Conditional Class Dependencies](https://openreview.net/pdf?id=BJfOXnActQ)   
ICLR 2019 [paper](https://openreview.net/pdf?id=BJfOXnActQ) | [openreview](https://openreview.net/forum?id=BJfOXnActQ)    


# 7 应用
## 7.1 分类

## 7.2 检测
1. [Zero-Shot Object Detection: Learning to Simultaneously Recognize and Localize Novel Concepts](http://cn.arxiv.org/abs/1803.06049)     
ACCV 2018 *2018-03-16* [paper](https://arxiv.org/abs/1803.06049)     

## 7.3 分割

## 7.4 GAN

## 7.5 强化学习
1. [Sample-efficient policy learning in multi-agent Reinforcement Learning via meta-learning](http://cn.arxiv.org/abs/1805.12375)   
ICML 2019 *2018-05-31* [paper](https://arxiv.org/abs/1805.12375) | [openreview](https://openreview.net/forum?id=r1fiFs09YX)    



-------------------  
[End](#head)
{:.warning}  

# 附录
## A 推荐资料
1. [paper-with-code/元学习](https://paperswithcode.com/task/meta-learning/codeless?page=9)    
1. [paper-with-code/少样本学习](https://paperswithcode.com/task/few-shot-image-classification)    
1. [awesome-zero-shot-learning](https://github.com/chichilicious/awesome-zero-shot-learning#Papers)    
