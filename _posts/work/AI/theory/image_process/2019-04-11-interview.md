---
layout: article
title:  "「CV」 图像处理问答"
date:   2019-04-11 11:35:40 +0800
key: image-process-question
aside:
  toc: true
tags: Q&A
category: [AI, image_process]
sidebar:
  nav: INTERVIEW
---
<span id='head'></span>  


<!--more-->


|  |  |  |  |
| --- | --- | --- | --- |
| [形态学](#morphology) | [仿射变换](#affine) |  |  |
| [噪声](#noise) |  |  |  |
| [HOG](#hog) |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


<span id="morphology">    </span>  

**形态学**
{:.warning}
```c++
Mat kernel(5,5,CV_8U,cv::Scalar(1));
Mat kernel = getStructuringElement(MORPH_RECT, (5, 5))
morphologyEx(); //  MORPH_OPEN、MORPH_CLOSE、MORPH_GRADIENT、MORPH_TOPHAT、MORPH_BLACKHAT
```

膨胀：扩大    
腐蚀：消除     
开：断开     
闭：连接     

*同一幅图像连续使用开操作或者闭操作是没有任何意义的，操作结果都和第一次的相同*     


<span id="noise">    </span>  

**噪声**
{:.warning}
椒盐噪声：随机出现的黑白点；通常来自于影响信号收到强烈干扰、数位转换器或位元传输错误而产生；    
高斯噪声：正态分布，钟形曲线；    

[python 实现](#noise_python)、[c++ 实现](#noise_cpp)   


<span id="affine">    </span>  

**仿射变换**
{:.warning}
```python
M = cv2.getRotationMatrix2D(center, angle, scale)
M = cv2.getAffineTransform()        # 输入三对点（变换前和变换后）
affine = cv2.warpAffine(img, M, (w, h), borderMode)       # 仿射变换
M = cv2.getPerspectiveTransform()   # 输入四对点
affine = cv2.warpPerspective(img, M, (w, h), borderMode)  # 透视变换·密集
findhomography()  perspectiveTransform()                  # 透视变换·稀疏 ？ 有什么区别
# borderMode： BORDER_REPLICATE 重复边界像素   BORDER_CONSTANT 填充固定值，默认 0  BORDER_ISOLATED  有效区域
#              BORDER_REFLECT  反射  BORDER_REFLECT101 / BORDER_DEFAULT  对称
```
仿射变换：3 点确定一平面，由一组线性变换（缩放、平移和旋转）组成；（就是方形到平行四边形的变化）    
透视变换：4 点确定三维面，实现了透视的效果（扭曲）        

[python 实现](#affine_python)、


<span id="hog">    </span>  

**HOG算法原理描述**
{:.warning}
**梯度直方图（Histogram of Oriented Gradient, HOG）**特征：先将原图划分成多个区域，然后球每个区域的梯度，再求直方图，构成图像的特征；。在深度学习取得成功之前；是传统图像中用来进行物体检测的特征描述子，在 DL 之前，常结合 SVM 分类器用来做目标检测；在行人检测中获得了较大的成功；    

**原理**：HOG 认为物体的局部形状可以被边缘的分布所描述；因此对原图等分，然后求子区域的梯度直方图，最终把所有区域的直方图连接在一起；为了提升对照射/阴影的不变性，可以对大的区域取梯度均值，用来给内部的子区域做归一化；     
**优势**：与其他描述子相比，HOG拥有几何和光学转化不变性（除非物体方向改变）；因此HOG描述子尤其适合人的检测；    

**过程**：     
1. 灰度化   
2. 划分成小 cells    
3. 计算每个 cell 的梯度     
4. 统计每个 cell 的梯度直方图，就是 cell 的描述子      

-------------------  
[End](#head)
{:.warning}  

# 附录
## A 代码示例
<span id="noise_python"> **噪声（python）**</span>
```python
#!/usr/bin/python3 python
# encoding: utf-8

import cv2
from random import uniform, randint
import numpy as np

__all__ = ['add_noise', 'add_gaussian_noise', 'add_salt_noise']

def transparent(img):
  return 4 == img.shape[2]

def random_set_pixel(img, n, value):
    n = int(n)
    w, h, c = img.shape

    for i in range(n):
        i, j = randint(0, w-1), randint(0, h-1)
        img[i, j, :] = value

def add_salt_noise(img, rate=0.5):
    w, h, c = img.shape
    n = max(w*h*rate, 20)
    out = img.copy()

    random_set_pixel(out, n, randint(0, 255)) # can use 255
    random_set_pixel(out, n, randint(0, 255)) # can use 0

    # keep transparent
    if transparent(img):
        out[:, :, 3] = img[:, :, 3]

    return out

def add_gaussian_noise(img, mean=0, var=0.001, gray=0.5):
    if uniform(0, 1) < gray:
        noise = np.random.normal(mean, var ** 0.5, (img.shape[0], img.shape[1])) * 60
        noise = np.tile(noise[:, :, np.newaxis], (1, 1, img.shape[2]))
    else:
        noise = np.random.normal(mean, var ** 0.5, img.shape) * 60
    img = img.astype(np.int16)
    noise = noise.astype(np.int16)
    if transparent(img):
        noise[:, :, 3] = img[:, :, 3]

    img = cv2.add(img, noise)
    img = np.clip(img, 0, 255)
    img = img.astype(np.uint8)

    return img

def add_noise(img, salt_rate=0.5, gaussian_rate=1):
    if uniform(0, 1) < gaussian_rate:
        img = add_gaussian_noise(img, mean=uniform(0.1, 2), var=uniform(0.002, 1), gray=0.9)
    if uniform(0, 1) < salt_rate:
        img = add_salt_noise(img, uniform(0.05, 0.3))

    return img
```


<span id="noise_cpp"> **噪声（c++）**</span>
[【OpenCV】给图像添加噪声](https://blog.csdn.net/qq_34784753/article/details/69379135)    


<span id="affine_python"> **仿射变换（python）**</span>
```python
#!/usr/bin/python3 python
# encoding: utf-8

import cv2
from random import uniform, randint
import numpy as np

__all__ = ['crop_foreground', 'random_affine']

def transparent(img):
  return 4 == img.shape[2]

def crop_foreground(img):
    if transparent(img):
        gray = img[:, :, 3]
        kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (30, 30))
        gray = cv2.dilate(gray, kernel)
        gray = cv2.copyMakeBorder(gray, 1, 1, 1, 1, cv2.BORDER_CONSTANT)
        contours, hierarchy = cv2.findContours(gray, cv2.RETR_CCOMP, cv2.CHAIN_APPROX_NONE)

        if len(contours) == 0:  # why
            return img

        x, y, w, h = cv2.boundingRect(contours[0])
        img_valid = img[y:y+h, x:x+w, :]

        return img_valid
    else:
        return img

def random_affine(img, crop=True, plain=False):
    w, h, c = img.shape
    top_left = (uniform(0, 0.3), uniform(0, 0.3))
    bottom_left = (uniform(0, 0.5), uniform(0.6, 1))
    top_right = (uniform(max(bottom_left[0], top_left[0]) +0.3, 1), uniform(0, bottom_left[1]-0.3))
    bottom_right = (uniform(max(bottom_left[0], top_left[0])+0.3, 1), uniform(max(top_right[1], top_left[1])+0.3, 1))

    if transparent(img):
        mode = cv2.BORDER_REPLICATE
    else:
        mode = cv2.BORDER_CONSTANT

    if plain:
        M = cv2.getAffineTransform(np.float32([(0,0), (w-1, 0), (0, h-1)]),
                                   np.float32([(w*top_left[0], h*top_left[1]),
                                               (w*top_right[0], h*top_right[1]),
                                               (w*bottom_left[0], h*bottom_left[1])]))
        affine = cv2.warpAffine(img, M, (w, h), borderMode=mode)
    else:
        M = cv2.getPerspectiveTransform(np.float32([(0,0), (w-1, 0), (0, h-1), (w-1, h-1)]),
                                        np.float32([(w*top_left[0], h*top_left[1]),
                                                    (w*top_right[0], h*top_right[1]),
                                                    (w*bottom_left[0], h*bottom_left[1]),
                                                    (w*bottom_right[0], h*bottom_right[1])]))
        affine = cv2.warpPerspective(img, M, (w, h), borderMode=mode)

    if crop:
        affine = crop_foreground(affine)

    return affine
```
