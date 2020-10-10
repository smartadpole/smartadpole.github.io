---
layout: article
title:  "「DL」 模型压缩资源汇总"
date:   2019-05-21 09:08:40 +0800
key: deep-compression-foundation-20190521
aside:
  toc: true
category: [AI, DL, compression]
tags: 资源
---
<span id='head'></span>  


<!--more-->


# 1 综述
1. [Deep Compression: Compressing Deep Neural Network with Pruning, Trained Quantization and Huffman Coding](https://arxiv.org/abs/1510.00149)   
ICLR 2016 oral *2015-10-01* [paper](https://arxiv.org/abs/1510.00149)    


# 2 理论
1. [Doctor of Crosswise: Reducing Over-parametrization in Neural Networks](http://cn.arxiv.org/abs/1905.10324)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10324)   

1. [NetTailor: Tuning the Architecture, Not Just the Weights](http://cn.arxiv.org/abs/1907.00274)   
CVPR 2019 *2019-06-29* [paper](https://arxiv.org/abs/1907.00274)   

# 3 剪枝
1. [FeTa: A DCA Pruning Algorithm with Generalization Error Guarantees](https://arxiv.org/abs/1803.04239)   
*2018-03-12* [paper](https://arxiv.org/abs/1803.04239)   

1. [Revisiting hard thresholding for DNN pruning](http://cn.arxiv.org/abs/1905.08793)   
*2019-05-21* [paper](https://arxiv.org/abs/1905.08793)   

1. [Dissecting Pruned Neural Networks](http://cn.arxiv.org/abs/1907.00262)   
*2019-01-29* [paper](https://arxiv.org/abs/1907.00262)   
修剪 resnet50，而不影响可解释性；    

# 5 低秩分解
1. [Learning Low-Rank Approximation for CNNs](http://cn.arxiv.org/abs/1905.10145)   
*2019-05-24* [paper](https://arxiv.org/abs/1905.10145)   

1. [Traned Rank Pruning for Efficient Deep Neural Networks](http://cn.arxiv.org/abs/1910.04576)     
NIPS 2019 workshop *2019-10-09* [paper](https://arxiv.org/abs/1910.04576)      
认为离线低秩分解误差太大，于是将其集成到训练过程；    

# 6 权值量化
1. [Integer Discrete Flows and Lossless Compression](http://cn.arxiv.org/abs/1905.07376)   
*2019-05-17* [paper](https://arxiv.org/abs/1905.07376)   

1. [Weight Normalization based Quantization for Deep Neural Network Compression](http://cn.arxiv.org/abs/1907.00593)   
*2019-07-01* [paper](https://arxiv.org/abs/1907.00593)   

1. [StatAssist & GradBoost: A Study on Optimal INT8 Quantization-aware Training from Scratch](http://cn.arxiv.org/abs/2006.09679)    
*2020-06-17* [paper](https://arxiv.org/abs/2006.09679) | [pytorch](https://github.com/clovaai/StatAssist-GradBoost)-official        

# 7 知识蒸馏
1. [Dream Distillation: A Data-Independent Model Compression Framework](http://cn.arxiv.org/abs/1905.07072)   
ICML 2019 workshop *2019-05-17* [paper](https://arxiv.org/abs/1905.07072)   
$\bullet \bullet$   
无需重新训练的模型压缩方法；   

1. [AVD: Adversarial Video Distillation](http://cn.arxiv.org/abs/1907.05640)    
*2019-07-12* [paper](https://arxiv.org/abs/1907.05640)     

1. [Cross-modal knowledge distillation for action recognition](http://cn.arxiv.org/abs/1910.04641)    
NIPS 2019 *2019-10-10* [paper](https://arxiv.org/abs/1910.04641)    
跨模态知识蒸馏（动作识别），使用交叉熵损失代替 KL 散度；认为其对于小数据集效果更好；   

# 8 嵌入式加速
1. [Closing the Accuracy Gap in an Event-Based Visual Recognition Task](http://cn.arxiv.org/abs/1906.08859)    
*2019-05-06* [paper](https://arxiv.org/abs/1906.08859)    

# 9 其他
1. [DARC: Differentiable ARchitecture Compression](http://cn.arxiv.org/abs/1905.08170)   
*2019-05-20* [paper](https://arxiv.org/abs/1905.08170)   

1. [Geometry of Deep Convolutional Networks](http://cn.arxiv.org/abs/1905.08922)   
*2019-05-21* [paper](https://arxiv.org/abs/1905.08922)   

1. [Deep Model Compression via Filter Auto-sampling](http://cn.arxiv.org/abs/1907.05642)   
*2019-07-12* [paper](https://arxiv.org/abs/1907.05642)    

1. [And the Bit Goes Down: Revisiting the Quantization of Neural Networks](http://cn.arxiv.org/abs/1907.05686)   
*2019-07-12* [paper](https://arxiv.org/abs/1907.05686)    
对 resnet 系列网络进行了压缩；    


-------------------  
[End](#head)
{:.warning}  

# 附录
## A 参考资料
1. EwenWanW. 神经网络压缩 剪枝 量化 嵌入式计算优化NCNN[EB/OL]. <https://blog.csdn.net/xiaoxiaowenqiang/article/details/80946522>. 2018-07-06/2019-09-18.     
1. 清水汪汪. 网络压缩论文整理(network compression)[EB/OL]. <https://www.cnblogs.com/zhonghuasong/p/7822572.html>. 2017-11-12/2019-02-17.    
