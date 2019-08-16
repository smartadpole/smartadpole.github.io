---
layout: article
title:  "「VIDEO」 检索资源汇总"
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
使用了一款视频编辑软件；    

1. [Survey on Web Scale Based Near Duplicate Video Retrieval](https://pdfs.semanticscholar.org/c6b0/0a76cb8c540b4824369ddbf7def551720394.pdf)   
*2016* [paper](https://pdfs.semanticscholar.org/c6b0/0a76cb8c540b4824369ddbf7def551720394.pdf)    

1. [视频拷贝检测方法综述](http://crad.ict.ac.cn/CN/article/downloadArticleFile.do?attachType=PDF&id=3395)    
*2017-04* 复旦·计算机 姜育刚 [paper](http://crad.ict.ac.cn/CN/article/downloadArticleFile.do?attachType=PDF&id=3395)    


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
1. [FIVR: Fine-grained Incident Video Retrieval](http://cn.arxiv.org/abs/1809.04094)    
*2018-09-11* [paper](https://arxiv.org/abs/1809.04094)   
发布了新数据集  FIVR-200K；     

## 1.5 跨模态视频检索

## 1.6 版权保护
1. [DETECTING DIGITAL COPYRIGHT VIOLATIONS ON THE INTERNET](http://infolab.stanford.edu/~shiva/Pubs/thesis.pdf)    
*1999* [paper](http://infolab.stanford.edu/~shiva/Pubs/thesis.pdf)    

# 2 理论

# 3 技术点
## 3.1 关键帧
`keyframe extract` · `shot boundary detection`;      

## 3.2 特征提取
>包括**低层特征**：颜色、边缘、纹理、动作；    
**中级特征**：运动轨迹、物体颜色；    
**高级特征**：；    

`feature extract` · `video fingerprinting` · `video DNA` · `video signature` · `video hash` · `video content-based watermarking`;          

### 3.2.1 帧特征提取
#### 3.2.1.1 传统
1. [Ordinal measures for visual correspondence](http://www1.cs.columbia.edu/CAVE/publications/pdfs/Bhat_TR95.pdf)    
*1996* [paper](http://www1.cs.columbia.edu/CAVE/publications/pdfs/Bhat_TR95.pdf)   
顺序度量 OM;    

1. [Ordinal measures for image correspondence](https://pdfs.semanticscholar.org/a431/2c7886c88cfae3bb8af9d75c2f91d700e466.pdf)    
*1998* [paper](https://pdfs.semanticscholar.org/a431/2c7886c88cfae3bb8af9d75c2f91d700e466.pdf)    
顺序度量 OM；     

1. [Robust video signature based on ordinal measure](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.69.8192&rep=rep1&type=pdf)   
*2004* [paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.69.8192&rep=rep1&type=pdf)   

1. [Aggregating local descriptors into a compact image representation](https://lear.inrialpes.fr/pubs/2010/JDSP10/jegou_compactimagerepresentation.pdf)    
*2010* [paper](https://lear.inrialpes.fr/pubs/2010/JDSP10/jegou_compactimagerepresentation.pdf)   

1. [Spatio–Temporal Transform Based Video Hashing](http://www.busim.ee.boun.edu.tr/~sankur/SankurFolder/SpatioTemporal_Hashing.pdf)    
*2006* [paper](http://www.busim.ee.boun.edu.tr/~sankur/SankurFolder/SpatioTemporal_Hashing.pdf)    
DCT + Hash;    

#### 3.2.1.2 DL
1. [Near-Duplicate Video Retrieval by Aggregating Intermediate CNN Layers](https://zenodo.org/record/240645/files/duplicate-video-retrieval.pdf?download=1)   
*2016-08* [paper](https://zenodo.org/record/240645/files/duplicate-video-retrieval.pdf?download=1) | [tensorflow](https://github.com/Chinmay26/Near-Duplicate-Video-Detection) | [caffe](https://github.com/MKLab-ITI/intermediate-cnn-features)       
CNN，map+准确ud+召回率；    

1. [Near-Duplicate Video Retrieval with Deep Metric Learning](http://openaccess.thecvf.com/content_ICCV_2017_workshops/papers/w5/Kordopatis-Zilos_Near-Duplicate_Video_Retrieval_ICCV_2017_paper.pdf)    
ICCV 2017 *2017-10-23* [paper](http://openaccess.thecvf.com/content_ICCV_2017_workshops/papers/w5/Kordopatis-Zilos_Near-Duplicate_Video_Retrieval_ICCV_2017_paper.pdf)   

#### 3.2.1.3 其他

1. [Submodular Video Hashing: A Unified Framework Towards Video Pooling and Indexing](http://www.ee.columbia.edu/~zgli/papers/MM12_VideoHashing.pdf)    
*2012* [paper](http://www.ee.columbia.edu/~zgli/papers/MM12_VideoHashing.pdf)    

1. [Unsupervised t-Distributed Video Hashing and Its Deep Hashing Extension](https://www.research.manchester.ac.uk/portal/files/58965691/final.pdf)    
*2016-12* [paper](https://www.research.manchester.ac.uk/portal/files/58965691/final.pdf)    

1. [Joint Audio-Video Fingerprint Media Retrieval Using Rate-Coverage Optimization](http://cn.arxiv.org/abs/1609.01331)    
*2016-09-05* [paper](https://arxiv.org/abs/1609.01331)   

1. [Unsupervised Deep Video Hashing via Balanced Code for Large-Scale Video Retrieval](https://eprints.lancs.ac.uk/id/eprint/130708/1/TIP_author_accepted_manuscript.pdf)    
*2018* [paper](https://eprints.lancs.ac.uk/id/eprint/130708/1/TIP_author_accepted_manuscript.pdf)    

### 3.2.2 时序特征提取

## 3.3 相似度度量
`sequence matching` · `similarity measure`    
`longest common sub-sequence`     

### 3.3.1 基于关键帧

### 3.3.2 基于序列
1. [A distance measure for video sequence similarity matching](http://www.cs.cuhk.edu.hk/~king/PUB/adjeroh98b.pdf)   
*1998* [paper](http://www.cs.cuhk.edu.hk/~king/PUB/adjeroh98b.pdf)    


# 4 应用方向
## 4.1 重复视频检测
`near-duplicate video detection`

1. [Efficient Near-duplicate Detection and Sub-image Retrieval](http://www.cs.cmu.edu/~rahuls/pub/mm2004-pcasift-rahuls.pdf)     
*2004* [paper](http://www.cs.cmu.edu/~rahuls/pub/mm2004-pcasift-rahuls.pdf)    
哈希；   

1. [A Framework for Handling Spatiotemporal Variations in Video Copy Detection](http://mclab.cs.ccu.edu.tw/files/ken2585699/A%20Framework%20for%20Handling%20Spatiotemporal%20Variations%20in%20Video%20Copy%20Detection/A%20Framework%20for%20Handling%20Spatiotemporal%20Variations%20in%20Video%20Copy%20Detection.rar)   
*2008* [rar](http://mclab.cs.ccu.edu.tw/files/ken2585699/A%20Framework%20for%20Handling%20Spatiotemporal%20Variations%20in%20Video%20Copy%20Detection/A%20Framework%20for%20Handling%20Spatiotemporal%20Variations%20in%20Video%20Copy%20Detection.rar)    

1. [Realtime near duplicate elimination for web video search with content and context](http://vireo.cs.cityu.edu.hk/papers/TMM_Context_wuxiao.pdf)    
*2009* [paper](http://vireo.cs.cityu.edu.hk/papers/TMM_Context_wuxiao.pdf)   

1. [Real-time Large Scale Near- duplicate Web Video Retrieval](https://www.microsoft.com/en-us/research/wp-content/uploads/2010/10/MM10_Real-time-Large-Scale-Near-Duplicate-Web-Video-Identification.pdf)    
*2010* [paper](https://www.microsoft.com/en-us/research/wp-content/uploads/2010/10/MM10_Real-time-Large-Scale-Near-Duplicate-Web-Video-Identification.pdf)    
倒排，map+准确度+召回率；     

1. [Multiple feature hashing for real-time large scale near-duplicate video retrieval](https://nanopdf.com/download/multiple-feature-hashing-for-real-time-large-scale-near_pdf)     
*2011-12* [ppt](https://nanopdf.com/download/multiple-feature-hashing-for-real-time-large-scale-near_pdf)    
发布了数据集 [UQ_VIDEO](http://staff.itee.uq.edu.au/shenht/UQ_VIDEO/)     

1. [VCDB: A Large-Scale Database for Partial Copy Detection in Videos](http://www.yugangjiang.info/publication/eccv14-VCDB.pdf)    
*2014* [paper](http://www.yugangjiang.info/publication/eccv14-VCDB.pdf)    
发布了数据集    

1. [SHOT AGGREGATING STRATEGY FOR NEAR-DUPLICATE VIDEO RETRIEVAL](https://www.eurasip.org/Proceedings/Eusipco/Eusipco2015/papers/1570097527.pdf)    
*2015* [paper](https://www.eurasip.org/Proceedings/Eusipco/Eusipco2015/papers/1570097527.pdf)    

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


## 4.2 视频拷贝检测
>Content Based Copy Detection, CDBC: 作用等同于水印，主要用于版权保护；不同之处在与他是直接从视频本身提取一些特征；     

`Video Copy Detection` · `Video Forgery Detection`；    

`跟重复视频检测有什么区别`{:.warning}    

1. [Partial Copy Detection in Videos: A Benchmark and An Evaluation of Popular Methods](http://yugangjiang.info/publication/TBD-VCDB.pdf)   
[paper](http://yugangjiang.info/publication/TBD-VCDB.pdf)   
1. [Feature statistical retrieval applied to content-based copy identification](https://www-sop.inria.fr/members/Alexis.Joly/ajolyICIP04.pdf)     
*2004* [paper](https://www-sop.inria.fr/members/Alexis.Joly/ajolyICIP04.pdf)    
兴趣点签名，对打数据检索高效；   

1. [A New Approach to Image Copy Detection Based on Extended Feature Sets](https://www.iis.sinica.edu.tw/papers/song/3769-F.pdf)    
*2007* [paper](https://www.iis.sinica.edu.tw/papers/song/3769-F.pdf)   

1. [Efficient and Effective Video Copy Detection Based on Spatiotemporal Analysis](https://www.iis.sinica.edu.tw/papers/song/15904-F.pdf)    
*2007* [paper](https://www.iis.sinica.edu.tw/papers/song/15904-F.pdf)   

1. [Scalable mining of large video databases using copy detection](http://cedric.cnam.fr/~crucianm/src/poullot08scalable.pdf)   
*2008* [paper](http://cedric.cnam.fr/~crucianm/src/poullot08scalable.pdf)   

1. [A compact, effective descriptor for video copy detection](http://www.csie.ntnu.edu.tw/~myeh/papers/mm09.pdf)   
*2009* [paper](http://www.csie.ntnu.edu.tw/~myeh/papers/mm09.pdf)    

1. [Video copy detection by fast sequence matching](http://aifc2011.csie.ntnu.edu.tw/~myeh/papers/civr09.pdf)    
*2009* [paper](http://aifc2011.csie.ntnu.edu.tw/~myeh/papers/civr09.pdf)   

1. [Video Copy Detection by Fast Sequence Matching ](http://lbmedia.ece.ucsb.edu/resources/ref/civr09.pdf)    
*2009* [paper](http://lbmedia.ece.ucsb.edu/resources/ref/civr09.pdf)    

1. [A PatchMatch-based Dense-field Algorithm for Video Copy-Move Detection and Localization](http://cn.arxiv.org/abs/1703.04636)    
*2017-03-14* [paper](https://arxiv.org/abs/1703.04636)    
发布了新的数据集；     

1. [Simple Yet Efficient Content Based Video Copy Detection](http://cn.arxiv.org/abs/1804.07019)   
*2018-04-19* [paper](https://arxiv.org/abs/1804.07019)   

1. Geometrically robust video hashing based on ST-PCT for video copy     

## 4.3 基于内容的视频检索
>Content Based Video retrieval, CBVR: 用于相似场景检测；    

1. [Retrieval of News Video using Video Sequence Matching](https://lms.comp.nus.edu.sg/sites/default/files/publication-attachments/mmm05-young.pdf)    
*2005* [paper](https://lms.comp.nus.edu.sg/sites/default/files/publication-attachments/mmm05-young.pdf)    

## 4.4 跨模态检索
### 4.4.1 图片

1. [Video2Shop: Exactly Matching Clothes in Videos to Online Shopping Images](http://cn.arxiv.org/abs/1804.05287)  
CVPR 2017 *2018-04-14* 西南交大、阿里巴巴 [paper](https://arxiv.org/abs/1804.05287)     
**AsymNet**: 用 FasterRCNN 检测出物体，然后进行比对；          

### 4.4.2 文本
1. [Dual Encoding for Zero-Example Video Retrieval](http://cn.arxiv.org/abs/1809.06181)    
CVPR 2019 *2018-09-17* [paper](https://arxiv.org/abs/1809.06181) | [pytorch](https://github.com/danieljf24/dual_encoding)-offical | [解读](/video/video_retrieval/paper_reading/2019/06/23/Dual-Encoding-for-Zero-Example-Video-Retrieval-reading.html)    

1. [Joint Embeddings with Multimodal Cues for Video-Text Retrieval](https://vcg.ece.ucr.edu/sites/g/files/rcwecm2661/files/2019-03/IJMIR_Camera_Ready.pdf)     
*2018* [paper](https://vcg.ece.ucr.edu/sites/g/files/rcwecm2661/files/2019-03/IJMIR_Camera_Ready.pdf)    


### 4.4.3 音频

1. [Content-Based Video-Music Retrieval Using Soft Intra-Modal Structure Constraint](http://cn.arxiv.org/abs/1704.06761)  
*2017-04-22* [paper](https://arxiv.org/abs/1704.06761) | [示例](https://youtu.be/ZyINqDMo3Fg) | [tensorflow](https://github.com/csehong/VM-NET)-offical    


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

## B 报告
1. ICIP 2017 [Near-Duplicate Video Detection Exploiting Noise Residual Traces](https://pdfs.semanticscholar.org/e604/9608e35f9633bb3c2cf50896f2d26d29a9cd.pdf)    
1. [Introduction to video hashing](http://signal.ee.psu.edu/VideoHashing_Version4.pdf)-limu      

## C 数据集

重复视频检测：    

| 名称 | 类型 | 数量(训练/测试) | 说明 | 发布日期 |
| --- | --- | --- | --- | --- |
| [TRECVID](https://trecvid.nist.gov/) & [data](https://www-nlpir.nist.gov/projects/trecvid/trecvid.data.html) |  |  |  | 2001~2019 |
| [CC_WEB_VIDEO](http://vireo.cs.cityu.edu.hk/webvideo/) |  |  | 包含颜色亮度变换，画面编辑和拼接 | 2007 |
| [MuscleVCD ST1](https://www.video-comparer.com/product-benchmark.php) |  |  |  |  |
| [UQ_VIDEO](http://staff.itee.uq.edu.au/shenht/UQ_VIDEO/) |  | 169,952 | 查询视频 400 个，检索视频 20 万；单个视频对应的检索视频最多 1000 个；<br>提取到的关键帧有 3,305,525 个；<br>共 15G； | 2011 |
| [Copy-move forgeries dataset](https://sites.google.com/site/rewindpolimi/downloads/datasets/video-copy-move-forgeries-dataset) |  |  |  |  |
| [VCDB](http://www.yugangjiang.info/research/VCDB/) |  |  | 8G | 2014 |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


## D 开源项目
1. [ThreatExchange](https://developers.facebook.com/docs/threat-exchange/v4.0): [code](https://github.com/facebook/ThreatExchange) | [TMK + PDQF](https://github.com/facebook/ThreatExchange/tree/master/hashing/tmk)-相似视频识别 | [PDQ](https://github.com/facebook/ThreatExchange/tree/master/hashing/pdq)-相似图片识别       
