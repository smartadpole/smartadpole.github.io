---
layout: article
title:  "「DL」 无监督学习资源汇总"
date:   2019-05-23 16:08:40 +0800
key: unsupervised-foundation-20190523
aside:
  toc: true
category: [AI, DL, unsupervised]
tags: 资源
---
<span id='head'></span>
>训练数据不包含标注信息的情况下完成目标任务；    

`unsupervised learning`

<!--more-->

# 1 综述

# 2 理论

# 3 生成式

# 4 判别式
## 4.1 对比学习
1. [Data-Efficient Image Recognition with Contrastive Predictive Coding](http://cn.arxiv.org/abs/1905.09272)   
*2019-05-22* [paper](https://arxiv.org/abs/1905.09272)   

1. [Learning representations by maximizing mutual information across views](http://cn.arxiv.org/abs/1906.00910)     
*2019-06-03* [paper](https://arxiv.org/abs/1906.00910) | [pytorch](https://github.com/Philip-Bachman/amdim-public)-official | [blog](https://www.zhihu.com/question/355779873/answer/896850345)       
$\bullet \bullet$ - AMDIM     
判别式对比学习，使用了特殊的网络结构，并且改动了数据增广；   

<span id="SimCLR"> </span>
1. [A Simple Framework for Contrastive Learning of Visual Representations](http://cn.arxiv.org/abs/2002.05709)    
AAAI 2020 *2020-02-13* [paper](https://arxiv.org/abs/2002.05709) | [blog](https://m.thepaper.cn/newsDetail_forward_6019161)    
$\bullet \bullet$ SimCLR    
**定位**：探索基于对比学习的判别式半监督网络，包括数据增广，特征提取和相似度计算；    
**总结**：文章收录了较为全面的半监督学习相关信息，并对各环节做了实验，最终给除了效果最好的组合——SimCLR，达到 SOTA；   
**核心**：各环节做了丰富的对比实验，对工程有很大指导作用；  
>
- 各环节只给出实验结果，缺乏理论分析；    
- 只给了实验结果，未给出实验细节；   
- 文章的核心“对比学习”就是孪生网络，相关任务有图片检索（人脸验证，REID 等）；不知道为什么非要换个名字；   
- 对比学习用于无监督分类准确度测试的时候，也没给出测试细节——怎么实现的半监督学习；    
- 结论说 SimCLR*（基于 4×ResNet）*在微调后达到监督学习*（基于 ResNet）*的水平是噱头，因为 backbone 不一样；   
>
>*看起来像是很努力但不聪明又的人写的文章；*    

# 5 其他
1. [Deep Clustering for Unsupervised Learning of Visual Features](http://cn.arxiv.org/abs/1807.05520)   
ECCV 2018 *2018-07-15* [paper](https://arxiv.org/abs/1807.05520) | [解读](/ai/cv/unsupervised/paper_reading/2019/03/04/Deep-Clustering-for-Unsupervised-Learning-of-Visual-Features.html)    


-------------------  
[End](#head)
{:.warning}  
