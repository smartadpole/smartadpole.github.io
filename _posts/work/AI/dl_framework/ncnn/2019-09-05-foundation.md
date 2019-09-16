---
layout: article
title:  "「DLFramework」 NCNN 入门"
date:   2019-01-30 15:00:40 +0800
key: ncnn-foundation-20190130
aside:
  toc: true
tags: 资源
categories: [dl_frameworks, ncnn, worktool]
---
<span id='head'></span>  
>腾讯 2017 年 7 月     开源的面向移动端的深度学习框架    
github:<https://github.com/Tencent/ncnn>  
document:<https://github.com/Tencent/ncnn/wiki>  
支持语言: C++      
支持框架: mxnet, caffe, onnx(pytorch)     
支持平台: 跨平台 ios/linux/windows，主要支持 Android；     

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

如果要支持 GPU(mobile)，需安装 vulkan；且为 cmake 添加参数 `-D Vulkan=ON`；    

```
该框架主要是在移动端做的优化，服务端（x86）基本没做；     
```
-------------------  
[End](#head)
{:.warning}  
# 附录
## A 参考资料
1. [NCNN入门](https://xywang93.github.io/2018/05/04/DeepLearning/%E5%B5%8C%E5%85%A5%E5%BC%8FAI/%E7%8E%A9%E8%BD%ACncnn/00-ncnn%E5%85%A5%E9%97%A8/)      
