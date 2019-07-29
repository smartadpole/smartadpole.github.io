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

1. [Deep Learning for Text Spotting](https://www.robots.ox.ac.uk/~vgg/publications/2015/Jaderberg15b/jaderberg15b.pdf)   
*2014* [paper](https://www.robots.ox.ac.uk/~vgg/publications/2015/Jaderberg15b/jaderberg15b.pdf)   
研究生课题（斯坦福）    

1. [Scene Text Detection and Recognition: Recent Advances and Future Trends](http://www.vlrlab.net/admin/uploads/avatars/FCS_TextSurvey_2015.pdf)   
*2014* [paper](http://www.vlrlab.net/admin/uploads/avatars/FCS_TextSurvey_2015.pdf)   

1. [Text Detection and Recognition in Imagery: A Survey](https://ucassdl.cn/downloads/publication/PAMI2015_YeQixiang.pdf)   
*2015-07* [paper](https://ucassdl.cn/downloads/publication/PAMI2015_YeQixiang.pdf)   

1. [Context Modeling for Semantic Text Matching and Scene Text Detection](https://etda.libraries.psu.edu/files/final_submissions/12356)    
*2016* [paper](https://etda.libraries.psu.edu/files/final_submissions/12356)   
研究生课题；    

1. [A Survey on Scene Text Detection and Text Recognition](https://www.ijarcce.com/upload/2016/march-16/IJARCCE%20208.pdf)   
*2016-03* [paper](https://www.ijarcce.com/upload/2016/march-16/IJARCCE%20208.pdf)   


1. [Text Detection and Recognition in Images: A Survey](http://cn.arxiv.org/abs/1803.07278)    
*2018-03-20* [paper](https://arxiv.org/abs/1803.07278)      
学生写的，还不完整；   

1. [Scene Text Detection and Recognition: The Deep Learning Era](http://cn.arxiv.org/abs/1811.04256)    
*2018-11-10* [paper](https://arxiv.org/abs/1811.04256) | [github](https://github.com/Jyouhou/SceneTextPapers)       


# 2 理论

# 3 其他
1. [Total-Text: A Comprehensive Dataset for Scene Text Detection and Recognition](http://cn.arxiv.org/abs/1710.10400)    
ICDAR 2017 *2017-10-28* [paper](https://arxiv.org/abs/1710.10400) | [code4downloads](https://github.com/cs-chan/Total-Text-Dataset)     

1. [ICDAR 2019 Robust Reading Challenge on Multi-lingual Scene Text Detection and Recognition -- RRC-MLT-2019](http://cn.arxiv.org/abs/1907.00945)   
ICDAR 2019 *2019-07-01* [paper](https://arxiv.org/abs/1907.00945) | [competition](https://rrc.cvc.uab.es/?ch=15)      



# 4 文本检测
>找到文字区域的位置；        

## 4.1 综述

## 4.2 理论

## 4.3 字符
>这个系列的方法感觉都好复杂；   

1. [Text-Attentional Convolutional Neural Network for Scene Text Detection](http://cn.arxiv.org/abs/1510.03283)    
*2015-10-12* [paper](https://arxiv.org/abs/1510.03283)    
用 CE-MSERs 检测出字符，外加其他方法尽可能多地检测出字符，然后再滤除掉不是字符的区域；后接文本行合成处理；       

1. [Text Flow: A Unified Text Detection System in Natural Scene Images](http://cn.arxiv.org/abs/1604.06877)   
ICCV 2015 *2016-04-23* [paper](https://arxiv.org/abs/1604.06877)   
Adaboost 检测字符区域，然后用图进行合并；

1. [Detecting oriented text in natural images by linking segments](http://cn.arxiv.org/abs/1703.06520)   
CVPR 2017 *2017-03-19* [paper](https://arxiv.org/abs/1703.06520) | [tensorflow](https://github.com/bgshih/seglink)       
**SegLink**: 提出文本行检测，基于 SSD 进行的改进；先检测字符，再拼接；        


1. [WordSup: Exploiting Word Annotations for Character based Text Detection](http://cn.arxiv.org/abs/1708.06720)    
ICCV 2017 *2017-08-22* [paper](https://arxiv.org/abs/1708.06720)      
使用预训练的字符检测网络，对结果进行聚类的到文本块，后接识别模块；    

## 4.4 文本行
### 4.4.1 常规
1. [Reading Text in the Wild with Convolutional Neural Networks](http://cn.arxiv.org/abs/1412.1842)   
*2014-12-04* [paper](https://arxiv.org/abs/1412.1842)   

1. [Deep Convolutional Neural Networks for Text Spotting in Natural Images](https://pdfs.semanticscholar.org/8c58/0758ad5541c357a46f4a0fd92dcf0955c24d.pdf)    
*2015* [paper](https://pdfs.semanticscholar.org/8c58/0758ad5541c357a46f4a0fd92dcf0955c24d.pdf)   

1. [TextBoxes: A Fast Text Detector with a Single Deep Neural Network](http://cn.arxiv.org/abs/1611.06779)   
AAAI 2017 *2016-11-21* [paper](https://arxiv.org/abs/1611.06779) | [caffe](https://github.com/MhLiao/TextBoxes)-offical      
SSD 基础上做的修改以适应文字检测；    

1. [PixelLink: Detecting Scene Text via Instance Segmentation](http://cn.arxiv.org/abs/1801.01315)   
AAAI 2018 *2018-01-04* [paper](https://arxiv.org/abs/1801.01315) | [tensorflow](https://github.com/ZJULearning/pixel_link)-offical        

### 4.4.2 多角度
1. [Accurate Text Localization in Natural Image with Cascaded Convolutional TextNetwork](http://cn.arxiv.org/abs/1603.09423)   
*2016-03-31* [paper](https://arxiv.org/abs/1603.09423)   

1. [Arbitrary-Oriented Scene Text Detection via Rotation Proposals](http://cn.arxiv.org/abs/1703.01086)   
*2017-03-03* [paper](https://arxiv.org/abs/1703.01086) | [caffe](https://github.com/mjq11302010044/RRPN)-offical | [pytorch](https://github.com/mjq11302010044/RRPN_pytorch)        
RRPN    
旋转 pooling；    

1. [Deep Matching Prior Network: Toward Tighter Multi-oriented Text Detection](http://cn.arxiv.org/abs/1703.01425)     
CVPR 2017 *2017-03-04* [paper](https://arxiv.org/abs/1703.01425)    
使用四边形检测文本；    

1. [Deep Direct Regression for Multi-Oriented Scene Text Detection](http://cn.arxiv.org/abs/1703.08289)   
*2017-03-24* [paper](https://arxiv.org/abs/1703.08289)   

1. [Cascaded Segmentation-Detection Networks for Word-Level Text Spotting](http://cn.arxiv.org/abs/1704.00834)   
*2017-04-03* [paper](https://arxiv.org/abs/1704.00834)   
基于 YOLO，先用分割的方法进行文字区域粗定位，再检测问题具体的位置； 1080Ti 上 1000×5600 的图像需要 450ms；   


1. [EAST: An Efficient and Accurate Scene Text Detector](http://cn.arxiv.org/abs/1704.03155)   
CVPR 2017 *2017-04-11* [paper](https://arxiv.org/abs/1704.03155) | [tensorflow](https://github.com/argman/EAST) | [pytorch](https://github.com/songdejia/EAST)   
参考了 DenseBox，使用 FCN 和 SSD 的多层输出；针对多方向问题，使用了旋转框和四边形；最后使用的是局部感知 nms；      
在 ICDAR 数据集上还可以，但是在其他数据集上效果很不理想；    

1. [R2CNN: Rotational Region CNN for Orientation Robust Scene Text Detection](http://cn.arxiv.org/abs/1706.09579)   
*2017-06-29* [paper](https://arxiv.org/abs/1706.09579) | [tensorflow](https://github.com/yangxue0827/R2CNN_FPN_Tensorflow) | [caffe](https://github.com/beacandler/R2CNN) | [一些改进代码](https://github.com/DetectionTeamUCAS)          
FasterRCNN 基础上做扩展；调整了 ROIPooling 的尺寸，引进了倾斜检测框，当然也针对倾斜的情况修正了 NMS；

1. [Single Shot Text Detector with Regional Attention](http://cn.arxiv.org/abs/1709.00138)   
ICCV 2017 *2017-09-01* [paper](https://arxiv.org/abs/1709.00138) | [caffe](https://github.com/BestSonny/SSTD)-offical | [pytorch](https://github.com/HotaekHan/SSTDNet)    
SSD + attention，通过修改网络结构提升检测效果;        

1. [TextBoxes++: A Single-Shot Oriented Scene Text Detector](http://cn.arxiv.org/abs/1801.02765)   
*2018-01-09* [paper](https://arxiv.org/abs/1801.02765) | [torch + caffe](https://github.com/MhLiao/TextBoxes_plusplus)        
多 anchor box 进行了倾斜和增多；    

1. [Multi-Oriented Scene Text Detection via Corner Localization and Region Segmentation](http://cn.arxiv.org/abs/1802.08948)   
CVPR 2018 *2018-02-25* 白翔组 [paper](https://arxiv.org/abs/1802.08948) | [pytorch](https://github.com/lvpengyuan/corner)-offical     
针对多方向文本识别；检测到文本区域的四个顶点，以提高检测任务对文本问题的适应性，同时减小了后处理过程；   
>怎么感觉那么像 cornernet 呢；   


### 4.4.3 不规则文字



# 5 文字识别
>识别出文字的内容；可以说是图片转文字；     

## 5.1 综述

## 5.2 理论

## 5.3 常规

### 5.3.1 CNN


### 5.3.2 CRNN

### 5.3.3 Seq2Seq

## 5.4 多角度

## 5.5 不规则
### 5.5.1 CNN
1. [Scene Text Recognition from Two-Dimensional Perspective](http://cn.arxiv.org/abs/1809.06508)   
AAAI 2019 *2018-09-18* 白翔组 [paper](https://arxiv.org/abs/1809.06508)   
检测时加入分割，定位到每个字符的位置，然后对单个字符进行分类，以分类代替是识别；同时使用了可变形卷积，以提取文字区域不同形状的特征；   


### 5.5.2 CRNN

### 5.5.3 Seq2Seq

### 5.5.4 其他
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

## 5.6 其他
1. [Study on Feature Extraction Methods for Character Recognition of Balinese Script on Palm Leaf Manuscript Images](https://hal.archives-ouvertes.fr/hal-01422135/document)   
*2016* [paper](https://hal.archives-ouvertes.fr/hal-01422135/document)   

1. [WeText: Scene Text Detection under Weak Supervision]()    
ICCV 2017   

1. [Single Shot Text Detector with Regional Attention]()   
ICCV 2017    

1. [Self-organized Text Detection with Minimal Post-processing via Border Learning]()   
ICCV 2017    

1. [Focusing Attention: Towards Accurate Text Recognition in Natural Images]()    
ICCV 2017    

1. [Towards End-to-end Text Spotting with Convolutional Recurrent Neural Networks]()    
ICCV 2017    

1. [Unambiguous Text Localization and Retrieval for Cluttered Scenes]()    
CVPR 2017    

1. [WordSup: Exploiting Word Annotations for Character based Text Detection]()    
ICCV 2017    

1. [Deep TextSpotter: An End-to-End Trainable Scene Text Localization and
Recognition Framework]()    
ICCV 2017    

1. [Cascaded Segmentation-Detection Networks for Word-Level Text Spotting]()    

1. [Detection and Recognition of Text Embedding in Online Images via Neural Context Models]()     
AAAI 2017    

1. [Improving Text Proposal for Scene Images with Fully Convolutional Networks]()    

1. [TextBoxes: A Fast TextDetector with a Single Deep Neural Network]()     
AAAI 2017    

1. [Detecting Oriented Text in Natural Images by Linking Segments]()     
CVPR 2017

1. [Arbitrary-Oriented Scene Text Detection via Rotation Proposals]()     

1. [Deep Matching Prior Network: Toward Tighter Multi-oriented Text Detection]()    
CVPR 2017   

1. [DeepText:A Unified Framework for Text Proposal Generation and Text Detection in Natural Images]()     

1. [Full-Page TextRecognition : Learning Where to Start and When to Stop]()    

1. [Reading Scene Text in Deep Convolutional Sequences]()    
AAAI 2016    

1. [Reading Text in the Wild with Convolutional Neural Networks]()    
IJCV 2016     

1. [Recursive Recurrent Nets with Attention Modeling for OCR in the Wild]()    
CVPR 2016     

1. [Robust Scene Text Recognition with Automatic Rectification]()   
CVPR 2016   

1. [Generative Shape Models: Joint Text Recognition and Segmentation with Very Little Training Data]()   
NIPS    

1. [AnEnd-to-End Trainable Neural Network for Image-based Sequence Recognition and Its Application to Scene Text Recognition]()   
CoRR 2015    

1. [Automatic Script Identification in the Wild](http://cn.arxiv.org/abs/1505.02982)      
ICDAR 2015    

1. [Deep structured output learning for unconstrained text recognition](http://cn.arxiv.org/abs/1412.5903)   
ICLR 2015        

1. [Synthetic Data and Artificial Neural Networks for Natural Scene Text Recognition]()   
NIPS 2014     

1. [A Unified Framework for Multi-Oriented Text Detection and Recognition]()   
TIP    

1. [End-to-End Text Recognition with Convolutional Neural Networks]()    
ICPR 2012


# 6 端到端文字识别
>检测 + 识别 不中断；      

1. [Towards End-to-end Text Spotting with Convolutional Recurrent Neural Networks](http://cn.arxiv.org/abs/1707.03985)   
ICCV 2017 *2017-07-13* [paper](https://arxiv.org/abs/1707.03985)    
FasterRCNN 接 LSTM；该方法在复杂任务上效果不是很好，原因是检测结果对整个任务起到决定性作用；    

1. [Deep TextSpotter: An End-to-End Trainable Scene Text Localization and Recognition Framework](http://openaccess.thecvf.com/content_ICCV_2017/papers/Busta_Deep_TextSpotter_An_ICCV_2017_paper.pdf)   
ICCV 2017 *2017* [paper](http://openaccess.thecvf.com/content_ICCV_2017/papers/Busta_Deep_TextSpotter_An_ICCV_2017_paper.pdf)    
检测任务中，除了坐标位置，还加入了旋转角度参数；但仍受检测结果限制；    

1. [Attention-based Extraction of Structured Information from Street View Imagery](http://cn.arxiv.org/abs/1704.03549)   
ICDAR 2017 *2017-04-11* Google [paper](https://arxiv.org/abs/1704.03549)   
$\bullet \bullet$   
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
## A 研究员
1. 白翔小组    
廖明辉，[石葆光](https://vision.cornell.edu/se3/people/baoguang-shi/)， 白翔, 王兴刚 ，刘文予      

## B 参考资料
1. [中文字幕分析](https://github.com/lars76/chinese-subtitle-ocr)    
SSD 做的检测，然后自适应与之分割，最后进行识别；    
1. [awesome-ocr](https://github.com/ChanChiChoi/awesome-ocr)    
1. [paper with code](https://paperswithcode.com/task/scene-text-detection/codeless?page=6)    
1. [场景文本位置感知与识别的论文资源汇总](https://github.com/whitelok/image-text-localization-recognition/blob/master/README.zh-cn.yearwise.md)    
1. [52CV-文字识别](https://www.52cv.net/?cat=18)    
1. [52CV-文本检测](https://www.52cv.net/?cat=37)    


## C 开源代码
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

## D 数据集

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

## E 报告
1. [OCR and Text Spotting](http://llcao.net/cu-deeplearning15/pdf/8OCR.pdf)    
