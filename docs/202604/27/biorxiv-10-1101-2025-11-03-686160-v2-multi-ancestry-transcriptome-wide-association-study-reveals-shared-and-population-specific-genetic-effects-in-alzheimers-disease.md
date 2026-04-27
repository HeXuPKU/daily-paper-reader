---
title: "Multi-ancestry Transcriptome-Wide Association Study Reveals Shared and Population-Specific Genetic Effects in Alzheimer's Disease"
title_zh: 多族裔全转录组关联研究揭示阿尔茨海默病中共享与群体特异性的遗传效应
authors: "Sun, X., Mews, M., Wheeler, N. R., Benchek, P., Gu, T., Gomez, L., Ray, N., Reitz, C., Naj, A. C., Below, J. E., Tosto, G., Cornejo-Olivas, M., Byrd, G. S., Feliciano-Astacio, B. E., Celis, K., Rajabli, F., Kunkle, B. W., Pericak-Vance, M. A., Haines, J. L., Griswold, A. J., Bush, W. S."
date: 2026-04-27
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.03.686160v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 使用SuShiE进行多人群顺式eQTL精细映射
tldr: 本研究针对阿尔茨海默病（AD）在不同族群间风险差异的问题，利用非裔、西班牙裔及非西班牙裔白人数据，通过多族群转录组关联研究（TWAS）和顺式表达定量性状位点（cis-eQTL）精细定位，识别了9个关键基因（如BIN1、PTK2B）。研究揭示了跨族群共享及特异的遗传效应，通过整合eQTL精细定位提升了模型解释力，为理解AD的复杂遗传机制提供了新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决阿尔茨海默病遗传研究过度集中于单一族群的问题，探索不同祖先背景下AD的共享与特异性遗传机制。
method: 采用SuShiE工具进行多族群cis-eQTL精细定位，并结合分层TWAS、元分析及MA-FOCUS基因级精细定位方法。
result: 成功识别并精细定位了BIN1、PTK2B等9个与AD显著相关的基因，并发现BIN1等位点在不同族群间具有一致效应。
conclusion: 多族群eQTL精细定位能有效提高TWAS模型的解释力，有助于解析阿尔茨海默病在不同人群中的调控机制。
---

## 摘要
阿尔茨海默病（AD）的风险在不同祖先群体间存在差异，但大多数遗传学研究都集中在非西班牙裔白人（NHW）队列上。我们利用来自 MAGENTA 项目的非西班牙裔白人（NHW，n=235）、非裔美国人（AA，n=224）和西班牙裔（HISP，n=292）参与者的全血 RNA-seq 和基因型数据，进行了一项多群体全转录组关联研究（TWAS）。利用 SuShiE 进行多群体顺式表达定量性状位点（cis-eQTL）精细映射，我们识别了 8,748 个基因的可信集，与使用较少群体的分析相比，提高了精细映射的精度。顺式 eQTL 效应在不同群体间很大程度上是共享的，其中一小部分表现出群体特异性的调控。我们对 AD 进行了群体分层 TWAS 和逆方差加权荟萃分析，随后进行了基因级 TWAS 精细映射（MA-FOCUS），优先确定了 9 个基因（FDR < 0.05，PIP > 0.8），其中包括已知的 AD 位点（BIN1、PTK2B、DMPK），这些位点在不同群体中表现出广泛一致的效应。在 BIN1 位点，TWAS 预测模型中使用的精细映射顺式 eQTL 变异突出了 rs11682128，该变异与 GWAS 索引 SNP rs6733839 仅呈中度相关（r² ≈ 0.34），这表明将 eQTL 精细映射与 TWAS 相结合如何能够细化超出哨兵 GWAS 变异的信号。我们还发现 NHW 中 COG4 表达与 AD 之间存在关联，提示涉及高尔基体相关通路。利用来自 TOPMed MESA（外周血单核细胞，PBMC）的独立 SuShiE 衍生模型，多个信号在不同族裔间实现了方向性复制，其中在 NHW 中具有最强的统计学支持。总体而言，多群体 eQTL 精细映射提高了模型的可解释性，并有助于解析与 AD 相关的共享及群体特异性调控机制。

## Abstract
Alzheimer's disease (AD) risk differs across ancestral populations, yet most genetic studies have focused on non-Hispanic White (NHW) cohorts. We conducted a multi-population transcriptome-wide association study (TWAS) using whole-blood RNA-seq and genotype data from NHW (n=235), African American (AA; n=224), and Hispanic (HISP; n=292) MAGENTA participants. Using SuShiE for multi-population cis-eQTL fine-mapping, we identified credible sets for 8,748 genes, improving fine-mapping precision relative to analyses using fewer populations. cis-eQTL effects were largely shared across populations, with a subset showing population-specific regulation. We performed population-stratified TWAS of AD and inverse variance-weighted meta-analysis, followed by gene-level TWAS fine-mapping (MA-FOCUS), prioritizing nine genes (FDR<0.05, PIP>0.8), including established AD loci (BIN1, PTK2B, DMPK) with broadly consistent effects across populations. At BIN1, fine-mapped cis-eQTL variants used in the TWAS prediction model highlighted rs11682128, which is only modestly correlated with the GWAS index SNP rs6733839 (r^2{approx}0.34), demonstrating how integrating eQTL fine-mapping with TWAS can refine signals beyond sentinel GWAS variants. We also identified an association between COG4 expression and AD in NHW, implicating Golgi-related pathways. Using independent SuShiE-derived models from TOPMed MESA (PBMC), several signals replicated directionally across ancestries, with the strongest statistical support in NHW. Overall, multi-population eQTL fine-mapping improves model interpretability and helps resolve shared and population-specific regulatory mechanisms relevant to AD.

---

## 论文详细总结（自动生成）

这篇论文题为《多族裔全转录组关联研究揭示阿尔茨海默病中共享与群体特异性的遗传效应》，是一项旨在通过整合多族裔转录组数据来解析阿尔茨海默病（AD）遗传机制的深度研究。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：阿尔茨海默病（AD）的患病风险在不同祖先群体（如非裔、西班牙裔和白人）之间存在显著差异，但现有的遗传学研究（如GWAS）绝大多数集中在非西班牙裔白人（NHW）身上，导致对其他族裔的遗传风险理解不足。
*   **研究动机**：为了弥补“多样性鸿沟”，研究者试图探索不同族裔间共享的以及群体特异性的顺式表达定量性状位点（cis-eQTL）效应，并识别在多人群中共同发挥作用的AD致病基因。

### 2. 论文提出的方法论
*   **核心思想**：利用多族裔样本进行eQTL精细映射（Fine-mapping），提高预测模型的精确度，随后通过全转录组关联研究（TWAS）将基因表达与AD风险关联。
*   **关键技术细节**：
    *   **SuShiE (Sum of Single Effects for eQTLs)**：采用该工具进行多群体顺式eQTL精细映射。SuShiE能够整合不同人群的连锁不平衡（LD）结构，识别跨人群共享的因果变异。
    *   **分层TWAS与元分析**：首先在NHW、AA（非裔美国人）和HISP（西班牙裔）三个群体中分别进行TWAS，然后使用逆方差加权（IVW）方法进行元分析。
    *   **MA-FOCUS**：应用多族裔基因级精细映射工具，从TWAS显著信号中筛选出具有高后验概率（PIP > 0.8）的因果基因。

### 3. 实验设计
*   **数据集**：
    *   **发现集（MAGENTA项目）**：包含NHW (n=235)、AA (n=224)和HISP (n=292)的全血RNA-seq和基因型数据。
    *   **验证集（TOPMed MESA）**：使用来自外周血单核细胞（PBMC）的独立SuShiE衍生模型进行方向性复制验证。
*   **Benchmark与对比**：
    *   对比了“多群体联合精细映射”与“单一群体精细映射”的效果，证明多群体分析能显著缩小可信集（Credible Sets）的大小，提高定位精度。
    *   将TWAS结果与已知的AD GWAS位点进行重叠分析。

### 4. 资源与算力
*   **算力说明**：论文中未明确提及具体的GPU型号、数量或训练时长。此类生物信息学研究通常依赖于高性能计算集群（HPC）进行大规模并行计算，主要消耗在RNA-seq数据预处理、SuShiE模型训练和大规模GWAS摘要统计数据的整合上。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了三个主要族裔群体，识别了8,748个基因的可信集。
*   **充分性评价**：
    *   **多维度验证**：不仅做了发现实验，还利用独立的MESA数据集进行了跨族裔的复制验证。
    *   **统计严谨性**：采用了FDR校正和高阈值的PIP（>0.8）进行筛选，确保了结果的可靠性。
    *   **局限性中的充分性**：虽然样本量（n=751）在eQTL研究中不算巨大，但通过多族裔LD结构的互补，弥补了单一人群样本量的不足。

### 6. 主要结论与发现
*   **识别关键基因**：优先确定了9个与AD显著相关的基因，包括已知的**BIN1、PTK2B、DMPK**以及新发现的**COG4**。
*   **跨族裔一致性**：发现大多数顺式eQTL效应在不同群体间是共享的。例如，BIN1位点的效应在不同人群中表现出高度一致性。
*   **信号精细化**：在BIN1位点，研究锁定了变异**rs11682128**，该变异与传统的GWAS索引SNP（rs6733839）仅呈中度相关，说明TWAS结合精细映射能发现比传统GWAS更接近功能核心的信号。
*   **新通路提示**：NHW群体中COG4的关联提示高尔基体相关通路在AD发病中可能具有重要作用。

### 7. 优点
*   **多样性贡献**：填补了非白人群体在AD转录组遗传学研究中的空白。
*   **精度提升**：证明了利用不同人群LD结构的差异可以有效压缩因果变异的搜索范围（精细映射）。
*   **模型可解释性**：通过SuShiE和MA-FOCUS的结合，将统计关联提升到了功能基因组学的解释层面。

### 8. 不足与局限
*   **组织特异性**：研究使用的是全血数据，虽然血液与大脑在某些代谢通路上有重叠，但AD作为神经退行性疾病，其核心病理发生在脑组织，血液模型可能无法捕捉脑部特异性的调控机制。
*   **样本量限制**：相比于超大规模的单族裔研究，本研究的多族裔样本量仍有提升空间，可能导致对微效基因的检测效力不足。
*   **群体代表性**：虽然涵盖了三大族裔，但对于亚裔等其他族裔的覆盖尚不存在。

（完）
