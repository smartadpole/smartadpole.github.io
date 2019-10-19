---
layout: article
title:  "「VIDEO」 视频检索资源汇总"
date:   2019-06-21 18:06:40 +0800
key: video-retrieval-foundation-20190621
aside:
  toc: true
category: [video, video_retrieval]
tags: 资源
---
<span id='head'></span>
>**相似视频检索**: 相似指的是通过修改原视频的到新的视频；      
相关资料：[检索概述](/video/video_retrieval/2019/07/30/survey.html) · [图像检索资源](/cv/retrieval/2019/05/22/foundation.html) · [音频检索资源](/audio/audio_retrieval/2019/08/14/foundation.html)    

<!--more-->
`video fingerprinting` · `video DNA` · `video signature` · `video hash` · `video content-based watermarking`;      
`video retrieval`; `near-duplicate video detection` · `Video Copy Detection` · `Video Forgery Detection` · `Video Content Identification`; `video vreification` · `video authentication` ;            


*发现这方面论文很凌乱，关键字都有很多个版本；每个方向也不多*      

不同的应用场景下，是否应该用相同的策略
{:.warning}    

# 1 综述

## 1.1 重复视频检测
1. [Large-scale near-duplicate web video search: Challenge and opportunity](http://vireo.cs.cityu.edu.hk/tansong/icme09-oral.pdf)    
*2009* [paper](http://vireo.cs.cityu.edu.hk/tansong/icme09-oral.pdf)    

1. [Million-scale Near-duplicate Video Retrieval System](http://www.cs.cmu.edu/~caiyang/papers/msndvr-cai-11.pdf)    
*2011-12* [paper](http://www.cs.cmu.edu/~caiyang/papers/msndvr-cai-11.pdf)    

1. [Near-Duplicate Video Retrieval: Current Research and Future Trends](http://vireo.cs.cityu.edu.hk/papers/a44-liu.pdf)    
*2013-08* [paper](http://vireo.cs.cityu.edu.hk/papers/a44-liu.pdf)    
使用了一款视频编辑软件；阐述了全局特征的劣势——忽略了中间物体；        

1. [Survey on Web Scale Based Near Duplicate Video Retrieval](https://pdfs.semanticscholar.org/c6b0/0a76cb8c540b4824369ddbf7def551720394.pdf)   
*2016* [paper](https://pdfs.semanticscholar.org/c6b0/0a76cb8c540b4824369ddbf7def551720394.pdf)    

1. [视频拷贝检测方法综述](http://crad.ict.ac.cn/CN/article/downloadArticleFile.do?attachType=PDF&id=3395)    
*2017-04* 复旦·计算机 姜育刚 [paper](http://crad.ict.ac.cn/CN/article/downloadArticleFile.do?attachType=PDF&id=3395)    
全方位的概述；    

1. [GVoS: A General System for Near-Duplicate Video Related Applications on Storm](http://net.pku.edu.cn/~cuibin/Papers/2017%20TOIS.pdf)    
*2017* [paper](http://net.pku.edu.cn/~cuibin/Papers/2017%20TOIS.pdf)    

1. [A Systematic Review of Near Duplicate Video Retrieval Techniques](https://acadpubl.eu/hub/2018-118-24/3/569.pdf)    
*2018-05-27* [paper](https://acadpubl.eu/hub/2018-118-24/3/569.pdf)    
>太简单，就是一个粗糙的博客；没有思考性的东西，也缺乏大量实验比对；图表模糊，不合格；     

## 1.2 拷贝检测

1. [Video Copy Detection: a Comparative Study](https://www.irisa.fr/vista/Papers/2007_civr_law-to.pdf)   
*2007* [paper](https://www.irisa.fr/vista/Papers/2007_civr_law-to.pdf)    

1. [A Survey On Video Forgery Detection](http://cn.arxiv.org/abs/1503.00843)    
*2015-03-03* [paper](https://arxiv.org/abs/1503.00843)   

1. [Recent advances in content based video copy detection](http://cn.arxiv.org/abs/1610.09087)    
*2016-10-28* [paper](https://arxiv.org/abs/1610.09087)   

## 1.3 视频签名
1. [Video Content Identification Using Video Signature: Survey](https://pdfs.semanticscholar.org/772a/ac1375c51bd984ac400c2bc4ccedd5fa0b43.pdf)    
*2017-07* [paper](https://pdfs.semanticscholar.org/772a/ac1375c51bd984ac400c2bc4ccedd5fa0b43.pdf)   

## 1.4 基于内容的视频检索
1. [Content based Video Retrieval: A Survey](https://pdfs.semanticscholar.org/379e/b29b015daa3fac6e0de2f6132733f16d46c7.pdf)    
*2015-01* [paper](https://pdfs.semanticscholar.org/379e/b29b015daa3fac6e0de2f6132733f16d46c7.pdf)     

1. [FIVR: Fine-grained Incident Video Retrieval](http://cn.arxiv.org/abs/1809.04094)    
*2018-09-11* [paper](https://arxiv.org/abs/1809.04094)   
发布了新数据集  FIVR-200K；     

1. [Interactive video retrieval in the age of deep learning](http://www.icmr2019.org/wp-content/uploads/2019/05/ICMR_tutorial_Interactive-video-retrieval-in-the-age-of-deep-learning.pdf)     
ICMR 2019 toturial *2019* [paper](http://www.icmr2019.org/wp-content/uploads/2019/05/ICMR_tutorial_Interactive-video-retrieval-in-the-age-of-deep-learning.pdf)    

## 1.5 跨模态视频检索

## 1.6 版权保护
1. [DETECTING DIGITAL COPYRIGHT VIOLATIONS ON THE INTERNET](http://infolab.stanford.edu/~shiva/Pubs/thesis.pdf)    
*1999* [paper](http://infolab.stanford.edu/~shiva/Pubs/thesis.pdf)    

# 2 理论

# 3 技术点
## 3.1 [关键帧](/cv/retrieval/2019/05/22/foundation.html)
`keyframe extract` · `shot boundary detection`;      

## 3.2 特征提取
>包括**低层特征**：颜色、边缘、纹理、动作；    
**中级特征**：运动轨迹、物体颜色；    
**高级特征**：；    

`feature extract` · `video fingerprinting` · `video DNA` · `video signature` · `video hash` · `video content-based watermarking`;          

### 3.2.1 [帧特征](/cv/retrieval/2019/05/22/foundation.html#31-特征提取)

### 3.2.2 视频特征
1. [Video Shot Characterization∗](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.99.7150&rep=rep1&type=pdf)     
[paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.99.7150&rep=rep1&type=pdf)    

1. [Deep Video Hashing](http://ivg.au.tsinghua.edu.cn/paper/2017_Deep%20video%20hashing.pdf)     
*2016* [paper](http://ivg.au.tsinghua.edu.cn/paper/2017_Deep%20video%20hashing.pdf)     


### 3.2.3 多帧融合
#### 3.2.3.1 聚类
1. [Towards effective indexing for very large video sequence database](http://staff.itee.uq.edu.au/zxf/_papers/SIGMOD05.pdf)      
对帧特征进行聚类；     

#### 3.2.3.2 降维
1. [UQLIPS: A Real-time Near-duplicate Video Clip Detection System](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.129.4492&rep=rep1&type=pdf)     
*2007* [paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.129.4492&rep=rep1&type=pdf)     
使用 PCA 对多帧视频特征降维得到视频特征；       

1. [Bounded coordinate system indexing for real-time video clip search](http://net.pku.edu.cn/~cuibin/Papers/2009-TOIS-vedio.pdf)      
*2009* [paper](http://net.pku.edu.cn/~cuibin/Papers/2009-TOIS-vedio.pdf)     
使用 PCA 对多帧视频特征降维得到视频特征；       

1. [Real-time Large Scale Near-duplicate Web Video Retrieval](#RLDW_LBP_BOW)     

1. [Visual word proximity and linguistics for semantic video indexing and near-duplicate retrieval](#SEMANTIC_BOW)      

#### 3.2.3.3 Fisher vector
1. [SHOT AGGREGATING STRATEGY FOR NEAR-DUPLICATE VIDEO RETRIEVAL](https://www.eurasip.org/Proceedings/Eusipco/Eusipco2015/papers/1570097527.pdf)    
*2015* [paper](https://www.eurasip.org/Proceedings/Eusipco/Eusipco2015/papers/1570097527.pdf)    
镜头聚合；     

#### 3.2.3.4 稀疏编码
1. Compact CNN Based Video Representation for Efficient Video Copy Detection    
*2016-12*      
CNN 提取特征，然后稀疏编码到固定长度；     

#### 3.2.3.4 其他

1. [Video histogram: A novel video signature for efficient Web video duplicate detection](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.91.1722&rep=rep1&type=pdf)     
*2007* [paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.91.1722&rep=rep1&type=pdf)    
相关直方图；    

1. [Practical elimination of near-duplicates from Web video search](http://vireo.cs.cityu.edu.hk/papers/mm07wu1.pdf)    
*2007* [paper](http://vireo.cs.cityu.edu.hk/papers/mm07wu1.pdf)     
累积直方图；     


### 3.2.4 视频编码
1. [Bit Rate-based H. 264 Video Copy Detection](https://jit.ndhu.edu.tw/article/download/1629/1637)     
*2018-01* [paper](https://jit.ndhu.edu.tw/article/download/1629/1637)     
无需解码视频，根据编码信息提取特征，可应对裁剪等拷贝操作；     

### 3.2.5 其他
1. [Submodular Video Hashing: A Unified Framework Towards Video Pooling and Indexing](http://www.ee.columbia.edu/~zgli/papers/MM12_VideoHashing.pdf)    
*2012* [paper](http://www.ee.columbia.edu/~zgli/papers/MM12_VideoHashing.pdf)    

1. [Unsupervised t-Distributed Video Hashing and Its Deep Hashing Extension](https://www.research.manchester.ac.uk/portal/files/58965691/final.pdf)    
*2016-12* [paper](https://www.research.manchester.ac.uk/portal/files/58965691/final.pdf)    

1. [Joint Audio-Video Fingerprint Media Retrieval Using Rate-Coverage Optimization](http://cn.arxiv.org/abs/1609.01331)    
*2016-09-05* [paper](https://arxiv.org/abs/1609.01331)   

1. [Unsupervised Deep Video Hashing via Balanced Code for Large-Scale Video Retrieval](https://eprints.lancs.ac.uk/id/eprint/130708/1/TIP_author_accepted_manuscript.pdf)    
*2018* [paper](https://eprints.lancs.ac.uk/id/eprint/130708/1/TIP_author_accepted_manuscript.pdf)    


## 3.3 检索
### 3.3.1 树形结构
1. [Prover: Probabilistic video retrieval using the Gauss-tree](https://www.dbs.ifi.lmu.de/Publikationen/Papers/icde-prover.pdf)     
*2007* [paper](https://www.dbs.ifi.lmu.de/Publikationen/Papers/icde-prover.pdf)     

### 3.3.2 VA-File
1. [A quantitative analysis and performance study for similarity-search methods in high-dimensional spaces](https://pdfs.semanticscholar.org/63ea/eb0c48175065ffd096aad10aed712c6d7bbb.pdf)     
*1998* [paper](https://pdfs.semanticscholar.org/63ea/eb0c48175065ffd096aad10aed712c6d7bbb.pdf)    

1. [ Trading quality for time with nearest-neighbor search](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.38.5809&rep=rep1&type=pdf)     
*2000* [paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.38.5809&rep=rep1&type=pdf)    

1. [iDistance: An Adaptive B+-Tree Based Indexing Method for Nearest Neighbor Search](https://people.eng.unimelb.edu.au/zr/publications/Tods05_idistance.pdf)     
*2007* [paper](https://people.eng.unimelb.edu.au/zr/publications/Tods05_idistance.pdf)     
iDistance;     

1. [Indexing High-Dimensional Data in Dual Distance Spaces: A Symmetrical Encoding Approach](https://openproceedings.org/2008/conf/edbt/ZhuangZLCY08.pdf)   
*2008* [paper](https://openproceedings.org/2008/conf/edbt/ZhuangZLCY08.pdf)    

1. Online Near-Duplicate Video Clip Detection and Retrieval: An Accurate and Fast System     
*2009*     

1. [Towards effective indexing for very large video sequence database](https://www.comp.nus.edu.sg/~ooibc/sigmod-video.pdf)     
*2005* [paper](https://www.comp.nus.edu.sg/~ooibc/sigmod-video.pdf)      
iDistance;    

### 3.3.3 Hash
1. [A Posteriori Multi-Probe Locality Sensitive Hashing](https://www.cs.princeton.edu/courses/archive/spring13/cos598C/p209-joly.pdf)     
*2008* [paper](https://www.cs.princeton.edu/courses/archive/spring13/cos598C/p209-joly.pdf)    
LSH: 提升准确度；    

1. [Quality and Efficiency in High Dimensional Nearest Neighbor Search](https://www.cse.ust.hk/~yike/sigmod09-lsb.pdf)    
*2009* [paper](https://www.cse.ust.hk/~yike/sigmod09-lsb.pdf)    
LSH: 改映射函数；    

1. An Image-Based Approach to Video Copy Detection With Spatio-Temporal Post-Filtering      
*2010*      
LSH 改进，词袋模型；    

1. Stochastic Multiview Hashing for Large-Scale Near-Duplicate Video Retrieval    
*2016-09-15*     
多视角随机 hash 提升检索精度和速度；     

### 3.3.4 倒排
<span id="SDP"></span>
1. [Scalable Detection of Partial Near-Duplicate Videos by Visual-Temporal Consistency](https://lms.comp.nus.edu.sg/sites/default/files/publication-attachments/acmmm09-tan.pdf)     
*2009* [paper](https://lms.comp.nus.edu.sg/sites/default/files/publication-attachments/acmmm09-tan.pdf)     
倒排，针对弱几何一致性做了改进；使用了图对齐；     

<span id='RLDW_LBP_BOW'></span>
1. [Real-time Large Scale Near-duplicate Web Video Retrieval](https://www.microsoft.com/en-us/research/wp-content/uploads/2010/10/MM10_Real-time-Large-Scale-Near-Duplicate-Web-Video-Identification.pdf)    
*2010* [paper](https://www.microsoft.com/en-us/research/wp-content/uploads/2010/10/MM10_Real-time-Large-Scale-Near-Duplicate-Web-Video-Identification.pdf)    
倒排，map+准确度+召回率；LBP 直方图相交；词袋模型+时序特征；     

## 3.4 时间对齐
### 3.4.1 滑窗  
1. [Compact video description for copy detection with precise temporal alignment](/cv/retrieval/2019/05/22/foundation.html#CVD_PTA)

### 3.4.2 树形结构
1. [Searching for repeated video sequences](http://www.cs.bilkent.edu.tr/~duygulu/papers/MIR2007.pdf)     
*2007* [paper](http://www.cs.bilkent.edu.tr/~duygulu/papers/MIR2007.pdf)     

### 3.4.3 图对齐
>[最大流](/algorithms/graph/2019/10/20/maximum-flow.html)      

1. [Scalable Detection of Partial Near-Duplicate Videos by Visual-Temporal Consistency](#SDP)    

1. Efficient mining of multiple partial near-duplicate alignments by temporal network       
*2010*     

1. [Video Hyperlinking: Libraries and Tools for Threading and Visualizing Large Video Collection](http://vireo.cs.cityu.edu.hk/papers/mm12-pang.pdf)     
*2012* [paper](http://vireo.cs.cityu.edu.hk/papers/mm12-pang.pdf) | [tool](https://sourceforge.net/projects/vireovh/)        

### 3.4.4 DL
1. [Temporal Cycle-Consistency Learning](http://cn.arxiv.org/abs/1904.07846)     
CVPR 2019 *2019-04-16* Google & Deepmind [paper](https://arxiv.org/abs/1904.07846) | [project](https://sites.google.com/view/temporal-cycle-consistency) | [tensorflow](https://github.com/google-research/google-research/tree/master/tcc)-official              

<span id="TA3N1"></span>
1. [Temporal Attentive Alignment for Video Domain Adaptation](http://cn.arxiv.org/abs/1905.10861)     
CVPR 2019 workshop *2019-05-26* [paper](https://arxiv.org/abs/1905.10861) | [pytorch](https://github.com/cmhungsteve/TA3N)-official           
与 [Temporal Attentive Alignment for Large-Scale Video Domain Adaptation](#TA3N2) 是同一团队；    

<span id="TA3N2"></span>
1. [Temporal Attentive Alignment for Large-Scale Video Domain Adaptation](http://cn.arxiv.org/abs/1907.12743)     
ICCV 2019 oral *2019-07-30* [paper](https://arxiv.org/abs/1907.12743) | [pytorch](https://github.com/cmhungsteve/TA3N)-official | [reddit](https://www.reddit.com/r/MachineLearning/comments/cn9eqd/research_temporal_attentive_alignment_for/)        
与 [Temporal Attentive Alignment for Video Domain Adaptation](#TA3N1) 是同一团队；    

### 3.4.5 其他
1. Efficient video copy detection via aligning video signature time series     
*2012*    
基于倾斜的时间对齐；对齐时引入了帧的插入、删除和替换策略；         

1. Video Copy Detection Based on Path Merging and Query Content Prediction     
*2015-10*    
基于图模型的路径合并；     

1. [Block based video alignment with linear time and space complexity](https://miliadis.github.io/papers/ICIP_video_align.pdf)    
ICIP *2016-09* [paper](https://miliadis.github.io/papers/ICIP_video_align.pdf)     
线性时间和空间复杂度；    

1. [Energy based fast event retrieval in video with temporal match kernel](http://home.ustc.edu.cn/~pjh/publications/ICIP2017Energy/paper.pdf)      
ICIP 2017 *2017-09* [paper](http://home.ustc.edu.cn/~pjh/publications/ICIP2017Energy/paper.pdf) |  [ppt](https://pdfs.semanticscholar.org/2d1d/b02a45e0a8152c14c80102211e2fec7ae999.pdf)     
乘积量化；    

1. Temporal Matching Kernel with Embedded Stability-Sensitive Filter      
*2017-12*     

1. [Circulant Temporal Encoding for Video Retrieval and Temporal Alignment](http://cn.arxiv.org/abs/1506.02588)     
*2015-06-08* [paper](https://arxiv.org/abs/1506.02588)     
使用复数处理特征，以达到精确匹配；    

1. [Burst-survive Temporal Matching Kernel with Fibonacci Periods](http://150.162.46.34:8080/icassp2019/ICASSP2019/pdfs/0002062.pdf)     
ICASSP 2019 *2019* [paper](http://150.162.46.34:8080/icassp2019/ICASSP2019/pdfs/0002062.pdf) | [python](https://github.com/fyang93/BURST)          


## 3.5 相似度度量
`sequence matching` · `similarity measure`    
`longest common sub-sequence`     

### 3.5.1 单帧

<span id='SEMANTIC_BOW'></span>
1. [Visual word proximity and linguistics for semantic video indexing and near-duplicate retrieval](http://www.ee.columbia.edu/~yjiang/publication/cviu09_yjiang.pdf)     
*2009* [paper](http://www.ee.columbia.edu/~yjiang/publication/cviu09_yjiang.pdf)    
在单帧的局部特征上用词袋模型，合成帧的全局特征，然后用 EMD 算法计算距离；    


### 3.5.2 串
1. [A distance measure for video sequence similarity matching](http://www.cs.cuhk.edu.hk/~king/PUB/adjeroh98b.pdf)   
*1998* 香港中文 [paper](http://www.cs.cuhk.edu.hk/~king/PUB/adjeroh98b.pdf)    
`distance measure` · `edit distance` · `sequence-tosequence matching` · `video string`     
**贡献**：在传统 edit distance 上融入了 vstring 的概念，并加入了三种操作来适应序列间的匹配；    
**说明**：vstring 负责序列数据的组织，edit distance 负责非等长数据之间的匹配；        
**算法特点**：对空间特征的鲁棒性要求较高；空间和时间复杂度较高；      
**疑问**：    
- vstring 怎么实现的；    
- edit distance 怎么实现的；     
>感觉 ED 系列的方法都是针对本身就相似的特征，使用串匹配的方法详细计算其相似度，所以更适合用来计算数据之间的相似性，而不适合用在拷贝检测相关问题中；因为拷贝检测问题是为了找出该视频副本，也就是副本和原视频越相似越好；而 ED 则是很客观地给出副本和原视频的不相似程度；      

### 3.5.3 对称匹配



## 3.6 多特征&多模态
1. [A MULTIMODAL VIDEO COPY DETECTION APPROACH WITH SEQUENTIAL PYRAMID MATCHING∗](https://projet.liris.cnrs.fr/imagine/pub/proceedings/ICIP-2011/papers/1569407283.pdf)    
*2011* [paper](https://projet.liris.cnrs.fr/imagine/pub/proceedings/ICIP-2011/papers/1569407283.pdf)    


# 4 应用方向
## 4.1 重复视频检测
>又叫视频拷贝检测，Content Based Copy Detection, CDBC: 作用等同于水印，主要用于版权保护；不同之处在与他是直接从视频本身提取一些特征；     

`Video Copy Detection` · `Video Forgery Detection` · `near-duplicate video detection`     


1. [Real time repeated video sequence identification](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.578.2230&rep=rep1&type=pdf)    
*2003* [paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.578.2230&rep=rep1&type=pdf)     


1. [Efficient Near-duplicate Detection and Sub-image Retrieval](http://www.cs.cmu.edu/~rahuls/pub/mm2004-pcasift-rahuls.pdf)     
*2004* [paper](http://www.cs.cmu.edu/~rahuls/pub/mm2004-pcasift-rahuls.pdf)    
哈希；   

1. [A Framework for Handling Spatiotemporal Variations in Video Copy Detection](http://mclab.cs.ccu.edu.tw/files/ken2585699/A%20Framework%20for%20Handling%20Spatiotemporal%20Variations%20in%20Video%20Copy%20Detection/A%20Framework%20for%20Handling%20Spatiotemporal%20Variations%20in%20Video%20Copy%20Detection.rar)   
*2008* [rar](http://mclab.cs.ccu.edu.tw/files/ken2585699/A%20Framework%20for%20Handling%20Spatiotemporal%20Variations%20in%20Video%20Copy%20Detection/A%20Framework%20for%20Handling%20Spatiotemporal%20Variations%20in%20Video%20Copy%20Detection.rar)    

1. [Scale-Rotation Invariant Pattern Entropy for Keypoint-based Near-Duplicate Detection](http://vireo.cs.cityu.edu.hk/papers/tip09_zhao.pdf)    
*2009* [paper](http://vireo.cs.cityu.edu.hk/papers/tip09_zhao.pdf)    


1. [Realtime near duplicate elimination for web video search with content and context](http://vireo.cs.cityu.edu.hk/papers/TMM_Context_wuxiao.pdf)    
*2009* [paper](http://vireo.cs.cityu.edu.hk/papers/TMM_Context_wuxiao.pdf)   

1. [Multiple feature hashing for real-time large scale near-duplicate video retrieval](https://nanopdf.com/download/multiple-feature-hashing-for-real-time-large-scale-near_pdf)     
*2011-12* [ppt](https://nanopdf.com/download/multiple-feature-hashing-for-real-time-large-scale-near_pdf)    
发布了数据集 [UQ_VIDEO](http://staff.itee.uq.edu.au/shenht/UQ_VIDEO/)     

1. [VCDB: A Large-Scale Database for Partial Copy Detection in Videos](http://www.yugangjiang.info/publication/eccv14-VCDB.pdf)    
*2014* [paper](http://www.yugangjiang.info/publication/eccv14-VCDB.pdf)    
发布了数据集    


1. [Pattern-Based Near-Duplicate Video Retrieval and Localization on Web-Scale Videos](https://www.semanticscholar.org/paper/Pattern-Based-Near-Duplicate-Video-Retrieval-and-on-Chou-Chen/b0a2b8945c947816ff0efa5605016c5ab25ef6a8)   
*2015* [paper](https://www.semanticscholar.org/paper/Pattern-Based-Near-Duplicate-Video-Retrieval-and-on-Chou-Chen/b0a2b8945c947816ff0efa5605016c5ab25ef6a8)    

1. [Near-Duplicate Video Detection Based on an Approximate Similarity Self-Join Strategy](https://hal.inria.fr/hal-01305691/document)    
*2016-04* [paper](https://hal.inria.fr/hal-01305691/document)    

1. [Near Duplicate Video Retrieval using Spatio Temporal Approach with Multifeature Mechanism](http://www.ijirset.com/upload/2016/june/174_Near.pdf)    
*2016-06* [paper](http://www.ijirset.com/upload/2016/june/174_Near.pdf)    

1. [Detecting near-duplicate videos by aggregating features from intermediate CNN layers](https://www.researchgate.net/publication/221572367_Detection_and_location_of_near-duplicate_video_sub-clips_by_finding_dense_subgraphs)    
*2016-08* [paper](https://www.researchgate.net/publication/221572367_Detection_and_location_of_near-duplicate_video_sub-clips_by_finding_dense_subgraphs) | [tensorflow](https://github.com/Chinmay26/Near-Duplicate-Video-Detection)        

1. [Stochastic Multiview Hashing for Large-Scale Near- Duplicate Video Retrieval](https://www.research.manchester.ac.uk/portal/files/46115431/Manuscript_final_with_bios.pdf)    
*2017-01* [paper](https://www.research.manchester.ac.uk/portal/files/46115431/Manuscript_final_with_bios.pdf)    
镜头边界检测，哈希，汉明距离，map；     

1. [Near-Duplicate Video Retrieval with Deep Metric Learning](http://openaccess.thecvf.com/content_ICCV_2017_workshops/papers/w5/Kordopatis-Zilos_Near-Duplicate_Video_Retrieval_ICCV_2017_paper.pdf)         
ICCV 2017 [paper](http://openaccess.thecvf.com/content_ICCV_2017_workshops/papers/w5/Kordopatis-Zilos_Near-Duplicate_Video_Retrieval_ICCV_2017_paper.pdf)     

1. [Multiscale video sequence matching for near-duplicate detection and retrieval](http://www.jdl.link/doc/2011/2019110_Multiscale%20video%20sequence%20matching%20for%20near-duplicate%20detection%20and%20retrieval.pdf)     
*2018-05* [paper](http://www.jdl.link/doc/2011/2019110_Multiscale%20video%20sequence%20matching%20for%20near-duplicate%20detection%20and%20retrieval.pdf)    

1. [A Coarse-to-fine Deep Convolutional Neural Network Framework for Frame Duplication Detection and Localization in Forged Videos](http://cn.arxiv.org/abs/1811.10762)    
*2018-11-27* [paper](https://arxiv.org/abs/1811.10762)   


1. [Partial Copy Detection in Videos: A Benchmark and An Evaluation of Popular Methods](http://yugangjiang.info/publication/TBD-VCDB.pdf)   
*2016-03-01* [paper](http://yugangjiang.info/publication/TBD-VCDB.pdf)   
公开 VCDB 数据集，有 10 万条视频，9000 对；   

1. [Feature statistical retrieval applied to content-based copy identification](https://www-sop.inria.fr/members/Alexis.Joly/ajolyICIP04.pdf)     
*2004* [paper](https://www-sop.inria.fr/members/Alexis.Joly/ajolyICIP04.pdf)    
兴趣点签名，对打数据检索高效；   

1. [Efficient and Effective Video Copy Detection Based on Spatiotemporal Analysis](https://www.iis.sinica.edu.tw/papers/song/15904-F.pdf)    
*2007* [paper](https://www.iis.sinica.edu.tw/papers/song/15904-F.pdf)   

1. [Scalable mining of large video databases using copy detection](http://cedric.cnam.fr/~crucianm/src/poullot08scalable.pdf)   
*2008* [paper](http://cedric.cnam.fr/~crucianm/src/poullot08scalable.pdf)   

1. [A compact, effective descriptor for video copy detection](http://www.csie.ntnu.edu.tw/~myeh/papers/mm09.pdf)   
*2009* [paper](http://www.csie.ntnu.edu.tw/~myeh/papers/mm09.pdf)    

1. [Video Copy Detection by Fast Sequence Matching ](http://lbmedia.ece.ucsb.edu/resources/ref/civr09.pdf)    
*2009* [paper](http://lbmedia.ece.ucsb.edu/resources/ref/civr09.pdf)    

1. [A PatchMatch-based Dense-field Algorithm for Video Copy-Move Detection and Localization](http://cn.arxiv.org/abs/1703.04636)    
*2017-03-14* [paper](https://arxiv.org/abs/1703.04636)    
发布了新的数据集；     

1. [Simple Yet Efficient Content Based Video Copy Detection](http://cn.arxiv.org/abs/1804.07019)   
*2018-04-19* [paper](https://arxiv.org/abs/1804.07019)   

1. [Geometrically robust video hashing based on ST-PCT for video copy](https://link.springer.com/article/10.1007/s11042-019-7513-8)     
*2019-04-08*    

## 4.2 签名验证
1. [Online Signature Verification Based on Writer Specific Feature Selection and Fuzzy Similarity Measure](http://cn.arxiv.org/abs/1905.08574)   
CVPR 2019 (Applications to Media Forensics) *2019-05-21* [paper](https://arxiv.org/abs/1905.08574)   


## 4.3 基于内容的视频检索
>Content Based Video retrieval, CBVR: 用于相似场景检测；    

1. [A Fully Automated Content-Based Video Search Engine Supporting Spatiotemporal Queries](https://pdfs.semanticscholar.org/ad44/ffbad45b2de2147585016e5272a7d745cb57.pdf)     
*1998* [paper](https://pdfs.semanticscholar.org/ad44/ffbad45b2de2147585016e5272a7d745cb57.pdf)     

1. [Retrieval of News Video using Video Sequence Matching](https://lms.comp.nus.edu.sg/sites/default/files/publication-attachments/mmm05-young.pdf)    
*2005* [paper](https://lms.comp.nus.edu.sg/sites/default/files/publication-attachments/mmm05-young.pdf)    

1. [FIVR: Fine-grained Incident Video Retrieval](https://arxiv.org/abs/1809.04094)    
*2018-09-11* [paper](https://arxiv.org/abs/1809.04094)    

1. [Use What You Have: Video Retrieval Using Representations From Collaborative Experts](http://cn.arxiv.org/abs/1907.13487)    
BMVC 2019 *2019-07-31* [paper](https://arxiv.org/abs/1907.13487) | [pytorch](https://github.com/albanie/collaborative-experts)-official       

## 4.4 重定位
>找到给定视频在目标视频中的位置；     

`video relocation`     

1. [AVA: A Video Dataset of Spatio-temporally Localized Atomic Visual Actions](http://cn.arxiv.org/abs/1705.08421)     
CVPR 2018 *2018-05-23* [paper](https://arxiv.org/abs/1705.08421) | [AVA](https://research.google.com/ava/)-dataset         


1. [Video Re-localization](http://cn.arxiv.org/abs/1808.01575)    
ECCV 2018 *2018-08-05* 腾讯 AI Lab + 美国罗切斯特大学 [paper](https://arxiv.org/abs/1808.01575) | [tensorflow](https://github.com/fengyang0317/video_reloc)-official        
重组ActivityNet数据集视频，生成了一个符合研究需求的新数据集，并提出一种交叉过滤的双线性匹配模型；        

1. [Spatio-temporal Video Re-localization by Warp LSTM](http://cn.arxiv.org/abs/1905.03922)     
*2019-05-10* [paper](https://arxiv.org/abs/1905.03922)     


## 4.5 跨模态检索
`multi-modal hashing` · `cross-modal retrieval`；    
`siam-network`；    
`Zero-Example Video Retrieval` · `Text-Video Retrieval`；     
`Video-Music Retrieval`；    

| 年份 | AAAI | ICML | NIPS | CVPR | ICCV | ECCV |
| --- | --- | --- | --- | --- | --- | --- |
| 2019 | 2 | 0 |  | 1 |  |  |
| 2018 | 0 |  | 0 | 0 |  | 0 |
| 2017 | 1 |  |  | 0 | 0 |  |
| 2016 | 1 |  |  | 0 |  |  |
| 2015 | 0 |  |  | 1 | 0 |  |
| 2014 | 0 |  |  | 0 |  |  |
| 2013 | 0 |  |  | 0 | 0 |  |


1. [一种多模态融合的网络视频相关性度量方法](http://html.rhhz.net/tis/html/20160311.htm)    
1. [多模态视频分析技术研究与应用](https://www.jishuwen.com/d/2FPy#tuit)    
1. [优酷在多模态内容理解上的研究及应用](https://www.infoq.cn/article/xgP_eyfidAA2l5ShcCPp)     

### 4.5.1 跨模态

1. [Coupled CycleGAN: Unsupervised Hashing Network for Cross-Modal Retrieval](http://cn.arxiv.org/abs/1903.02149)    
AAAI 2019 *2019-03-06* [paper](https://arxiv.org/abs/1903.02149)     
UCH： 为了解决跨模态散列问题，使用 GAN 将特征提取和哈希连接起来；       



### 4.5.2 图片
#### 4.5.2.1 [行人重识别](/cv/human/human_reid/2019/05/14/foundation.html#352-视频)    
#### 4.5.2.2 商品检索
1. [Video2Shop: Exactly Matching Clothes in Videos to Online Shopping Images](http://cn.arxiv.org/abs/1804.05287)  
CVPR 2017 *2018-04-14* 西南交大、阿里巴巴 [paper](https://arxiv.org/abs/1804.05287)     
**AsymNet**: 用 FasterRCNN 检测出物体，然后进行比对；          

### 4.5.3 [文本](/video/video_caption/2019/08/23/foundation.html#4-零样本检索)

#### 4.5.3.1 广告植入
>根据输入的关键词，给出视频中与之呼应的情景片段；    


### 4.5.4 音频

1. [Content-Based Video-Music Retrieval Using Soft Intra-Modal Structure Constraint](http://cn.arxiv.org/abs/1704.06761)  
*2017-04-22* [paper](https://arxiv.org/abs/1704.06761) | [示例](https://youtu.be/ZyINqDMo3Fg) | [tensorflow](https://github.com/csehong/VM-NET)-official    


1. [Cross-modal Embeddings for Video and Audio Retrieval](http://cn.arxiv.org/abs/1801.02200)  
*2018-01-07* [paper](https://arxiv.org/abs/1801.02200) | [Youtube-8m](https://github.com/surisdi/youtube-8m)-训练   



-------------------  
[End](#head)
{:.warning}  


# 附录
## A 参考资料
1. [Cross-Modal Retrieval](https://paperswithcode.com/task/cross-modal-retrieval)-paper_with_code     
1. [InVID H2020 Project](https://zenodo.org/communities/invid-h2020/?page=1&size=20)    
1. [Multiple feature hashing for real-time large scale near-duplicate video retrieval](https://scite.ai/reports/multiple-feature-hashing-for-real-time-JX3G1Y)-引用文献     
1. [scinapse](https://scinapse.io/papers/2165798132)    
1. [video-retrieval](https://github.com/topics/video-retrieval)-github    

## B 报告
1. ICIP 2017 [Near-Duplicate Video Detection Exploiting Noise Residual Traces](https://pdfs.semanticscholar.org/e604/9608e35f9633bb3c2cf50896f2d26d29a9cd.pdf)    
1. [Introduction to video hashing](http://signal.ee.psu.edu/VideoHashing_Version4.pdf)-limu      

## C 数据集

重复视频检测：    

| 名称 | 类型 | 数量(训练/测试) | 说明 | 发布日期 |
| --- | --- | --- | --- | --- |
| [TRECVID](https://trecvid.nist.gov/) & [data](https://www-nlpir.nist.gov/projects/trecvid/trecvid.data.html) |  |  | 著名的视频拷贝检测竞赛 | 2001~2019 |
| [CC_WEB_VIDEO](http://vireo.cs.cityu.edu.hk/webvideo/) |  |  | 包含颜色亮度变换，画面编辑和拼接 | 2007 |
| [MuscleVCD ST1](https://www.video-comparer.com/product-benchmark.php) |  |  |  |  |
| [UQ_VIDEO](http://staff.itee.uq.edu.au/shenht/UQ_VIDEO/) |  | 169,952 | 查询视频 400 个，检索视频 20 万；单个视频对应的检索视频最多 1000 个；<br>提取到的关键帧有 3,305,525 个；<br>共 15G； | 2011 |
| [Copy-move forgeries dataset](https://sites.google.com/site/rewindpolimi/downloads/datasets/video-copy-move-forgeries-dataset) |  |  |  |  |
| [VCDB](http://www.yugangjiang.info/research/VCDB/) |  |  | 8G | 2014 |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


## D 开源项目
1. [ThreatExchange](https://developers.facebook.com/docs/threat-exchange/v4.0)    
[code](https://github.com/facebook/ThreatExchange) | [TMK + PDQF](https://github.com/facebook/ThreatExchange/tree/master/hashing/tmk)-相似视频识别 | [PDQ](https://github.com/facebook/ThreatExchange/tree/master/hashing/pdq)-相似图片识别       

## E 研究员
1. [OLIVES Research](https://ghassanalregib.info/)、[github](https://github.com/olivesgatech)       
