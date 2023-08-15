---
layout: page
permalink: /blogs/CrackImageIdentification/index.html
title: CrackImageIdentification
---
## 深度学习在材料性能研究领域的应用————裂纹识别

### 项目名称：基于深度学习算法的质子交换膜裂纹检测

#### 项目简介

在化工、设备等领域常用到各种膜材料，这些膜材料在服役期间可能产生疲劳裂纹。通过疲劳试验机可以直观地观察到材料在承受不同强度的载荷时的裂纹状态，但由于裂纹是不断扩展的，试验机需要一种高效的方法实现对裂纹尖端的
实时追踪。传统的基于机器学习的裂纹识别方法迁移性较差、耗时长；<br>
**基于深度学习的方法因其深层网络结构，无需人工选取图像特征，能够逐层从原始图像中直接学习到不同尺度的特征，使模型具有良好的自适应能力和泛化能力**。<br>
本文描述的工作主要针对质子交换膜材料的裂纹尖端进行识别。由于检测目标较精细，需要较高的定位精度，故选用了目标检测和语义分割两类不同的深度学习算法对裂纹进行检测，并在最后进行了两种方法的优劣对比。

- **目标检测部分选用Faster RCNN 网络，并对 VGG16 和 ResNet101 两种特征提取网络的效果进行对比**
- **语义分割部分选择 U-Net 网络，并进行参数调整和网络结构优化**。
- 对比实验结果发现，目标检测算法的训练速度更快，效率高；而语义分割算法所依赖的数据量更少，且迁移能力更强。

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/Crackfig1.jpg">
</div>

### 基于 Faster-RCNN 的裂纹检测

#### 运行环境

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/Crackfig2.jpg">
</div>

#### 数据集

本实验的数据集为真实项目中拍摄的质子交换膜裂纹数据集，即质子交换膜材料经过力学拉伸后所产生的裂纹的拍摄图片

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/Crackfig3.jpg">
</div>

#### 实验结果

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/Crackfig4.jpg">
</div>

随后对训练好的模型进行测试，模型的训练时间、测试时间以及对于裂纹检验情况的 MAP(因只有裂纹一类识别目标，故AP 值与 MAP 值相同)如下表 2-3所示。由表格中的结果可知，基于 ResNet101 特征提取网络的模型的训练、测试时间都比较短，训练的时长比 VGG16 快 11.4%;且对裂纹的检测也比较准确,MAP 值达到了 0.986，比 VGG16 提高了 5.79%。

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/Crackfig5.jpg">
</div>


<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/Crackfig6.jpg">
</div>

### 基于 U-Net 的裂纹检测

#### 语义分割算法

图像语义分割是计算机视觉的另一重要分支领域，目的在于将图像分为两个或两个以上有意义区域，或理解为区分图像中实体边界的过程。图像分割中最经典的任务即为语义分割。闽值法、聚类法等传统的分割方法无法识别图像中像素的所属类别，只是将目标与背景分割开来: 而基于深度学习的语义分割模型可以对图像中的每一个像素的类别进行判断标注，执行端到端的训练，输出的结果为图像的像素级分割图像。全像素语义分割即通过训练和学习为每个像素分配类别，并转化为可区分不同类别的、突出显示的感兴趣区域掩码 (mask)。Long等人提出的全卷积神经网络(FCN) 是将深度学习用于语义分割的开始，将分割的目标转变为像素，极大程度上提高了语义分割的准确性。

#### U-Net 语义分割网络

U-net 网络最初在 2015 年被 Ronneberger 等人提出并应用在医学领域的细胞壁分割上，是一个典型的编码器-解码器的结构，因网络结构像“U”而得名，U-net 网络结构如图 3-2 所示，由左半部分的编码器(Encoder) 和右半部分的解码器 (Decoder) 构成。

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/Crackfig7.jpg"><br>U-Net 结构示意图
</div>

#### 数据介绍

本实验的数据集为真实项目中拍摄的质子交换膜裂纹数据集，即质子交换膜材料经过力学拉伸后所产生的裂纹的拍摄图片。

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/Crackfig8.jpg">
</div>
<br>

#### 实验结果

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/Crackfig9.jpg">
</div>

> *本项目为实验室同族人员共同完成，是一个简单的模型复习应用于新背景的任务，仅以此为记录*
