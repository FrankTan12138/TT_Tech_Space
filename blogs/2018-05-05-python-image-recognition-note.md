---
layout: post
category : technology
tags : [datascience,datamining,development]
title: Python Image Recognition Note
---

Python图像识别研究


#### 研究方案

- 图像处理的相关库-openCV
- 基于PIL的相关库-pillow
- SIFT算法
- openCV+Keras+Tensorflow

#### 1.openCV+pillow

直方图计算法

哈希感知算法基本原理如下：

1、把图片转成一个可识别的字符串，这个字符串也叫哈希值
2、和其他图片匹配字符串

* aHash算法(平均哈希法)

* pHash算法(余弦变换感知哈希算法)

* dHash算法(均值感知哈希算法)

#### 2.openCV+SIFT

SIFT=Scale Invariant Feature Transform(尺度不变特征变换)

	SIFT特征对旋转、尺度缩放、亮度变化等保持不变性，是一种非常稳定的局部特征。

SIFT的4个主要步骤

1. 尺度空间的极值检测 搜索所有尺度空间上的图像，通过高斯微分函数来识别潜在的对尺度和选择不变的兴趣点。
2. 特征点定位 在每个候选的位置上，通过一个拟合精细模型来确定位置尺度，关键点的选取依据他们的稳定程度。
3. 特征方向赋值 基于图像局部的梯度方向，分配给每个关键点位置一个或多个方向，后续的所有操作都是对于关键点的方向、尺度和位置进行变换，从而提供这些特征的不变性。
4. 特征点描述 在每个特征点周围的邻域内，在选定的尺度上测量图像的局部梯度，这些梯度被变换成一种表示，这种表示允许比较大的局部形状的变形和光照变换。

核心关键:

	- DoG尺度空间的极值检测
	- 删除不稳定的极值点
	- 确定特征点的主方向
	- 生成特征点的描述点

#### 3.openCV+Keras+Tensorflow

验证码CAPTCHAs图片识别

3.1.创立数据集

python3 extract_single_letters_from_captchas.py

3.2.训练神经网络识别

python3 train_model.py

3.3.利用模型识别CAPTCHAs

python3 solve_captchas_with_model.py


