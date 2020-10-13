---
layout: article
title:  "「DL」 模型量化概述"
date:   2020-10-10 14:08:40 +0800
key: quantization
aside:
  toc: true
category: [AI, DL, compression]
---
<span id='head'></span>  

>在推理中使用低精度(FP16、INT8 、二值网络、三值网络)表示，取代原有精度(FP32)；     

<!--more-->

# 1 工具

| 工具 | 说明 |
| --- | --- |
| TensorRT | 是 NVIDIA 提出的神经网络推理(Inference)引擎, 支持训练后 8BIT 量化, 它使用基于交叉熵的模型量化算法, 通过最小化两个分布的差异程度来实现；  |
| [Pytorch](/ai/dl/compression/2020/10/10/quantization-pytorch.html) | pytorch 1.3 开始已经支持量化功能, 基于 QNNPACK 实现, 支持训练后量化, 动态量化和量化感知训练等技术；  |
| Distiller | 是 Intel 基于 Pytorch 开源的模型优化工具, 自然也支持 Pytorch 中的量化技术； |
| NNI | 微软的 NNI 集成了多种量化感知的训练算法, 并支持 PyTorch/TensorFlow/MXNet/Caffe2 等多个开源框架； |


-------------------  
[End](#head)
{:.warning}  

# 附录
## A 参考资料
1. lartpang. Some Tricks of PyTorch[EB/OL]. <https://github.com/lartpang/PyTorchTricks>. -/2020-10-10.     
1. 有三AI. 当前模型量化有哪些可用的开源工具？[EB/OL]. <https://cloud.tencent.com/developer/article/1559658>. 2019-12-18/2020-10-10.    
1. 商汤科技SenseTime. 模型量化了解一下？[EB/OL]. <https://zhuanlan.zhihu.com/p/132561405>. 2020-04-17/2020-10-13.    
内容很丰富，有很多指导性观点；    

1. [pytorch MobileNet-v2-pruning](https://github.com/wlguan/MobileNet-v2-pruning)    
