---
layout: article
title:  "Meta Learning"
date:   2018-12-17 19:06:40 +0800
key: meta-learning-review-20181217
aside:
  toc: true
tags: meta-learning
category: [深度学习, 深度学习基础]
---

> 译自：Meta-Learning: Learning to Learn Fast <https://lilianweng.github.io/lil-log/2018/11/30/meta-learning.html>，有增删  
元学习，又叫“学会学习”，旨在通过少量样本的 fine-tuning 快速设计出具有类似属性的机器学习模型；甚至，推广到在训练期间从未遇到过的新任务和新环境；这就是元学习也被称为[学习如何学习](https://www.cs.cmu.edu/~rsalakhu/papers/LakeEtAl2015Science.pdf)的原因；  
`旨在通过少量样本的fine-tuning，使该模型可以适应训练样本中没有遇到的新任务和新环境`{:.warning}  
`跟 finetuning 有啥区别啊`{:.warning}  

常见的方法：
- 1）「基于度量」学习有效的距离度量;  
- 2）「基于模型」使用（循环）网络与外部或内部存储器;   
- 3）「基于优化」明确优化模型参数以进行快速学习；  

几个元学习的具体示例：  
- 在不包含猫的训练集上训练出的模型，在输入少量猫的图像后就可以识别猫；  
- 游戏机器人能够快速掌握新游戏；  
- 一个只在平地环境训练过的机器人，可以完成上坡的任务；  

## 一、元学习
本文以监督学习为例探讨元学习，元强化学习不做赘述；  

### 1. 一个简单的视角
小样本分类，又叫 [Few-shot classification](/深度学习/深度学习基础/2018/12/20/few-shot-classification.html) 或 **k-shot classification**，是监督学习领域中元学习的代表； 与常规分类任务不同的地方在于，小样本分类可以预测出训练集中未出现过的类别，不过需提供额外的 [support set](#support_set) 来辅助分类；  `few-shot classification 和 k-shot classification 是一回事吗？`{:.warning}  `这里的可识别未知样本，指的是对网络未知，但对模型调用者是已知的`{:.warning}    
该想法在某种程度上类似于模型预训练或 fine tuning；但 fine tuning 是针对新任务进行具体的模型优化，模型能力更具体化了；而元学习则是旨在训练出一个具有较强泛化能力的模型，以完成对未知类别的分类；`感觉这段对比写的不够明显`{:.warning}    
如下图所示：  
![](/assets/images/cv/dl/base/few-shot-classification.png)
*图 1. [4-shot 2-class image classification](#k_shot_n_class) 的示例 (图片来源 [Pinterest](https://www.pinterest.com/))*  

| | 基于模型  | 基于度量 | 基于优化 |
| -- | -- | -- | -- |
| 核心思想 | RNN，memory | 度量学习 | 梯度下降 |
| $$P_\theta(y\|\vec x)$$ 是如何被建模的 | $$f_\theta(\vec x, S)$$ | $$\sum_{(x_i, y_i)\in S}{k_\theta(x, x_i)y_i}$$  (*)| $$P_{g_\phi(\theta, S^L)}(y\|x)$$ |

 (*)：$$k_\theta$$ 是衡量 $$x_i$$ 和 $$x$$ 相似性的函数；  
 `看不懂，但是感觉很重要`{:.warning}  

## 二、基于度量的元学习
基于度量的元学习中的核心思想类似于最近邻算法（即，k-NN 分类器和 k 均值聚类）和核密度估计； 一组已知标签上的预测概率是支持集样本的标签的加权和； 权重由核函数生成，测量两个数据样本之间的相似性；  
学习一个好的内核对于基于度量的元学习模型的成功至关重要；度量学习与此意图完全一致，因为它旨在学习对象的度量或距离函数；良好指标的概念取决于问题；它应该代表任务空间中输入之间的关系，并促进解决问题；  
下面介绍的所有模型都明确地学习了输入数据的嵌入向量，并使用它们来设计适当的核函数；  

### 1. 挛生网络
>用图像验证的方法来处理样本图像分类（one-shot classification）问题；  
那么这个方式其实是将未知类别的待测试样本与给定的 [support set](#support_set) 进行关联，相似度最高的即为该类别；并非真正意义上判断出这个类别是新的类别，如果加上一个阈值来判断是否出现新类别也可以，只是这个阈值的确定似乎是复杂的；  


[挛生网络](https://papers.nips.cc/paper/769-signature-verification-using-a-siamese-time-delay-neural-network.pdf)是用来学习输入数据样本对之间关系的网络，输入的样本数据对依次经过网络，得到两组特征，通过计算他们的联合损失来训练网络；  

[Koch，Zemel和Salakhutdinov（2015）](http://www.cs.toronto.edu/~rsalakhu/papers/oneshot1.pdf)提出了使用挛生网络进行「单样本图像分类」的方法；整体思路是，按图像验证任务进行训练，测试时将测试图和训练集中所有图片一一比对，取与之相似读最高的训练样本的类别为测试图类别；  `不就是化分类为验证吗，而且是以牺牲速度为代价，为啥要起个元学习这么高大上的名字`{:.warning}

挛生网络简述：  
- 输入两张图像，通过 CNN 网络后在 [embedding](#embedding) 层（$$f_\theta$$）提取一对特征向量 $$f_\theta(x_i)$$ 和 $$f_\theta(x_j)$$；  
- 计算两个特征向量的 $$L1$$ 距离  $$D = \|f_\theta(x_i) - f_\theta(x_j)\|$$；  
- 接一个全连接层 和 Sigmoid，将距离转换为概率 p；  
- 因为是二分类，所以我们用交叉熵作为损失函数；    
    $$p(x_i, x_j) = \sigma(W*D)$$    
    $$L(B) = \sum_{(x_i,x_j,y_i,y_j)\in B}l_{y_i=y_j}logp(x_i,x_j) + (1-l_{y_i=y_j}log(1-p(x_i,x_j))$$  
*注：$$B$$ 是训练时的单个批次； $$L1$$ 距离可以换做其他距离，比如欧式距离（$$L2$$）、夹角余弦等；  
预测结果 $$\hat c_S(x) = c(arg  max_{x_i\in S}P(x,x_i))$$，其中 $$S$$ 为 support set，$$x$$ 为测试图像，$$c(x)$$ 为 $$x$$ 的标签*；   

![](/assets/images/cv/dl/base/siamese-conv-net-cat.png)  
*图 2. 少样本分类中挛生网络的结构*   `少样本分类的译法对吗`{:.warning}    

假设学习到的特征提取函数 $$f_\theta$$ 可以对未知类别进行分类，这和迁移学习中的预训练（fine tuning）相似，只不过如果新任务和原任务特征偏差较大时，预训练效果会变差；`此处没有阐述元学习为啥会好啊`{:.warning}  

### 2. 匹配网络
Matching Networks(Vinyals et al., 2016[^1])，是为了学习出一个针对任意给定的 support set 都可以进行分类的网络；  
`看不出来，跟挛生有啥区别；核心都在于 embedding ，非整出来个 挛生和匹配`{:.warning}   

相似度：$$a(x,x_i) = \frac {exp(cosine (f(x), g(x_i)))}{\sum_{j=i}^k exp(cosine (f(x), g(x_j))}$$    
`归一化的时候为什么不直接求和，而要用 softmax呢，夹角余弦值域很明显啊，为啥要多做一个处理`{:.warning}   
分类网络：$$c_S(x) = P(y|x, S)=\sum_{i=1}^ka(x,x_i)y_i$$ , 其中 $$S={\{(x_i,y_i)\}}_{i=1}^k$$ 为 support set，$$f$$ 为作用于测试样本的 embedding function，$$g$$ 为作用于support set 的 embedding function   
`为什么要乘以 $$y_i$$`{:.warning}  `不是 k-shot n-class 吗，为什么感觉 k 像是整个 support set 的数据量`{:.warning}   

![](/assets/images/cv/dl/base/matching-networks-dog.png)  
*图 3. Match Net 结构图[^1]*   

**（1）简单嵌入**   
简单的 Matching Networks 中，embedding 向量 来源于神经网络和单个输入样本；此时 $$f = g$$；  

**（2）全上下文嵌入（FCE）**  
将整个 support set 作为注意力模型的输入，使得可以基于与其他 support 样本的关系来调整 embedding 的效果，以提高 embedding function 的性能；  
- $$g_\theta(x_i,S)$$ 使用双向 LSTM 在整个 support set $$S$$ 上对 $$x_i\in S$$ 进行编码；    
- $$f_\theta(x,S)$$ 使用 LSTM 对测试样本编码，并结合 $$S$$ 上的注意力来计算相似度；  
`细节读的不是很懂4`{:.warning}  

该方法对于较难的任务（比如在 mini ImageNet 上进行小样本分类）确实有精度提升，但在简单任务上没有任何区别；  
Matching Networks 的训练过程旨在与测试时的推理匹配`翻译的有问题`{:.warning}；他修正了训练和测试条件应该匹配的观点；    

### 3. 关系网络
Relation Network (RN)(Sung et al., 2018[^2]) 和挛生网络有些相似，但也有如下不同：  
- 相似度不是基于 $$L1$$ 距离，而是由 CNN 网络（$$g_\phi$$）计算得到；  
- 使用 MSE 损失代替 Softmax，因为相似度度量更像是回归，而不是二分类；$$\mathcal{L}(B) = \sum_{(x_i, x_j, y_i, y_j)\in B} (r_{ij} - 1_{y_i=y_j})^2$$    

<img src="/assets/images/cv/dl/base/relation-network.png"  width="1000px">    
*图 4.一个 5-way 1-shot（5分类单样本） 的关系网络结构图[^2]*   

*有一篇 DeepMing 出的关于关系推理的[关系网络](https://deepmind.com/blog/neural-approach-relational-reasoning/)，别弄混了；*   

### 4. 原型网络
原型网络[^3]针对 support set 中的每个类，取该类嵌入特征的均值作为该类别的嵌入特征；此嵌入特征被成为该类的**原型特征向量**： $$v_c = {\frac {1}{\|S_c\|}}{\sum_{(x_i, y_i) \in S_c} f_\theta(x_i)}$$，*C 为 support set 中的类别，$$c\in C$$，$$f_\theta$$ 为 embedding function*；
测试样本 $$x$$ 在 support set 上的分布为：$$P(y=c\vert \mathbf{x})=\text{softmax}(-d_\varphi(f_\theta(\mathbf{x}), \mathbf{v}_c)) = \frac {\exp(-d_\varphi(f_\theta(x), v_c))}{\sum_{c' \in \mathcal{C}}\exp(-d_\varphi(f_\theta(\mathbf{x}), \mathbf{v}_{c'}))}$$  

![](/assets/images/cv/dl/base/prototypical-networks.png)  
*图 5.零样本和小样本原型网络结构图[^3]*   

其中 $$dφ$$ 可以是任何距离函数，只要 $$φ$$ 是可微分的；论文中使用了欧氏距离的平方；  
损失函数为：$$\mathcal{L}(\theta) = -\log P_\theta(y=c\vert\mathbf{x})$$  

## 三、 基于模型的元学习

## 四、 基于优化的元学习

## 附录  
A **名词**  
<span id="k_shot_n_class">**1. K-shot N-class classification**</span>  
每个类别有 K 个训练样本的 N 分类问题；  

<span id="support_set">**2. support set**</span>  
一个包含多个类别标签的数据集 $$S$$，他的单个类别样本数一般都比较少；$$S$$ 数据集中的标签在训练过程中是完全没有出现过的；网络会基于 $$S$$ 为测试集进行分类，预测的标签就来源于这个数据集；  

<span id="embedding">**2. embedding**</span>  `这段解释好像是有问题的`{:.warning}  
该操作意在不需要网络输出直接的结果，而是时候最后一个可用的 feature map；由之派生而来的 embedding layer，embedding vector，embedding function；
以分类网络为例，embedding 层指的是产生分类的上一层；该层输出的特征叫做 embedding vector，可简单译作「嵌入特征」；去掉了分类层的网络就是 embedding function；    

B **参考资料**    
1. Oriol Vinyals 在 NIPS 2018 中的[演讲](http://metalearning-symposium.ml/files/vinyals.pdf)   
2. Brenden M. Lake, Ruslan Salakhutdinov, and Joshua B. Tenenbaum. [“Human-level concept learning through probabilistic program induction.”](https://www.cs.cmu.edu/~rsalakhu/papers/LakeEtAl2015Science.pdf) Science 350.6266 (2015): 1332-1338.  
3. Oriol Vinyals’ talk on [“Model vs Optimization Meta Learning”]()  
4. Gregory Koch, Richard Zemel, and Ruslan Salakhutdinov. [“Siamese neural networks for one-shot image recognition.”](http://metalearning-symposium.ml/files/vinyals.pdf) ICML Deep Learning Workshop. 2015.  
8. Adam Santoro, et al. [“Meta-learning with memory-augmented neural networks.”](http://proceedings.mlr.press/v48/santoro16.pdf) ICML. 2016.  
9. Alex Graves, Greg Wayne, and Ivo Danihelka. [“Neural turing machines.”](https://arxiv.org/abs/1410.5401) arXiv preprint arXiv:1410.5401 (2014).  
10. Tsendsuren Munkhdalai and Hong Yu. [“Meta Networks.”](https://arxiv.org/abs/1703.00837) ICML. 2017.
11. Sachin Ravi and Hugo Larochelle. [“Optimization as a Model for Few-Shot Learning.”](https://bair.berkeley.edu/blog/2017/07/18/learning-to-learn/) ICLR. 2017.
12. Chelsea Finn’s BAIR blog on [“Learning to Learn”](https://arxiv.org/abs/1703.03400).  
13. Chelsea Finn, Pieter Abbeel, and Sergey Levine. [“Model-agnostic meta-learning for fast adaptation of deep networks.”](https://arxiv.org/abs/1703.03400) ICML 2017.  
14. Alex Nichol, Joshua Achiam, John Schulman. [“On First-Order Meta-Learning Algorithms.”](https://arxiv.org/abs/1803.02999) arXiv preprint arXiv:1803.02999 (2018).
15. [Slides on Reptile](https://www.slideshare.net/YoonhoLee4/on-firstorder-metalearning-algorithms) by Yoonho Lee.  

[^1]: Vinyals, Oriol et al. [Matching Networks for One Shot Learning.](http://www.cs.toronto.edu/~rsalakhu/papers/oneshot1.pdf) NIPS (2016)  arXiv preprint [arXiv:1606.04080](https://arxiv.org/abs/1606.04080).   
[^2]: Flood Sung, et al. Learning to Compare: Relation Network for Few-Shot Learning. In CVPR, 2018. [arXiv:1711.06025](https://arxiv.org/abs/1711.06025).   
[^3]: Jake Snell, Kevin Swersky, and Richard Zemel. Prototypical Networks for Few-shot Learning. CVPR. 2018. [arXiv:1703.05175](https://arxiv.org/abs/1703.05175)  
