---
layout: article
title:  "「DL」 TensorRT 入门"
date:   2019-02-12 16:00:40 +0800
key: tensorrt-foundation-20190212
aside:
  toc: true
tags: 资源
categories: [dl_frameworks, tensorrt]
---

> TensorRT 是 NVIDIA 发布的推理框架，用于在 NVIDIA GPUs 上进行深度学习模型部署；针对 NVIDIA 显卡做了优化；支持 TensorFlow、Caffe、PyTorch、MXnet、CNTK等所有主流框架及 ONNX；支持 C++（核心） 和 Python；  
官网: <https://developer.nvidia.com/tensorrt>  
ONNX TensorRT: <https://github.com/onnx/onnx-tensorrt>  
官方文档汇总: <https://docs.nvidia.com/deeplearning/sdk/tensorrt-archived/index.html>,  
python API: <https://docs.nvidia.com/deeplearning/sdk/tensorrt-api/python_api/>  

## 一、 安装  
### 1. Linux 环境[^1]' [^2]  

[安装报错解决方案](#error_install)  
1）准备  
- 安装 cuda；（建议用 deb 安装）  
- 下载安装包 <https://developer.nvidia.com/nvidia-tensorrt-download>  
*根据自己的环境，下载相应的版本（ubuntu1x04, cudax.x, trt4.x.x.x ）；*   

2）安装  
```shell
sudo dpkg -i nv-tensorrt*.deb
sudo apt-get update
sudo apt-get install tensorrt
```

3）检测是否安装成功  
`dpkg -l | grep TensorRT`  
有输出则是安装成功  

4）卸载  

[TensorRT 文件组织](#install_dir)  

## 二、 Demo




-------------------  
 End
{:.warning}  



## 附录
### A 基本操作
<span id="error_install">**1. 安装时报错**</span>  
1） 密钥没注册  
提示： `The public CUDA GPG key does not appear to be installed.
To install the key, run this command:
sudo apt-key add /var/nv-tensorrt-repo-cuda8.0-ga-trt4.0.1.6-20180612/7fa2af80.pub`  

解决： 执行最后提示的那句话 `sudo apt-key add /var/nv-tensorrt*.pub`  

2） 缺乏依赖  
报错信息：  
```
The following packages have unmet dependencies:
 tensorrt : Depends: libnvinfer4 (>= 4.1.2) but it is not going to be installed
            Depends: libnvinfer-dev (>= 4.1.2) but it is not going to be installed
            Depends: libnvinfer-samples (>= 4.1.2) but it is not going to be installed
E: Unable to correct problems, you have held broken packages.
```
分析： 缺什么安什么，最终发现缺乏 `cuda-cublas-8-0`；是因为本机 cuda 使用了 run 安装，而 TensorRT 的 cuda 用的是 deb 安装的，deb 中有特别的依赖库；

解决： 准备 cuda deb 包即可  
下载 cuda 8.0 的相关 deb 包（如下图红框所示） <https://developer.nvidia.com/cuda-80-ga2-download-archive>；  
<img src="/assets/images/AI/dl_framework/tensorrt/cuda-8-0-deb.png" height="600"/>    

```shell
# 准备 cuda 依赖
sudo dpkg -i cuda-repo-ubuntu1604-8-0-local-cublas-performance-update_8.0.61-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1604-8-0-local-ga2_8.0.61-1_amd64.deb
sudo apt-get update

# 安装依赖
sudo apt-get install python3-libnvinfer-doc
```

<span id="install_dir">**2. TensorRT 的文件组织**</span>  
安装后会生成 `/usr/src/tensorrt` 文件夹：   
```
tensorrt
    ├── bin     # 文件夹用于存放编译后的二进制文件
    ├── data
    ├── python  # 和 data 一起存放官方例程用到的资源文件，比如caffemodel文件，TensorFlow模型文件，一些图片等
    └── samples # 文件夹中是官方例程的源码
```

进入 samples 文件夹直接 make，会在 bin 目录中生成可执行文件，可以一一进行测试学习；  

tensorRT 是不开源的：  
1） 头文件位于 `/usr/include/x86_64-linux-gnu`  
```
/usr/include/x86_64-linux-gnu/NvCaffeParser.h
/usr/include/x86_64-linux-gnu/NvInfer.h
/usr/include/x86_64-linux-gnu/NvInferPlugin.h
/usr/include/x86_64-linux-gnu/NvOnnxConfig.h
/usr/include/x86_64-linux-gnu/NvOnnxParser.h
/usr/include/x86_64-linux-gnu/NvUffParser.h
/usr/include/x86_64-linux-gnu/NvUtils.h
```

2） 库文件位于 `/usr/lib/x86_64-linux-gnu`   
```
/usr/lib/x86_64-linux-gnu/libnvinfer.so
/usr/lib/x86_64-linux-gnu/libnvToolsExt.so
/usr/lib/x86_64-linux-gnu/libnvinfer_plugin.a
/usr/lib/x86_64-linux-gnu/libnvinfer_plugin.so.4
/usr/lib/x86_64-linux-gnu/libnvcaffe_parser.so
/usr/lib/x86_64-linux-gnu/libnvparsers.so.4.1.2
/usr/lib/x86_64-linux-gnu/stubs/libnvrtc.so
/usr/lib/x86_64-linux-gnu/libnvcaffe_parser.a
/usr/lib/x86_64-linux-gnu/libnvidia-opencl.so.1
/usr/lib/x86_64-linux-gnu/libnvvm.so
/usr/lib/x86_64-linux-gnu/libnvinfer.a
/usr/lib/x86_64-linux-gnu/libnvvm.so.3
/usr/lib/x86_64-linux-gnu/libnvToolsExt.so.1
/usr/lib/x86_64-linux-gnu/libnvrtc.so.7.5
/usr/lib/x86_64-linux-gnu/libnvparsers.a
/usr/lib/x86_64-linux-gnu/libnvblas.so.7.5
/usr/lib/x86_64-linux-gnu/libnvToolsExt.so.1.0.0
/usr/lib/x86_64-linux-gnu/libnvcaffe_parser.so.4.1.2
/usr/lib/x86_64-linux-gnu/libnvinfer_plugin.so
/usr/lib/x86_64-linux-gnu/libnvrtc-builtins.so
/usr/lib/x86_64-linux-gnu/libnvparsers.so
/usr/lib/x86_64-linux-gnu/libnvrtc-builtins.so.7.5.18
/usr/lib/x86_64-linux-gnu/libnvblas.so.7.5.18
/usr/lib/x86_64-linux-gnu/libnvvm.so.3.0.0
/usr/lib/x86_64-linux-gnu/libnvrtc.so
/usr/lib/x86_64-linux-gnu/libnvrtc-builtins.so.7.5
/usr/lib/x86_64-linux-gnu/libnvinfer.so.4.1.2
/usr/lib/x86_64-linux-gnu/libnvidia-opencl.so.390.30
/usr/lib/x86_64-linux-gnu/libnvrtc.so.7.5.17
/usr/lib/x86_64-linux-gnu/libnvblas.so
/usr/lib/x86_64-linux-gnu/libnvinfer.so.4
/usr/lib/x86_64-linux-gnu/libnvparsers.so.4
/usr/lib/x86_64-linux-gnu/libnvinfer_plugin.so.4.1.2
/usr/lib/x86_64-linux-gnu/libnvcaffe_parser.so.4
```

## B 推荐资料
1. arleyzhang. TensorRT(5)-INT8校准原理. <https://arleyzhang.github.io/articles/923e2c40/>. 2018年09月03.   

### C 参考资料
[^1]:  NVIDIA. TensorRT Installation Guide[EB/OL]. <https://docs.nvidia.com/deeplearning/sdk/tensorrt-archived/tensorrt_401/tensorrt-install-guide/index.html#installing-debian>. -/2019-02-12.   
[^2]:  arleyzhang. TensorRT(1)-介绍-使用-安装[EB/OL]. <https://arleyzhang.github.io/articles/7f4b25ce/>. 2018-08-31/2019-02-12.   
