---
layout: article
title:  "「CV」 图像处理问答"
date:   2019-04-11 11:35:40 +0800
key: image-process-question
aside:
  toc: true
tags: Q&A
category: [AI, image_process]
sidebar:
  nav: INTERVIEW
---
<span id='head'></span>  


<!--more-->


|  |  |  |  |
| --- | --- | --- | --- |
| [HOG](#hog) |  |  |  |
|  |  |  |  |
|  |  |  |  |

<span id="hog">    </span>  

**HOG算法原理描述**
{:.warning}
**梯度直方图（Histogram of Oriented Gradient, HOG）**特征：先将原图划分成多个区域，然后球每个区域的梯度，再求直方图，构成图像的特征；。在深度学习取得成功之前；是传统图像中用来进行物体检测的特征描述子，在 DL 之前，常结合 SVM 分类器用来做目标检测；在行人检测中获得了较大的成功；    

**原理**：HOG 认为物体的局部形状可以被边缘的分布所描述；因此对原图等分，然后求子区域的梯度直方图，最终把所有区域的直方图连接在一起；为了提升对照射/阴影的不变性，可以对大的区域取梯度均值，用来给内部的子区域做归一化；     
**优势**：与其他描述子相比，HOG拥有几何和光学转化不变性（除非物体方向改变）；因此HOG描述子尤其适合人的检测；    

**过程**：     
1. 灰度化   
2. 划分成小 cells    
3. 计算每个 cell 的梯度     
4. 统计每个 cell 的梯度直方图，就是 cell 的描述子      

-------------------  
[End](#head)
{:.warning}  

# 附录
## A 资源
