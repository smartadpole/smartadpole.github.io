---
layout: article
title:  "「论文解读」Fully Supervised Speaker Diarization"
date:   2019-01-02 10:06:40 +0800
key: fully-supervise-sd-reading-20190102
aside:
  toc: true
category: [Audio, VoiceprintAnalysis, PaperReading]
---

这一论文的主要贡献如下：

提出了无界间隔状态(. Unbounded interleaved-state )RNN，一个可以通过监督学习训练的对于时变数据分割和聚类的算法；

全监督的说话人分类系统；

数据集上误差提升到7.6%；

提高线上任务表现。

unbounded interleaved-state recurrent neural network (UIS-RNN)的聚类算法来提高了模型的性能  

以 92% 的准确率识别出每个人声音；  

数据集 NIST SRE 2000 CALLHOME，达到了7.6%的错误率，超过了其先前基于聚类方法（8.8%）和深度网络嵌入方法（9.9%）；  

只要开始发言，每个说话者都会建立一个属于他的 RNN（递归神经网络） 模型，然后在过程中，不断更新相应的 RNN 状态；  
