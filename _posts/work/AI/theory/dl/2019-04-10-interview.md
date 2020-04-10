---
layout: article
title:  "「DL」 深度学习问答"
date:   2019-04-10 01:20:40 +0800
key: dl-question
aside:
  toc: true
tags: 资源
category: [AI, DL]
sidebar:
  nav: INTERVIEW
---
<span id='head'></span>  


<!--more-->

**1 列举常见的一些范数及其应用场景，如 L0，L1，L2，L∞，Frobenius 范数**
{:.warning}
p39-p40 ；还有 p230-p236 有 regularization 的应用

**2 简单介绍一下贝叶斯概率与频率派概率，以及在统计中对于真实参数的假设。**
{:.warning}
p55

答：p67：3.10 上面那一段

**4 简单介绍一下 sigmoid，relu，softplus，tanh，RBF 及其应用场景**
{:.warning}
sigmoid 和 softplus 在 p67 页；全部的在 p193-p197

**5 Jacobian，Hessian 矩阵及其在深度学习中的重要性**
{:.warning}
p86-p92

**6 KL 散度在信息论中度量的是那个直观量**
{:.warning}
p74

**7 数值计算中的计算上溢与下溢问题，如 softmax 中的处理方式**
{:.warning}
p80-p81

**8 与矩阵的特征值相关联的条件数 (病态条件) 指什么，与梯度爆炸与梯度弥散的关系**
{:.warning}
p82;

**9 在基于梯度的优化问题中，如何判断一个梯度为 0 的零界点为局部极大值／全局极小值还是鞍点，Hessian 矩阵的条件数与梯度下降法的关系**
{:.warning}
p86-p92

**10 KTT 方法与约束优化问题，活跃约束的定义**
{:.warning}
p93-p95

**11 模型容量，表示容量，有效容量，最优容量概念**
{:.warning}
p111;p113;p114;p115

**12 正则化中的权重衰减与加入先验知识在某些条件下的等价性**
{:.warning}
p119;p138

**13 高斯分布的广泛应用的缘由**
{:.warning}
p63-p64

**14 最大似然估计中最小化 KL 散度与最小化分布之间的交叉熵的关系**
{:.warning}
p132

**15 在线性回归问题，具有高斯先验权重的 MAP 贝叶斯推断与权重衰减的关系，与正则化的关系**
{:.warning}
 p138-p139

**16 稀疏表示，低维表示，独立表示**
{:.warning}
p147

**17 列举一些无法基于地图 (梯度？) 的优化来最小化的代价函数及其具有的特点**
{:.warning}
p155 最顶一段

**18 在深度神经网络中，引入了隐藏层，放弃了训练问题的凸性，其意义何在**
{:.warning}
p191-192

**19 函数在某个区间的饱和与平滑性对基于梯度的学习的影响**
{:.warning}
p160

**20 梯度爆炸的一些解决办法**
{:.warning}
p302

答：p198

**22 在前馈网络中，深度与宽度的关系及表示能力的差异**
{:.warning}
p200-p201

**23 为什么交叉熵损失可以提高具有 sigmoid 和 softmax 输出的模型的性能，而使用均方误差损失则会存在很多问题。分段线性隐藏层代替 sigmoid 的利弊**
{:.warning}
p226;p226

**24 表示学习的发展的初衷？并介绍其典型例子: 自编码器**
{:.warning}
p3-p4;p4

**25 在做正则化过程中，为什么只对权重做正则惩罚，而不对偏置做权重惩罚**
{:.warning}
p230

**26 在深度学习神经网络中，所有的层中考虑使用相同的权重衰减的利弊**
{:.warning}
p230

**27 正则化过程中，权重衰减与 Hessian 矩阵中特征值的一些关系，以及与梯度弥散，梯度爆炸的关系**
{:.warning}
p231-234

**28 L1／L2 正则化与高斯先验／对数先验的 MAP 贝叶斯推断的关系**
{:.warning}
p234-p237

**29 什么是欠约束，为什么大多数的正则化可以使欠约束下的欠定问题在迭代过程中收敛**
{:.warning}
p239

**30 为什么考虑在模型训练时对输入 (隐藏单元／权重) 添加方差较小的噪声，与正则化的关系**
{:.warning}
p240-p243

**31 共享参数的概念及在深度学习中的广泛影响**
{:.warning}
p245;p253

**32 Dropout 与 Bagging 集成方法的关系，以及 Dropout 带来的意义与其强大的原因**
{:.warning}
p258-p268

**33 批量梯度下降法更新过程中，批量的大小与各种更新的稳定性关系**
{:.warning}
p279

**34 如何避免深度学习中的病态，鞍点，梯度爆炸，梯度弥散**
{:.warning}
p282-p293

**35.SGD 以及学习率的选择方法，带动量的 SGD 对于 Hessian 矩阵病态条件及随机梯度方差的影响**
{:.warning}
p294；p296-p300

**36 初始化权重过程中，权重大小在各种网络结构中的影响，以及一些初始化的方法；偏置的初始化**
{:.warning}
初始化权重：p301-p305；偏置初始化：p305-p306

**37 自适应学习率算法: AdaGrad，RMSProp，Adam 等算法的做法**
{:.warning}
AdaGrad:p307; RMSProp:p307-p308; Adam:p308-p309

**38 二阶近似方法: 牛顿法，共轭梯度，BFGS 等的做法**
{:.warning}
牛顿法：p310-p313; 共轭梯度: p313-p316; BFGS:p316-p317

**39.Hessian 的标准化对于高阶优化算法的意义**
{:.warning}
p318-p321

**40 卷积网络中的平移等变性的原因，常见的一些卷积形式**
{:.warning}
平移等变性：p338-p339；常见的一些卷积形式：p347-p358

**41 pooling 的做法的意义**
{:.warning}
p342-p347

**42 循环神经网络常见的一些依赖循环关系，常见的一些输入输出，以及对应的应用场景**
{:.warning}
p378-p395

**43 seq2seq，gru，lstm 等相关的原理**
{:.warning}
seq2seq:p396-p397; gru:p411-p412; lstm:p408-p411

**44 采样在深度学习中的意义**
{:.warning}
p469-p471

**45 自编码器与线性因子模型，PCA，ICA 等的关系**
{:.warning}
自编码器与线性因子模型: p489-p490;PCA:p490-p491;ICA:p491-p493

**46 自编码器在深度学习中的意义，以及一些常见的变形与应用**
{:.warning}
意义: p502-p503; 常见变形: p503-p508；p509-p512; p521-p524 应用: p515-p520;p524-p525

**47 受限玻尔兹曼机广泛应用的原因**
{:.warning}
p460: 想特别了解的人注意这句话：  See Mohamed et al (2012b) for an analysis of reasons for the success of these models.

答：p595-p598

答：p599

**50 配分函数通常难以计算的解决方案**
{:.warning}
p605,p606 第一段

**51 几种参数估计的联系与区别: MLE／MAP／贝叶斯**
{:.warning}
P134-P139

**52 半监督的思想以及在深度学习中的应用**
{:.warning}
p541-p546

**53 举例 CNN 中的 channel 在不同数据源中的含义**
{:.warning}
p360-p362

**54 深度学习在 NLP，语音，图像等领域的应用及常用的一些模型**
{:.warning}
p452-p485

**55 word2vec 与 glove 的比较**
{:.warning}
How is GloVe different from word2vec?；GloVe 以及 Word2vec 能称为 deep learning 么？这俩模型的层次其实很浅的；

http://t.cn/RvYslDf

这个问题没找到答案，我去找了 quora 和知乎上的相关问题以及 quora 一个回答提及的论文。   （若有人在书中找到，请批评指正）

**56 注意力机制在深度学习的某些场景中为何会被大量使用，其几种不同的情形**
{:.warning}
p475-p476

**57.wide&deep 模型中的 wide 和 deep 介绍**
{:.warning}
https://arxiv.org/pdf/1606.07792.pdf   此问题答案未在书中找到，为此我去找了原论文，论文图 1 有详细的介绍。 （若有人在书中找到，请批评指正）

**58 核回归与 RBF 网络的关系**
{:.warning}
p142

**59.LSTM 结构推导，为什么比 RNN 好？**
{:.warning}
p408-p411

**60 过拟合在深度学习中的常见的一些解决方案或结构设计**
{:.warning}
p230-p268；包括：Parameter Norm Penalties(参数范数惩罚); Dataset Augmentation (数据集增强); Early Stopping(提前终止);   Parameter Tying and Parameter Sharing (参数绑定与参数共享); Bagging and Other Ensemble Methods(Bagging 和其他集成方法)；Dropout          另外还有 Batch Normalization。


**61 怎么理解贝叶斯模型的有效参数数据会根据数据集的规模自动调整**
{:.warning}
关于非参数模型：p115-p116 ；非参数模型不依赖于特定的概率模型，它的参数是无穷维的，数据集的规模的大小影响着模型使用更多或者更少的参数来对其进行建模。(并未在书中找到准确的答案，若有更好的回答，请联系我改正)

*本答案是根据问题在Deep Learning上找到的答案；有些答案只是自己读书后在书上做的笔记的具体页面，毕竟原 po（http://t.cn/RObdPGk） 说还有另外一本书，所以该答案可能不是特别准确也不完善，答案也是给大家做个参考，若发现答案有问题，请联系我并指正，大家共同进步，谢谢*

-------------------  
[End](#head)
{:.warning}  

# 附录
## A 资源
1 [那些深度学习《面试》你可能需要知道的](https://zhuanlan.zhihu.com/p/29936999)    
