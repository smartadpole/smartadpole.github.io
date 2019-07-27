---
layout: article
title:  "「CV」 目标检测资源汇总"
date:   2019-05-10 15:00:40 +0800
key: ObjectDetection-foundation-20190510
aside:
  toc: true
category: [CV, detection]
tags: 资源
---
<span id='head'></span>
<center class="half">
  <img src="/assets/images/cv/detection/overview.jpg" /><br>图1：目标检测发现路线&emsp;
</center>

<!--more-->  

# 1 综述

# 2 理论
1. [Uncertainty Estimation in One-Stage Object Detection](http://cn.arxiv.org/abs/1905.10296)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10296)   

1. [Generalized Intersection over Union: A Metric and A Loss for Bounding Box Regression](http://cn.arxiv.org/abs/1902.09630)    
CVPR 2019 *2019-02-25* [paper](https://arxiv.org/abs/1902.09630)   
使用 IoU 设计新的 loss 函数；    

# 3 经典论文
1. [Rich feature hierarchies for accurate object detection and semantic segmentation](https://arxiv.org/abs/1311.2524)     
*2013-11* [Paper](https://arxiv.org/abs/1311.2524)    
**RCNN**：

1. [Fast R-CNN](http://cn.arxiv.org/abs/1504.08083)   
*2015-04-30* [Paper](https://arxiv.org/abs/1504.08083)   

1. [Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks](http://cn.arxiv.org/abs/1506.01497)   
*2015-06* [Paper](https://arxiv.org/abs/1506.01497) | [pytorch](https://ai.yanxishe.com/page/TextTranslation/1304?from=groupmessage)   

1. [SSD: Single Shot MultiBox Detector](http://cn.arxiv.org/abs/1512.02325)    
ECCV 2016 Oral *2015-12* ​[Paper](https://arxiv.org/abs/1512.02325) | [caffe](https://github.com/weiliu89/caffe/tree/ssd)-Official | [Caffe-MobileNet](https://github.com/chuanqi305/MobileNet-SSD) | [MxNet](https://github.com/zhreshold/mxnet-ssd) | [MxNet-cpp](https://github.com/zhreshold/mxnet-ssd.cpp) | [Keras](https://github.com/rykov8/ssd_keras) | [Keras](https://github.com/pierluigiferrari/ssd_keras) | [Tensorflow](https://github.com/balancap/SSD-Tensorflow) | [Pytorch](https://github.com/amdegroot/ssd.pytorch)    


# 4 通用目标检测
## 4.1 检测框去重
1. NMS   
FasterRCNN 中有对其效果进行分析；   

1. [Soft-NMS -- Improving Object Detection With One Line of Code](http://cn.arxiv.org/abs/1704.04503)    
*2017.4* [Paper](https://arxiv.org/abs/1704.04503)   
1. [Softer-NMS: Rethinking Bounding Box Regression for Accurate Object Detection](http://cn.arxiv.org/abs/1809.08545)    
*2018.9* [Paper](https://arxiv.org/abs/1809.08545)   

1. [Acquisition of Localization Conﬁdence for Accurate Object Detection](http://cn.arxiv.org/abs/1807.11590)   
ECCV 2018 *2018.7* [Paper](https://arxiv.org/abs/1807.11590)   
**NMS Network**：设计了 IoU-Net 用来估计 proposal 与其对应 ground-truth 框的 IoU 值，提出了新的边框回归算法以及 NMS 的改进算法；[解读](https://zhuanlan.zhihu.com/p/43590558)   

## 4.2 Anchors
1. [MetaAnchor: Learning to Detect Objects with Customized Anchors](http://cn.arxiv.org/pdf/1807.00980v2)   
​NIPS 2018 *2018-07* 旷视科技 & 复旦大学 [Paper](https://arxiv.org/abs/1807.00980)   
动态 anchor；    

1. [Region Proposal by Guided Anchoring](http://cn.arxiv.org/abs/1901.03278)   
*2019-01* 香港中文大学-商汤联合实验室&Amazon Rekognition&南洋理工大学 [Paper](https://arxiv.org/abs/1901.03278) | [mmdetection](https://github.com/open-mmlab/mmdetection)   
**Guided Anchoring**:​融合Anchor与关键点   

## 4.3 技巧

1. [Bag of Freebies for Training Object Detection Neural Networks]()  
[2019.2] GluonCV 检测调参技巧​
http://cn.arxiv.org/abs/1902.04103
https://github.com/dmlc/gluon-cv
https://mp.weixin.qq.com/s/pkFcmm15gnuRJtngFX7f0w

1. [Training Object Detectors With Noisy Data](https://arxiv.org/abs/1905.07202)   
*2019-05-17* [paper](https://arxiv.org/abs/1905.07202)   
教师网络处理噪声图像；   

## 4.4 单阶段

## 4.5 两阶段

1. [Light-Weight RetinaNet for Object Detection](http://cn.arxiv.org/abs/1905.10011)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10011)   

## 4.6 Anchor free

1. [A closer look: Small object detection in faster R-CNN]()   
无 pdf 介绍了一种生成anchor proposals的改进建议，并对Faster R-CNN进行修改，利用较高分辨率的小目标的feature maps​
https://blog.csdn.net/zhangjunhit/article/details/78900298

1. [Scale-aware Pixel-wise Object Proposal Networks]()  
[2016.1 - 2016.7] 提出Scale-aware Pixel-wise Object Proposal（SPOP）网络，可以生成具有高召回率和平均最佳重叠（ABO）的proposals，即使对于小目标也是如此。另外，引入了一个类似分段的像素定位网络来密集预测每个像素的对象坐标，并开发了一种尺度感知对象定位策略，该策略将来自大尺寸和小尺寸网络的预测与加权机制相结合，以提高各种对象尺寸的坐标预测精度​
https://arxiv.org/abs/1601.04798

## 4.7 无类别
1. [Learning Objectness from Sonar Images for Class-Independent Object Detection](http://cn.arxiv.org/abs/1907.00734)   
*2019-07-01* [paper](https://arxiv.org/abs/1907.00734)    

## 4.8 其他

1. [YOLO]()  
官网 https://pjreddie.com/darknet/yolo/

1. [R-FCN: Object Detection via Region-based Fully Convolutional Networks]()  
[2016.5 - 2016.6] cvpr2017, 对预测特征图引入位置敏感分数图提增强征位置信息，提高检测精度​
https://arxiv.org/abs/1605.06409
github.com/daijifeng001/R-FCN

1. [Feature Pyramid Networks for Object Detection]()  
[2016.12 - 2017.4] cvpr, 特征金字塔网络​
https://arxiv.org/abs/1612.03144v2

1. [YOLO9000: Better, Faster, Stronger]()  
[2016.12]
https://arxiv.org/abs/1612.08242

1. [A-Fast-RCNN: Hard Positive Generation via Adversary for Object Detection]()  
[2017.4] 提出学习一个可以生成遮挡和变形样本的对抗网络，对抗器的目标是生成让目标检测器难以进行分类的样本。在我们的框架中，原始检测器和对抗器都是以联合的方式学习的​
https://arxiv.org/abs/1704.03414v1
https://github.com/xiaolonw/adversarial-frcnn

1. [Detecting Small Signs from Large Images]()  
[2017.6] large images are broken into small patches as input to a Small Object-Sensitive-CNN (SOS-CNN) modified from a Single Shot Multibox Detector (SSD) framework with a VGG-16 network as the base network to produce patch-level object detection results. Scale invariance is achieved by applying the SOS-CNN on an image pyramid. Then, image-level object detection is obtained by projecting all the patch-level detection results to the image at the original scale.​
https://arxiv.org/abs/1706.08574

1. [Perceptual Generative Adversarial Networks for Small Object Detection]()  
P-GAN [2017.6] P-GAN将小目标的特征映射到相似的大目标特征上来缩小差别，便能将小目标足够近似到大目标来欺骗判别器，达到小目标检测的目的​
https://arxiv.org/abs/1706.05274

1. [R-FCN++: Towards Accurate Region-Based Fully Convolutional Networks for Object Detection]()  
[2017]
http://www.skicyyu.org/Paper/RFCN_plus_plus.pdf

1. [DSSD : Deconvolutional Single Shot Detector]()  
[2017.1]  使用 Top-Down 网络结构，解决小物体检测的问题​
https://arxiv.org/abs/1701.06659
github.com/MTCloudVision/mxnet-dssd
https://zhuanlan.zhihu.com/p/33036037

1. [Mask R-CNN]()  
[2017.3 - 2018.1] cvpr 2017, 1. 解决 RoIPooling 在 Pooling 过程中对 RoI 区域产生形变，且位置信息提取不精确的问题。2. 通过改进 Faster R-CNN 结构完成分割任务​
github.com/TuSimple/mx-maskrcnn

1. [Deformable Convolutional Networks]()  
[2017.3 - 2017.6]
 https://arxiv.org/abs/1703.06211
https://github.com/msracver/Deformable-ConvNets

1. [Enhancement of SSD by concatenating feature maps for object detection]()  
[2017.5]
https://arxiv.org/abs/1705.09587

1. [Enhancement of SSD by concatenating feature maps for object detection]()  
RSSD [2017.5]
https://arxiv.org/abs/1705.09587

1. [DSOD : learning deeply supervised object detectors from scratch]()  
[2017.08 - 2018.4] iccv 2017,
https://arxiv.org/abs/1708.01241
github.com/szq0214/DSOD

1. [Focal Loss for Dense Object Detection]()  
RetinaNet [2017.8 - 2018.2] Facebook AI​
https://arxiv.org/abs/1708.02002
mxnet https://github.com/TuSimple/mx-maskrcnn

1. [Relation Networks for Object Detection]()  
[2017.11 - 2018.1] cvpr2018, 这篇文章的出发点在于目前大部分的目标检测（object detection）算法都是独立地检测图像中的object，但显然如果模型能学到object之间的关系显然对于检测效果提升会有帮助，因此这篇文章希望在检测过程中可以通过利用图像中object之间的相互关系或者叫图像内容（context）来优化检测效果，这种关系既包括相对位置关系也包括图像特征关系​
https://arxiv.org/abs/1711.11575
https://github.com/msracver/Relation-Networks-for-Object-Detection

1. [Receptive Field Block Net for Accurate and Fast Object Detection]()  
RBF [2017.11 - 2018.7]
https://arxiv.org/abs/1711.07767

1. [Receptive Field Block Net for Accurate and Fast Object Detection]()  
[2017.11-2018.7] ​
https://arxiv.org/abs/1711.07767

1. [An Analysis of Scale Invariance in Object Detection - SNIP]()  
SNIP [2017.11 - 2018.3] cvpr2018, 可看成改版版本的Image Pyramid。分析了小尺度与预训练模型尺度之间的关系, 提出了Scale Normalization for Image Pyramids (SNIP)：在训练中，每次只回传那些大小在一个预先指定范围内的proposal的gradient，而忽略掉过大或者过小的proposal；在测试中，建立大小不同的Image Pyramid，在每张图上都运行这样一个detector，同样只保留那些大小在指定范围之内的输出结果，最终在一起NMS。这样就可以保证网络总是在同样scale的物体上训练，也就是标题中Scale Normalized的意思​
 https://arxiv.org/abs/1711.08189
http://bit.ly/2yXVg4c

1. [Single-Shot Refinement Neural Network for Object Detection]()  
RefineNet [2017.11 - 2018.1] cvpr2018, 可看做将Faster RCNN的two stages检测方法和SSD结合​；主要思想：一方面引入two stage类型的object detection算法中对box的由粗到细的回归思想（由粗到细回归其实就是先通过RPN网络得到粗粒度的box信息，然后再通过常规的回归支路进行进一步回归从而得到更加精确的框信息，这也是two stage类型的object detection算法效果优于one stage类型的一个重要原因）。另一方面引入类似FPN网络的特征融合操作用于检测网络，可以有效提高对小目标的检测效果，检测网络的框架还是SSD​propose a novel one-stage framework(RefineDet) consists of two inter-connected modules. the former aims to (1) filter out negative anchors to reduce search space for the classifier, and (2) coarsely adjust the locations and sizes of anchors to provide better initialization for the subsequent regressor. The latter module takes the refined anchors as the input from the former to further improve the regression and predict multi-class label. Meanwhile, we design a transfer connection block to transfer the features in the anchor refinement module to predict locations, sizes and class labels of objects in the object detection module. The multitask loss function enables us to train the whole network in an end-to-end way.​
 http://arxiv.org/abs/1711.06897
caffe https://github.com/sfzhang15/RefineDet

1. [FSSD: Feature Fusion Single Shot Multibox Detector]()  
FSSD [2017.12 - 2018.5]
https://arxiv.org/abs/1712.00960

1. [ R-FCN-3000 at 30fps: Decoupling Detection and Classification]()  
R-FCN-3000  [2017.12] cvpr 2018, YOLO9000 将检测数据集和分类数据集合并训练检测模型，但 r-fcn-3000 仅采用具有辅助候选框信息的 ImageNet 数据集训练检测分类器​
https://arxiv.org/abs/1712.01802

1. [Cascade R-CNN: Delving into High Quality Object Detection]()  
[2017.12] cvpr2018, 基于two-stage detector。Cascade R-CNN是R-CNN的multi-stage延伸，由一系列随着IOU临界值增加而训练的检测器构成，从而对close false positives更具有选择性。R-CNN阶段的cascade是按顺序训练的，使用一个阶段的输出来训练下一阶段。类似于boostrapping methods，不同点是Cascade R-CNN的重采样过程并不旨在mine hard negatives，而是通过调整bounding boxes，每个阶段的目的都是为了找到一组好的false positive来训练下一阶段​
 https://arxiv.org/abs/1712.00726
caffe matlab https://github.com/zhaoweicai/cascade-rcnn

1. [Single-Shot Object Detection with Enriched Semantics]()  
DES [2017.12 - 2018.4] cvpr2018, 在SSD网络基础上，增加了语义分割分支和全局激活模块。前者增加低层检测特征，后者通过学习特征通道和目标类别的语义关系来进行高层目标检测特征。​
https://arxiv.org/abs/1712.00433

1. [Zero-Shot Detection]()  
[2018.3]
https://arxiv.org/abs/1803.07113

1. [Zero-Shot Object Detection]()  
[2018] eccv,
https://arxiv.org/abs/1804.04340

1. [Zero-Shot Object Detection by Hybrid Region Embedding]()  
[2018]
https://arxiv.org/abs/1805.06157

1. [SAN: Learning Relationship between Convolutional Features for Multi-Scale Object Detection]()  
SAN [2018.8] 提出了Scale Aware Network (SAN)，将来自不同尺度的卷积特征映射到尺度不变的子空间，并设计了一种独特的学习方法，纯粹考虑了没有空间信息的渠道之间的关系。所提出的SAN减少了标度空间中的特征差异并提高了检测精度​
https://arxiv.org/abs/1808.04974v1

1. [Quantization Mimic: Towards Very Tiny CNN for Object Detection]()  
[2018.3 - 2018.9] ​ECCV 2018，香港中文，商汤；检测，知识蒸馏，架构混合；​
 https://arxiv.org/abs/1805.02152

1. [Domain Adaptive Faster R-CNN for Object Detection in the Wild]()  
[2018.3]
https://arxiv.org/abs/1803.03243

1. [Scale-Transferrable Object Detection]()  
STDN [2018] cvpr2018, Scale-Transferrable Detection Network（STDN）算法主要用于提高object detection算法对不同scale的object的检测效果。该算法采用DenseNet网络作为特征提取网络（自带高低层特征融合），基于多层特征做预测（类似SSD），并对预测结果做融合得到最终结果。该算法有两个特点：1、主网络采用DenseNet，了解DenseNet的同学应该知道该网络在一个block中，每一层的输入feature map是前面几层的输出feature map做concate后的结果，因此相当于高低层特征做了融合。高低层特征融合其实对object detection算法而言是比较重要的，FPN算法是显式地做了高低层特征融合，而SSD没有，这也是为什么SSD在小目标问题上检测效果不好的原因之一，因此该算法虽然看似SSD，但其实和SSD有区别。2、引入scale-transfer layer，实现了在几乎不增加参数量和计算量的前提下生成大尺寸的feature map（其他常见的算法基本上都是采用deconvolution或upsample），由于scale-transfer layer是一个转换操作，因此基本不会引入额外的参数量和计算量​
http://openaccess.thecvf.com/content_cvpr_2018/CameraReady/1376.pdf

1. [Multi-scale Location-aware Kernel Representation for Object Detection]()  
[2018.4] cvpr, 提出了一种新颖的多尺度位置感知核表示（MLKP），将判别性高阶统计量结合到object proposals的表示中以进行有效的对象检测。MLKP基于多项式核近似，可以有效生成低维高阶表示，其固有的位置保持性和敏感性也保证了可以灵活地用于目标检测​
https://arxiv.org/abs/1804.00428
caffe https://github.com/Hwang64/MLKP

1. [YOLOv3: an incremental improvement]()  
YOLO V3  [2018.4]
arxiv.org/abs/1804.02767
https://github.com/pascal1129/yolo_person_detect
Caffe C++ https://github.com/jinfagang/yolov3_mobilenet_caffe.git
官方 github.com/pjreddie/darknet

1. [Pelee: A Real-Time Object Detection System on Mobile Devices]()  
Pelee [2018.4 - 2019.1] NIPS； ​轻量、高效的目标检测网络；

1. [DetNet: A Backbone network for Object Detection]()  
DetNet [2018.4] ECCV； ​检测和分类不同，较多的下采样降低了检测性能，本文对此设计了新的检测骨干网络 DetNet；​
https://arxiv.org/abs/1804.06215
https://mp.weixin.qq.com/s/oxStDMh90jB7_EY4vqja2w

1. [Object detection at 200 Frames Per Second]()  
[2018.5]
arxiv.org/abs/1805.06361

1. [You Only Look Twice: Rapid Multi-Scale Object Detection In Satellite Imagery]()  
[2018.5]
https://arxiv.org/abs/1805.09512

1. [CFENet: An Accurate and Efficient Single-Shot Object Detector for Autonomous Driving]()  
CFENet [2018.6 - 2018.10]
https://arxiv.org/abs/1806.09790

1. [Acquisition of Localization Confidence for Accurate Object Detection]()  
Iou-Net [2018.7.30] ECCV 用来学习来预测每个检测到的边界框与匹配的ground truth 之间的IoU
https://arxiv.org/abs/1807.11590

1. [Object Detection with Deep Learning: A Review]()  
[2018.7] 可看成改版版本的Image Pyramid；​分析了小尺度与预训练模型尺度之间的关系, 提出了Scale Normalization for Image Pyramids (SNIP)：在训练中，每次只回传那些大小在一个预先指定范围内的proposal的gradient，而忽略掉过大或者过小的proposal；在测试中，建立大小不同的Image Pyramid，在每张图上都运行这样一个detector，同样只保留那些大小在指定范围之内的输出结果，最终在一起NMS。这样就可以保证网络总是在同样scale的物体上训练，也就是标题中Scale Normalized的意思。​
https://arxiv.org/abs/1807.05511

1. [SOD-MTGAN: Small Object Detection via Multi-Task Generative Adversarial Network]()  
[2018] eccv, 无 pdf提出一个对于小目标检测的标准的端到端的多任务生成对抗网络（MTGAN），适用于任何已有的检测器。In the MTGAN, the generator network produces super-resolved images and the multi-task discriminator network is introduced to distinguish the real high-resolution images from fake ones, predict object categories, and refine bounding boxes, simultaneously. More importantly, the classification and regression losses are back-propagated to further guide the generator network to produce super-resolved images for easier classification and better localization​

1. [MetaAnchor: Learning to Detect Objects with Customized Anchors]()  
MetaAnchor [2018.7 - 2018.11] NIPS； ​旷视科技

1. [CornerNet: Detecting Objects as Paired Keypoints]()  
CornerNet [2018.8] ECCV2018；​密歇根大学
https://arxiv.org/abs/1808.01244
解读 https://zhuanlan.zhihu.com/p/41865617

1. [Deep Feature Pyramid Reconfiguration for Object Detection]()  
[2018.8] eccv, 当前特征金字塔的设计在如何整合不同尺度的语义信息方面仍然不够高效。本文把特征金字塔转换为特征的再组合过程，创造性地提出了一种高度非线性但是计算快速的结构将底层表示和高层语义特征进行整合。该网络由两个模块组成：全局注意力和局部再组合。这两个模块分布能全局和局部地去在不同的空间和尺度上提取任务相关的特征。重要的是，这两个模块具有轻量级、可嵌入和可端到端训练的优点​
https://arxiv.org/abs/1808.07993?context=cs

1. [Recent Advances in Object Detection in the Age of Deep Convolutional Neural Networks]()  
[2018.9] 目标检测综述
https://arxiv.org/abs/1809.03193

1. [Deep Learning for Generic Object Detection: A Survey]()  
[2018.9] IJCV；
https://arxiv.org/abs/1809.02165
https://github.com/hoya012/deep_learning_object_detection#2014
解读 https://zhuanlan.zhihu.com/p/45196320

1. [Context Refinement for Object Detection]()  
ECCV 2018
http://openaccess.thecvf.com/content_ECCV_2018/papers/Zhe_Chen_Context_Refinement_for_ECCV_2018_paper.pdf

1. [Hybrid Knowledge Routed Modules for Large-scale Object Detection]()  
[2018.10] NIPS；
http://cn.arxiv.org/abs/1810.12681

1. [Polarity Loss for Zero-shot Object Detection]()  
[2018.11] 使用SPP模块通过扩大网络宽度而不是增加深度来生成金字塔形特征图。提出MSCA模块有效地组合了不同规模的上下文信息​
https://arxiv.org/abs/1811.08982

1. [Parallel Feature Pyramid Network for Object Detection]()  
[2018] eccv
http://openaccess.thecvf.com/content_ECCV_2018/papers/Seung-Wook_Kim_Parallel_Feature_Pyramid_ECCV_2018_paper.pdf

1. [YOLO-LITE: A Real-Time Object Detection Algorithm Optimized for Non-GPU Computers]()  
YOLO-LITE [2018.11] ​速度是tiny-yolo的10倍；
https://arxiv.org/abs/1811.05588v1
https://github.com/reu2018dl/yolo-lite
https://mp.weixin.qq.com/s/xNaXPwI1mQsJ2Y7TT07u3g

1. [Progressive Attention Guided Recurrent Network for Salient Object Detection]()  
http://openaccess.thecvf.com/content_cvpr_2018/CameraReady/1235.pdf

1. [Bottom-up Object Detection by Grouping Extreme and Center Points]()  
[2019.1] ​德克萨斯大学奥斯汀分校)​one-stage 中准确度第一；测试耗时333ms； UT Austin；
https://arxiv.org/abs/1901.08043
https://github.com/xingyizhou/ExtremeNet
https://mp.weixin.qq.com/s/Th6vFE9Gy1Wl-Vf_Lz3w8w

1. [Scale-Aware Trident Networks for Object Detection]()  
TridentNet [2019.01] ​中国科学院大学&图森未来； 高 retinanet近 10 个百分点；主要处理了多尺度问题
https://arxiv.org/abs/1901.01892
https://mp.weixin.qq.com/s/7Pi5J8-d1HD2lapAD0_qHA

1. [DeRPN: Taking a further step toward more general object detection]()  
DeRPN [2018.11] ​这篇文章对RPN进行了改进，将anchor box进行了空间宽高解耦，使得anchor选择的复杂度从O(n^2)降到了O(n)
https://arxiv.org/abs/1811.06700v1
https://github.com/HCIILAB/DeRPN
https://mp.weixin.qq.com/s/4nJGdV3qF4IsfxLM8BBeqg


1. [Consistent Optimization for Single-Shot Object Detection]()  
[2019.1]​清华、宾夕法尼亚大学和字节跳动
https://arxiv.org/abs/1901.06563
https://mp.weixin.qq.com/s/4T90Lac_1GX2uy8xtWb1Ng


# 5 应用场景
## 5.1 人
### 5.1.1 人脸检测
### 5.1.2 行人检测

## 5.2 [文本](/cv/ocr/2019/07/27/foundation.html)

## 5.3 交通
### 5.3.1 车道线检测
### 5.3.2 交通标志检测
[keras](https://github.com/kuhung/SSD_keras)    
### 5.3.3 车辆检测
### 5.3.4 船体检测

## 5.4 商品
### 5.4.1 Logo 检测

### 5.4.2 商品检测

## 5.5 医疗
### 5.5.1 肺结节检测

## 5.6 视频目标检测
## 5.7 航拍
1. [DOTA: A Large-scale Dataset for Object Detection in Aerial Images](https://arxiv.org/abs/1711.10398)   
CVPR 2018 *2017-11-28* [paper](https://arxiv.org/abs/1711.10398)   

# 6 小目标检测
1. [Multiple receptive fields and small-object-focusing weakly-supervised segmentation network for fast object detection](http://cn.arxiv.org/abs/1904.12619)   
*2019-04-19* [paper](https://arxiv.org/abs/1904.12619)   

1. [A Real-Time Tiny Detection Model for Stem End and Blossom End of Navel Orange](http://cn.arxiv.org/abs/1905.09994)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.09994)   

# 7 面向终端的目标检测
1. [Towards High Performance Video Object Detection for Mobiles](http://cn.arxiv.org/abs/1804.05830)   
*2018-04-16* [Paper](https://arxiv.org/abs/1804.05830)    

# 8 3D 检测


# 9 其他
1. [Cloud-Net: An end-to-end Cloud Detection Algorithm for Lan](http://cn.arxiv.org/abs/1901.10077)   
2019-01-29 [Paper](https://arxiv.org/abs/1901.10077)   
云层检测   


-------------------  
[End](#head)
{:.warning}  


# 附录
## A 参考资料

## B 资源
### a 论文
[amusi](https://github.com/amusi/awesome-object-detection)，[韩东](https://handong1587.github.io/deep_learning/2015/10/09/object-detection.html)   


### b 代码
- 数据增强   
[Paperspace](https://github.com/Paperspace/DataAugmentationForObjectDetection/blob/master/data_aug/data_aug.py)，[maozezhong](https://github.com/maozezhong/CV_ToolBox/blob/master/DataAugForObjectDetection/DataAugmentForObejctDetection.py)    
- [opencv 跟踪检测](https://github.com/Smorodov/Multitarget-tracker)   
- [yolo 小目标检测](https://github.com/avanetten/yolt)    

[mmdetection](https://github.com/open-mmlab/mmdetection)   

### c 总结
[物体检测论文阅读路线图](https://mp.weixin.qq.com/s/X2ReSIU9Qq1OA3bywCNNig)，[hoya012](https://github.com/hoya012/deep_learning_object_detection)，[ECCV2018 目标检测](http://bbs.cvmart.net/topics/194/eccv2018-mu-biao-jian-ce-object-detection-suan-fa-zong-lan-bu-fen-han-dai-ma?from=groupmessage)    
美图：[一](https://mp.weixin.qq.com/s/oMs4MEQRwIZfGZa-HmzC_w)，[二](https://mp.weixin.qq.com/s/Uu_4DUqDzkZgEMJ7KenMcg)，[三](https://mp.weixin.qq.com/s/XlVGuoUlQwimTWXEE6gPBQ
https://mp.weixin.qq.com/s/LGj_2Zw6XA_EfZb8Rvv7bg)    
[目标检测研究综述+LocNet](https://zhuanlan.zhihu.com/p/33058849)   
[anchor 机制](https://mp.weixin.qq.com/s/oW4vUx7fXRhMRKh7QSQ5TA)，[yolo2 中的trick](https://mp.weixin.qq.com/s/us0VbQgu8YLNCAU5i_5QuA)   
[NMS](https://mp.weixin.qq.com/s/HeOOHyeeJvAuJr3iNm18Ow)   
