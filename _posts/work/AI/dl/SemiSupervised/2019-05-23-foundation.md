---
layout: article
title:  "「DL」 半监督学习资源汇总"
date:   2019-05-23 16:08:40 +0800
key: semi-supervised-foundation-20190523
aside:
  toc: true
category: [AI, DL, semi_supervised]
tags: 资源
---
<span id='head'></span>
>训练数据中只有一小部分具有标签，根据训练数据完成训练；这种情况常常是因为数据标注困难，比如医疗诊断；    

`semi supervised learning`    

<!--more-->

# 1 综述

# 2 理论

# 3 分类
1. [Data-Efficient Image Recognition with Contrastive Predictive Coding](http://cn.arxiv.org/abs/1905.09272)   
*2019-05-22* [paper](https://arxiv.org/abs/1905.09272)   

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
>*看起来像是一个不聪明又很努力的人写的文章；*    

-------------------  
[End](#head)
{:.warning}  
# 附录
## A 数据集

## B 资源

## C 参考资料
