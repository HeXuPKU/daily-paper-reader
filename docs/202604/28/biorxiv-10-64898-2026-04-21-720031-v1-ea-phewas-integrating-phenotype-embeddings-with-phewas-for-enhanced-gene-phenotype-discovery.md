---
title: "EA-PheWAS: Integrating Phenotype Embeddings with PheWAS for Enhanced Gene-Phenotype Discovery"
title_zh: EA-PheWAS：将表型嵌入与 PheWAS 集成以增强基因-表型发现
authors: "Zheng, W., Liu, T., Xu, L., Xie, Y., Jing, Y., Shao, H., Zhao, H."
date: 2026-04-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.720031v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 利用EHR数据将表型嵌入与PheWAS集成
tldr: 本研究针对传统全表型组关联分析（PheWAS）在处理稀有变异和稀有表型时统计效力不足的问题，提出了EA-PheWAS框架。该方法首先通过EmbedPheScan将稀有功能缺失变异携带者的表型特征映射到连续嵌入空间，再利用聚合柯西关联检验将嵌入信号与传统回归结果结合。在英国生物样本库数据上的实验表明，EA-PheWAS在多种基因场景下均优于传统方法，显著提升了基因-表型关联的发现能力。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统PheWAS采用二元表型表示且独立处理各表型，导致在分析稀有变异、稀有表型或跨临床代码分布的表型时统计效力受限。
method: 提出EA-PheWAS框架，通过EmbedPheScan生成表型嵌入信号，并利用聚合柯西关联检验将其与传统回归分析结果进行整合。
result: 在英国生物样本库的实验中，EA-PheWAS在保持假阳性控制的同时，在全基因组扫描和特定基因案例分析中均表现出优于传统方法的性能。
conclusion: EA-PheWAS通过整合表型嵌入与传统统计方法，为发现稀有变异相关的复杂基因-表型关联提供了一个更强大的分析工具。
---

## 摘要
全表型组关联研究（PheWAS）能够系统地探索遗传变异与源自电子健康档案（EHR）的临床表型之间的关系。传统的基于回归的 PheWAS 将表型分开处理，并依赖于二元表型表示，这限制了罕见变异和罕见表型的统计效能，并降低了检测与分布在多个临床代码中的表型之间关联的能力。为了解决这一局限性，我们首先开发了 EmbedPheScan，这是一个基于表型嵌入的优先级排序框架，它在连续嵌入空间中总结了罕见功能缺失（LoF）变异携带者的表型特征。随后，我们通过使用聚合柯西关联检验（ACAT），将这些源自嵌入的信号与传统的基于回归的 PheWAS 结果相结合，提出了 EA-PheWAS。利用英国生物样本库（UK Biobank）的全外显子组测序和 EHR 数据，我们证明了所提出的方法能够保持适当的假阳性控制。随后，我们在所有基因以及生物学定义的基因类别中进行了全基因组表型扫描，以评估 EA-PheWAS 相对于传统 PheWAS 和 EmbedPheScan 的表现，一致发现 EA-PheWAS 优于其他两种方法。我们重点关注了代表不同场景的四个基因，以说明 EA-PheWAS 的实用性，包括强效应致病基因（PKD1、PKD2）、具有大量罕见 LoF 携带者的基因（NF1）以及携带者计数极稀疏的基因（FBN1）。

## Abstract
Phenome-wide association studies (PheWAS) enable systematic exploration of relationships between genetic variants and clinical phenotypes derived from electronic health records (EHRs). Conventional regression-based PheWAS treats phenotypes separately and relies on binary phenotype representations, which limits statistical power for rare variants and rare phenotypes and reduces the ability to detect associations with phenotypes that are distributed across clinical codes. To address this limitation, we first developed EmbedPheScan, a phenotype embedding-based prioritization framework that summarizes the phenotypic profiles of rare loss-of-function variant carriers in a continuous embedding space. We then proposed EA-PheWAS by combining these embedding-derived signals with conventional regression-based PheWAS results using the aggregated Cauchy association test. Using the UK Biobank whole-exome sequencing and EHR data, we show that the proposed methods maintain appropriate false-positive control. We then performed genome-wide phenome scans across all genes and across biologically defined gene classes to evaluate EA-PheWAS relative to conventional PheWAS and EmbedPheScan, consistently finding that EA-PheWAS outperformed the other two methods. We illustrate the utility of EA-PheWAS focusing on four genes representing distinct scenarios, including strong-effect disease genes (PKD1, PKD2), genes with large numbers of rare LoF carriers (NF1), and genes with extremely sparse carrier counts (FBN1).

---

## 论文详细总结（自动生成）

这是一份关于论文《EA-PheWAS: Integrating Phenotype Embeddings with PheWAS for Enhanced Gene-Phenotype Discovery》的结构化深度总结：

### 1. 核心问题与研究动机
*   **核心问题**：传统的全表型组关联分析（PheWAS）在处理**罕见遗传变异**（如功能缺失变异 LoF）和**罕见临床表型**时，统计效能严重不足。
*   **研究动机**：
    *   **表型表示单一**：传统方法将表型视为独立的二元变量（0/1），忽略了临床诊断代码（ICD-10）之间的语义相似性、层级结构和共病模式。
    *   **信号碎片化**：罕见变异携带者的临床表现往往具有异质性和多系统性，信号分散在多个临床代码中，导致单个代码的统计显著性难以达到。
    *   **数据稀疏性**：在大型生物样本库中，特定基因的罕见变异携带者人数极少，传统回归模型难以捕捉关联。

### 2. 方法论
EA-PheWAS（嵌入增强型 PheWAS）的核心思想是将**表型语义嵌入**与**传统统计回归**相结合。
*   **表型嵌入生成**：利用 Word2Vec 模型对英国生物样本库（UKBB）中的纵向 ICD-10 诊断序列进行训练，将每个代码映射为连续向量。
*   **个体与基因表型谱构建**：
    *   **个体嵌入**：取该个体所有 ICD-10 嵌入的平均值。
    *   **基因嵌入**：取该基因所有罕见 LoF 变异携带者的个体嵌入平均值，形成该基因的“表型特征指纹”。
*   **EmbedPheScan 框架**：计算基因嵌入与特定表型（Phecode）嵌入之间的余弦相似度。通过 10,000 次随机采样构建经验零分布，将相似度得分转化为经验 P 值。
*   **信号集成（EA-PheWAS）**：使用**聚合柯西关联检验（ACAT）**，将 EmbedPheScan 产生的嵌入相似性 P 值与传统逻辑回归 PheWAS 的 P 值进行融合。这种方法能自适应地放大任一维度的强信号。

### 3. 实验设计
*   **数据集**：英国生物样本库（UK Biobank）500K 数据集，筛选出 328,737 名无亲缘关系的欧洲裔个体，包含全外显子组测序（WES）和电子健康档案（EHR）。
*   **基准（Benchmark）**：使用人类表型本体（HPO）数据库作为“金标准”，将已知的基因-表型关联作为真值。
*   **对比方法**：
    1.  **Conventional PheWAS**：传统的基于协变量调整的逻辑回归方法。
    2.  **EmbedPheScan**：仅使用表型嵌入相似性的排序方法。
*   **评估指标**：Top-k 命中精确度（Hit Precision @ 5/10/15）、召回率（Recall）以及胜率（Beat Rate）。

### 4. 资源与算力
*   论文中**未明确说明**具体的硬件配置（如 GPU 型号、数量）或具体的训练时长。
*   提到使用了 PLINK 进行基因型质控，Word2Vec 进行嵌入训练，以及基于 10,000 次采样的经验 P 值计算。由于涉及 1.7 万个基因的全基因组扫描和大规模重采样，该研究对 CPU 集群算力有一定要求。

### 5. 实验数量与充分性
*   **实验规模**：
    *   **全基因组扫描**：对 17,233 个基因进行了完整的表型扫描。
    *   **功能子集分析**：针对单倍体不足（HI）基因和组织特异性基因进行了专门评估。
    *   **模拟实验**：针对不同携带者人数（50、120、300 人）进行了假阳性率（Type I Error）控制测试。
    *   **案例研究**：深入分析了 PKD1/2、NF1、FBN1 四个具有代表性的基因。
*   **充分性评价**：实验设计非常充分且客观。通过模拟实验验证了统计学严谨性，通过全基因组评估验证了普适性，通过案例研究展示了在不同数据稀疏程度下的鲁棒性。

### 6. 主要结论与发现
*   **性能提升**：EA-PheWAS 在所有评估指标上均一致优于传统 PheWAS 和单纯的嵌入方法。
*   **假阳性控制**：模拟实验表明，EA-PheWAS 在不同携带者规模下均能很好地控制假阳性率。
*   **互补性**：嵌入信号能捕捉语义相关的临床模式，而回归信号能捕捉直接的统计重叠。EA-PheWAS 成功整合了这两者，尤其在携带者极少（如 FBN1，仅 18 人）的情况下，嵌入信号提供了关键的发现能力。
*   **生物学发现**：在 PKD1/2 等案例中，EA-PheWAS 不仅找回了 HPO 标注的表型，还识别出了如“肾移植”、“透析”等临床高度相关但未被传统方法排在首位的表型。

### 7. 优点
*   **创新集成**：首次将 NLP 领域的嵌入技术与经典的 ACAT 统计检验结合，解决了罕见变异分析中的“小样本”难题。
*   **信息利用率高**：通过连续空间表示，利用了 EHR 数据中的纵向结构和共病信息，而非简单的二元切分。
*   **自适应性**：ACAT 检验使得模型在回归信号强时依赖回归，在数据稀疏时依赖嵌入相似性，具有很强的灵活性。

### 8. 不足与局限
*   **人群偏差**：研究仅限于欧洲裔人群，其表型嵌入和关联结果在多民族人群中的泛化性有待验证。
*   **嵌入模型简单**：使用的是较为基础的 Word2Vec 模型，未探索更先进的医疗大模型（如基于 Transformer 的 BERT 类模型）是否能进一步提升性能。
*   **外部验证**：目前仅在 UKBB 单一数据源上进行了验证，跨医院系统、跨生物样本库的迁移能力（Portability）尚不明确。
*   **计算开销**：基于采样的经验 P 值计算在处理超大规模基因组数据时可能存在计算瓶颈。

（完）
