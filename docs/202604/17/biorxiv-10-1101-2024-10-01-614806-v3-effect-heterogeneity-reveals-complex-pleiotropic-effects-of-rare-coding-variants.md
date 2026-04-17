---
title: Effect heterogeneity reveals complex pleiotropic effects of rare coding variants
title_zh: 效应异质性揭示了罕见编码变异复杂的基因多效性
authors: "Lu, W., Chen, S., Auwerx, C., Fu, J., Posthuma, D., Neale, B., O'Connor, L. J., Karczewski, K."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.1101/2024.10.01.614806v3.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 罕见变异关联研究和多效性的统计方法
tldr: 本研究针对现有统计框架难以处理基因水平罕见变异多效性的问题，开发了名为 ALLSPICE 的似然比检验方法。该方法利用汇总统计量，在考虑表型相关性的基础上，评估基因在不同连续性状间的罕见变异效应是成比例还是具有异质性。通过对 UK Biobank 中 359 个性状的分析，研究成功识别出 124 个显著的异质性事件，揭示了罕见变异背后复杂的遗传架构，为理解跨表型关联提供了重要工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-001.webp\", \"caption\": \"Figure 1 | Definition of gene-annotation pairs and association pairs. A, Schematic representation of gene-annotation pairs, defined as sets of rare variants within a gene grouped according to functional annotations (pLoF, missense, synonymous, and pLoF+ missense) for burden testing, and of cross-phenotype associations, defined as a gene-annotation pair showing significant burden associations (pburden < 2.5 ⨉ 10-6) with more than one phenotype. B, Definition of an association pair (left), schematic illustrations of gene-level horizontal pleiotropy (middle) and vertical (right) pleiotropy, and corresponding expected variant-level effect size patterns shown in the scatter plots.\", \"page\": 7, \"index\": 1, \"width\": 979, \"height\": 735}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-002.webp\", \"caption\": \"Figure 2 | Summary of cross-phenotype associations and ALLSPICE results. A, Distributions of genes by the number of associated phenotypes (x-axis) across four functional annotation groups (panels and colors). Labels above the bars indicate the proportion of genes with more than one association among genes with at least one association in the corresponding annotation group. B, Heatmap of pALLSPICE for strictly significant pairs of pLoF associations: with phenotype pairs on the x- and y-axes, and genes labeled accordingly. Cell color indicates -log10(pALLSPICE). Cells marked with asterisks denote association pairs with pALLSPICE=0. C, Heatmap of pALLSPICE for strictly significant missense association pairs, using the same display format as in B.\", \"page\": 10, \"index\": 2, \"width\": 979, \"height\": 754}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-003.webp\", \"caption\": \"Figure 3 | Examples of association pairs significant in ALLSPICE. A, Comparison of variant effect sizes on albumin (x-axis) and calcium (y-axis) among variants in ALB, stratified by functional annotation group (colors and columns). Point shapes indicate nominal significance (pGWAS < 0.05) in single-variant association tests for the two phenotypes. The missense variant chr4:73412072:A:G, labeled and highlighted by a blue circle, is significantly associated with both traits but exhibits opposite directions of effect and represents one of the strongest contributors in the LOVO analysis. The value shown in the bottom right of each panel denotes pALLSPICE for the corresponding annotation group. B, Comparison of ALPL variant effect sizes on alkaline phosphatase (x-axis) to phosphate level (y-axis). Panels A and B share the same legend.\", \"page\": 12, \"index\": 3, \"width\": 979, \"height\": 654}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-004.webp\", \"caption\": \"Figure 4 | Rare protein-coding variants in ALB (AF < 0.0001) on ALB protein structure. A, Distribution of ALB missense variants associated with calcium level but not albumin level (pink), variants associated with albumin but not calcium level (green), and known calcium binding sites (orange) on the 3D structure of ALB protein (PDB ID: 1AO6). B, Comparison of pairwise distances from missense variants only associated with calcium (pink) or albumin-level (green) to calcium binding sites on ALB protein structure in the 3D space. Colors in panel B are defined the same as in panel A. C, Distribution of ALB missense variants associated with either albumin or calcium level that affect the two biomarker levels in the same (blue) or different (red) direction, and calcium binding sites (orange) on the 3D structure of ALB protein (PDB ID: 1AO6). D, Comparison of pairwise distances between missense variants to calcium binding sites on the ALB protein structure in the 3D space. Colors in panel D are defined the same as in panel C.\", \"page\": 14, \"index\": 4, \"width\": 979, \"height\": 718}]"
motivation: 现有的多表型关联分析方法主要针对常见变异设计，不适用于基因水平的罕见变异研究，限制了对罕见变异多效性的深入解读。
method: 开发了基于似然比的 ALLSPICE 方法，通过汇总统计量测试基因在不同性状间的罕见变异效应是否存在异质性，并校正了表型间的相关性。
result: "在对 UK Biobank 中 359 个连续性状的分析中，从 11,810 对基因-性状关联中识别出 124 个具有显著效应异质性的事件。"
conclusion: ALLSPICE 能够有效区分跨表型关联中共享与异质的罕见变异架构，为理解罕见编码变异的复杂多效性提供了新见解。
---

## 摘要
近年来大规模生物样本库资源的扩展，使得罕见变异关联研究（RVAS）以及同时对数千种表型进行罕见变异多效性的系统研究成为可能。然而，现有的剖析多效性的统计框架主要针对常见变异开发，并不完全适用于基于基因的罕见变异信号，从而限制了对跨表型关联的解释。在此，我们开发了 ALLSPICE，这是一种基于似然的方法，利用汇总统计量并考虑表型相关性，测试表现出跨表型关联的基因中的罕见变异效应在连续性状之间是成比例的还是异质的。ALLSPICE 在模拟中表现出良好的校准性，并作为一个 R 软件包实现，用于基因级罕见变异负荷关联的可扩展分析。我们将 ALLSPICE 应用于英国生物样本库（UK Biobank）中 359 种连续性状的 RVAS，并在 11,810 对基因-性状关联中识别出 124 个显著的异质性事件。通过识别与多种表型相关的基因内的效应异质性，ALLSPICE 阐明了跨表型关联背后的共享和异质罕见变异架构，并为罕见变异多效性提供了见解。

## Abstract
Recent expansion of large-scale biobank resources has enabled rare-variant association studies (RVAS) and systematic investigation of rare variant pleiotropy across thousands of phenotypes simultaneously. However, existing statistical frameworks for dissecting pleiotropy were largely developed for common variants and are not well suited to gene-based rare variant signals, limiting the interpretation of cross-phenotype associations. Here, we develop ALLSPICE, a likelihood-based method that tests whether rare variant effects in genes exhibiting cross-phenotype associations are proportional or heterogeneous across continuous traits while accounting for phenotypic correlation using summary statistics. ALLSPICE is well-calibrated in simulations and is implemented as an R package for scalable analysis of gene-level rare-variant burden associations. We applied ALLSPICE to RVAS of 359 continuous traits in the UK Biobank and identified 124 significant heterogeneous events among 11,810 pairs of gene-trait associations. By identifying effect heterogeneity within genes associated with multiple phenotypes, ALLSPICE clarifies shared and heterogeneous rare variant architectures underlying cross-phenotype associations and provides insight into rare variant pleiotropy.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **ALLSPICE** 的新统计方法，旨在解析罕见编码变异在不同表型之间的复杂多效性（Pleiotropy）。以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：当一个基因的罕见变异与多个性状相关时，这种“多效性”究竟是因为该基因通过单一路径影响所有性状（垂直多效性，效应成比例），还是通过不同路径影响不同性状（水平多效性，效应异质）？
*   **研究背景**：
    *   随着大规模生物样本库（如 UK Biobank）的普及，罕见变异关联研究（RVAS）发现了大量跨表型关联。
    *   现有的多效性分析工具（如共定位、孟德尔随机化）主要针对常见变异（基于连锁不平衡 LD），不适用于基因水平的罕见变异负荷（Burden）分析。
    *   理解罕见变异的效应模式对于揭示生物学机制、药物靶点发现和疾病风险预测至关重要。

### 2. 论文提出的方法论：ALLSPICE
*   **核心思想**：利用似然比检验（Likelihood Ratio Test, LRT）来评估一个基因内多个罕见变异在两个性状间的效应量是否满足**比例关系**。
*   **关键技术细节**：
    *   **输入**：仅需变异水平的汇总统计量（效应量 $\beta$ 和标准差 $SE$）以及表型间的相关性矩阵。
    *   **零假设 ($H_0$)**：比例效应模型（Proportional Model）。即对于基因内的所有变异 $j$，性状 2 的效应量是性状 1 效应量的固定倍数 ($\beta_{j,2} = \rho \beta_{j,1}$)。这通常对应于基因功能的整体改变（如蛋白质全丢失）。
    *   **备择假设 ($H_1$)**：异质效应模型（Heterogeneous Model）。效应量不遵循统一比例，暗示变异可能通过不同机制影响不同表型。
    *   **协方差校正**：模型考虑了由于样本重叠或生物学相关性导致的表型间相关性，确保了检验的稳健性。
    *   **LOVO 分析**：引入“留一变异法”（Leave-One-Variant-Out），用于识别驱动异质性信号的具体关键变异。

### 3. 实验设计
*   **数据集**：
    *   **UK Biobank (UKB)**：包含约 20 万人的全外显子组测序（WES）数据。
    *   **表型**：359 个连续性状（包括生物标志物、物理测量值等）。
*   **实验流程**：
    1.  **模拟实验**：在不同变异数量、效应量大小和表型相关性下验证方法的 I 类错误率（Type I error）和统计效能（Power）。
    2.  **真实数据应用**：对 UKB 中的基因-性状对进行负荷测试，筛选出显著关联的对，随后应用 ALLSPICE。
*   **对比基准**：模拟实验中对比了忽略表型相关性的朴素模型，证明了 ALLSPICE 在处理相关性状时的优越性。

### 4. 资源与算力
*   **算力说明**：论文未详细列出具体的 GPU 型号或训练时长。
*   **实现方式**：该方法被实现为一个 **R 软件包**。由于 ALLSPICE 基于汇总统计量而非个体级数据，其计算效率极高，能够在大规模生物样本库数据上实现可扩展分析。

### 5. 实验数量与充分性
*   **实验规模**：
    *   分析了 **11,810 对**具有显著负荷关联的“基因-性状”组合。
    *   涵盖了四种功能注释（pLoF、错义变异、同义变异、pLoF+错义）。
    *   进行了详尽的模拟实验，覆盖了多种遗传架构场景。
*   **充分性评价**：实验设计非常充分。研究不仅在大规模真实数据上验证了方法，还通过具体的生物学案例（如 *ALB* 基因与钙离子/白蛋白的关系）进行了深入的功能解释和结构生物学验证，增强了结论的可信度。

### 6. 主要结论与发现
*   **异质性普遍存在**：在 11,810 对关联中识别出 **124 个显著的异质性事件**。
*   **典型案例**：
    *   ***ALB* 基因**：发现某些错义变异对血钙水平的影响远超其对白蛋白水平的影响。结构分析显示，这些变异直接位于钙结合位点，而非影响蛋白质整体丰度。
    *   ***ALPL* 基因**：揭示了其在碱性磷酸酶和磷酸盐水平之间的复杂调节作用。
*   **注释差异**：错义变异比 pLoF（蛋白质功能丧失）变异更容易表现出效应异质性，因为 pLoF 通常导致蛋白质完全缺失，而错义变异可能仅改变蛋白质的特定功能域。

### 7. 优点
*   **统计严谨性**：有效解决了罕见变异分析中样本重叠和表型相关的统计偏差问题。
*   **高效性**：仅需汇总统计量，便于在不同研究团队间共享数据进行元分析。
*   **生物学洞察**：能够区分“基因水平”的整体影响和“变异水平”的特定影响，有助于精准医疗和机制研究。

### 8. 不足与局限
*   **表型限制**：目前主要针对**连续性状**设计，尚未直接扩展到二元性状（如疾病患病与否）。
*   **变异数量依赖**：对于变异数量极少（如仅 1-2 个变异）的基因，统计效能受限，难以检测异质性。
*   **线性假设**：模型假设两个性状间的关系是线性的，对于更复杂的非线性生物学相互作用可能解释不足。

（完）
