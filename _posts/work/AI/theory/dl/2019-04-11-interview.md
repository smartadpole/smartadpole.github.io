---
layout: article
title:  "「DL」 深度学习问答"
date:   2019-04-11 08:20:40 +0800
key: dl-question
aside:
  toc: true
tags: Q&A
category: [AI, DL]
sidebar:
  nav: INTERVIEW
---
<span id='head'></span>  


<!--more-->



| 基础 |  |  |  |
| --- | --- | --- | --- |
| [传统的图像处理的意义](#traditional) |  |  |  |
| [为什么网络的输入大多是 224×224](#input_224) | [CNN 输入必须是 RGB 三通道吗](#input_channel) |  |  |
| [CNN 中术语解释](#cnn_term) | [特征图大小计算](#feature_map_size) |  |  |
| [常见激活函数](#activate_func) | [交叉熵损失](#cross_entropy) |  |  |
|  |  |  |  |
|  |  |  |  |

| 进阶 |  |  |  |
| --- | --- | --- | --- |
| [为什么交叉熵可以用作代价函数](#cross_entropy_loss) |  |  |  |
|  |  |  |  |
|  |  |  |  |

| 理论 |  |  |  |
| --- | --- | --- | --- |
|  |  |  |  |

| 实战 |  |  |  |
| --- | --- | --- | --- |
| [梯度消失/爆炸](#gradient_abnormal) | [调参流程](#train_param) | [过拟合解决方案](#overfit_adverse) |  |
|  |  |  |  |
|  |  |  |  |


# 1 基础

<span id="traditional">    </span>    

**图像领域卷积神经网络大行其道，传统的图像处理还有意义吗**
{:.warning}  
[知乎](https://www.zhihu.com/question/322742318)     

<span id="input_224">    </span>    

**为什么网络的输入大多是 $224 \times 224$**
{:.warning}  
用于分类的卷积网络包括下采样和分类；   
- **一个分类对应的最后一个特征图的大小——$7 \times 7$**   
最后一个特征图经过分类操作（全连接或全局池化）得到分类结果，一个分类对应的最后一层特征图大小可以是 $3 \times 3$，$5 \times 5$，$7 \times 7$ 等；其中 $7 \times 7$ 更合理，因为尺寸过小会造成信息丢失严重，尺寸太大，信息的抽象程度不够，计算量也大；$7 \times 7$ 较为平衡；    
- **整个卷积网络下采样的程度为—— $2^5$**  
图像从输入到最后一层，分辨率降低的程度通常是 $2^n$；  
下采样 $1/4$，输入是 $7 \times 2^4=112$；下采样 $1/5$，输入是 $7 \times 2^5=224$；下采样 $1 / 6$，输入是 $7 \times  2^6=228$；  
而 imagenet 的图像大小都在 300 左右；与 300 最接近的就是 224 了，故选择了 $2^5$；

>以上只是多多种巧合情况的综合，使得经典论文中大多使用 $224 \times 224$ 的输入尺寸；实际应用中，仍需根据网络本身结构（下采样程度）和采集到的图像尺寸来综合考虑最终使用输入尺寸；   

[1]. 龙鹏. 【AI-1000问】为什么深度学习图像分类的输入多是224*224[EB/OL]. <https://zhuanlan.zhihu.com/p/58188430>. 2019-03-03/2019-03-18.    


<span id="input_channel">    </span>    

**CNN 输入必须是 RGB 三通道吗**
{:.warning}  
图像的表示使用的是矩阵,每个矩阵代表一个通道；图像的类型包括二值图、灰度图和彩色图，其中彩色图又包括 RGB、YUV、HSV 和 HSL等；   
深度学习算法的输入看的是一个个通道，所以可以输入二值图、灰度图和彩色图，也可以是将几种表示方法拼接起来作为输入（[ColorNet](https://arxiv.org/abs/1902.00267) 中就此问题进行过探讨）；    


<span id="cnn_term">    </span>  

**CNN 中术语解释**
{:.warning}  
CNN 的主要参数：    
+ 卷积（Kernal/filter）；    
+ 填充；    
+ 滑动步长；     
+ 池化；    
+ 通道；      

<span id="feature_map_size">    </span>  

**特征图大小计算**   
{:.warning}
1. 卷积：    
`N = (W − F + 2P )/S+1`           
+ 输入图片大小 W×W   
+ Filter大小 F×F   
+ 步长 S    
+ padding的像素数 P    

输出通道数 = 卷积核/池化核数量    

2. 反卷积：   
**反卷积的大小是由卷积核大小与滑动步长决定**， in是输入大小， k是卷积核大小， s是滑动步长， padding的像素数 P, out是输出大小。
得到 `out = (in - 1) * s -2p + k`，还有另外一个写法：`W = (N - 1)*S - 2P + F`    

例如 输入：2x2， 卷积核：4x4， 滑动步长：3，填充像素为0， 输出：7x7 ，其计算过程就是， (2 - 1) * 3 + 4 = 7    

3. 池化得到的特征图大小计算方式：    
`N=(W-F)/S+1`，池化层一般不填充像素(`VALID`)    
**卷积向下取整，池化向上取整**；**卷积层一般填充像素(`SAME`)，池化层一般不填充像素(`VALID`)**？注意：`stride`为1的时候，当`kernel`为 3 `padding`为1或者`kernel`为5 `padding`为2，这种情况可直接得出卷积前后尺寸不变；     

[CNN中的参数解释及计算](https://flat2010.github.io/2018/06/15/%E6%89%8B%E7%AE%97CNN%E4%B8%AD%E7%9A%84%E5%8F%82%E6%95%B0/)

<span id="activate_func">    </span>    

**常见激活函数**
{:.warning}
 sigmoid，relu，softplus，tanh，RBF 及其应用场景；    
>《深度学习》 sigmoid 和 softplus 在 3.10 常用函数及其性质；6.3 隐藏单元（激活函数）

| 函数 | 公式 | 特点 | 应用 |
| --- | --- | --- | --- |
| sigmoid | $\frac{1}{1 + \exp(-x)}$  | 值域在 (0, 1)；<br>绝对值较大时函数进入饱和状态，即对微小的输入变化不敏感； | |
| ReLu | $\max (0, x)$  |  |  |
| softplus |  $\log {(1 + \exp (x))}$ |  |  |
| tanh |   |  |  |
| RBF |   |  |  |

`函数求导及换算关系`{:.warning}

softmax:      
分类问题中，直接使用输出层的输出有两个问题：
+ 神经网络输出层的输出值的范围不确定，我们难以直观上判断这些值的意义
+ 由于真实标签是离散值，这些离散值与不确定范围的输出值之间的误差难以衡量

`softmax回归`解决了以上两个问题，它**将输出值变换为值为正且和为1的概率分布**，公式如下：

$$softmax(y)_{i} = y_{i}^{'} = \frac{e^{yi}}{\sum_{j=1}^{n}e^{yj}}$$

<span id="cross_entropy">    </span>   

**交叉熵损失**
{:.warning}
交叉熵刻画了两个概率分布之间的距离，它是分类问题中使用比较广泛的一种损失函数，交叉熵一般会与softmax回归一起使用，公式如下：    
$$L = -\sum_{c=1}^{M}y_{c}log(p_{c})或者H(p,q)=-\sum p(x)logq(x)$$（p代表正确答案，q代表预测值）    
- $M$ ——类别的数量；    
- $y_{c}$ ——指示变量（0或1）,如果该类别和样本的类别相同就是1，否则是0；    
- $p_{c}$ ——对于观测样本属于类别 $c$ 的预测概率；    


# 2 进阶



<span id="cross_entropy_loss">    </span>   

**为什么交叉熵可以用作代价函数**
{:.warning}
从数学上来理解就是，为了让学到的模型分布更接近真实数据的分布，我们需要最小化模型数据分布与训练数据之间的 `KL 散度`，而因为训练数据的分布是固定的，因此最小化 `KL 散度`等价于最小化交叉熵，而且交叉熵计算更简单，所以机器/深度学习中常用交叉熵 `cross-entroy` 作为分类问题的损失函数；    


# 3 理论

<span id="audio_image_fusion">   </span>    

**视频信息包括图片和音频，这两种特征怎么融合**
{:.warning}  
`神经网络是否能融合这两种特征`{:.warning}     
**融合**：此处图像和音频属于多模态信息，可以通过一定方法映射到统一空间，然后进行融合；至于融合方式就简单了，算数运算都可以；     
神经网络**当然可以**融合多模态特征：对于卷积网络来说，输入就是矩阵，图像就是具有1～3个通道的二维矩阵，而声音就是1～2个声道的特殊二维矩阵（特殊在行数为1）；只要保证后续提取到的特征维度一样，就能够进行融合；          

<span id="calc_feature_map">   </span>    

**计算 feature map 大小**
{:.warning}  
输出的 feature map 大小：
$\mathbf{H_{out} = { {H_{in} + 2 \times {pad} - kernel} \over stride} + 1}$   
$\mathbf{W_{out} = { {W_{in} + 2 \times {pad} - kernel} \over stride} + 1}$   

*注：当 stride 为 1 时，若 $\mathbf{pad = { {kernel − 1} \over 2} }$，则输出 feature map大小不变*   

<span id="">    </span>    

**列举常见的范数及其应用**
{:.warning}
>《深度学习》2.5 范数，7.1、7.2 正则化      

*范数，norm：$L^p$ 范数就是元素绝对值的 $p$ 次方的和开 $p$ 次根号；用于衡量向量的大小，直观上来看是衡量从原点到 $x$ 的距离；*    
$${ \left \| x \right \| }_p = \left(\sum_i|x_i|^p \right)^{1/p}  \qquad （p \in R,\quad p \geq 1）$$     

常见范数：    

| 范数 | 解释 | 说明 | 作用 |
| --- | --- | --- | --- |
| $L_0$| 非 0 元素个数；| 但因数学意义不对（不满足尺度缩放）故常用 $L_1$ 来代替；  |  |
| $L_1$| 绝对值之和；| 通常用来衡量 0 值和非 0 值的差异；| 让权重变得稀疏（更多0）`推导`{:.warning}  |
| $L_2$| 欧式距离；| 原点附近增长缓慢；导数与所有元素相关，而平方 $L_2$ 导数只与当前元素相关；|  感知具有较高方差的输入`推导`{:.warning} |
| $L_{\infty}$| 最大范数，最大的绝对值；| |   |
| $L_F$| 矩阵的 Frobenius 范数，相当与向量的二范数；| |   |

应用：正则化：减小过拟合；通常正则项加在损失函数上，来对权重施加限制；     
*正则化会用少量偏差的增加换取方差的减少；正则通常只加在权重上；*
<span id="">    </span>    

**简单介绍一下贝叶斯概率与频率派概率，以及在统计中对于真实参数的假设。**
{:.warning}
p55

答：p67：3.10 上面那一段

<span id="">    </span>    

**Jacobian，Hessian 矩阵及其在深度学习中的重要性**
{:.warning}
p86-p92
<span id="">    </span>    

**KL 散度在信息论中度量的是那个直观量**
{:.warning}
p74
<span id="">    </span>    

**数值计算中的计算上溢与下溢问题，如 softmax 中的处理方式**
{:.warning}
p80-p81
<span id="">    </span>    

**与矩阵的特征值相关联的条件数 (病态条件) 指什么，与梯度爆炸与梯度弥散的关系**
{:.warning}
p82;
<span id="">    </span>    

**在基于梯度的优化问题中，如何判断一个梯度为 0 的零界点为局部极大值／全局极小值还是鞍点，Hessian 矩阵的条件数与梯度下降法的关系**
{:.warning}
p86-p92

<span id="">    </span>    

**KTT 方法与约束优化问题，活跃约束的定义**
{:.warning}
p93-p95

<span id="">    </span>    

**模型容量，表示容量，有效容量，最优容量概念**
{:.warning}
p111;p113;p114;p115

<span id="">    </span>    

**正则化中的权重衰减与加入先验知识在某些条件下的等价性**
{:.warning}
p119;p138

<span id="">    </span>    

**高斯分布的广泛应用的缘由**
{:.warning}
p63-p64

<span id="">    </span>    

**最大似然估计中最小化 KL 散度与最小化分布之间的交叉熵的关系**
{:.warning}
p132

<span id="">    </span>    

**在线性回归问题，具有高斯先验权重的 MAP 贝叶斯推断与权重衰减的关系，与正则化的关系**
{:.warning}
 p138-p139

<span id="">    </span>    

**稀疏表示，低维表示，独立表示**
{:.warning}
p147

<span id="">    </span>    

**列举一些无法基于地图 (梯度？) 的优化来最小化的代价函数及其具有的特点**
{:.warning}
p155 最顶一段

<span id="">    </span>    

**在深度神经网络中，引入了隐藏层，放弃了训练问题的凸性，其意义何在**
{:.warning}
p191-192

<span id="">    </span>    

**函数在某个区间的饱和与平滑性对基于梯度的学习的影响**
{:.warning}
p160

<span id="">    </span>    

**梯度爆炸的一些解决办法**
{:.warning}
p302

答：p198

<span id="">    </span>    

**在前馈网络中，深度与宽度的关系及表示能力的差异**
{:.warning}
p200-p201

<span id="">    </span>    

**为什么交叉熵损失可以提高具有 sigmoid 和 softmax 输出的模型的性能，而使用均方误差损失则会存在很多问题。分段线性隐藏层代替 sigmoid 的利弊**
{:.warning}
p226;p226

<span id="">    </span>    

**表示学习的发展的初衷？并介绍其典型例子: 自编码器**
{:.warning}
p3-p4;p4

<span id="">    </span>    

**在做正则化过程中，为什么只对权重做正则惩罚，而不对偏置做权重惩罚**
{:.warning}
p230

<span id="">    </span>    

**在深度学习神经网络中，所有的层中考虑使用相同的权重衰减的利弊**
{:.warning}
p230

<span id="">    </span>    

**正则化过程中，权重衰减与 Hessian 矩阵中特征值的一些关系，以及与梯度弥散，梯度爆炸的关系**
{:.warning}
p231-234

<span id="">    </span>    

**L1／L2 正则化与高斯先验／对数先验的 MAP 贝叶斯推断的关系**
{:.warning}
p234-p237

<span id="">    </span>    

**什么是欠约束，为什么大多数的正则化可以使欠约束下的欠定问题在迭代过程中收敛**
{:.warning}
p239

<span id="">    </span>    

**为什么考虑在模型训练时对输入 (隐藏单元／权重) 添加方差较小的噪声，与正则化的关系**
{:.warning}
p240-p243

<span id="">    </span>    

**共享参数的概念及在深度学习中的广泛影响**
{:.warning}
p245;p253

<span id="">    </span>    

**Dropout 与 Bagging 集成方法的关系，以及 Dropout 带来的意义与其强大的原因**
{:.warning}
p258-p268

<span id="">    </span>    

**批量梯度下降法更新过程中，批量的大小与各种更新的稳定性关系**
{:.warning}
p279

<span id="">    </span>    

**如何避免深度学习中的病态，鞍点，梯度爆炸，梯度弥散**
{:.warning}
p282-p293

<span id="">    </span>    

**SGD 以及学习率的选择方法，带动量的 SGD 对于 Hessian 矩阵病态条件及随机梯度方差的影响**
{:.warning}
p294；p296-p300

<span id="">    </span>    

**初始化权重过程中，权重大小在各种网络结构中的影响，以及一些初始化的方法；偏置的初始化**
{:.warning}
初始化权重：p301-p305；偏置初始化：p305-p306

<span id="">    </span>    

**自适应学习率算法: AdaGrad，RMSProp，Adam 等算法的做法**
{:.warning}
AdaGrad:p307; RMSProp:p307-p308; Adam:p308-p309

<span id="">    </span>    

**二阶近似方法: 牛顿法，共轭梯度，BFGS 等的做法**
{:.warning}
牛顿法：p310-p313; 共轭梯度: p313-p316; BFGS:p316-p317

<span id="">    </span>    

**Hessian 的标准化对于高阶优化算法的意义**
{:.warning}
p318-p321

<span id="">    </span>    

**卷积网络中的平移等变性的原因，常见的一些卷积形式**
{:.warning}
平移等变性：p338-p339；常见的一些卷积形式：p347-p358

<span id="">    </span>    

**pooling 的做法的意义**
{:.warning}
p342-p347

<span id="">    </span>    

**循环神经网络常见的一些依赖循环关系，常见的一些输入输出，以及对应的应用场景**
{:.warning}
p378-p395

<span id="">    </span>    

**seq2seq，gru，lstm 等相关的原理**
{:.warning}
seq2seq:p396-p397; gru:p411-p412; lstm:p408-p411

<span id="">    </span>    

**采样在深度学习中的意义**
{:.warning}
p469-p471

<span id="">    </span>    

**自编码器与线性因子模型，PCA，ICA 等的关系**
{:.warning}
自编码器与线性因子模型: p489-p490;PCA:p490-p491;ICA:p491-p493

<span id="">    </span>    

**自编码器在深度学习中的意义，以及一些常见的变形与应用**
{:.warning}
意义: p502-p503; 常见变形: p503-p508；p509-p512; p521-p524 应用: p515-p520;p524-p525

<span id="">    </span>    

**受限玻尔兹曼机广泛应用的原因**
{:.warning}
p460: 想特别了解的人注意这句话：  See Mohamed et al (2012b) for an analysis of reasons for the success of these models.

答：p595-p598

答：p599

<span id="">    </span>    

**配分函数通常难以计算的解决方案**
{:.warning}
p605,p606 第一段

<span id="">    </span>    

**几种参数估计的联系与区别: MLE／MAP／贝叶斯**
{:.warning}
P134-P139

<span id="">    </span>    

**半监督的思想以及在深度学习中的应用**
{:.warning}
p541-p546

<span id="">    </span>    

**举例 CNN 中的 channel 在不同数据源中的含义**
{:.warning}
p360-p362

<span id="">    </span>    

**深度学习在 NLP，语音，图像等领域的应用及常用的一些模型**
{:.warning}
p452-p485

<span id="">    </span>    

**word2vec 与 glove 的比较**
{:.warning}
How is GloVe different from word2vec?；GloVe 以及 Word2vec 能称为 deep learning 么？这俩模型的层次其实很浅的；

http://t.cn/RvYslDf

这个问题没找到答案，我去找了 quora 和知乎上的相关问题以及 quora 一个回答提及的论文。   （若有人在书中找到，请批评指正）

<span id="">    </span>    

**注意力机制在深度学习的某些场景中为何会被大量使用，其几种不同的情形**
{:.warning}
p475-p476

<span id="">    </span>    

**wide&deep 模型中的 wide 和 deep 介绍**
{:.warning}
https://arxiv.org/pdf/1606.07792.pdf   此问题答案未在书中找到，为此我去找了原论文，论文图 1 有详细的介绍。 （若有人在书中找到，请批评指正）

<span id="">    </span>    

**核回归与 RBF 网络的关系**
{:.warning}
p142

<span id="">    </span>    

**LSTM 结构推导，为什么比 RNN 好？**
{:.warning}
p408-p411

<span id="">    </span>    

**怎么理解贝叶斯模型的有效参数数据会根据数据集的规模自动调整**
{:.warning}
关于非参数模型：p115-p116 ；非参数模型不依赖于特定的概率模型，它的参数是无穷维的，数据集的规模的大小影响着模型使用更多或者更少的参数来对其进行建模。(并未在书中找到准确的答案，若有更好的回答，请联系我改正)

*本答案是根据问题在Deep Learning上找到的答案；有些答案只是自己读书后在书上做的笔记的具体页面，毕竟原 po（http://t.cn/RObdPGk） 说还有另外一本书，所以该答案可能不是特别准确也不完善，答案也是给大家做个参考，若发现答案有问题，请联系我并指正，大家共同进步，谢谢*


# 4 实战


<span id="overfit_adverse">    </span>    

**过拟合解决方案**
{:.warning}
>p230-p268；    

- Parameter Norm Penalties(参数范数惩罚)；   
- Dataset Augmentation (数据集增强)；  
- Early Stopping(提前终止)；    
- Parameter Tying and Parameter Sharing (参数绑定与参数共享)；   
- Bagging and Other Ensemble Methods(Bagging 和其他集成方法)；     
- Dropout；     
- 另外还有 Batch Normalization；     


<span id="gradient_abnormal">    </span>  

**如何解决梯度消失和梯度爆炸的问题？**   
{:.warning}  

| 问题 | 描述 | 方案|
|:--------:|--------|--------|
|梯度消失|根据链式法则，如果`每一层神经元对上一层的输出的偏导乘上权重的结果`都小于1的话，那么即使这个结果是0.99，在经过足够多层传播之后，误差对输入层的偏导会趋于0.|使用`Relu`和`batch normalization`以及循环神经网络里面的`LSTM`和`GRU`都可以解决这个问题|
|梯度爆炸|根据链式法则，如果`每一层神经元对上一层的输出的偏导乘上权重结果`大于1的话，在经过足够多层传播之后，误差对输入层的偏导会趋于无穷大|可以使用`梯度截断`、`激活函数`、`Batch Normalization`来解决|


<span id="train_param">    </span>  

**深度学习调参经验**   
{:.warning}  
 - 参数初始化    
 - 数据的预处理方式    
 - 训练技巧    
 - 尽量对数据进行shuffle和augmentation    
 - Ensemble    
 - 学习率    
 - dropout    
 - relu+bn    
 - 网络层数    
 - batch_size      


-------------------  
[End](#head)
{:.warning}  

# 附录
## A 资源
1. [那些深度学习《面试》你可能需要知道的](https://zhuanlan.zhihu.com/p/29965072)    
1. [机器学习及大数据相关面试的职责和面试问题](https://zhuanlan.zhihu.com/p/27151345)    
1. [如何准备机器学习工程师的面试](https://zhuanlan.zhihu.com/p/29969587)    
1. [推荐算法相关的文档整理](https://zhuanlan.zhihu.com/p/29969721)    
1. [机器学习和深度学习习题集（上）](https://zhuanlan.zhihu.com/p/86154440)    
1. [深度学习 500 问](https://zhuanlan.zhihu.com/p/71979604)    
1. [深度学习专项课程精炼图笔记](https://zhuanlan.zhihu.com/p/91178285)    
1. [笔记——深度学习](https://github.com/amusi/Deep-Learning-Interview-Book/blob/master/docs/%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0.md)    

## B 示例
<span id="receptive"> </span>
**计算 AlexNet VGG 网络的感受野**    
```Python
#!/usr/bin/env python

# [filter size, stride, padding]
net_struct = {'alexnet': {'net':[[11,4,0],[3,2,0],[5,1,2],[3,2,0],[3,1,1],[3,1,1],[3,1,1],[3,2,0]],
                   'name':['conv1','pool1','conv2','pool2','conv3','conv4','conv5','pool5']},
       'vgg16': {'net':[[3,1,1],[3,1,1],[2,2,0],[3,1,1],[3,1,1],[2,2,0],[3,1,1],[3,1,1],[3,1,1],
                        [2,2,0],[3,1,1],[3,1,1],[3,1,1],[2,2,0],[3,1,1],[3,1,1],[3,1,1],[2,2,0]],
                 'name':['conv1_1','conv1_2','pool1','conv2_1','conv2_2','pool2','conv3_1','conv3_2',
                         'conv3_3', 'pool3','conv4_1','conv4_2','conv4_3','pool4','conv5_1','conv5_2','conv5_3','pool5']},
       'zf-5':{'net': [[7,2,3],[3,2,1],[5,2,2],[3,2,1],[3,1,1],[3,1,1],[3,1,1]],
               'name': ['conv1','pool1','conv2','pool2','conv3','conv4','conv5']}}



def outFromIn(isz, net, layernum):
    """
    计算feature map大小
    """
    totstride = 1
    insize = isz
    for layer in range(layernum):
        fsize, stride, pad = net[layer]
        outsize = (insize - fsize + 2*pad) / stride + 1
        insize = outsize
        totstride = totstride * stride
    return outsize, totstride

def inFromOut(net, layernum):
    """
    计算感受野receptive file大小
    """
    RF = 1
    for layer in reversed(range(layernum)):
        fsize, stride, pad = net[layer]
        RF = ((RF -1)* stride) + fsize
    return RF

if __name__ == '__main__':
    imsize = 224

    print "layer output sizes given image = %dx%d" % (imsize, imsize)

    for net in net_struct.keys():
        print '************net structrue name is %s**************'% net
        for i in range(len(net_struct[net]['net'])):
            p = outFromIn(imsize,net_struct[net]['net'], i+1)
            rf = inFromOut(net_struct[net]['net'], i+1)
            print "Layer Name = %s, Output size = %3d, Stride = % 3d, RF size = %3d" % (net_struct[net]['name'][i], p[0], p[1], rf)
```


<span id="iou"> </span>
**IoU 计算**     
```python
# candidateBound = [x1, y1, x2, y2]
def calculateIoU(candidateBound, groundTruthBound):
    cx1， cy1， cx1, cx2 = candidateBound
    gx1, gy1, gx2, gy2 = groundTruthBound

    carea = (cx2 - cx1) * (cy2 - cy1) #C的面积
    garea = (gx2 - gx1) * (gy2 - gy1) #G的面积
    x1, y1, x2, y2 = max(cx1, gx1), min(cy1, gy1), min(cx2, gx2), max(cy2, gy2)
    # 原点为(0, 0)，所以 min(cy1, gy1) 是min不是max
    w, h = max(0, (x2 - x1)), max(0, (y2 - y1))
    area_intersection = w * h
    area_union = carea + garea - area_intersection

    iou = area_intersection / area_union
    return iou
```
