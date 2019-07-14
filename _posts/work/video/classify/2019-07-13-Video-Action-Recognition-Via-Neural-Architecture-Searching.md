---
layout: article
title:  "「论文解读」 Video Action Recognition Via Neural Architecture Searching"
date:   2019-07-13 17:06:40 +0800
key: VAR-NASNet-20190713
aside:
  toc: true
category: [video, video_classification, paper_reading]
---
<span id='head'></span>   
**视频动作识别**:在工业和学术界都是热点，因为这对于行为分析和情感计算等应用的基础；虽然目前该领域的数据集和神经网络都有着很大进步，但是这需要耗费大量的时间和专家；     
视频任务对于时间和空间的需求决定了网络结构复杂和较高的计算代价；    
**神经网络自动搜索**:Neural Architecture Search（NAS），是通过机器自动生成神经网络，通常效果都比人工设计的好；他在分类和分割等领域都有着很好的应用；    

>
论文发表时间：2019-07-10 ICIP 2019      
作者：Wei Peng, Xiaopeng Hong, Guoying Zhao        
单位：奥卢大学，西安交大            
论文地址：<https://arxiv.org/abs/1907.04632>   

<!--more-->   

# 1 一句话总结文章
用新的方法对视频进行时序采样；并且通过 AutoML 引入了伪 3D 操作，网络参数量是同水平网络的 1%；    

# 2 方案
前导知识：`CNN`，`深度学习基本知识`，`视频分类`     

>之前，神经网络搜索的输入都是低维数据（图像，文本），还没有高维数据（视频）相关的研究；     


<center class="half">
  <img src="/assets/images/video/claaification/automl/Video-Action-Recognition-Via-Neural-Architecture-Searching/net.png" />&emsp;<br>图1：网络结构
</center>

# 3 损失函数


# 4 实验
## 4.1 数据集


## 4.2 实验结果



# 5 思考


# 6 总结


------------------
[End](#head)   
{:.warning}  
