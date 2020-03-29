---
layout: article
title:  "「DLFramework」 TVM + Darknet 部署"
date:   2020-03-29 18:00:40 +0800
key: tvm-darknet
aside:
  toc: true
category: [AI, dl_frameworks, tvm]
---
<span id='head'></span>  
>

<!--more-->     


# 1 环境部署
```shell
TVM 编译   
pip install cffi opencv-python decorator Pillow
```
# 2 模型转换
下载：下载 YOLO 模型；     
编译：转成 TVM 可识别的格式；   

# 3 运行
调用：python，C++    

-------------------  
[End](#head)
{:.warning}  


# 附录
## A 参考资料
1. [利用TVM完成C++端的部署](https://oldpan.me/archives/the-first-step-towards-tvm-2)     
1. [Insightface c++](https://zhuanlan.zhihu.com/p/55996985)     
1. [官网](https://docs.tvm.ai/install/from_source.html#build-the-shared-library)     
1. [YOLO C++](https://blog.csdn.net/weixin_43953703/article/details/94889958#_TVMYOLODarkNet_37)     
