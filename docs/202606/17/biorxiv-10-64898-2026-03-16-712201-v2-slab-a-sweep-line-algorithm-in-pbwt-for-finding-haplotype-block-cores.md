---
title: "SLAB: A Sweep Line Algorithm in PBWT for Finding Haplotype Block Cores"
title_zh: "SLAB: 一种基于PBWT的扫描线算法用于寻找单倍型块核心"
authors: "Naseri, A., Sanaullah, A., Zhang, S., Zhi, D."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.16.712201v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 基于PBWT的单倍型块核心查找算法
tldr: 随着高质量单倍型数据的增加，研究人员需要有效识别多个单倍型块重叠的基因组区域（块核心）。本文提出SLAB算法，基于PBWT的扫描线方法高效分析宽度最大匹配并提取块核心。应用于UK Biobank数据，发现块核心能反映选择信号，且与IBD率分析结果互补，为群体遗传学研究提供新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以高效检测多个单倍型块重叠形成的核心区域，需开发新算法以捕获更精细的共享模式。
method: 提出SLAB算法，利用PBWT的扫描线技术快速枚举宽度最大匹配并提取块核心。
result: 在UK Biobank中成功识别块核心，其分布与已知选择信号区域一致，且补充了IBD率未覆盖的信息。
conclusion: 块核心作为选择信号检测的新型特征，与经典方法互补，揭示了更丰富的群体遗传结构。
---

## 摘要
随着高质量定相单倍型数据的日益普及，研究人员能够更有效地识别单倍型共享的详细模式，并研究塑造这些模式的群体遗传过程。在这项工作中，我们将块核心定义为多个单倍型块重叠的基因组片段。我们开发了一种高效的算法来分析单倍型块，重点关注宽度最大匹配和单倍型块核心的识别。我们将该算法应用于英国生物银行的单倍型数据，以量化块核心，并证明从其模式中可以推断出的生物学和群体层面 insights。具体来说，识别出的块核心可作为检测选择信号的基础。尽管我们的结果与IBD比率分析等方法的结果基本一致，但它们也揭示了IBD比率或其他常规方法未能捕捉到的互补信息。源代码可在 https://github.com/ZhiGroup/SLAB 获取。

## Abstract
With the increasing availability of high-quality phased haplotype data, researchers can more effectively identify detailed patterns of haplotype sharing and investigate the population genetic processes that shape them. In this work, we define block cores as genomic segments where multiple haplotype blocks overlap. We develop an efficient algorithm to analyze haplotype blocks, focusing on width-maximal matches and the identification of haplotype block cores. We apply our algorithm to UK Biobank haplotypes to quantify block cores and demonstrate the biological and population-level insights that can be inferred from their patterns. Specifically, identified block cores can serve as a basis for detecting signals of selection. Although our results are largely consistent with those from methods such as IBD rate analysis, they also reveal complementary information not captured by IBD rates or other conventional approaches. Source code is available at https://github.com/ZhiGroup/SLAB.