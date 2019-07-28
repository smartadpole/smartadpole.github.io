---
layout: article
title:  "「CV」 文本分析资源汇总"
date:   2019-07-27 14:21:40 +0800
key: ocr-foundation-20190727
aside:
  toc: true
category: [CV, ocr]
tags: 资源
---
<span id='head'></span>
>光学字符识别；   

<!--more-->

# 1 综述
1. [Feature extraction methods for character recognition-A survey](http://www.ee.bgu.ac.il/~dinstein/stip2002/FeatureExtractionReviewTrierJainTaxt95.pdf)   
*1995-07-19* [paper](http://www.ee.bgu.ac.il/~dinstein/stip2002/FeatureExtractionReviewTrierJainTaxt95.pdf)   

1. [A Survey Paper on Scene Text Detection Methods](https://pdfs.semanticscholar.org/f9e8/d104b257c42d2ebc2386c8c1ca0d68e8273a.pdf)   
*2012* [paper](https://pdfs.semanticscholar.org/f9e8/d104b257c42d2ebc2386c8c1ca0d68e8273a.pdf)   

1. [An Overview of Feature Extraction Techniques in OCR for Indian Scripts Focused on Offline Handwriting](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.415.3676&rep=rep1&type=pdf)   
*2013* [paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.415.3676&rep=rep1&type=pdf)   


1. [Scene Text Detection and Recognition: Recent Advances and Future Trends](http://www.vlrlab.net/admin/uploads/avatars/FCS_TextSurvey_2015.pdf)   
*2014* [paper](http://www.vlrlab.net/admin/uploads/avatars/FCS_TextSurvey_2015.pdf)   

1. [A Survey on Scene Text Detection and Text Recognition](https://www.ijarcce.com/upload/2016/march-16/IJARCCE%20208.pdf)   
*2016-03* [paper](https://www.ijarcce.com/upload/2016/march-16/IJARCCE%20208.pdf)   


1. [Text Detection and Recognition in Images: A Survey](http://cn.arxiv.org/abs/1803.07278)    
*2018-03-20* [paper](https://arxiv.org/abs/1803.07278)      
学生写的，还不完整；   

1. [Scene Text Detection and Recognition: The Deep Learning Era](http://cn.arxiv.org/abs/1811.04256)    
*2018-11-10* [paper](https://arxiv.org/abs/1811.04256) | [github](https://github.com/Jyouhou/SceneTextPapers)       


# 2 理论

# 3 其他
1. [ICDAR2019 Robust Reading Challenge on Multi-lingual Scene Text Detection and Recognition -- RRC-MLT-2019](http://cn.arxiv.org/abs/1907.00945)   
ICDAR 2019*2019-07-01* [paper](https://arxiv.org/abs/1907.00945) | [competition](https://rrc.cvc.uab.es/?ch=15)      

1. [Total-Text: A Comprehensive Dataset for Scene Text Detection and Recognition](http://cn.arxiv.org/abs/1710.10400)    
ICDAR 2017 *2017-10-28* [paper](https://arxiv.org/abs/1710.10400) | [code4downloads](https://github.com/cs-chan/Total-Text-Dataset)     


# 4 文本检测
EAST/CTPN/SegLink/PixelLink/TextBoxes/TextBoxes++/TextSnake/MSR/     

## 4.1 综述

## 4.2 理论

## 4.3 其他


# 5 文本行检测
## 5.1 综述

## 5.2 理论

## 5.3 其他



# 6 文字识别
CRNN或Seq2Seq    

## 6.1 综述

## 6.2 理论

## 6.3 常规文本
### 6.3.1 CNN


### 6.3.2 CRNN

### 6.3.3 Seq2Seq

## 6.4 不规则文本
### 6.4.1 CNN
1. [Scene Text Recognition from Two-Dimensional Perspective](http://cn.arxiv.org/abs/1809.06508)   
AAAI 2019 *2018-09-18* 白翔组 [paper](https://arxiv.org/abs/1809.06508)   
检测时加入分割，定位到每个字符的位置，然后对单个字符进行分类，以分类代替是识别；同时使用了可变形卷积，以提取文字区域不同形状的特征；   


### 6.4.2 CRNN

### 6.4.3 Seq2Seq

### 6.4.4 其他
1. [Robust Scene Text Recognition with Automatic Rectification](http://cn.arxiv.org/abs/1603.03915)    
CVPR 2016 *2016-03-12* [paper](https://arxiv.org/abs/1603.03915)    
使用 STN 空间仿射网络对不规则文本进行仿射变换，修正后再送入识别网络；    

1. [SqueezedText: A Real-time Scene Text Recognition by Binary Convolutional Encoderdecoder Network](https://pdfs.semanticscholar.org/0e59/f7d7e9c9380b425a94038c7a2500b2f6063a.pdf)   
AAAI 2018 *2018* [paper](https://pdfs.semanticscholar.org/0e59/f7d7e9c9380b425a94038c7a2500b2f6063a.pdf)   

1. [Handwriting Recognition in Low-resource Scripts using Adversarial Learning](http://cn.arxiv.org/abs/1811.01396)   
CVPR 2019 *2018-11-04* [paper](https://arxiv.org/abs/1811.01396)   

1. [ESIR: End-to-end Scene Text Recognition via Iterative Image Rectification](http://cn.arxiv.org/abs/1812.05824)    
CVPR 2019 *2018-12-14* [paper](https://arxiv.org/abs/1812.05824)   
**ESIR**:设计了仿射网络；       

## 6.5 其他
1. [Study on Feature Extraction Methods for Character Recognition of Balinese Script on Palm Leaf Manuscript Images](https://hal.archives-ouvertes.fr/hal-01422135/document)   
*2016* [paper](https://hal.archives-ouvertes.fr/hal-01422135/document)   



# 7 端到端文字识别
>检测 + 识别   

1. [Towards End-to-end Text Spotting with Convolutional Recurrent Neural Networks](http://cn.arxiv.org/abs/1707.03985)   
ICCV 2017 *2017-07-13* [paper](https://arxiv.org/abs/1707.03985)    
FasterRCNN 接 LSTM；该方法在复杂任务上效果不是很好，原因是检测结果对整个任务起到决定性作用；    

1. [Deep TextSpotter: An End-to-End Trainable Scene Text Localization and Recognition Framework](http://openaccess.thecvf.com/content_ICCV_2017/papers/Busta_Deep_TextSpotter_An_ICCV_2017_paper.pdf)   
ICCV 2017 *2017* [paper](http://openaccess.thecvf.com/content_ICCV_2017/papers/Busta_Deep_TextSpotter_An_ICCV_2017_paper.pdf)    
检测任务中，除了坐标位置，还加入了旋转角度参数；但仍受检测结果限制；    

1. [Attention-based Extraction of Structured Information from Street View Imagery](http://cn.arxiv.org/abs/1704.03549)   
ICDAR 2017 *2017-04-11* Google [paper](https://arxiv.org/abs/1704.03549)   
针对多视角的街景采集数据进行 OCR；使用空间注意力代替检测；       

1. [STN-OCR: A single Neural Network for Text Detection and Text Recognition](http://cn.arxiv.org/abs/1707.08831)   
*2017-07-27* [paper](https://arxiv.org/abs/1707.08831)   


1. [SEE: Towards Semi-Supervised End-to-End Scene Text Recognition](http://cn.arxiv.org/abs/1712.05404)   
AAAI 2018 *2017-12-14* [paper](https://arxiv.org/abs/1712.05404) | [tensorflow](https://github.com/Bartzi/see)        
**SEE**:      

1. [FOTS: Fast Oriented Text Spotting with a Unified Network](http://cn.arxiv.org/abs/1801.01671)   
CVPR 2018 *2018-01-05* [paper](https://arxiv.org/abs/1801.01671) | [pytorch](https://github.com/xieyufei1993/FOTS)       
**FOTS**: FPN + 角度；插值后送入双向 LSTM；单阶段检测网络，所以速度快一点；            

1. [An end-to-end TextSpotter with Explicit Alignment and Attention](http://cn.arxiv.org/abs/1803.03474)   
CVPR 2018 *2018-03-09* [paper](https://arxiv.org/abs/1803.03474) | [caffe](https://github.com/tonghe90/textspotter)-offical    
与 TextSpotter 类似，加入了角度信息，然后进行 ROIPooling，再送入 RNN + Seq2Seq + Attention；   

1. [Mask TextSpotter: An End-to-End Trainable Neural Network for Spotting Text with Arbitrary Shapes](http://cn.arxiv.org/abs/1807.02242)   
ECCV 2018 *2018-07-06* 旷视 [paper](https://arxiv.org/abs/1807.02242)   
不规则文本处理，借鉴 MaskRCNN；    

1. [Towards End-to-End License Plate Detection and Recognition: A Large Dataset and Baseline](http://openaccess.thecvf.com/content_ECCV_2018/papers/Zhenbo_Xu_Towards_End-to-End_License_ECCV_2018_paper.pdf)   
ECCV 2018 *2018* [paper](http://openaccess.thecvf.com/content_ECCV_2018/papers/Zhenbo_Xu_Towards_End-to-End_License_ECCV_2018_paper.pdf)   
**PRNet**:发布了一个包含 250k 图的中国车牌数据集 CCPD，每个标注包含 1 个 box，4 个定位点，及文字 GT；   
对不同尺度的特征图进行 ROIPooling，拼接后进行识别；只是一个 BaseLine 方案；     


-------------------  
[End](#head)
{:.warning}  

# 附录
## A 参考资料
1. [中文字幕分析](https://github.com/lars76/chinese-subtitle-ocr)    
SSD 做的检测，然后自适应与之分割，最后进行识别；    

## B 开源代码
1. [OCRE(OCR Easy)](http://lem.eui.upm.es/ocre.html)   

1. [Clara OCR](http://directory.fsf.org/claraocr.html)          
99 年起的一个项目，C 语言开发的，支持 win 和 linux；提供了 GUI 和 Web 接口；           

1. [OCRAD](http://directory.fsf.org/ocrad.html)       
2019-01-11 分布的，基于特征提取的方式分析文本，可以按列或者空格对文字进行分割；    

1. [JOCR](http://sourceforge.net/projects/jocr)     
2013-04-15 最后一次更新；    

1. [OCR-CHIE](http://http.cs.berkeley.edu/~fateman/kathey/ocrchie.html)     
2001-03；      

1. [TESSERACT-OCR](http://code.google.com/p/tesseract-ocr/)     
2005年 由 HP 开源，2006年之后，由 Google 维护； 4.0 版本中加入了 LSTM；目前支持 100 多种语言的文本识别；支持文档格式包括文本、HTML 和 PDF 等；提供 C 和 C++ 接口；   

## C 数据集

| 名称 | 类型 | 数量(训练/测试) | 说明 | 发布日期 |
| --- | --- | --- | --- | --- |
| [MNIST](http://yann.lecun.com/exdb/mnist/ ) | 手写数字识别 |  | 入门级 |  |
| [USPS](http://www.gaussianprocess.org/gpml/data/) | 手写数字识别 | 10×4696<br>10×4696 |  |   |
| [UCI](http://archive.ics.uci.edu/ml/datasets/Letter+Recognition) | 字母识别 | 20000 | 包含 20 中不同字体；二值图像； | 1991-01-01 |
| ICDAR 2011<br>[Born-Digital Image (Web and Email)](http://www.cvc.uab.es/icdar2011competition/) | 文档分析 |  |  | 2011-06 |
| ICDAR 2011<br>[Scene Images](http://robustreading.opendfki.de/wiki/SceneText) | 检测+识别 |  |  | 2011-06 |
| ICDAR 2013<br>[Born-Digital Image (Web and Email)](http://dagdata.cvc.uab.es/icdar2013competition/) | 文档分析 |  |  | 2013-01 |
| ICDAR 2013<br>[Scene Images](http://dag.cvc.uab.es/icdar2013competition/?ch=2&com=downloads) | 检测+识别 |  |  | 2013-01 |
| ICDAR 2013<br>[videos](http://dag.cvc.uab.es/icdar2013competition/?ch=3&com=downloads) | 文档分析 |  |  | 2013-01 |
| []() |  |  |  |  |
| []() |  |  |  |  |
| []() |  |  |  |  |
