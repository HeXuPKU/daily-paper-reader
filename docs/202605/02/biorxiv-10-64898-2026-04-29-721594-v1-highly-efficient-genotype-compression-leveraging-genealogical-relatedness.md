---
title: Highly efficient genotype compression leveraging genealogical relatedness
title_zh: 利用谱系亲缘关系的高效基因型压缩
authors: "Shen, A., Wang, X., O'Connor, L. J., Mancuso, N."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.29.721594v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 用于大规模统计分析的高效基因型压缩算法
tldr: 针对大规模基因组数据存储和计算挑战，本研究提出了一种名为 kodama 的无损压缩算法。该算法利用个体间的家系亲缘关系，推断出一种称为“线性祖先重组图（linear ARG）”的新型数据结构。kodama 不仅能将数据体积缩小 17-89 倍，还支持极速的矩阵乘法运算，在英国生物样本库（UK Biobank）的 GWAS 分析中实现了比 PLINK 2.0 快 4700 倍的性能，为百万级样本的遗传学分析提供了高效方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 随着基因测序规模扩大，TB 级的遗传数据集给存储和大规模统计分析带来了巨大的计算挑战。
method: 提出 kodama 算法，通过推断一种类似于祖先重组图的“线性 ARG”结构，利用非亲属个体间的家系相关性实现高效压缩。
result: 在 UK Biobank 数据集上，该方法比原始数据缩小 17-89 倍，且在 GWAS 任务中比 PLINK 2.0 提速 4700 倍。
conclusion: 线性 ARG 结构显著提升了基因型数据的压缩率和计算效率，能够支持未来数百万样本规模的遗传学研究。
---

## 摘要
大型遗传数据集的大小可达数 TB，随着测序规模的扩大，这带来了日益严峻的计算挑战。我们提出了一种名为 kodama 的无损压缩算法，它支持矩阵乘法，适用于大规模统计分析。Kodama 利用了名义上无关个体之间的谱系亲缘关系，并推断出一种类似于祖先重组图（ARG）的新型数据结构，称为线性 ARG。我们将 kodama 应用于来自 UK Biobank 和 All of Us 的全基因组测序数据。推断出的线性 ARG 在磁盘上的体积比输入数据小 17-89 倍；整个 UK Biobank N=200k 数据集可以加载到内存中（58GB）。与最近提出的基因型表示图（GRG）相比，线性 ARG 的体积缩小了 2.5 倍。基因型矩阵乘法是大多数统计应用中的瓶颈，而使用线性 ARG 进行此类运算速度极快；我们在 100 秒内完成了对 UK Biobank 200k 队列中 89 个性状和 42 个协变量的全基因组关联研究（GWAS），相比 PLINK 2.0 实现了 4,700 倍的加速。我们预期线性 ARG 将使遗传分析能够扩展到数百万个样本的规模。

## Abstract
Large genetic datasets are terabytes in size, presenting a computational challenge that will intensify as sequencing efforts scale. We present a lossless compression algorithm, kodama, which supports matrix multiplication and is suitable for large-scale statistical analyses. Kodama leverages genealogical relatedness among nominally unrelated individuals and infers a novel data structure similar to the ancestral recombination graph (ARG), called the linear ARG. We applied kodama to whole genome sequencing data from UK Biobank and All of Us. Inferred linear ARGs were 17-89 times smaller on disk compared to the input data; the entire UK Biobank N=200k dataset can be loaded into memory (58GB). Compared with the recently proposed genotype representation graph (GRG), the linear ARG is 2.5 times smaller. Genotype matrix multiplications, which are the bottleneck in most statistical applications, are extremely fast with the linear ARG; we performed a GWAS on the UK Biobank 200k cohort across 89 traits with 42 covariates in 100 seconds, representing a 4,700-fold speedup over PLINK 2.0. We expect that the linear ARG will enable genetic analyses to scale to millions of samples.