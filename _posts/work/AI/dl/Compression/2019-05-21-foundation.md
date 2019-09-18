---
layout: article
title:  "「DL」 模型压缩资源汇总"
date:   2019-05-21 09:08:40 +0800
key: deep-compression-foundation-20190521
aside:
  toc: true
category: [DL, compression]
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

# 6 权值量化
1. [Integer Discrete Flows and Lossless Compression](http://cn.arxiv.org/abs/1905.07376)   
*2019-05-17* [paper](https://arxiv.org/abs/1905.07376)   

1. [Weight Normalization based Quantization for Deep Neural Network Compression](http://cn.arxiv.org/abs/1907.00593)   
*2019-07-01* [paper](https://arxiv.org/abs/1907.00593)   

# 7 知识蒸馏
1. [Dream Distillation: A Data-Independent Model Compression Framework](http://cn.arxiv.org/abs/1905.07072)   
ICML 2019 workshop *2019-05-17* [paper](https://arxiv.org/abs/1905.07072)   
$\bullet \bullet$   
无需重新训练的模型压缩方法；   

1. [AVD: Adversarial Video Distillation](http://cn.arxiv.org/abs/1907.05640)    
*2019-07-12* [paper](https://arxiv.org/abs/1907.05640)     


# 8 其他
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
