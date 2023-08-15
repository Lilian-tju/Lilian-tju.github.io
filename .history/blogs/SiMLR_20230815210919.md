---
layout: page
permalink: /blogs/SiMLR/index.html
title: SiMLR:来自高维生物医学数据的相似性驱动的多视图嵌入
---


## **SiMLR:来自高维生物医学数据的相似性驱动的多视图嵌入**

<div align=left>
<img src="https://Lilian-tju.github.io/blogs/img/SiMLR1.jpg">
</div>

> 文献来源：2021.2.22/nature computational science/弗吉尼亚大学放射学和医学影像系

### abstract 

在大型队列中收集的多样化、高维模式为综合科学假设的制定和测试提供了新的机会。

相似性驱动的多视图线性重建 (SiMLR) 是一种**利用模态间关系将大型科学数据集转换为更小、更强大且可解释的低维空间的算法**。

SiMLR**提供了一个目标函数来识别基于表示先前模态内关系的稀疏矩阵的联合信号正则化，以及一种允许应用到大数据矩阵的联合缩减的实现。**
证明了在模拟数据、多组学癌症生存预测数据集和多模态神经影像数据集的监督学习问题上，SiMLR 优于密切相关的方法。总之，这组结果表明，SiMLR 可以应用于来自不同模态的联合信号估计，并且可以在各种应用领域中产生实际有用的结果。

### introduction

**多视图（也称为多模态或多块）（Multi-view (also known as multiple modality or multi-block)）数据集**在生物医学科学中越来越常见。

在理想化的情况下，每个视图或模态将提供底物生物学的完全唯一的测量。然而往往每一种观点都对一种复杂的现象提供了**一种部分的、而不是完全独立的观点**。在这种情况下，可以利用协变来筛选噪声测量并更好地识别有意义的信号。此外，跨大脑系统或跨尺度的联合关系可以构成综合科学假说的基础。

预先指定的联合假设使科学家能够避免对可能的相互作用进行组合爆炸测试。尽管在足够大的、充分理解的数据集中功能强大，但先前的多变量假设可能很难用足够的细节来列举以支持实现和测试。（PCA&ICA)

#### 本文工作

1. 相似性驱动的多视图线性重建 (SiMLR)，是一种联合嵌入方法 - 针对生物医学数据 。  
2. SiMLR 建立在 SCCAN和基于先验的特征解剖学 之上。
3. SiMLR 对 SCCAN 进行了改进，因为它采用两种或多种模式作为输入，允许自定义正则化模型，并使用适合大型数据集的快速且内存高效的实现。
4. SiMLR 为每个最能预测其伙伴模态的模态输出局部最优的低维矩阵嵌入。 它通过从伙伴模态派生的基组重构每个模态矩阵来实现这一点。

#### 术语介绍Terminology.

- **Multi-view**: several modalities collected in one cohort; alternatively, the same
measurements taken across different studies61. We focus on the first case here.

> 在一个队列中收集了几种模式；或者，在不同的研究中进行相同的测量。我们在这里关注第一个案例。

- **Covariation**： we use the term in two contexts. As a general concept, we mean
systematic changes in one modality are reflected in a predictable amount of
change in other modalities. In the mathematical context, we use the definition
of covariation for discrete random variables.

> 作为一般概念，意思是**一种模式的系统性变化反映在其他模式的可预测变化量中**。 在数学中，我们使用**离散随机变量的协变定义**。

- **Latent space or embeddings**：both terms refer to a representation of
high-dimensional data that is often lower-dimensional. These are also known
as components in PCA. In the context of this paper, we are ‘approximating’
the (hidden) latent space with the learned embeddings. Often, the true
latent space cannot be known. We compute embeddings (or components) by
multiplying feature vectors against input data matrices. Importantly, SiMLR
can compute latent spaces that target either statistical independence (the
ICA source separation algorithm40) or orthogonality (the SVD algorithm).
Deflation-based schemes, on the other hand, target only orthogonality.

> 潜在空间或嵌入：这两个术语都是指通常是低维的高维数据的表示。这些也称为PCA中的组件。在本文的上下文中，我们用学习的嵌入来“逼近”（隐藏的）潜在空间。通常，无法知道真正的潜在空间。我们通过将特征向量与输入数据矩阵相乘来计算嵌入（或分量）。重要的是，SIMLR可以计算以统计独立性（ICA源分离算法40）或正交性（SVD算法）为目标的潜在空间。另一方面，基于紧缩的方案仅以正交性为目标。

- **Feature vectors**：these are weights on the original features. In SiMLR, the
feature vectors are the solutions that we are seeking. Projecting the feature
vectors onto the original data will provide a low-dimensional representation.
These concepts are described in more detail below

> 特征向量：这些是原始特征的权重。在SIMLR中，特征向量是我们正在寻求的解决方案。将特征向量投影到原始数据上将提供低维表示。

### Technical background.

数据表示。 SiMLR 假设输入是“干净的”数据。 这些数据没有缺失值，并以矩阵格式结构化，每种模式都与行（主题或样本）和列所代表的特征相匹配。

SiMLR 接受以这种方式组织的 >1 个矩阵。 对 m 个不同模态的研究将具有维度为 n × pi（主题 × 预测变量）的输入矩阵，注意对于任何 i、j ∈ 1、⋯、m，pi 不必等于 pj。 我们简要讨论了 SiMLR 所基于的主要算法。 我们假设数据矩阵是标准化的（具有零均值的列，单位方差）并且∥ ⋅ ∥ 表示 Frobenius 范数。

### Similarity-driven multi-view linear reconstruction.相似性驱动的多视图线性重建。

SIMLR是一个通用框架，可以以与稀疏PCA（一种类似回归的目标）或稀疏CCA（一种与协方差相关的目标）相关的形式指定。主要概念如图所示。我们对将应用SIMLR的数据集做了两个假设。

- 假设 1：真正的潜在信号是独立的，并且在我们正在收集多个测量值的生物系统中线性混合（盲源分离的标准假设）。  
- 假设2：稀疏的正则化特征向量可以通过线性运算将假设1中估计的潜在信号与原始数据矩阵相关联。

> 盲源分离在维基百科的定义：指的是从多个观测到的混合信号中分析出没有观测的原始信号。
盲信号的“盲”字强调了两点：1)原始信号并不知道；2)对于信号混合的方法也不知道。
最常用在的领域是在数字信号处理，且牵涉到对混合讯号的分析。盲信号分离最主要的目标就是将原始的信号还原出原始单一的讯号。

如果数据与这些假设相匹配，那么可以组合模态的方法就有更好的机会发现潜在的信号。例如，来自遗传学、神经成像和认知的联合分析可以提供影响所有其他信号的真实潜在信号的更可靠的恢复。

此外，可能不会以一致的方式在所有模态或模态内的特征的所有元素之间共享杂散信号。噪声的自然过滤发生在联合分析中，因为大多数形式的噪声不会在测量实例之间共变。正则化的增加有助于进一步增加鲁棒性：用稀疏项（ℓ0或ℓ1）正则化的方法可以降低不改善目标函数的特征的权重（甚至为零）。这些假设的一个警告是，如果测量之间不存在协变，或者如果噪声淹没了所有模态或测量，则这些方法可能不相关。

SIMLR目标函数。我们首先介绍了高级框架，然后提供了相似性度量和正则化的细节。**SIMLR的核心概念是，它结合了灵活的方法来测量模态之间的差异（相似性驱动），可以将几个不同的矩阵作为输入（多视图），并执行本质上都是线性代数的操作（线性重建）。**

首先，对于给定的测量或视图或模态，我们将Xi定义为N×Pi（主题特征）矩阵。I的值的范围,从1到m，m是模态（或视图）的数量。然后，SIMLR优化目标函数，该目标函数通过稀疏特征矩阵（Vi）和低维表示（u≠I）寻求从其伙伴矩阵逼近每个模态：

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/SiMLR2.jpg">
</div>

a，这里显示了两个统计上独立的信号来表示隐藏的潜在信号，这可能是疾病过程的两个组成部分。 二维的

b，潜在信号通过三种不同的模态表现出来（每个模态由一个椭圆表示），信号的联合分量在重叠中表示。 

c、将这些三视图数据转换为三个矩阵XA、XB、XC； 在这项工作中，我们专注于具有共同数量的主题的矩阵，这里用 n 表示，以及可变数量的预测变量 (pA pA pB pC )

d，稀疏正则化矩阵（GA、GB、GC）是基于领域知识或通过辅助函数使用用户输入构建的。

e，SimMLR 迭代地优化模态在留一法中相互预测的能力。  

f，出现稀疏特征向量，可以解释为输入矩阵的选定列的加权平均值，这些列保持数据的原始单元。 

g，来自 f 的稀疏特征向量用于计算嵌入； 然后将这些传递给下游分析。 或者，可以置换 SiMLR 解决方案以获得有关其解决方案的经验统计数据。

#### 总结

SiMLR 提取的信号与相关方法的信号不同。 该特征可能与该方法的核心有关：高维嵌入向量纯粹由模态内数据构建，而低维基则来自由用户选择的源分离算法确定的跨模态表示。 
如果选择 SVD 源分离方法，则表示将是正交的； 如果选择 ICA，它们将在统计上独立，其中独立性是通过测量非高斯性来定义的（FastICA 的原则之一是“非高斯性就是独立性”）。 
这种方法仅在表现出某种程度的跨模态协变的数据集中有效，这些协变可以有意义地解码为多个“真实”源信号。

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/SiMLR3.jpg"><br><img src="https://Lilian-tju.github.io/blogs/img/SiMLR4.jpg"><br><img src="https://Lilian-tju.github.io/blogs/img/SiMLR5.jpg"><br><img src="https://Lilian-tju.github.io/blogs/img/SiMLR6.jpg"><br>
</div>

#### 实验结果

<div align=center>
<img src="https://Lilian-tju.github.io/blogs/img/SiMLR7.jpg">
</div>

> [**<font color='red'>对于文献理解点击此处：组会report</font>**](https://Lilian-tju.github.io/blogs/reports/20220808-来自高维生物医学数据的相似性驱动的多视图嵌入.pdf)
