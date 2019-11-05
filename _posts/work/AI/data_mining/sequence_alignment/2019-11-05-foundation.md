---
layout: article
title:  "「DM」 序列匹配资源汇总"
date:   2019-11-05 15:08:40 +0800
key: sequence-alignment-foundation-20191105
aside:
  toc: true
category: [data_mining, sequence_alignment]
tags: 资源
---
<span id='head'></span>  
>计算两个序列的相似度，可找到两者公共的部分，可带容错；   


<!--more-->

`序列匹配算法` · `序列匹配`     
`sequence alignment` · `significant alignment` · `global alignment` · `local alignment`   
*不同关键字在搜索引擎上搜索结果不同*     


# 1 综述

# 2 理论

# 3 其他

1. [The similarity metric](http://cn.arxiv.org/abs/cs/0111054)    
*2001-11-20* [paper](https://arxiv.org/abs/cs/0111054)     

1. [Approximate word matches between two random sequences](http://cn.arxiv.org/abs/0801.3145)    
*2008-01-21* [paper](https://arxiv.org/abs/0801.3145)    

1. [Empirical distribution of k-word matches in biological sequences](http://cn.arxiv.org/abs/0803.2085)   
*2008-03-14* [paper](https://arxiv.org/abs/0803.2085)   

1. [An Algorithm for Alignment-free Sequence Comparison using Logical Match](http://cn.arxiv.org/abs/1407.2237)    
ICCAE 2010 *2014-07-06* [paper](https://arxiv.org/abs/1407.2237)    

1. [Ultra-fast Multiple Genome Sequence Matching Using GPU](http://cn.arxiv.org/abs/1303.3692)    
*2013-03-15* [paper](https://arxiv.org/abs/1303.3692)     
$\bullet \bullet$    

1. [SlopMap: a software application tool for quick and flexible identification of similar sequences using exact k-mer matching](http://cn.arxiv.org/abs/1307.8407)     
*2013-07-31* [paper](https://arxiv.org/abs/1307.8407)    

1. [Geometry-based Adaptive Symbolic Approximation for Fast Sequence Matching on Manifolds](http://cn.arxiv.org/abs/1403.0820)    
*2014-03-04* [paper](https://arxiv.org/abs/1403.0820)     

1. [Measuring Congruence on High Dimensional Time Series](http://cn.arxiv.org/abs/1805.10697)    
*2018-05-27* [paper](https://arxiv.org/abs/1805.10697)    
针对高维序列度量；    

1. [Efficient Measuring of Congruence on High Dimensional Time Series](http://cn.arxiv.org/abs/1811.11856)    
*2018-11-27* [paper](https://arxiv.org/abs/1811.11856)    
比 DTW 更稳健；    


# 4 应用
## 4.1 全局

### 4.1.1 [串模式匹配](/algorithms/string/2019/10/29/pattern-match-foundation.html#11-模式匹配)

## 4.2 局部

### 4.2.1 [最长公共子序列](/algorithms/string/2019/10/29/pattern-match-foundation.html#12-最长公共子序列)

### 4.2.2 生物序列

1. [Measuring the similarity of protein structures by means of the universal similarity metric](https://pdfs.semanticscholar.org/5edd/204c9c3ecb4513ec3de44ef0a51795b1d870.pdf?_ga=2.197400687.1153843306.1572339852-129004075.1557370518)    
*2004* [paper](https://pdfs.semanticscholar.org/5edd/204c9c3ecb4513ec3de44ef0a51795b1d870.pdf?_ga=2.197400687.1153843306.1572339852-129004075.1557370518)    
蛋白质序列相似度计算；   


1. [A Comparative Study on String Matching Algorithm of Biological Sequences](http://cn.arxiv.org/abs/1401.7416)     
*2014-01-29* [paper](https://arxiv.org/abs/1401.7416)     

1. [An optimized Parallel Failure-less Aho-Corasick algorithm for DNA sequence matching](http://cn.arxiv.org/abs/1811.10498)    
ICIAfS 2016 *2018-11-26* [paper](https://arxiv.org/abs/1811.10498)    


1. [FindeR: Accelerating FM-Index-based Exact Pattern Matching in Genomic Sequences through ReRAM technology](http://cn.arxiv.org/abs/1907.04965)    
*2019-07-11* [paper](https://arxiv.org/abs/1907.04965)    

### 4.2.3 购买意向

1. [Personalized Purchase Prediction of Market Baskets with Wasserstein-Based Sequence Matching](http://cn.arxiv.org/abs/1905.13131)    
KDD 2019 oral *2019-03-24* [paper](https://arxiv.org/abs/1905.13131)    
购买意向匹配；    



### 4.2.4 股票预测

### 4.2.5 [视频序列匹配](/video/video_retrieval/2019/06/21/foundation.html#35-相似度度量)     

### 4.2.6 手势识别


-------------------  
[End](#head)
{:.warning}  

# 附录
## A 参考资料
1. wikipedia. Sequence alignment[EB/OL]. <https://en.wikipedia.org/wiki/Sequence_alignment>. -/2019-11-05.     
1. 维基百科. 序列比对[EB/OL]. <https://zh.wikipedia.org/wiki/%E5%BA%8F%E5%88%97%E6%AF%94%E5%B0%8D>. -/2019-11-05.     
1. 维基百科. 尼德曼-翁施算法[EB/OL]. <https://zh.wikipedia.org/wiki/%E5%B0%BC%E5%BE%B7%E6%9B%BC-%E7%BF%81%E6%96%BD%E7%AE%97%E6%B3%95>. -/2019-11-05.     
1. 维基百科. 史密斯-沃特曼算法[EB/OL]. <https://zh.wikipedia.org/wiki/%E5%8F%B2%E5%AF%86%E6%96%AF-%E6%B2%83%E7%89%B9%E6%9B%BC%E7%AE%97%E6%B3%95>. -/2019-11-05.     
1. 维基百科. 莱文斯坦距离[EB/OL]. <https://zh.wikipedia.org/wiki/%E8%90%8A%E6%96%87%E6%96%AF%E5%9D%A6%E8%B7%9D%E9%9B%A2>. -/2019-11-05.     
1. 小狗贤. 从零开始生物信息学(2):序列比对-Needleman-Wunsch算法[EB/OL]. <https://zhuanlan.zhihu.com/p/54142276>. 2019-01-17/2019-11-05.   
1. 小狗贤. 从零开始生物信息学(3):序列比对-Smith–Waterman算法[EB/OL]. <https://zhuanlan.zhihu.com/p/54194091>. 2019-01-17/2019-11-05.   
1. wikipedia. FASTA[EB/OL]. <https://en.wikipedia.org/wiki/FASTA>. -/2019-11-05.     
1. wikipedia. BLAST[EB/OL]. <https://en.wikipedia.org/wiki/BLAST_(biotechnology)>. -/2019-11-05.     
1. Paul Reiners. 动态编程和基因序列比对[EB/OL]. <https://www.ibm.com/developerworks/cn/java/j-seqalign/index.html>. 2008-04-17/2019-11-05.   
