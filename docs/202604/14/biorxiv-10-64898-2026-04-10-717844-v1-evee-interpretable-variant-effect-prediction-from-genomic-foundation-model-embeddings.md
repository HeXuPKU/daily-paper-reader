---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异致病性预测的基因组基础模型
tldr: 本研究提出EVEE，利用70亿参数的基因组基础模型Evo 2的嵌入表示，实现了高精度且可解释的遗传变异致病性预测。通过在Evo 2嵌入上训练分类器，EVEE在ClinVar数据集上达到了SOTA性能，并能零样本泛化至插入缺失变异。此外，该工具结合监督注释探针与推理模型，为变异影响提供自然语言解释，为基因组医学提供了统一的预测与解释框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC heatmap for Evo 2 covariance probe, Evo 2 mean probe, Evo 2 loss, CADD v1.7, AlphaMissense, GPN-MSA, NTv3, and AlphaGenome composite on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC for Evo 2 covariance probe, Evo 2 mean probe, CADD v1.7, and NTv3 probe on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier for Evo 2 probes, AlphaMissense, CADD v1.7, Evo 2 loss, and GPN-MSA. Evo 2 probes and AlphaMissense maintain performance across all bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Methods compared: CADD, AlphaMissense, Evo 2 loss, ClinVar-trained mean-pooled probe (ClinVar probe), ClinVar-trained covariance probe (ClinVar cov probe), DMS-trained mean-pooled probe from held-out genes (DMS probe), and DMS covariance probe (DMS cov probe). Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into natural-language explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 918, \"height\": 987}]"
motivation: 旨在解决基因组医学中大量遗传变异临床意义不明的问题，提升变异致病性预测的准确性与可解释性。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与大语言模型生成自然语言解释。
result: 在ClinVar变异预测中达到0.997的AUROC，在插入缺失变异上表现优异，并成功应用于多个关键基因的深度突变扫描数据。
conclusion: 证明了基因组基础模型可以作为变异效应预测和机制解释的统一基础，将可解释性从权衡转变为生物结构的互补产物。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义未明的变异。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在单一框架下支持对各种变异类型进行准确且可解释的致病性预测。一种在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.9 万个 ClinVar 变异上总体 AUROC 达到 0.997），并能零样本泛化到插入缺失（AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 839k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

这篇论文介绍了 **EVEE**，一个基于 70 亿参数基因组基础模型 **Evo 2** 的遗传变异效应预测与解释框架。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：临床基因组学中，大量观察到的遗传变异被归类为“意义未明变异”（VUS），缺乏准确且可解释的致病性预测工具。
*   **研究背景**：现有的预测工具存在局限性，如 AlphaMissense 仅限于错义变异，CADD 等元预测器虽然覆盖全基因组但其内部逻辑是不透明的“黑箱”，且大多数工具无法提供符合临床指南（如 ACMG/AMP）要求的机制性解释。
*   **整体含义**：本研究旨在利用大规模预训练基因组模型的内部表示（Embeddings），构建一个既能覆盖各类变异（SNV、插入缺失等）又具备自然语言解释能力的统一预测框架。

### 2. 方法论
*   **核心思想**：利用 Evo 2 模型的中间层嵌入表示，通过训练轻量级的“探针”（Probes）来提取生物学特征，并结合大语言模型（LLM）生成解释。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：不同于传统的均值池化（Mean-pooling），该方法计算嵌入矩阵的 Gram 矩阵（$X^T X$），捕捉模型维度间的二阶相关性，从而更精细地描述序列结构的变化。
    *   **监督注释探针（Supervised Annotation Probes）**：在 Evo 2 嵌入上训练了 357 个分类器，用于预测蛋白质结构、调控标记、结构域等生物学属性。
    *   **破坏概况（Disruption Profiling）**：计算变异序列与参考序列在上述注释探针输出上的差异（$\Delta$），量化变异对特定生物功能的破坏程度。
    *   **LLM 合成解释**：将前 10 个最显著的破坏特征连同变异元数据输入前沿推理模型（如 Claude 4.6），生成结构化的自然语言解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV 和 7.4 万个插入缺失（Indels）。
    *   **深度突变扫描（DMS）**：BRCA1、BRCA2、TP53 和 LDLR 四个关键基因的实验功能数据。
    *   **去混淆基准（Deconfounded Benchmark）**：通过平衡各类后果类型的致病/良性标签，消除模型仅靠变异类型（如无义变异通常致病）来“刷分”的偏见。
*   **对比方法**：CADD v1.7、AlphaMissense、GPN-MSA、Nucleotide Transformer v3 (NTv3)、AlphaGenome 以及 Evo 2 自身的似然得分（Loss-based）。

### 4. 资源与算力
*   **算力消耗**：论文明确提到，提取 420 万个变异的嵌入数据消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的嵌入数据集大小约为 **34 TB**（采用 bf16 格式存储）。
*   **模型规模**：核心模型为 Evo 2-7B。

### 5. 实验数量与充分性
*   **实验规模**：
    *   对 83.3 万个 ClinVar 变异进行了全方位的性能评估。
    *   进行了零样本（Zero-shot）泛化实验，验证模型在未训练过的插入缺失变异上的表现。
    *   针对 4 个基因的 DMS 数据进行了迁移学习验证。
    *   **消融实验**：包括层扫（Layer sweep，确定第 27 层效果最好）、上下文窗口大小实验、存储策略实验等。
*   **充分性与客观性**：实验设计非常严谨，特别是引入了“去混淆基准”来应对基因组任务中常见的分布偏见，确保了对比的公平性。

### 6. 主要结论与发现
*   **性能领先**：Evo 2 协方差探针在 ClinVar SNV 预测上达到了 **0.997 的 AUROC**，在所有后果类型（错义、无义、剪接、内含子等）中均优于现有 SOTA 方法。
*   **强大的泛化力**：仅在 SNV 上训练的探针能完美泛化至插入缺失变异（AUROC 0.991），且在不同进化保守水平下表现稳健。
*   **可解释性的突破**：通过注释探针发现，Evo 2 内部表示确实编码了丰富的生物学结构。LLM 生成的解释在机制覆盖率和生物学准确性上得到了高分评价。

### 7. 优点
*   **统一性**：一个模型、一个框架即可处理编码区和非编码区的所有变异类型。
*   **二阶特征提取**：协方差池化技术显著提升了从基础模型中提取功能信息的能力。
*   **实用性**：提供了 EVEE 在线工具，预计算了 420 万个变异，极大方便了社区使用。
*   **透明度**：将“黑箱”嵌入转化为人类可读的生物学属性破坏报告。

### 8. 不足与局限
*   **进化偏见**：Evo 2 基于进化先验，可能对不影响进化适应度但具有临床意义的微小多基因效应（Polygenic effects）不够敏感。
*   **注释限制**：监督探针只能预测已知的生物学注释，对于全新的致病机制可能无法识别。
*   **LLM 风险**：生成的自然语言解释虽然准确度高，但仍存在“幻觉”风险，必须作为专家审核的辅助参考，而非最终临床诊断。
*   **算力门槛**：提取大规模嵌入的成本极高，普通实验室难以复现同等规模的特征提取。

（完）
