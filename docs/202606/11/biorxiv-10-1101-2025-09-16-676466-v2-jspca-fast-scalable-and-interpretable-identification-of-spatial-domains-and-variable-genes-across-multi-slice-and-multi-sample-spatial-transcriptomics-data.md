---
title: "jsPCA: fast, scalable, and interpretable identification of spatial domains and variable genes across multi-slice and multi-sample spatial transcriptomics data"
title_zh: jsPCA：快速、可扩展且可解释的多切片和多样本空间转录组数据中空间域和可变基因的识别
authors: "Assali, I., Escande, P., Picard, F., Villoutreix, P."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.16.676466v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 空间转录组学方法可用于与GWAS整合进行功能解释
tldr: 空间转录组数据规模大、维度高，需高效分析方法。jsPCA基于空间协方差矩阵的联合对角化，快速识别空间域和可变基因。在多切片联合分析中无需空间对齐，计算速度远超现有方法。在人类脑和鼠胚胎数据上性能优异且可解释。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有空间转录组分析方法计算慢、可扩展性差，难以处理多切片联合分析。
method: 提出jsPCA，通过基因表达协方差与空间自相关的乘积构建空间协方差，并利用联合对角化实现多切片无对齐联合表示。
result: 在Visium和Stereo-seq数据集上，jsPCA在速度、准确性和可扩展性上显著优于10种对比方法。
conclusion: jsPCA提供了一种快速、可解释、可扩展的空间域和可变基因识别方案，适用于大规模多切片空间转录组数据。
---

## 摘要
组织内空间结构化的细胞异质性对于健康器官功能至关重要。这种异质性通过不同空间位置的差异基因表达活性来体现。空间转录组学技术以高空间分辨率记录整个组织规模的全基因组基因表达测量。虽然这些技术彻底改变了我们对组织结构的定量理解，但它们产生的大型高维数据集包含数万个空间位置记录的数万个基因，需要高效的自动化方法进行分析。在本研究中，我们介绍了联合空间PCA（jsPCA），这是一种新颖、快速、可扩展且可解释的方法，用于自动识别多切片和多样本空间转录组数据中的空间域和可变基因。jsPCA依赖于一个简单的数学公式，即空间协方差定义为基因表达协方差与空间自相关的乘积。该空间协方差的主成分产生具有生物学意义的低维表示。从这个表示中，我们可以通过简单的聚类推导出空间域。此外，可以直接从主成分系数中识别空间可变基因。此外，该方法能够联合表示多个切片和样本，这是一种常见的实验设置。这种联合表示无需空间对齐，通过对每个切片获得的空间协方差矩阵集进行联合对角化来计算公共主成分。通过利用流形上的稀疏性和非凸优化，jsPCA的计算时间在几秒到几分钟内，显著优于现有方法。我们在人类背外侧前额叶皮层的Visium 10x数据集和小鼠胚胎发育的Stereo-seq MOSTA数据集中，将jsPCA与10种现有方法进行了基准测试。我们的方法表现出优异的性能，与SpatialPCA、BASS、GraphPCA或Stagate等现有方法相当或更好，同时速度更快、可解释性更强，并且可扩展到非常大的数据集。

## Abstract
Spatially structured cell heterogeneity within tissues is essential for healthy organ function. This heterogeneity is reflected by differential gene expression activity at various spatial location. Spatial transcriptomics technologies record genome-wide measurements of gene expression at the scale of entire tissues with high spatial resolution. While they have revolutionized our quantitative understanding of tissue architecture, these technologies generate large and high dimensional datasets encompassing tens of thousands of genes recorded at tens of thousands of spatial locations, requiring efficient automated methods for their analysis. In this study we introduce joint spatial PCA (jsPCA), a novel, fast, scalable and interpretable method for the automatic identification of spatial domains and variable genes in multi-slice and multi-sample spatial transcriptomics data. jsPCA relies on a simple mathematical formulation of a spatial covariance defined as the product of the gene expression covariance with the spatial autocorrelation. The principal components of this spatial covariance yield a biologically meaningful low-dimensional representation. From this representation, we can derive spatial domains by simple clustering. In addition, spatially variable genes can be identified directly from the principal components coefficients. Moreover, this approach enables the joint representation of multiple slices and samples, a frequent experimental setting. This joint representation is obtained without spatial alignment by computing common principal components via joint diagonalization of the set of spatial covariance matrices obtained for each slice. By leveraging sparsity and non-convex optimization on manifold, jsPCA leads to computing time in the order of seconds to minutes, substantially outperforming state-of-the-art approaches. We benchmarked jsPCA on the Visium 10x dataset of human dorsolateral prefrontal cortex and the Stereo-seq MOSTA dataset of mouse embryonic development against 10 state-of-the-art methods. Our approach demonstrated excellent performances, comparable or better than state-of-the-art methods, such as SpatialPCA, BASS, GraphPCA or Stagate, while being much faster, interpretable, and scalable to very large datasets.