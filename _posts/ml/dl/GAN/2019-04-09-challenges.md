---
layout: article
title:  "「DL」 GAN 中的难题"
date:   2019-04-09 15:48:40 +0800
key: gan-challenges-20190409
aside:
  toc: true
category: [DL, GAN]
sidebar:
  nav: GAN
---

>GAN 解决了生成式模型的一些问题, 并且对其他方法的发展也有一定的启发意义, 但是 GAN 并不完美, 它在解决已有问题的同时也引入了一些新的问题；   

<!--more-->

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


**训练不稳定**  
GAN 最突出的优点同时也是它最大的问题根源；GAN 采用对抗学习的准则，理论上还不能判断模型的收敛性和均衡点的存在性；  
训练过程需要保证两个对抗网络的平衡和同步，而实际过程中两个对抗网络的同步不易把控，训练过程可能不稳定；   
*Wasserstein GAN 彻底解决了训练不稳定问题；*   
容易崩溃，这个问题有学者提出了许多解决方案，比如 WGAN，LSGAN 等；   

**收敛评估指标**
木便并没有一个指标可以评估生成器和判别器是否收敛   

# 可解释性差
作为以神经网络为基础的生成式模型，GAN 存在神经网络类模型的一般性缺陷，即可解释性差；    

# 模式崩溃
又叫模型坍塌，生成器陷入一个极小的分布内，生成的样本不再变化；   
Wasserstein GAN 基本解决了崩溃模式现象；   
尽管有很多相关的研究，但是由于图像数据的高维度特性，这个问题依然还没完全解决；   
**2.7.1 改进目标函数**  
为了避免前面提到的由于优化 maxmin 导致 mode 跳来跳去的问题，UnrolledGAN 采用修改生成器 loss 来解决；具体而言，UnrolledGAN 在更新生成器时更新k次生成器，参考的 Loss 不是某一次的 loss，是判别器后面 k 次迭代的 loss；注意，判别器后面 k 次迭代不更新自己的参数，只计算 loss 用于更新生成器；这种方式使得生成器考虑到了后面 k 次判别器的变化情况，避免在不同 mode 之间切换导致的模式崩溃问题；此处务必和迭代k次生成器，然后迭代 1 次判别器区分开；DRAGAN 则引入博弈论中的无后悔算法，改造其 loss 以解决 mode collapse 问题；前文所述的 EBGAN 则是加入 VAE 的重构误差以解决 mode collapse；    

**2.7.2 改进网络结构**  
**MAD-GAN**（Multi agent diverse GAN）采用多个生成器，一个判别器以保障样本生成的多样性；相比于普通 GAN，多了几个生成器，且在 loss 设计的时候，加入一个正则项；正则项使用余弦距离惩罚三个生成器生成样本的一致性；   
**MRGAN**则添加了一个判别器来惩罚生成样本的 mode collapse 问题；输入样本 x 通过一个 Encoder 编码为隐变量 $E(x)$ ，然后隐变量被 Generator 重构，训练时，Loss 有三个；$D_M$ 和 $R$（重构误差）用于指导生成 real-like 的样本；而 $D_D$ 则对 $E(x)$ 和 $z$ 生成的样本进行判别，显然二者生成样本都是 fake samples，所以这个判别器主要用于判断生成的样本是否具有多样性，即是否出现 mode collapse；   

**2.7.3 Mini-batch Discrimination**  
Mini-batch discrimination 在判别器的中间层建立一个 mini-batch layer 用于计算基于 L1 距离的样本统计量，通过建立该统计量去判别一个 batch 内某个样本与其他样本有多接近；这个信息可以被判别器利用到，从而甄别出哪些缺乏多样性的样本；对生成器而言，则要试图生成具有多样性的样本；    

# 计数问题
因视角太多而在特定位置生成过多的结构；  

# 角度问题
生成样本的视角错误；   

# 全局结构问题
生成样本的结构混乱；   


-------------------  
 End
{:.warning}  


# 附录
## A 参考资料
[1]. Kuntal G. 著, 刘梦馨 译. GAN 实战生成对抗网络[M]. 北京:电子工业出版社, 2018.38-41.     
[2]. 史丹青. 生成对抗网络入门指南[M]. 北京:机械工业出版社, 2018.   
[3]. Goodfellow I. [NIPS 2016 tutorial: generative adversarial networks](http://cn.arxiv.org/abs/1701.00160). arXiv preprint [arXiv: 1701.00160](https://arxiv.org/abs/1701.00160), 2016.    
