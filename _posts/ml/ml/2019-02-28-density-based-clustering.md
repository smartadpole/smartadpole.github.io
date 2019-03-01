---
layout: article
title:  "「ML」 DBSCAN：噪声场景下的密度聚类"
date:   2019-02-28 9:30:40 +0800
key: density-based-clustering-20190228
aside:
  toc: true
sidebar:
  nav: Unsupervised
category: [ML, Unsupervised]
---

>层次聚类算法和划分式聚类算往往只能发现凸形的聚类簇；为了弥补这一缺陷，发现各种任意形状的聚类簇，提出了基于密度的聚类算法；而 Density-based Spatial Clustering of Applications with Noise（**DBSCAN**）就是其中一种简单的实现；它是 1996 年由 M. Ester, H. Kriegel, J. Sander 及 X. Xu 提出的[聚类算法]()    
论文:<https://www.aaai.org/Papers/KDD/1996/KDD96-037.pdf>  


## 一、了解
密度聚类算法认为，这些稠密样本点被低密度区域（噪声）分割，而算法的目的就是要过滤低密度区域，发现稠密样本点；     

### 1. 基本概念

| 概念 | 描述 |  
| --- | --- |  
| **核心点** | 该点在距离 $\epsilon$ 范围内至少有 $MinPts$ 个样本点  |  
| **直接密度可达** | 核心点的 $\epsilon$ 范围内的其他点都是由核心点直接可达的 |  
| **可达性**(Reachability) | 样本点 $p_1 ,p_2 ….p_n$ 中, 假如 $p_{i+1}$ 从 $p_i$ 直接密度可达，那么我们就称 $p_1$ 到 $p_n$ 可达 |  
| **连结性**(Connectedness) | 两个点相互可达，则两点连结  |  
| **局外点** | 任何点都不可达的点 |  

可达性是直接密度可达的传递闭包，并且这种关系是非对称的；连结性是对称关系；DBSCAN 目的是找到密度相连对象的最大集合；  

### 2. 定义  
算法流程：  

    输入： $\epsolin$ — 半径
        MinPts — 给定点在 $\epsolin$ 邻域内成为核心点的最小领域点数
        $D$ — 集合
    输出：目标类簇集合
    方法： repeat
        1) 判断输入点是否为核心点
            util 所有输入点都判断完毕
        2) $\epsolin$ 距离内的所有直接密度可达点
            repeat
               针对所有核心点的 $\epsolin$ 邻域内所有直接密度可达点找到最大密度相连对象集合
               密度可达点的合并
            Util 所有核心点的 $\epsolin$ 邻域都遍历完毕


### 3. 优缺点
优势：  
  - 不需要预先声明聚类数量
  - 能分辨噪音（局外点）；   
  - 能够发现各种形状的聚类簇，甚至能找出一个聚类，它包围但不连接另一个聚类，另外，由于 MinPts 参数，single-link effect （不同聚类以一点或极幼的线相连而被当成一个聚类）能有效地被避免  ；      
  - 只需两个参数，且对数据库内的点的次序几乎不敏感（两个聚类之间边缘的点有机会受次序的影响被分到不同的聚类，另外聚类的次序会受点的次序的影响）  
  - 可以被设计成能配合可加速访问的数据库结构，例如 R*树  
  - 如果对资料有足够的了解，可以选择适当的参数以获得最佳的分类  

缺点：  
  - DBSCAN 不是完全决定性的：在两个聚类交界边缘的点会视乎它在数据库的次序决定加入哪个聚类，幸运地，这种情况并不常见，而且对整体的聚类结果影响不大——DBSCAN 对核心点和噪音都是决定性的。DBSCAN* 是一种变化了的算法，把交界点视为噪音，达到完全决定性的结果  
  - DBSCAN 聚类分析的质素受函数 regionQuery(P,ε) 里所使用的度量影响，最常用的度量是欧几里得距离，尤其在高维度资料中，由于受所谓“维数灾难”影响，很难找出一个合适的 ε ，但事实上所有使用欧几里得距离的算法都受维数灾难影响  
  - 如果数据库里的点有不同的密度，而该差异很大，DBSCAN 将不能提供一个好的聚类结果，因为不能选择一个适用于所有聚类的 minPts-ε 参数组合  
  - 如果没有对资料和比例的足够理解，将很难选择适合的 ε 参数  

### 4. 复杂度


### 5. 优化

## 二、 实践
[sklearn 示例](#sklearn_code)

-------------------  
 End
{:.warning}  



## 附录
### A 示例
<span id="sklearn_code">**1. sklearn DBSCAN 示例**</span>

简单例子：  

```python
import numpy as np  # 数据结构
import sklearn.cluster as skc  # 密度聚类
from sklearn import metrics   # 评估模型
import matplotlib.pyplot as plt  # 可视化绘图


X = np.random.random((30,2))

db = skc.DBSCAN(eps=1.5, min_samples=3).fit(X) #DBSCAN聚类方法 还有参数，matric = ""距离计算方法
labels = db.labels_  #和X同一个维度，labels对应索引序号的值 为她所在簇的序号。若簇编号为-1，表示为噪声

print('每个样本的簇标号:')
print(labels)

raito = len(labels[labels[:] == -1]) / len(labels)  #计算噪声点个数占总数的比例
print('噪声比:', format(raito, '.2%'))

n_clusters_ = len(set(labels)) - (1 if -1 in labels else 0)  # 获取分簇的数目

print('分簇的数目: %d' % n_clusters_)
print("轮廓系数: %0.3f" % metrics.silhouette_score(X, labels)) #轮廓系数评价聚类的好坏

for i in range(n_clusters_):
    print('簇 ', i, '的所有样本:')
    one_cluster = X[labels == i]
    print(one_cluster)
    plt.plot(one_cluster[:,0],one_cluster[:,1],'o')

plt.show()
```

复杂例子：  

```python
import numpy as np
from sklearn.cluster import DBSCAN
from sklearn import metrics
from sklearn.datasets.samples_generator import make_blobs
from sklearn.preprocessing import StandardScaler


# #############################################################################
# 产生样本数据
centers = [[1, 1], [-1, -1], [1, -1]]  # 生成聚类中心点
X, labels_true = make_blobs(n_samples=750, centers=centers, cluster_std=0.4,random_state=0) # 生成样本数据集

X = StandardScaler().fit_transform(X) # StandardScaler作用：去均值和方差归一化。且是针对每一个特征维度来做的，而不是针对样本。

# #############################################################################
# 调用密度聚类  DBSCAN
db = DBSCAN(eps=0.3, min_samples=10).fit(X)
# print(db.labels_)  # db.labels_为所有样本的聚类索引，没有聚类索引为-1
# print(db.core_sample_indices_) # 所有核心样本的索引
core_samples_mask = np.zeros_like(db.labels_, dtype=bool)  # 设置一个样本个数长度的全false向量
core_samples_mask[db.core_sample_indices_] = True #将核心样本部分设置为true
labels = db.labels_

# 获取聚类个数。（聚类结果中-1表示没有聚类为离散点）
n_clusters_ = len(set(labels)) - (1 if -1 in labels else 0)

# 模型评估
print('估计的聚类个数为: %d' % n_clusters_)
print("同质性: %0.3f" % metrics.homogeneity_score(labels_true, labels))  # 每个群集只包含单个类的成员。
print("完整性: %0.3f" % metrics.completeness_score(labels_true, labels))  # 给定类的所有成员都分配给同一个群集。
print("V-measure: %0.3f" % metrics.v_measure_score(labels_true, labels))  # 同质性和完整性的调和平均
print("调整兰德指数: %0.3f" % metrics.adjusted_rand_score(labels_true, labels))
print("调整互信息: %0.3f" % metrics.adjusted_mutual_info_score(labels_true, labels))
print("轮廓系数: %0.3f" % metrics.silhouette_score(X, labels))

# #############################################################################
# Plot result
import matplotlib.pyplot as plt

# 使用黑色标注离散点
unique_labels = set(labels)
colors = [plt.cm.Spectral(each) for each in np.linspace(0, 1, len(unique_labels))]
for k, col in zip(unique_labels, colors):
    if k == -1:  # 聚类结果为-1的样本为离散点
        # 使用黑色绘制离散点
        col = [0, 0, 0, 1]

    class_member_mask = (labels == k)  # 将所有属于该聚类的样本位置置为true

    xy = X[class_member_mask & core_samples_mask]  # 将所有属于该类的核心样本取出，使用大图标绘制
    plt.plot(xy[:, 0], xy[:, 1], 'o', markerfacecolor=tuple(col),markeredgecolor='k', markersize=14)

    xy = X[class_member_mask & ~core_samples_mask]  # 将所有属于该类的非核心样本取出，使用小图标绘制
    plt.plot(xy[:, 0], xy[:, 1], 'o', markerfacecolor=tuple(col),markeredgecolor='k', markersize=6)

plt.title('Estimated number of clusters: %d' % n_clusters_)
plt.show()
```

### B 参考文献  
[1]. 诸葛越. 百面机器学习[M]. 北京:人民邮电出版社. 2018.  
