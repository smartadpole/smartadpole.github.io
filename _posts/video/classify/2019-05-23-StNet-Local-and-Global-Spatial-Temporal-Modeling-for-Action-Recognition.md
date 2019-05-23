---
layout: article
title:  "「论文解读」 StNet: Local and Global Spatial-Temporal Modeling for Action Recognition"
date:   2019-05-23 17:26:40 +0800
key: StNet-20190523
aside:
  toc: true
category: [video, classification, paper_reading]
---
<span id='head'></span>   

>AAAI 2019  
论文发表时间：2018-11-05     
作者：何栋梁，Zhichao Zhou，Chuang Gan，Fu Li，Xiao Liu，Yandong Li，Limin Wang，Shilei Wen            
机构：百度，MIT-IBM Watson AI Lab，University of Central Florida，南京大学   
论文地址：<https://arxiv.org/abs/1811.01549>  
代码：Pytorch <https://github.com/hyperfraise/Pytorch-StNet>   

<center class="half">
  <img src="/assets/images/video/claaification/classic/StNet-Local-and-Global-Spatial-Temporal-Modeling-for-AR/activaton_maps.png" height="400"/>&emsp;<br>图1：激活地图
</center>

# 1 一句话总结文章
针对视频特征提取提出了 TXB 来获取时域特征；    

# 2 方案
前导知识：`CNN`，`深度学习基本知识`     

<center class="half">
  <img src="/assets/images/video/claaification/classic/StNet-Local-and-Global-Spatial-Temporal-Modeling-for-AR/StNet.png" height="400"/>&emsp;<br>图2：StNet 示意图
</center>


# 3 损失函数
$$
\begin{align}   
 \label{loss}\\
\end{align}
$$

# 4 实验
## 4.1 数据集


## 4.2 实验结果



# 5 思考


# 6 总结
对于视频特征提取，局部信息用二维卷积提取；然后在这些特征上应用时间 Xception 块，提取全局特征；模型小，效果好；       

------------------
[End](#head)   
{:.warning}  
