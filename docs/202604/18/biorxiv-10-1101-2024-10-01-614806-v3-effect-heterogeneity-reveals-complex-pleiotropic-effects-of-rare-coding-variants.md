---
title: Effect heterogeneity reveals complex pleiotropic effects of rare coding variants
title_zh: 效应异质性揭示了罕见编码变异的复杂多效性效应
authors: "Lu, W., Chen, S., Auwerx, C., Fu, J., Posthuma, D., Neale, B., O'Connor, L. J., Karczewski, K."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.1101/2024.10.01.614806v3.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 罕见变异关联研究和多效性的似然法
tldr: 本研究针对现有罕见变异关联研究（RVAS）中缺乏解析基因水平多效性工具的问题，开发了基于似然比的统计方法ALLSPICE。该方法利用汇总统计量，在考虑表型相关性的基础上，检测基因在不同连续性状间的效应是成比例还是异质的。通过对英国生物样本库（UK Biobank）359个表型的分析，研究揭示了罕见变异在跨表型关联中的复杂异质性架构，为理解罕见变异的多效性提供了新视角。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-001.webp\", \"caption\": \"Figure 1 | Definition of gene-annotation pairs and association pairs. A, Schematic representation of gene-annotation pairs, defined as sets of rare variants within a gene grouped according to functional annotations (pLoF, missense, synonymous, and pLoF+ missense) for burden testing, and of cross-phenotype associations, defined as a gene-annotation pair showing significant burden associations (pburden < 2.5 ⨉ 10-6) with more than one phenotype. B, Definition of an association pair (left), schematic illustrations of gene-level horizontal pleiotropy (middle) and vertical (right) pleiotropy, and corresponding expected variant-level effect size patterns shown in the scatter plots.\", \"page\": 7, \"index\": 1, \"width\": 979, \"height\": 735}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-002.webp\", \"caption\": \"Figure 2 | Summary of cross-phenotype associations and ALLSPICE results. A, Distributions of genes by the number of associated phenotypes (x-axis) across four functional annotation groups (panels and colors). Labels above the bars indicate the proportion of genes with more than one association among genes with at least one association in the corresponding annotation group. B, Heatmap of pALLSPICE for strictly significant pairs of pLoF associations: with phenotype pairs on the x- and y-axes, and genes labeled accordingly. Cell color indicates -log10(pALLSPICE). Cells marked with asterisks denote association pairs with pALLSPICE=0. C, Heatmap of pALLSPICE for strictly significant missense association pairs, using the same display format as in B.\", \"page\": 10, \"index\": 2, \"width\": 979, \"height\": 754}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-003.webp\", \"caption\": \"Figure 3 | Examples of association pairs significant in ALLSPICE. A, Comparison of variant effect sizes on albumin (x-axis) and calcium (y-axis) among variants in ALB, stratified by functional annotation group (colors and columns). Point shapes indicate nominal significance (pGWAS < 0.05) in single-variant association tests for the two phenotypes. The missense variant chr4:73412072:A:G, labeled and highlighted by a blue circle, is significantly associated with both traits but exhibits opposite directions of effect and represents one of the strongest contributors in the LOVO analysis. The value shown in the bottom right of each panel denotes pALLSPICE for the corresponding annotation group. B, Comparison of ALPL variant effect sizes on alkaline phosphatase (x-axis) to phosphate level (y-axis). Panels A and B share the same legend.\", \"page\": 12, \"index\": 3, \"width\": 979, \"height\": 654}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-10-01-614806-v3/fig-004.webp\", \"caption\": \"Figure 4 | Rare protein-coding variants in ALB (AF < 0.0001) on ALB protein structure. A, Distribution of ALB missense variants associated with calcium level but not albumin level (pink), variants associated with albumin but not calcium level (green), and known calcium binding sites (orange) on the 3D structure of ALB protein (PDB ID: 1AO6). B, Comparison of pairwise distances from missense variants only associated with calcium (pink) or albumin-level (green) to calcium binding sites on ALB protein structure in the 3D space. Colors in panel B are defined the same as in panel A. C, Distribution of ALB missense variants associated with either albumin or calcium level that affect the two biomarker levels in the same (blue) or different (red) direction, and calcium binding sites (orange) on the 3D structure of ALB protein (PDB ID: 1AO6). D, Comparison of pairwise distances between missense variants to calcium binding sites on the ALB protein structure in the 3D space. Colors in panel D are defined the same as in panel C.\", \"page\": 14, \"index\": 4, \"width\": 979, \"height\": 718}]"
motivation: 现有的多效性分析框架主要针对常见变异，难以有效解析基因水平罕见变异在不同性状间的复杂关联模式。
method: 开发了名为ALLSPICE的似然比检验方法，通过汇总统计量评估基因内罕见变异效应在不同连续性状间是否存在异质性。
result: "在对英国生物样本库359个连续性状的分析中，从11,810对基因-性状关联中识别出124个显著的异质性事件。"
conclusion: ALLSPICE能够有效区分罕见变异的共享与异质架构，深化了对罕见编码变异复杂多效性的理解。
---

## 摘要
近期大规模生物样本库资源的扩展使得罕见变异关联研究（RVAS）以及同时针对数千种表型的罕见变异多效性系统性研究成为可能。然而，现有的剖析多效性的统计框架主要针对常见变异开发，并不适用于基于基因的罕见变异信号，从而限制了对跨表型关联的解释。在此，我们开发了 ALLSPICE，这是一种基于似然的方法，利用汇总统计量并在考虑表型相关性的情况下，测试表现出跨表型关联的基因中的罕见变异效应在连续性状之间是成比例的还是异质的。ALLSPICE 在模拟实验中经过了良好校准，并作为一个 R 软件包实现，用于基因水平罕见变异负荷关联的可扩展分析。我们将 ALLSPICE 应用于英国生物样本库（UK Biobank）中 359 种连续性状的 RVAS，并在 11,810 对基因-性状关联中识别出 124 个显著的异质性事件。通过识别与多种表型相关的基因内的效应异质性，ALLSPICE 阐明了跨表型关联背后的共享和异质罕见变异架构，并为罕见变异多效性提供了见解。

## Abstract
Recent expansion of large-scale biobank resources has enabled rare-variant association studies (RVAS) and systematic investigation of rare variant pleiotropy across thousands of phenotypes simultaneously. However, existing statistical frameworks for dissecting pleiotropy were largely developed for common variants and are not well suited to gene-based rare variant signals, limiting the interpretation of cross-phenotype associations. Here, we develop ALLSPICE, a likelihood-based method that tests whether rare variant effects in genes exhibiting cross-phenotype associations are proportional or heterogeneous across continuous traits while accounting for phenotypic correlation using summary statistics. ALLSPICE is well-calibrated in simulations and is implemented as an R package for scalable analysis of gene-level rare-variant burden associations. We applied ALLSPICE to RVAS of 359 continuous traits in the UK Biobank and identified 124 significant heterogeneous events among 11,810 pairs of gene-trait associations. By identifying effect heterogeneity within genes associated with multiple phenotypes, ALLSPICE clarifies shared and heterogeneous rare variant architectures underlying cross-phenotype associations and provides insight into rare variant pleiotropy.

---

## 论文详细总结（自动生成）

这是一份关于论文《Effect heterogeneity reveals complex pleiotropic effects of rare coding variants》的结构化深度总结：

### 1. 核心问题与整体含义
*   **研究动机**：全基因组关联研究（GWAS）已发现大量多效性（Pleiotropy）现象，即一个基因或变异影响多个表型。然而，现有的多效性分析框架主要针对常见变异设计，难以直接应用于罕见变异。罕见变异通常需要进行基因水平的负荷测试（Burden Test），这掩盖了基因内部不同变异之间可能存在的效应异质性。
*   **核心问题**：如何系统地检测和量化基因内罕见变异在不同性状之间的效应异质性，从而区分“共享路径（垂直多效性）”与“不同生物机制（水平多效性）”？

### 2. 方法论：ALLSPICE 框架
*   **核心思想**：ALLSPICE（ALLelic Spectrum of Pleiotropy Informed Correlated Effects）是一种基于似然比检验（LRT）的统计方法。它通过测试两个性状间的变异效应是否满足“成比例关系”来识别异质性。
*   **关键技术细节**：
    *   **模型假设**：对于一个基因内的多个罕见变异，假设其对性状 1 的效应向量为 $\beta_1$，对性状 2 的效应向量为 $\beta_2$。
    *   **零假设 ($H_0$)**：$\beta_1 = c\beta_2$，即变异效应在两个性状间是完美成比例的（暗示共享同一生物路径）。
    *   **备择假设 ($H_1$)**：$\beta_1 \neq c\beta_2$（暗示存在异质性效应）。
    *   **统计实现**：利用单变异关联的汇总统计量（Summary Statistics），在封闭形式的线性回归框架下，通过极大似然估计（MLE）推导比例参数 $c$，同时显式校正表型之间的相关性。
    *   **适用范围**：目前仅限于连续性状，且针对超罕见变异（MAF < 0.01%），此时可忽略连锁不平衡（LD）的影响。

### 3. 实验设计
*   **数据集**：
    *   **UK Biobank (UKB)**：包含 394,841 个个体的全外显子组测序（WES）数据。
    *   **Genebass**：利用其提供的 3,500+ 表型的基因水平关联结果。
*   **场景与 Benchmark**：
    *   **模拟实验**：设计了 1,584 种零假设场景和 792 种备择假设场景（包括独立效应、相关但不成比例效应、非线性效应），验证方法的第 I 类错误控制和统计效力。
    *   **真实数据应用**：分析了 359 个连续性状，涉及 11,810 对具有显著负荷关联的“基因-性状”对。
*   **对比分析**：通过留一法（LOVO）分析识别对异质性贡献最大的特定变异，并结合蛋白质 3D 结构（PDB 数据）验证变异的功能聚类。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU/CPU 型号、核心数量或具体的训练/运行总时长。
*   **效率评价**：作者强调 ALLSPICE 仅需汇总统计量即可运行，计算效率极高，并已封装为 R 软件包 `ALLSPICER`，适合大规模生物样本库的扩展分析。

### 5. 实验数量与充分性
*   **实验规模**：
    *   模拟实验非常详尽，覆盖了不同的变异数量（m=5 到 100）、不同的比例系数 $c$、以及从 -1 到 1 的表型相关性 $r$。
    *   真实数据分析涵盖了 185 个独特基因和数百个表型。
*   **充分性评价**：实验设计较为充分且客观。作者不仅验证了统计学的校准度，还通过具体的生物学案例（如 *ALB* 基因与钙/白蛋白的关系）进行了深度功能验证，证明了该方法能捕捉到具有生物学意义的信号。

### 6. 主要结论与发现
*   **广泛的异质性**：在 11,810 对关联中识别出 124 个显著的异质性事件（校正后 $p < 4.23 \times 10^{-6}$）。
*   **变异类型差异**：蛋白质丢失功能（pLoF）变异通常表现出更一致的效应方向，而错义变异（Missense）更容易表现出效应异质性。
*   **典型案例分析**：
    *   **ALB (白蛋白基因)**：发现某些错义变异对血钙和白蛋白水平具有相反方向的效应，且这些变异在空间结构上显著富集在钙结合位点附近。
    *   **APOB 与 TET2**：在这些长基因中观察到显著的 pLoF 效应异质性，挑战了“pLoF 效应总是均一”的传统假设。

### 7. 优点与亮点
*   **无需个体数据**：仅依赖汇总统计量，极大降低了数据获取门槛和计算开销。
*   **考虑表型相关性**：有效解决了因表型本身相关（如身高与体重）导致的伪多效性干扰。
*   **生物学解释力强**：通过结合蛋白质 3D 结构分析，将抽象的统计异质性转化为具体的分子机制解释。
*   **工具化**：提供了开源 R 包，便于社区使用。

### 8. 不足与局限
*   **性状限制**：目前仅支持连续性状，不支持二元性状（如疾病患病情况），限制了其在临床诊断研究中的应用。
*   **LD 假设**：假设变异间无 LD，虽然对超罕见变异合理，但若应用于频率略高的变异（如 MAF > 0.1%），可能会导致结果偏差。
*   **统计效力受限**：罕见变异本身携带信息有限，对于变异数量极少的基因，该方法检测异质性的效力较低。
*   **注释依赖**：结果高度依赖于变异的功能注释准确性，误注释可能引入虚假的异质性信号。

（完）
