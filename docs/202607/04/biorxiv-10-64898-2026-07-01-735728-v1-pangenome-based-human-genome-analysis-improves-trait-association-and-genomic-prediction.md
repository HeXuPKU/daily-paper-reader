---
title: Pangenome-based human genome analysis improves trait association and genomic prediction
title_zh: 基于泛基因组的人类基因组分析改善性状关联和基因组预测
authors: "Lu, S., Liao, W.-W., DeGorter, M. K., Goddard, P. C., Ebler, J., Lu, T.-Y., Chaisson, M. J. P., Marschall, T., Montgomery, S. B., Stitziel, N. O., Hall, I. M."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.01.735728v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 基于泛基因组的性状关联和基因组预测方法
tldr: "传统线性参考基因组难以全面捕获复杂遗传变异，限制性状关联分析。本研究利用人类泛基因组资源，开发基于变异图的EdgeDepth方法，分析短读长测序数据。在430个样本中发现812个基因的关联显著性提升≥20%，其中GBAP1拷贝数变异解释克罗恩病GWAS位点。基因表达预测方差解释从10.1%提升至12.5%。结果表明整合泛基因组能改善人类遗传研究的性状关联与预测。"
source: biorxiv
selection_source: fresh_fetch
motivation: 克服线性参考基因组局限性，评估泛基因组方法对性状映射的改进效果。
method: 利用人类泛基因组变异图，开发EdgeDepth方法关联序列变异与性状。
result: "检测到多等位基因indel和结构变异，812个基因显著性提升≥20%，GBAP1拷贝数影响克罗恩病。"
conclusion: 整合泛基因组能显著提升部分基因的关联分析和预测性能。
---

## 摘要
人类泛基因组参考联盟已生成462个开放获取的参考基因组和一个表示它们之间差异的变异图，为基于泛基因组的分析方法提供了基础，克服了将所有基因组数据与单个线性参考进行比较的长期限制。一个关键未解决的问题是这些方法能在多大程度上改进性状定位。我们使用基因表达变异的遗传学作为模型进行研究。我们开发了一种基于图的方法（EdgeDepth），用于使用短读长基因组测序数据将序列变异与性状关联起来，并表明它能捕获其他方法漏掉的复杂形式的遗传变异。我们使用430个具有深度RNA-seq数据的样本评估了性状定位性能，发现泛基因组方法能够检测涉及多等位基因插入缺失和结构变异的表达数量性状位点，从而在一部分基因上提高检测效力。其中包括812个基因（占总数的7.9%），其统计显著性相对于1000基因组计划数据集提高了至少20%，有185个（1.8%）提高了50%，其中10个是解释先前GWAS结果的候选基因。值得注意的是，这些分析表明GBAP1假基因拷贝数是克罗恩病的因果因素，可能通过miRNA介导的GBA1调控，这解释了先前基于侧翼SNP的GWAS结果。纳入泛基因组特异性变异也改善了基因表达预测模型的性能，解释的中位数方差从10.1%增加到12.5%，14.6%的基因显示出显著改善（Δr^2>0.05）。总之，这些结果表明，将泛基因组方法整合到人类遗传学研究中将改善有意义基因子集的性状关联和基因组预测。

## Abstract
The Human Pangenome Reference Consortium has generated 462 open-access reference genomes and a variation graph that represents differences among them, providing a substrate for pangenome-based analysis methods that overcome the longstanding limitation of comparing all genomic data to a single linear reference. A key unresolved question is the extent to which these approaches can improve trait mapping. We investigate this using the genetics of gene expression variation as a model. We developed a graph-based method (EdgeDepth) for associating sequence variation with traits using short-read genome sequencing data, and show that it captures complex forms of genetic variation missed by other methods. We evaluated trait mapping performance using 430 samples with deep RNA-seq data, and found that pangenomic methods enable the detection of expression quantitative trait loci involving multiallelic indels and structural variants, leading to increased power at a subset of genes. These include 812 genes (7.9% of total) with [&ge;]20% improvement in statistical significance relative to the 1000 Genomes Project callset, and 185 (1.8%) with a 50% improvement, 10 of which are candidates to explain prior GWAS results. Notably, these analyses implicate GBAP1 pseudogene copy number as a causal factor in Crohn's disease, likely via miRNA-mediated regulation of GBA1, which explains prior GWAS results based on flanking SNPs. The inclusion of pangenome-specific variation also improved the performance of gene expression prediction models, with median variance explained increasing from 10.1% to 12.5%, and 14.6% of genes showing significant improvement ({Delta}r2>0.05). Taken together, these results suggest that integration of pangenomic methods into human genetic studies will improve trait association and genomic prediction at a meaningful subset of genes.

---

## 论文详细总结（自动生成）

# 基于泛基因组的人类基因组分析改善性状关联与基因组预测——论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：传统线性参考基因组（如GRCh38）无法全面捕获复杂遗传变异（如多等位基因结构变异SV、可变数目串联重复VNTR等），导致短读WGS数据在变异检测和性状关联分析中存在大量遗漏。
- **背景**：人类泛基因组参考联盟（HPRC）发布了包含462个高质量参考基因组和变异图（pangenome graph）的资源，为克服线性参考限制提供了可能。但泛基因组方法能否实质性改善性状映射（如eQTL、GWAS）仍未明确。
- **意义**：以基因表达变异作为模型，评估泛基因组方法对复杂性状遗传研究的改进潜力，为未来大规模GWAS和基因组预测提供依据。

## 2. 方法论：EdgeDepth方法
### 核心思想
- 直接利用pangenome graph中边的比对深度（edge depth）进行性状关联，无需预先解析精确的等位基因结构或分型，从而捕获传统方法难以处理的复杂多等位基因变异。

### 关键技术细节
1. **读序比对**：将短读WGS数据使用vg giraffe比对到HPRC2 Minigraph-Cactus构建的pangenome graph。
2. **边深度量化**：使用vg pack计算每个样本在每个graph edge上的比对读深度。
3. **归一化**：采用DESeq2的median-of-ratios方法，计算每个样本的size factor，对深度进行跨样本归一化。
4. **选择代表性边**：在biconnected组件内，按平均深度排序，迭代选取最高深度边作为代表，移除结构冗余边（桥边判定），确保每个等位基因仅保留一个标记。
5. **筛选可变边**：使用约束高斯混合模型（类似Genome STRiP）拟合深度分布，保留至少10个样本携带非主基因型的边；并对漏检边进行异常值救援。
6. **等位基因平衡**：对于双等位变异（snarl拓扑），用alt深度/(ref+alt深度)替代归一化深度作为基因型剂量。
7. **关联测试**：以等位基因平衡或归一化深度作为定量输入，使用tensorQTL进行cis-eQTL映射。

## 3. 实验设计
### 数据集
- **训练/捕获率评估**：201个HPRC样本（有PacBio Kinnex长读RNA-seq），以HPRC2 graph-based callset（201样本）为truth。
- **eQTL映射主实验**：430个AFGR样本（1000Genomes非洲人群LCL细胞系，有30×短读WGS和短读RNA-seq，其中407个不在HPRC中）。
- **GWAS共定位**：41个GWAS研究的汇总统计量（血液标志物、复杂疾病等）。

### 基准/对比方法
- **1KG callset**：传统线性参考方法（GATK小变异 + 整合SV callset），代表当前最佳线性参考分析。
- **PanGenie**：基于k-mer的泛基因组分型方法（T2T-CHM13参考）。
- **danbing-tk**：专门针对VNTR的k-mer定量方法。
- **EdgeDepth**：本文提出的基于graph边深度的关联方法。

### 实验场景
1. **捕获率比较**：在201个HPRC样本中，各callset对truth变异的覆盖比例。
2. **单独eQTL映射**：每个callset独立进行eQTL分析，比较eGene数和lead变异类型分布。
3. **联合eQTL映射**：合并所有callset的变异，评估每个方法贡献的lead标记数量与信号改善程度。
4. **合并callset（HPRC2+1KG）**：用1KG为基础，添加非冗余的pangenome特异变异，进行eQTL、精细定位（SuSiE）、基因表达预测（5种模型：Lasso、Ridge、Elastic Net、top-1、SuSiE）。
5. **GWAS共定位**：对812个有pangenome信号改善的eQTL，使用coloc进行共定位分析。

## 4. 资源与算力
- **文中未明确说明**使用的GPU型号、数量、训练时长等具体算力资源。
- 仅提及使用了vg giraffe、PanGenie、danbing-tk等工具，但未报告计算集群配置或运行耗时。因此，无法量化资源需求。

## 5. 实验数量与充分性
- **实验数量**：覆盖捕获率评估（1组）、单独eQTL（4种方法×1组）、联合eQTL（1组）、合并callset eQTL+精细定位+表达预测（2种callset对比×5种模型交叉验证）、GWAS共定位（156对eQTL-GWAS）。实验较为系统。
- **充分性**：
  - 使用了实际短读WGS和RNA-seq数据，适合评估真实应用。
  - 对比了多种典型方法，包括传统线性、k-mer泛基因型、graph深度关联。
  - 进行了5折交叉验证的表达预测，统计方法合理。
- **客观性与公平性**：
  - 注意了多重检验、LD结构、callset间变异匹配和救援步骤。
  - 但存在潜在偏向：EdgeDepth在简单变异上不如1KG/PanGenie准确（补充图6），文中也指出PanGenie在共享变异上略优。整体结论较为平衡。

## 6. 主要结论与发现
1. **EdgeDepth捕获率更高**：在201个HPRC样本中，EdgeDepth捕获97.4%的常见graph变异（1KG为86.3%），尤其对SV和多等位基因indel。
2. **eQTL检测**：联合分析中，EdgeDepth贡献41.6%的lead eQTL标记（1KG为31.7%，PanGenie为26.5%），且检测到更多多等位基因SV相关eQTL（2.3% vs 1KG的0.1%）。
3. **信号改善**：812个基因（7.9%）的eQTL显著性相对1KG提高≥20%，185个（1.8%）提高≥50%。这些基因多位于重复区、涉及SV/VNTR。
4. **基因表达预测**：合并HPRC2+1KG callset使表达预测中位数解释方差从10.1%提升至12.5%，14.6%的基因Δr²>0.05。
5. **GWAS共定位**：10个eQTL与GWAS共定位，其中GBAP1假基因拷贝数变异通过ceRNA机制（竞争内源RNA海绵miR-22-3p）调控GBA1表达，解释克罗恩病GWAS信号。

## 7. 优点
- **方法创新**：EdgeDepth直接对graph edge深度做关联，避免了复杂变异的等位基因解析难题，具有普适性。
- **实验系统**：覆盖了从捕获率、eQTL发现、精细定位、表达预测到GWAS共定位的完整链条，证明泛基因组方法在多个环节均有改进。
- **发现新颖**：GBAP1机制是首次报道的常见疾病GWAS中假基因拷贝数通过miRNA海绵调控的实例，具有重要生物学意义。
- **实用导向**：证明了在现有短读WGS数据上，整合泛基因组变异即可获得有意义改进，为大规模重分析提供了依据。

## 8. 不足与局限
- **方法局限**：EdgeDepth在简单双等位变异上噪声更大，关联效力不如离散基因型方法（1KG/PanGenie），且未输出硬基因型，限制了群体遗传学应用。
- **样本偏差**：eQTL映射仅基于LCL细胞系（淋巴母细胞系），基因表达调控具有组织特异性；且样本全部为非洲血统（430人），GWAS共定位群体多为欧洲血统，可能低估真实效益。
- **方法覆盖不全**：未包含所有最新泛基因组方法（如pangenome-aware DeepVariant、DRAGEN、PanVariants），仅以1KG作为基线。
- **计算资源未报告**：缺乏对EdgeDepth运行时间、内存、GPU需求的分析，难以评估大规模部署成本。
- **因果验证不足**：GBAP1机制主要基于关联和已报道实验证据，缺乏直接功能验证。
- **改进幅度有限**：大多数基因（>90%）的eQTL信号并未显著改善，且1KG在某些位点仍优于泛基因组方法，说明当前方法仍有提升空间。

（完）
