---
layout: article
title:  "「DL」 GAN 综述"
date:   2019-03-26 11:08:40 +0800
key: gan-survey-20190326
aside:
  toc: true
category: [DL, GAN]
---

>文章目的是介绍 GAN 的基本概念和组件（流程）；    


<!--more-->

# 1 概览

## 1.1 模型总结

| 主题 | 方向 | 模型 |  
| --- | --- | :-: |  
| Loss | f-divergence | GAN, f-GAN, LSGAN |
| Loss | IPM | WGAN, WGAN-GP, FISHER GAN, McGAN, MMDGAN |  
| 结构 | DCGAN | DCGAN |   
| 结构 | 层次结构 | StackedGAN, GoGAN, ProgressiveGAN |
| 结构 | 自编码 | BEGAN, EBGAN, MAGAN |
| 难题 | 理论 | [Towards Principled Methods for Training GANs](https://arxiv.org/abs/1701.04862), [Generalization and Equilibrium in GANs](https://arxiv.org/abs/1703.00573) |
| 难题 | 模式崩溃 | MRGAN, DRAGAN, MAD-GAN, Unrolled GAN |
| 隐空间 | 解耦 | CGAN, ACGAN, InfoGAN, ss-InfoGAN |
| 隐空间 | 自编码 | ALI, BiGAN, Adversarial Generator-Encoder Networks |
| 隐空间 | VAE | VAEGAN, $\alpha$-GAN |

## 1.2 应用方向总结

| 领域 | 主题 | 模型 | 说明 |
| --- | --- | :-: | --- |
| 图像 | 图像翻译 | Pix2pix, PAN; CycleGAN, DiscoGAN | 一幅图像转换为另一幅图像，即风格变换 |
| 图像 | 超分辨率 | SRGAN | 主要关注中间层误差，避免生成图像缺乏纹理 |
| 图像 | 物体检测 | SeGAN, Perceptual GAN for small object detection | 引入超分辨率，进而提高小目标检测效果 |
| 图像 | 目标变换 | GeneGAN, GP-GAN |  |
| 图像 | 联合分布图像生成 | Coupled GAN | 使用权重共享，以学习到多个域的数据分布 |
| 图像 | 视频生成 | VideoGAN, Pose-GAN, MoCoGAN | |
| 图像 | 文本转图片 | Stack GAN, TAN-GAN |  |
| 图像 | 人脸迁移 | SD-GAN, SL-GAN, DR-GAN, AGEGAN |  |
| 序列数据 | 音乐生成 | C-RNN-GAN, SeqGAN, ORGAN | 使用了策略梯度下降 |
| 序列数据 | 文本生成 | RankGAN |  |
| 序列数据 | 语音转换 | VAW-GAN（VAE+WGAN） | 编码器进行语音编码，解码器负责重建音色 |
| 其他 | 半监督学习 | SSL-GAN, CatGAN; Triple-GAN | 生成的样本辅助分类器学习到数据空间 |
| 其他 | 域适应 | DANN, ARDA, CycleGAN, CyCADA, Unsupervised pixel-lecel domain adaptation | 原域到目标域的迁移 |
| 其他 | 持续学习 | Deep generative replay | 通过不断学习来解决多个任务 |
| 其他 | 医学图像分割 | DI2IN; SCAN; SegAN |  |
| 其他 | 图片隐写 | Steganography GAN, Secure steganography GAN | 图片中写入信息 |

GAN 在文本、语音领域应用较少的原因：    
- GAN 在优化的时候使用的是反向传播，对于文本，语音这种离散数据，GAN 没法直接跳到目标值，只能根据梯度一步步靠近；    
- 对于序列生成问题，每生成一个单词，我们就需要判断这个序列是否合理，可是 GAN 里面的判别器是没法做到的；除非我们针对每一个 step 都设置一个判别器，这显然不合理；   
为了解决这些问题，强化学习中的策略梯度下降（Policy gredient descent）被引入到 GAN 中应对序列生成问题；   

# 2 基础

生成对抗网络（GAN，Generative Adversarial Networks）是生成式模型中较为优秀的一员；  

*扩展：周志华的《机器学习》中对各种采样方式的介绍；*    

## 2.1 特点
**2.1.1 优点**    
GAN的优点在开头已有所介绍。这里再总结一下：

- **不依赖任何先验假设**：传统的许多方法会假设数据服从某一分布，然后使用极大似然去估计数据分布；   
GAN 不需要通过引入下界来近似似然；VAE 由于优化困难，引入了变分下界来优化似然；但是 VAE 对于先验和后验分布做了假设，使得 VAE 很难逼近其变分下界；   
- **生成方式简单**：只需生成器进行前向传播即可；而传统方法的采样方式非常复杂；  
- **速度快**：GAN 可以并行生成数据；相比于 PixelCNN，PixelRNN，GAN 生成非常快，因为 GAN 使用 Generator 替代了采样的过程；  
- **效果好**：从实践来看，GAN 生成的结过要比 VAE 更清晰；    

**2.1.2 缺点**    
- **训练不稳定**:容易崩溃，这个问题有学者提出了许多解决方案，比如 WGAN，LSGAN 等；   
- **模式崩溃**：尽管有很多相关的研究，但是由于图像数据的高维度特性，这个问题依然还没完全解决；   

## 2.2 基本概念
**GAN** 是一种通过对抗的方式，去学习数据分布的生成式模型；**对抗**指的是生成网络（Generator，G）和判别网络（Discriminator/Divergence，D）的互相对抗；生成网络尽可能生成逼真样本，判别网络则尽可能去判别该样本是真实样本，还是生成的假样本；   
G 的输入叫做隐变量 z（通常为服从高斯分布的随机噪声），通过 G 生成 $X_{fake}$ , 判别器负责判别输入的 data 是生成的样本 $X_{fake}$ 还是真实样本 $X_{real}$；  
对于 D 来说，这是一个二分类问题，使用交叉熵损失；对于生成器 G 来说，为了尽可能欺骗 D；   
实际训练时，生成器和判别器交替训练；   
`纳什均衡`{:.warning}    

## 2.3 目标函数
GAN 的目标函数是最小化两个分布的 JS 散度；实际上，衡量两个分布距离的方式有很多种，JS 散度只是其中一种；如果我们定义不同的距离度量方式，就可以得到不同的目标函数；许多对 GAN 训练稳定性的改进，比如 EBGAN，LSGAN 等都是定义了不同的分布之间距离度量方式；   

*散度这种度量方式不具备对称性，即 $D_f(p{data} \parallel p_g)$ 和 $D_f(p_g \parallel p_{data})$ 不相等（严格来说，距离度量方式必须具备对称性，所以散度不是一种距离度量方式，不过此处不去刻意关注这一点，直接把散度也作为一种距离度量方式，下文也是如此）*   

**2.3.1 f-divergence**    
\begin{equation}   
D_f(p_{data} \parallel p_g)=\int_xp_g(x)f(\frac{p_{data}(x)}{p_g(x)})dx
\end{equation}  

上述公式中 $f$ 为凸函数，且 $f(1)=0$ ；采用不同的 $f$ 函数（Generator），可以得到不同的优化目标：

| GAN | Divergence | Generator ($f(t)$) |   
| --- | :-: | :-: |   
| | KLD | $t \log t$ |  
| GAN | JSD - $2 \log2$ | $t \log t - (t+1) \log(t+1)$ |
| LSGAN | Pearson $mathcal{x}^2$ | $(t-1)^2$ |   
| EBGAN | Total Variance | $\|t-1\|$ |  

**LSGAN**: 是 f-divergence 中 $f(x)=(t-1)^2$ 时的特殊情况；   
Loss：  
\begin{equation}  
\mathop{\min}\limits_D J(D)=\mathop{\min} \limits_D [{\frac{1}{2}} {E_{x \sim {p_{data}} (x)} } [D(x)-a]^2 + {\frac{1}{2}} {E_{z \sim {p_z}(z)}} [D(G(z))-b]^2]    
\end{equation}   
原作中取 a=c=1，b=0；   
优点：
- **稳定训练**：解决了传统 GAN 训练过程中的梯度饱和问题    
- **改善生成质量**：惩罚距离判别器决策边界较远的生成样本；因为样本类别正确时，训练的效果不一定好；  


**2.3.2 Integral probality metric(IPM)**    
IPM 定义了一组评价函数 $f$，用于度量任意两个分布之间的距离；在一个紧凑的空间 $\chi\subset\mathrm{R^d}$ 中，定义 $\mathcal P(\chi)$ 为在 $\chi$ 上的概率测度；那么两个分布 $p_{data}$，$p_g$ 之间的 IPM 可以定义为：   
\begin{equation}  
d_{\mathcal{F}}(p_{data},p_g)=sup_{f \in \mathcal{F}}\mathbb E_{x \sim p_{data}} [f(x)]-\mathbb E_{x \sim {p_{data}}} [f(x)]   
\end{equation}  

类似于 f-divergence，不同函数 $f$ 也可以定义出一系列不同的优化目标；典型的有 WGAN，Fisher GAN；   

**WGAN**:提出了一种全新的距离度量方式——地球移动距离(EM, Earth-mover distance)，也叫 Wasserstein 距离：  

\begin{equation}
W(p_{data},p_g)=inf_{\gamma\in\sqcap(p_{data},p_g)}\mathbb E_{(x,y)\in\gamma}[\lVert{x-y}\rVert]
\end{equation}    

$\sqcap(p_{data},p_g)$ 表示一组联合分布，这组联合分布里的任一分布 $\gamma$ 的边缘分布均为 $p_{data}(x)$ 和 $p_g(x)$  
直观上来说，概率分布函数可以理解为随机变量在每一点的质量，所以 $W(p_{data},p_g)$ 则表示把概率分布 $p_{data}(x)$ 搬到 $p_g(x)$ 需要的最小工作量；  
WGAN 也可以用最优传输理论来解释，WGAN的生成器等价于求解最优传输映射，判别器等价于计算 Wasserstein 距离，即最优传输总代价；WGAN 的理论推导和解释比较复杂，但代码实现非常简单：  
- 判别器最后一层去掉 sigmoid   
- 生成器和判别器的 loss 不取 log   
- 每次更新判别器的参数之后把它们的绝对值截断到不超过一个固定常数 c   
*上述第三点，在WGAN的后来一篇工作 WGAN-GP 中，将梯度截断替换为了梯度惩罚*   

**2.3.3 f-divergence 和 IPM 对比**   
- f-divergence 两个问题  
    - 随着数据空间的维度 $x\in\mathcal X=\mathcal R^d$ 的增加，f-divergence 会非常难以计算；  
    - 两个分布的支撑集通常是未对齐的，这将导致散度值趋近于无穷；   
- IPM 不受数据维度的影响，且一致收敛于 $p_{data}$，$p_g$ 两个分布之间的距离；而且即便是在两个分布的支撑集不存在重合时，也不会发散；   

**2.3.4 辅助的目标函数**   
在许多 GAN 的应用中，会使用额外的 Loss 用于稳定训练或者达到其他的目的；  
- 比如在图像翻译，图像修复，超分辨当中，生成器会加入目标图像作为监督信息；  
- EBGAN 则把 GAN 的判别器作为一个能量函数，在判别器中加入重构误差；  
- CGAN 则使用类别标签信息作为监督信息；   

## 2.4 生成式模型
**2.4.1 自回归模型：pixelRNN 与 pixelCNN**  
自回归模型通过对图像数据的概率分布 $p_{data}(x)$ 进行显式建模，从而定义一个易处理的密度函数，然后利用极大似然估计优化模型：  
\begin{equation}
p_{data}(x)=\prod_{i=1}^n p(x_i\|x_1,x_2,...,x_{i-1})
\end{equation}  
给定 $x_1,x_2,...,x_{i-1}$ 条件下，所有 $p(x_i)$ 的概率乘起来就是图像数据的分布。如果使用 RNN 对上述依然关系建模，就是 pixelRNN；如果使用 CNN，则是 pixelCNN；由于两者都是逐像素操作，所以**速度很慢**；语音领域大火的 WaveNet 就是一个典型的自回归模型；  

**2.4.2 VAE**（变分自编码器）  
定义一个不易处理的密度函数，通过附加的隐变量 z 对密度函数进行建模：真实样本 X 通过神经网络计算出均值方差（假设隐变量服从正态分布），然后通过采样得到采样变量 Z 并进行重构；VAE 和 GAN 均是学习了隐变量 z 到真实数据分布的映射，但是和GAN不同的是：  
- GAN 的思路比较粗暴，使用一个判别器去度量分布转换模块（即生成器）生成的分布与真实数据分布的距离；   
- VAE 则没有那么直观，VAE 通过约束隐变量 z 服从标准正态分布以及重构数据实现了分布转换映射 X=G(z)；   

**2.4.3 生成式模型对比**  
- 自回归模型通过对概率分布显式建模来生成数据；   
- VAE 和 GAN 均是：假设隐变量 z 服从某种分布，并学习一个映射 X=G(z) ，实现隐变量分布 z 与真实数据分布 p_{data}(x) 的转换；   
- GAN 使用判别器去度量映射 X=G(z) 的优劣，而 VAE 通过隐变量 z 与标准正态分布的 KL 散度和重构误差去度量；   

## 2.5 常见的 GAN
**2.5.1 DCGAN**  
DCGAN 使用 CNN 结构来稳定 GAN 的训练，并使用了一些 trick：  
- Batch Normalization；  
- 使用Transpose convlution进行上采样；  
- 使用Leaky ReLu作为激活函数；  
上面这些 trick 对于稳定 GAN 的训练有许多帮助，自己设计 GA 网络时也可以酌情使用；   

**2.5.2 层级结构**  
GAN 对于高分辨率图像生成一直存在许多问题，层级结构的 GAN 通过逐层次，分阶段生成，一步步提生图像的分辨率；  
- 多对 GAN： **StackGAN**，**GoGAN**；  
- 单一 GAN：分阶段生成的有 **ProgressiveGAN**；   

**2.5.3 自编码结构**  
经典的 GAN 结构里面，判别网络通常被当做一种用于区分真实——生成样本的概率模型；而在自编码器结构里面，判别器（使用AE作为判别器）通常被当做能量函数(Energy function)；对于离数据流形空间比较近的样本，其能量较小，反之则大；有了这种距离度量方式，自然就可以使用判别器去指导生成器的学习；`和 LSGAN 有啥区别`{:.warning}  
AE 作为判别器，为什么就可以当做能量函数，用于度量生成样本离数据流形空间的距离呢？首先，先看AE的loss：

$D(u)=\lVert u-AE(u)\rVert$  

AE 的 loss 是一个重构误差；使用 AE 做为判别器时，如果输入真实样本，其重构误差会很小；如果输入生成的样本，其重构误差会很大；因为对于生成的样本，AE 很难学习到一个图像的压缩表示（即生成的样本离数据流行形空间很远）；所以，VAE的重构误差作为 $p_{data}$ 和 $p_g$ 之间的距离度量是合理的；典型的自编码器结构的 GAN 有：**BEGAN**，**EBGAN**, **MAGAN** 等；

## 2.6 训练难点
**2.6.1 理论中存在的问题**  
经典 GAN 的判别器有两种 loss，分别是：
\begin{equation}\label{loss_1}
\mathbb E_{x\sim p_{g}}[log(1-D(x))]
\end{equation}
 \begin{equation}\label{loss_2}
\mathbb E_{x\sim p_g}[-log(D(x))]
 \end{equation}

公式 $\eqref{loss_1}$ ：在判别器达到最优的时候，等价于最小化生成分布与真实分布之间的 JS 散度，由于随机生成分布很难与真实分布有不可忽略的重叠以及 JS 散度的突变特性，使得生成器面临**梯度消失**的问题；  
公式 $\eqref{loss_2}$ ：在最优判别器下，等价于既要最小化生成分布与真实分布直接的 KL 散度，又要最大化其 JS 散度，相互矛盾，导致梯度不稳定，而且 KL 散度的不对称性使得生成器宁可丧失多样性也不愿丧失准确性，导致 collapse mode现象；  

**2.6.2 实践中存在的问题**  
GAN在实践中存在两个问题：

其一，Ian Goodfellow 在理论中虽然证明了 GAN 是可以达到纳什均衡的；可是我们在实际实现中，我们是在参数空间优化，而非函数空间，这导致理论上的保证在实践中是不成立的；  
其二，GAN 的优化目标是一个极小极大(min max)问题，即 $\mathop {\min }\limits_G \mathop {\max }\limits_D V(G,D)$ ，也就是说，优化生成器的时候，最小化的是 $\mathop{max} \limits_D V(G,D)$；可是我们是迭代优化的，要保证 $V(G,D)$ 最大化，就需要迭代非常多次，这就导致训练时间很长；如果我们只迭代一次判别器，然后迭代一次生成器，不断循环迭代；这样原先的极小极大问题，就容易变成极大极小(max min)问题，可二者是不一样的，即：  
\begin{equation}
\mathop {\min }\limits_G \mathop {\max }\limits_D V(G,D)\neq\mathop{\max}\limits_D \mathop\min\limits_G V(G,D)
\end{equation}  

按极小极大问题考虑，那么迭代就是这样的，生成器先生成一些样本，然后判别器给出错误的判别结果并惩罚生成器，于是生成器调整生成的概率分布；可是这样往往导致生成器变“懒”，只生成一些简单的，重复的样本，即缺乏多样性，也叫 **mode collapse**；  

**2.6.3 稳定GAN训练的技巧**  
如上所述，GAN 训练过程十分不稳定，可以通过一些技巧来文帝给你训练：  
- **Feature matching**: 方法很简单，使用判别器某一层的特征替换原始 GAN Loss 中的输出；即最小化：生成图片通过判别器的特征和真实图片通过判别器得到的特征之间的距离；  
- **标签平滑**：GAN 训练中的标签非 0 即 1，这使得判别器预测出来的 confidence 倾向于更高的值；使用标签平滑可以缓解该问题；具体来说，就是把标签1替换为0.8~2.0之间的随机数；  
- **谱归一化**：WGAN 和 Improve WGAN 通过施加 Lipschitz 条件来约束优化过程，谱归一化则是对判别器的每一层都施加 Lipschitz 约束，但是谱归一化相比于 Improve WGAN 计算效率要高一些；  
- **PatchGAN**：准确来说 PatchGAN 并不是用于稳定训练，但这个技术被广泛用于图像翻译当中，PatchGAN 相当于对图像的每一个小 Patch 进行判别，这样可以使得生成器生成更加锐利清晰的边缘；具体做法是这样的：假设输入一张 256x256 的图像到判别器，输出的是一个4x4的 confidence map，confidence map中每一个像素值代表当前 patch 是真实图像的置信度，即为 PatchGAN；当前图像 patch 的大小就是感受野的大小，最后将所有 Patch 的 Loss 求平均作为最终的 Loss；  

## 2.7 模式崩溃
**2.7.1 改进目标函数**  
为了避免前面提到的由于优化 maxmin 导致 mode 跳来跳去的问题，UnrolledGAN 采用修改生成器 loss 来解决；具体而言，UnrolledGAN 在更新生成器时更新k次生成器，参考的 Loss 不是某一次的 loss，是判别器后面 k 次迭代的 loss；注意，判别器后面 k 次迭代不更新自己的参数，只计算 loss 用于更新生成器；这种方式使得生成器考虑到了后面 k 次判别器的变化情况，避免在不同 mode 之间切换导致的模式崩溃问题；此处务必和迭代k次生成器，然后迭代 1 次判别器区分开；DRAGAN 则引入博弈论中的无后悔算法，改造其 loss 以解决 mode collapse 问题；前文所述的 EBGAN 则是加入 VAE 的重构误差以解决 mode collapse；    

**2.7.2 改进网络结构**  
**MAD-GAN**（Multi agent diverse GAN）采用多个生成器，一个判别器以保障样本生成的多样性；相比于普通 GAN，多了几个生成器，且在 loss 设计的时候，加入一个正则项；正则项使用余弦距离惩罚三个生成器生成样本的一致性；   
**MRGAN**则添加了一个判别器来惩罚生成样本的 mode collapse 问题；输入样本 x 通过一个 Encoder 编码为隐变量 $E(x)$ ，然后隐变量被 Generator 重构，训练时，Loss 有三个；$D_M$ 和 $R$（重构误差）用于指导生成 real-like 的样本；而 $D_D$ 则对 $E(x)$ 和 $z$ 生成的样本进行判别，显然二者生成样本都是 fake samples，所以这个判别器主要用于判断生成的样本是否具有多样性，即是否出现 mode collapse；   

**2.7.3 Mini-batch Discrimination**  
Mini-batch discrimination 在判别器的中间层建立一个 mini-batch layer 用于计算基于 L1 距离的样本统计量，通过建立该统计量去判别一个 batch 内某个样本与其他样本有多接近；这个信息可以被判别器利用到，从而甄别出哪些缺乏多样性的样本；对生成器而言，则要试图生成具有多样性的样本；    

# 3 隐空间
>隐空间是数据的一种压缩表示的空间；通常来说，我们直接在数据空间对图像进行修改是不现实的，因为图像属性位于高维空间中的流形中；但是在隐空间，由于每一个隐变量代表了某个具体的属性，所以这是可行的；

这部分探讨 GAN 是如何处理隐空间及其属性的，此外还将探讨变分方法如何结合到GAN的框架中；  

## 3.1 隐空间分解
GAN的输入隐变量 z 是非结构化的，我们不知道隐变量中的每一位数分别控制着什么属性；因此有学者提出，将隐变量分解为一个条件变量 c 和标准输入隐变量 z；具体包括监督的方法和无监督的方法；  

**3.1.1 监督方法**    
**CGAN**：将随机噪声 z 和类别标签 c 作为生成器的输入，判别器则将生成的样本/真实样本与类别标签作为输入；以此学习标签和图片之间的关联性。

**ACGAN**：将随机噪声 z 和类别标签 c 作为生成器的输入，判别器则将生成的样本/真实样本输入，且回归出图片的类别标签；以此学习标签和图片之间的关联性；   

**3.1.2 无监督方法**    
无监督方法不使用任何标签信息；因此，无监督方法需要对隐空间进行解耦得到有意义的特征表示；  
**InfoGAN**：对把输入噪声分解为隐变量 z 和条件变量 c （训练时，条件变量 c 从均匀分布采样而来），二者被一起送入生成器；在训练过程中通过最大化 c 和 G(z,c) 的互信息 I(c;G(z,c)) 以实现变量解耦（ I(c;G(z,c)) 的互信息表示 c 里面关于 G(z,c) 的信息有多少，如果最大化互信息  I(c;G(z,c)) ，也就是最大化生成结果和条件变量 c 的关联性）；模型结构和 CGAN 基本一致，除了 Loss 多了一项最大互信息；  

从上面分析可以看出，InfoGAN 只是实现了信息的解耦，至于条件变量 c 每一个值的具体含义是什么，我们无法控制；  
**ss-InfoGAN**:采用半监督学习方法，把条件变量 c 分成两部分， $c=c_{ss}\bigcap c_{us}$，$c_{ss}$ 则利用标签像 CGAN 一样学习，$c_{us}$ 则像 InfoGAN 一样学习；   

## 3.2 GAN & VAE
GAN 相比于 VAE 可以生成清晰的图像，但是却容易出现 mode collapse 问题；VAE 的目标就是                                                                                                                                                                    重构所有样本，所以不会出现 mode collapse 问题；   
**VAEGAN**:结构很像前文提及的 MRGAN；Loss 包括三个部分，分别是判别器某一层特征的重构误差，VAE 的 Loss，GAN 的 Loss；   


# 4 模型评估

>实验发现，MMD 和 1-NN two-sample test 是最为合适的评价指标，这两个指标可以较好的区分真实样本和生成的样本, mode collapsing，且计算高效；   
总体说来，GAN 的学习是一个无监督学习过程，所以很难找到一个比较客观的，可量化的评估指标；有许多指标在数值上虽然高，但是生成效果却未必好；总之，GAN的评价目前依然是一个开放性的问题；  


**符号**：$P_g$: 生成数据分布；$P_r$ 表示真实数据分布；$E$ :数学期望；$x$ :输入样本；$x\sim P_g$ :表示 $x$ 为生成样本的采样；$x\sim P_r$ :表示 $x$ 为真实样本的采样；$y$ :样本标签；$M$ :分类网络，通常选择 Inception network；   

现有的 example-based（基于样本层面做评价）方法，均是对生成样本与真实样本提取特征（通常用 InceptionNet），然后在特征空间做距离度量；    

## 4.1 Inception Score
以 ImageNet 为例，训练好的 GAN 所生成的样本经过 InceptionNet后，得到的判别概率应该具有如下特性：   
- 对于同一个类别的图片，其输出的概率分布应该趋向于一个脉冲分布；可以保证生成样本的准确性；    
- 对于所有类别，其输出的概率分布应该趋向于一个均匀分布，这样才不会出现 mode collapsing 等，可以保证生成样本的多样性；    
因此，设计指标：  
\begin{equation}
IS(P_g)=e^{E_{x \sim P_g}[KL(p_M(y\|x)\Vert{p_M(y)})]}  
\end{equation}
理想的 GAN， $p_M(y|x)$ 趋近于脉冲分布， $p_M(y)$ 趋近于均匀分布；二者 KL 散度会很大；Inception Score 自然就高。实际实验表明，Inception Score 和人的主观判别趋向一致；IS 的计算没有用到真实数据，具体值取决于模型 M 的选择；    
**特点**：可以一定程度上衡量生成样本的多样性和准确性，但是无法检测过拟合；Mode Score 也是如此；不推荐在和 ImageNet 数据集差别比较大的数据上使用；`什么叫差别较大`{:.warning}  

## 4.2 Mode Score
Mode Score 作为 Inception Score 的改进版本，关注了关于生成样本和真实样本预测的概率分布的相似性：    
\begin{equation}
 MS(P_g)=e^{E_{x\sim P_g}[KL(p_M(y|x)\Vert{p_M(y)})-KL(p_M(y)\Vert p_M(y^*))]}
\end{equation}

## 4.3 Kernel MMD
Maximum Mean Discrepancy；   
\begin{equation}\label{MMD}
MMD^2(P_r,P_g)=E{x_r\sim{P_r},x_g\sim{P_g}}[\lVert\Sigma{i=1}^{n1}k(x_r)-\Sigma{i=1}^{n2}k(x_g)\rVert]
\end{equation}  
核函数 k 把样本映射到再生希尔伯特空间(Reproducing Kernel Hilbert Space, RKHS) ，RKHS 相比于欧几里得空间有许多优点，对于函数内积的计算是完备的；  
公式 $\eqref{MMD}$ 后得到：   
\begin{equation}
MMD^2(P_r,P_g)=E{x_r,x_r^\prime \sim{P_r},x_g,x_g^\prime \sim{P_g}}[k(x_r,x_r^\prime)-2k(x_r,x_g)+k(x_g,x_g^\prime)]
\end{equation}
MMD值越小，两个分布越接近；   
**特点**：可以一定程度上衡量模型生成图像的优劣性，计算代价小；推荐使用；    

## 4.4 Wasserstein distance
Wasserstein distance 在最优传输问题中通常也叫做推土机距离；这个距离的介绍在 WGAN 中有详细讨论；   
Wasserstein distance 可以衡量两个分布之间的相似性；距离越小，分布越相似；  
**特点**：如果特征空间选择合适，会有一定的效果；但是计算复杂度为 $O(n^3)$ 太高；   

## 4.5 FID
FID（Fréchet Inception Distance） 距离计算真实样本和生成样本在特征空间之间的距离；首先利用 Inception 网络来提取特征，然后使用高斯模型对特征空间进行建模；根据高斯模型的均值和协方差来进行距离计算：  
\begin{equation}
FID(\mathbb P_r,\mathbb P_g)=\lVert\mu_r-\mu_g\rVert+Tr(C_r+C_g-2(C_rC_g)^{1/2})
\end{equation}
$\mu$, $C$ 分别代表协方差和均值；   
**特点**：尽管只计算了特征空间的前两阶矩，但是鲁棒，且计算高效；   

## 4.6 1-NN classifier
使用留一法，结合 1-NN（1-Nearest Neighbor classifier） 分类器（别的也行）计算真实图片、生成图像的精度；如果二者接近，则精度接近50%，否则接近0%。对于 GAN 的评价问题，作者分别用正样本的分类精度，生成样本的分类精度去衡量生成样本的真实性，多样性；     
对于真实样本 $x_r$ ，进行 1-NN 分类的时候，如果生成的样本越真实；则真实样本空间 $\mathbb R$ 将被生成的样本 $x_g$ 包围；那么 $x_r$ 的精度会很低；   
对于生成的样本 $x_g$ ，进行 1-NN 分类的时候，如果生成的样本多样性不足。由于生成的样本聚在几个 mode，则 $x_g$ 很容易就和 $x_r$ 区分，导致精度会很高；   
**特点**：理想的度量指标，且可以检测过拟合；     

## 4.7 其他   
AIS，KDE 方法也可以用于评价 GAN，但这些方法不是 model agnostic metrics；也就是说，这些评价指标的计算无法只利用：生成的样本，真实样本来计算；  


# 5 GAN & RL
强化学习的目标是对于一个智能体，给定状态 s，去选择一个最佳的行为 a(action)；通常的可以定义一个价值函数 Q(s,a) 来衡量，对于状态 s，采取行动 a 的回报是 Q(s,a)，显然，我们希望最大化这个回报值；对于很多复杂的问题，我们是很难定义这个价值函数 Q(s,a) 的，就像我们很难定义 GAN 生成的图片到底有多好一样；   
说到这里，大家可能反应过来了；GAN 生成的图片好不好，我确实找不到一个合适的指标，那我学习一个判别器去判断一下生成图片和真实图片的距离不就好了吗；强化学习里面的价值函数 Q(s,a) 难以定义，那直接用个神经网络去学习它就好了；典型的模型有 InverseRL，GAIL等；   


# 6 展望
- GAN 的训练崩溃，模式崩溃问题等依然有待研究改进；    
- Deep learning 尽管很强大，但目前仍有许多领域无法征服，期待 GAN 在此基础上会有一些作为；   



-------------------  
 End
{:.warning}  


## 附录
### A  推荐资料
[1]: Hong, Yongjun, et al. "How Generative Adversarial Networks and its variants Work: An Overview of GAN."


### B 参考资料

[1].  我爱馒头. GAN万字长文综述[EB/OL]. <https://zhuanlan.zhihu.com/p/58812258>. 2019-03-23/2019-03-26.     
