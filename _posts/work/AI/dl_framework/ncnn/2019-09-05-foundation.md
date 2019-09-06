---
layout: article
title:  "「DLFramework」 NCNN 入门"
date:   2019-01-30 15:00:40 +0800
key: mace-foundation-20190130
aside:
  toc: true
tags: 资源
categories: [dl_frameworks, ncnn, worktool]
---
<span id='head'></span>  
>腾讯 2017 年 7 月     开源的面向移动端的深度学习框架    
github:<https://github.com/Tencent/ncnn>  
document:<https://github.com/Tencent/ncnn/wiki>  

<!--more-->   

# 1 安装
## 1.1 Linux
下载源码，使用 [cmake]() 编译；    
```shell
cd <ncnn-root-dir>
mkdir build && cd build
cmake -D CMAKE_INSTALL_PREFIX=<install_dir> ..
make -j4
```

-------------------  
[End](#head)
{:.warning}  
# 附录
## A 参考资料
1. [NCNN入门](https://xywang93.github.io/2018/05/04/DeepLearning/%E5%B5%8C%E5%85%A5%E5%BC%8FAI/%E7%8E%A9%E8%BD%ACncnn/00-ncnn%E5%85%A5%E9%97%A8/)      
