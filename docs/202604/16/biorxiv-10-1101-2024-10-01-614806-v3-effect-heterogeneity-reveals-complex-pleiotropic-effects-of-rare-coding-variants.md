---
title: Effect heterogeneity reveals complex pleiotropic effects of rare coding variants
title_zh: 效应异质性揭示了罕见编码变异复杂的基因多效性
authors: "Lu, W., Chen, S., Auwerx, C., Fu, J., Posthuma, D., Neale, B., O'Connor, L. J., Karczewski, K."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.1101/2024.10.01.614806v3.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 罕见变异关联研究和多效性分析的统计方法
tldr: 针对现有统计框架难以处理基因水平罕见变异多效性的问题，本研究开发了ALLSPICE方法。该方法利用汇总统计量，通过似然比检验评估基因在不同连续性状间的效应是成比例还是异质的。在UK Biobank的359个连续性状分析中，ALLSPICE成功识别出显著的效应异质性事件，揭示了罕见变异多效性背后的复杂遗传架构，为理解跨表型关联提供了新视角。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-001.webp\", \"caption\": \"Figure 1 | Definition of gene-annotation pairs and association pairs. A, Schematic representation of gene-annotation pairs, defined as sets of rare variants within a gene grouped according to functional annotations (pLoF, missense, synonymous, and pLoF+ missense) for burden testing, and of cross-phenotype associations, defined as a gene-annotation pair showing significant burden associations (pburden < 2.5 ⨉ 10-6) with more than one phenotype. B, Definition of an association pair (left), schematic illustrations of gene-level horizontal pleiotropy (middle) and vertical (right) pleiotropy, and corresponding expected variant-level effect size patterns shown in the scatter plots.\", \"page\": 7, \"index\": 1, \"width\": 979, \"height\": 735}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-002.webp\", \"caption\": \"Figure 2 | Summary of cross-phenotype associations and ALLSPICE results. A, Distributions of genes by the number of associated phenotypes (x-axis) across four functional annotation groups (panels and colors). Labels above the bars indicate the proportion of genes with more than one association among genes with at least one association in the corresponding annotation group. B, Heatmap of pALLSPICE for strictly significant pairs of pLoF associations: with phenotype pairs on the x- and y-axes, and genes labeled accordingly. Cell color indicates -log10(pALLSPICE). Cells marked with asterisks denote association pairs with pALLSPICE=0. C, Heatmap of pALLSPICE for strictly significant missense association pairs, using the same display format as in B.\", \"page\": 10, \"index\": 2, \"width\": 979, \"height\": 754}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-003.webp\", \"caption\": \"Figure 3 | Examples of association pairs significant in ALLSPICE. A, Comparison of variant effect sizes on albumin (x-axis) and calcium (y-axis) among variants in ALB, stratified by functional annotation group (colors and columns). Point shapes indicate nominal significance (pGWAS < 0.05) in single-variant association tests for the two phenotypes. The missense variant chr4:73412072:A:G, labeled and highlighted by a blue circle, is significantly associated with both traits but exhibits opposite directions of effect and represents one of the strongest contributors in the LOVO analysis. The value shown in the bottom right of each panel denotes pALLSPICE for the corresponding annotation group. B, Comparison of ALPL variant effect sizes on alkaline phosphatase (x-axis) to phosphate level (y-axis). Panels A and B share the same legend.\", \"page\": 12, \"index\": 3, \"width\": 979, \"height\": 654}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-004.webp\", \"caption\": \"Figure 4 | Rare protein-coding variants in ALB (AF < 0.0001) on ALB protein structure. A, Distribution of ALB missense variants associated with calcium level but not albumin level (pink), variants associated with albumin but not calcium level (green), and known calcium binding sites (orange) on the 3D structure of ALB protein (PDB ID: 1AO6). B, Comparison of pairwise distances from missense variants only associated with calcium (pink) or albumin-level (green) to calcium binding sites on ALB protein structure in the 3D space. Colors in panel B are defined the same as in panel A. C, Distribution of ALB missense variants associated with either albumin or calcium level that affect the two biomarker levels in the same (blue) or different (red) direction, and calcium binding sites (orange) on the 3D structure of ALB protein (PDB ID: 1AO6). D, Comparison of pairwise distances between missense variants to calcium binding sites on the ALB protein structure in the 3D space. Colors in panel D are defined the same as in panel C.\", \"page\": 14, \"index\": 4, \"width\": 979, \"height\": 718}]"
motivation: 现有的多效性分析框架主要针对常见变异，不适用于基因水平的罕见变异关联研究，限制了对跨表型关联的解释。
method: 开发了基于似然比的统计方法ALLSPICE，利用汇总统计量在考虑表型相关性的基础上，测试基因内罕见变异效应在不同性状间是否具有异质性。
result: "在对UK Biobank中359个连续性状的分析中，从11,810对基因-性状关联中识别出124个显著的效应异质性事件。"
conclusion: ALLSPICE通过识别基因内的效应异质性，阐明了跨表型关联下共享与异质的罕见变异架构，深化了对罕见变异多效性的理解。
---

## 摘要
近期大规模生物样本库资源的扩展使得罕见变异关联研究（RVAS）以及同时对数千种表型进行罕见变异多效性的系统研究成为可能。然而，现有的剖析多效性的统计框架主要针对常见变异开发，并不完全适用于基于基因的罕见变异信号，从而限制了对跨表型关联的解释。在此，我们开发了 ALLSPICE，这是一种基于似然的方法，利用汇总统计量并考虑表型相关性，测试表现出跨表型关联的基因中的罕见变异效应在连续性状之间是成比例的还是异质的。ALLSPICE 在模拟中经过了良好的校准，并作为一个 R 包实现，用于基因级罕见变异负荷关联的可扩展分析。我们将 ALLSPICE 应用于英国生物样本库（UK Biobank）中 359 个连续性状的 RVAS，并在 11,810 对基因-性状关联中识别出 124 个显著的异质性事件。通过识别与多种表型相关的基因内的效应异质性，ALLSPICE 阐明了跨表型关联背后的共享和异质罕见变异架构，并为罕见变异多效性提供了见解。

## Abstract
Recent expansion of large-scale biobank resources has enabled rare-variant association studies (RVAS) and systematic investigation of rare variant pleiotropy across thousands of phenotypes simultaneously. However, existing statistical frameworks for dissecting pleiotropy were largely developed for common variants and are not well suited to gene-based rare variant signals, limiting the interpretation of cross-phenotype associations. Here, we develop ALLSPICE, a likelihood-based method that tests whether rare variant effects in genes exhibiting cross-phenotype associations are proportional or heterogeneous across continuous traits while accounting for phenotypic correlation using summary statistics. ALLSPICE is well-calibrated in simulations and is implemented as an R package for scalable analysis of gene-level rare-variant burden associations. We applied ALLSPICE to RVAS of 359 continuous traits in the UK Biobank and identified 124 significant heterogeneous events among 11,810 pairs of gene-trait associations. By identifying effect heterogeneity within genes associated with multiple phenotypes, ALLSPICE clarifies shared and heterogeneous rare variant architectures underlying cross-phenotype associations and provides insight into rare variant pleiotropy.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **ALLSPICE** 的新统计框架，旨在通过分析罕见编码变异的效应异质性，揭示复杂的基因多效性（Pleiotropy）。以下是对该论文的深度结构化总结：

### 1. 核心问题与研究动机
*   **研究背景**：全基因组关联研究（GWAS）显示，一个基因往往影响多个表型（即多效性）。多效性可分为**垂直多效性**（一个性状介导另一个性状）和**水平多效性**（通过独立机制影响多个性状）。
*   **核心问题**：现有的多效性分析方法主要针对常见变异设计，而罕见变异通常需要进行基因水平的“负荷测试”（Burden Test）来增强统计效能。然而，简单的基因级汇总会掩盖基因内部不同变异对不同性状的差异化影响。
*   **研究动机**：缺乏一种能够利用汇总统计量（Summary Statistics）来区分基因内罕见变异效应是“成比例一致”还是“异质化”的统计工具。

### 2. 方法论：ALLSPICE 框架
*   **核心思想**：ALLSPICE（ALLelic Spectrum of Pleiotropy Informed Correlated Effects）基于似然比检验（LRT），测试一个基因内多个罕见变异对两个连续性状的效应量是否符合线性比例关系。
*   **关键技术细节**：
    *   **零假设 ($H_0$)**：$\beta_1 = c\beta_2$。即变异对性状1的效应量与对性状2的效应量成正比（反映共享的生物学路径或垂直多效性）。
    *   **备择假设 ($H_1$)**：$\beta_1 \neq c\beta_2$。即效应不成比例，存在异质性（反映水平多效性或不同的分子机制）。
    *   **模型构建**：在封闭形式的线性回归框架下，通过最大似然估计（MLE）确定比例参数 $c$，同时显式考虑表型之间的相关性（Phenotypic Correlation）。
    *   **适用范围**：针对超罕见变异（MAF < 0.01%），假设变异间连锁不平衡（LD）可以忽略不计。

### 3. 实验设计
*   **数据集**：使用 **UK Biobank**（约39.5万个全外显子组序列）的 **Genebass** 汇总统计数据。
*   **分析场景**：
    *   对 359 个连续性状进行分析。
    *   筛选出 11,810 对具有显著负荷关联的“基因-性状”对。
*   **Benchmark 与对比**：
    *   通过大规模模拟实验（1,584 种零假设场景和 792 种备择假设场景）验证方法的校准度（Type I Error）和统计效能（Power）。
    *   对比了不同功能注释（pLoF、错义变异、同义变异）下的异质性表现。
    *   引入蛋白质 3D 结构分析（PDB 数据）来验证识别出的异质性变异是否具有生物学功能聚集性。

### 4. 资源与算力
*   **算力说明**：论文未明确提及具体的 GPU 型号或训练时长。
*   **实现方式**：该方法被实现为一个名为 `ALLSPICER` 的 R 语言包。由于其基于汇总统计量而非个体级数据，计算效率极高，适合大规模生物样本库的扩展分析。

### 5. 实验数量与充分性
*   **实验规模**：
    *   **模拟实验**：进行了数千组参数组合的模拟，涵盖了不同的效应大小、变异数量、表型相关性和斜率。
    *   **实际应用**：测试了超过 1.1 万对关联，最终识别出 124 个显著的异质性事件。
*   **充分性评价**：实验设计非常充分。除了统计学验证，作者还通过 **LOVO（留一变异法）** 分析了单个变异对信号的贡献，并结合蛋白质结构进行了深入的案例研究（如 *ALB* 和 *ALPL* 基因），增强了结论的说服力。

### 6. 主要结论与发现
*   **广泛的异质性**：在 11,810 对关联中发现了 124 个显著的效应异质性事件，说明罕见变异的多效性架构比预想的更复杂。
*   **注释类别差异**：错义变异（Missense）比预测的功能丧失变异（pLoF）表现出更高的异质性，这符合错义变异可能通过多种分子机制改变蛋白功能的预期。
*   **生物学发现**：
    *   在 **白蛋白基因 (*ALB*)** 中，发现某些错义变异对血钙和白蛋白水平的影响方向相反，且这些变异在 3D 结构上聚集在钙结合区域。
    *   在 ***ALPL*** 基因中，错义变异对碱性磷酸酶和磷酸盐水平表现出复杂的异质效应。

### 7. 优点与亮点
*   **高效性**：仅需汇总统计量即可运行，无需访问受限的个体级基因型数据。
*   **鲁棒性**：显式考虑了表型相关性，避免了因性状本身相关而产生的伪异质性。
*   **解释力**：通过区分比例效应和异质效应，为理解基因如何通过不同变异影响不同生物路径提供了新工具。

### 8. 不足与局限
*   **性状限制**：目前仅适用于**连续性状**，尚未扩展到二元性状（如疾病患病情况）。
*   **LD 假设**：假设变异间无 LD，虽然对超罕见变异合理，但若应用于频率略高的变异可能会导致偏倚。
*   **统计效能**：受限于罕见变异的稀缺性，对于变异数量极少的基因，检测异质性的效能较低。
*   **注释依赖**：结果高度依赖于变异的功能注释准确性，误报的注释可能干扰异质性判断。

（完）
