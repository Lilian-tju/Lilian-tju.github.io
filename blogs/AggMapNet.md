---
layout: page
permalink: /blogs/AggMapNet/index.html
title: AggMapNet：使用特征聚合的多通道网络增强和可解释的低样本组学深度学习 
---
## **AggMapNet：使用特征聚合的多通道网络增强和可解释的低样本组学深度学习**

![](https://secure2.wostatic.cn/static/418LoYsTWUpVsKxi8icHb5/image.png?auth_key=1692079347-bzGgrTKrZMvGwbfz23TCG9-0-dd400c5985a086277b0fe6c9ad684fa0)

> 文献来源：Nucleic Acids Research/2022.5.6/新加坡国立大学、清华大学

### Abstract

- 基于组学的生物医学学习经常依赖于高维（多达数千）和低样本量（数十到数百）的数据，这对高效的深度学习 (DL) 算法提出了挑战，尤其是对于低样本的组学研究。
- 在这里，开发了一种无监督的新型特征聚合工具 AggMap 来**聚合**和**映射**基于它们的内在相关性，**将组学特征转化为多通道 2D 空间相关的类图像特征图 (Fmaps)**。AggMap 在随机基准数据集上表现出强大的特征重建能力，优于现有方法。
- 以 AggMap 多通道 Fmap 作为输入，新开发的多通道 DL-AggMapNet 模型在 18 个低样本组学基准任务上优于最先进的机器学习模型。AggMapNet 在学习噪声数据和疾病分类方面表现出更好的鲁棒性。AggMapNet 可解释模块 Simply-explainer 确定了用于 COVID-19 检测和严重程度预测的关键代谢物和蛋白质。

### introduction

生物医学研究经常依赖于来自组学（转录组学、蛋白质组学、代谢组学）分析的高维、**无序**特征、**低样本量**和**多平台** (**highdimensional, unordered feature, low-sample size, and multiplatform**, BioHULM ) 数据。个别调查主要集中在数十到数百个样本上。派生的组学数据包含成百上千的无序特征（按出现的顺序）。

尽管深度学习 (DL) 在学习复杂数据方面具有优势，但传统的机器学习 (ML) 方法是最近基于 BioHULM 的生物医学研究的主要工具 。

*BioHULM 数据应用于 DL的两个问题：*

> 1. 由 BioHULM 数据训练的深度学习倾向于过度拟合大量超参数。一项综合研究表明，ML 模型优于由相同的低样本转录组数据训练的深度表示学习模型。
> 2. DL 结果比一些 ML 算法更难以解释。可解释性在生物医学研究中至关重要，特别是对于知情决策、机制调查、生物标志物发现和模型评估。

**BioHULM 任务需要高性能和可解释的 DL 算法。**

#### 本文工作

BioHULM 任务需要高性能和可解释的 DL 算法。

- 为了充分缓解 BioHULM 学习中的“维度灾难”问题，最近的研究集中在将 1D 无序数据转换为**基于遗传位置、数据邻域或功能关系。**尽管这种转换可以使用卷积神经网络 (CNN) 进行有效的深度学习，但它们缺乏关于输入特征点的聚类组的丰富通道信息。因为多通道网络通过单独学习特征子集有助于学习复杂数据，它们的代表性丰富性通常允许在多个尺度上捕获非线性依赖关系。

- CNN可以有效地提取数据的局部平稳性和组合性，CNN的成功取决于其利用组合层次结构和内在数据结构的能力。

- 在这项工作中，为了增强对低样本组学数据的基于 CNN 的有效学习，开发了**一种新的无监督特征聚合工具 AggMap**，用于将单个无序 BioHULM 特征点 (FP) 聚合和映射到空间相关的多通道 2D Fmap（图[1A] )。AggMap 特征重构侧重于 Fmap 的空间和通道维度。使用无监督的 AggMap，FP基于它们的成对相关距离，使用流形学习方法统一流形近似和投影 (UMAP)嵌入到二维空间中。同时，使用凝聚层次聚类方法将 FP 凝聚成多个特征集群（特征集群）。FPs通过线性分配算法LAPJV基于嵌入坐标聚合成二维网格，形成空间相关的Fmaps，feat-clusters将特征分配引导到分割通道中。所提出的 AggMap 被定义为一个拼图求解器，因为它基于它们的内在相似性和拓扑结构来解决无序 FP 的拼图。我们还构建了一个新的多通道 CNN 架构 AggMapNet（图[1B]），其中包含两个可解释的模块（Shapley-explainer 和 Simply-explainer），用于从 AggMap Fmaps 中增强和可解释地学习 BioHULM。

> AggMap/AggMapNet 开源代码在https://github.com/shenwanxiang/bidd-aggmap。

![Figure 1. AggMap/AggMapNet pipeline and key applications. (A) Unsupervised AggMap flowchart of feature mapping and aggregation into ordered (spatially-correlated) channel-split feature maps (Fmaps). (B) CNN-based AggMapNet architecture for Fmaps learning. The unsupervised AggMap converts unordered vectors into spatially correlated multi-channel Fmaps (3D data), which are the inputs of AggMapNet.](https://secure2.wostatic.cn/static/kV7v5Shg72gqRaEPZdxS5E/image.png?auth_key=1692079347-aw4Ag1LQTd89FHcWJgCLGZ-0-7ecdb968c86ba33e063a677c30529090)

图1.AggMap/AggMapNet管道和关键应用。(A)无监督的AggMap流程图，用于将特征映射和聚集成有序(空间相关的)通道分割特征映射(Fmap)。(B)基于CNN的用于Fmap学习的AggMapNet架构。无监督AggMap将无序向量转换为空间相关的多通道Fmap(3D数据)，这些Fmap是AggMapNet的输入。

![(C) proof-of-concept illustration of AggMap restructuring of unordered data (randomized MNIST) into clustered channel-split Fmaps (reconstructed MNIST) for CNN-based learning and important feature analysis. (D) typical biomedical application pipelines of transferable AggMap in restructuring omics data into channel-split Fmaps for multi-channel CNN-based AggMapNet diagnosis and biomarker discovery (explanation global important features from saliency-map).](https://secure2.wostatic.cn/static/pPKsoXehRdqG6QpG59erKM/image.png?auth_key=1692079347-o1YuWjqj3Lxzsj1DFJZG4F-0-d589cf10571d82f037c783fb4e549ad7)

(C)将无序数据的AggMap重组(随机化MNIST)为基于CNN的学习和重要特征分析的集群频道分裂Fmap(重构MNIST)的概念验证图解。(D)可转移AggMap在将组学数据重组为通道分裂Fmap以用于基于CNN的多通道AggMapNet诊断和生物标记物发现方面的典型生物医学应用管道(解释来自显著图的全球重要特征)。

AggMap 的特征重构能力通过在 MNIST 上的概念验证 (POC) 实验进行评估。有趣的是，AggMap 几乎可以根据它们的内在相关性从随机排列中完全重建原始图像（图[1C]，如果用更大样本量的随机数据拟合，可以增强 AggMap 的重建能力。AggMap 重新排列 FP 的良好能力提高了对随机数据的学习。AggMap 对学习 BioHULM 数据的有用性通过几个测试进行了评估。

- AggMap 多通道 Fmap 在 AggMapNet 对多个数据集的学习上显示出比单通道 Fmap 显着的改进和更好的鲁棒性。
- AggMap 优于现有的 2D 特征工程方法，例如 Lyu-reshape 和 Bazgir-REFINED (基于 RNA-seq 的泛癌分类的多任务。在细胞周期数据集中，AggMap 可以通过聚合和分组 FP 轻松获取特定阶段的基因。
- 多通道 AggMapNet 优于六个 ML 模型，它们是 k-最近邻 (kNN)、L2 正则化多项逻辑回归 (LGR)、随机森林 (RF)、旋转森林 (RotF)、Xgboost (XGB) 和 LightGBM (GBM) ) 在 18 个低样本转录组基准数据集中的大多数中。
- 基于 AggMapNet 中开发的 Simply-explainer，我们进一步探索了用于 COVID-19 检测和严重性预测的重要生物标志物。那些确定的 COVID-19 相关生物标志物与文献报道的发现或生物学机制高度一致

### materials and methods

#### AggMap 特征重构的动机

人类能够对破碎的碎片对象进行逻辑还原，例如解决拼图游戏或恢复文化财产，如图[2A]所示。这种能力源于预先学习的先验知识，可以根据片段的相关性和边缘连接来连接和组合片段。这些知识是**通过各种碎片恢复过程学习的**。

尽管我们能够从较大的片段中恢复图像，这是因为图像从“b”到“a”的原始信息已经完全丢失。尽管如此，我们可以根据“a”中像素（特征点，FP）的相似性将图像从“a”重构为“c”。新图像“c”比图像“a”更结构化，甚至在花朵、树干和树叶等各种图案上的碎片非常接近原始图像的碎片。所提出的**AggMap**旨在通过以自我监督的方式模仿人类的组装能力（解决拼图游戏），将无序的 FP聚合和**映射到结构化特征图（** **Fmap ）中。**这种重组过程能够将无序 FP 映射到结构化模式中，以实现更有效的深度学习 (DL)。

![恢复和重组过程的插图。( **A** ) 将破碎的片段恢复为具有特定模式的对象。( **B** ) 将随机排列的图像分别重构和恢复为结构化图像和原始图像。](https://secure2.wostatic.cn/static/wpxfPcnWLaR9SJTToJDf6h/image.png?auth_key=1692079348-tMXKwJ8WaYeqtLfAWj3cUk-0-a444cabd15c78d3f143d11ddc9de1e1b)

#### 无监督 AggMap 的理论基础

为了将无序的 FP 重构为结构化的 Fmap，自监督 AggMap 需要一个度量来衡量 FP 之间的相似性，一种嵌入 FP 的方法，以及一种将嵌入的 FP 分配到规则网格的算法（即FP）。

在 AggMap 中，这些任务分别由相关度量、基于流形的 UMAP 方法和线性分配 Jonker-Volgenant (J-V) 算法执行。

UMAP 最初是通过将样本嵌入低维空间来开发降维的。它可以有效地聚合相似的 FP，同时保留它们对本地和全局数据结构的相对接近度，导致在现实世界数据中降维的 SOTA 性能 。默认情况下，UMAP 在 AggMap 中用于将 FP 而不是样本嵌入到 2D 空间中。

![](https://secure2.wostatic.cn/static/t8ZYrKFWcyr1qaemGjxRCm/image.png?auth_key=1692079347-nYYin4DPzfCLpMvn51mtAX-0-36c5d7d92ee9fb3091ded6785d866c7c)

AggMap 的拟合有九个步骤，使用随机 MNIST FP 的重构（像素是随机排列的 MNIST）作为示例。

> **<font color='red'>[对于文献理解点击此处：组会report：AggMap](https://Lilian-tju.github.io/blogs/20220616-AggMapNet.pdf)</font>**