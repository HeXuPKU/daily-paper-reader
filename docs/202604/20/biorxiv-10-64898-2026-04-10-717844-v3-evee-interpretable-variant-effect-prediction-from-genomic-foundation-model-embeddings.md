---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异效应预测的基因组基础模型
tldr: 针对基因变异临床意义预测中存在的大量不确定性变异难题，本研究提出了EVEE框架。该框架利用70亿参数的基因组基础模型Evo 2的嵌入表示，通过训练分类探针实现了对单核苷酸变异和插入缺失的高精度致病性预测。此外，EVEE结合监督注释探针与推理模型，能生成自然语言解释，为420万个ClinVar变异提供了兼具准确性与可解释性的预测资源。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v3/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance matrix along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier. Evo 2 probes and AlphaMissense maintain performance across bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v3/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into naturallanguage explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 925, \"height\": 893}]"
motivation: 旨在解决基因组医学中大量遗传变异临床意义不明的问题，提升变异致病性预测的准确性与可解释性。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与大语言模型生成变异影响的自然语言解释。
result: 在ClinVar数据集上取得了SOTA性能（AUROC达0.997），且在插入缺失预测和深度突变扫描任务中表现优异。
conclusion: 证明了基因组基础模型能作为统一表征，将高精度变异预测与机械论解释相结合，重塑了计算基因组学的可解释性范式。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异（VUS）。在此，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异（SNV）后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels）（AUROC 为 0.991），优于生物信息学元预测因子、蛋白质模型以及现有的基础模型方法。其性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的补充产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **EVEE**（Evo Variant Effect Explorer）的框架，旨在利用大规模基因组基础模型的表征能力，解决临床遗传变异解释中的准确性与可解释性难题。

以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心挑战**：临床基因组学面临“意义不明变异”（VUS）泛滥的瓶颈。虽然已有多种预测工具，但存在以下局限：
    *   **覆盖范围窄**：如 AlphaMissense 仅限于错义变异，AlphaGenome 侧重非编码调控。
    *   **缺乏可解释性**：如 CADD 等元预测因子整合了上百种特征，输出的是难以理解的黑盒评分，不符合临床指南（ACMG/AMP）对证据分类的要求。
*   **研究动机**：探索 70 亿参数的基因组基础模型 **Evo 2** 是否能作为一个统一的基质，同时提供跨变异类型的高精度预测和人类可读的生物学解释。

### 2. 方法论：核心思想与关键技术
*   **嵌入提取**：使用 Evo 2（第 27 层）提取参考序列和变异序列的嵌入表示。
*   **协方差探针（Covariance Probe）**：
    *   **核心思想**：不使用简单的均值池化，而是计算嵌入矩阵的 **Gram 矩阵（$X^\top X$）**，以捕捉维度间的二阶相关性和序列中的稀疏特征共现。
    *   **技术细节**：通过线性下投影将高维矩阵压缩，训练轻量级的线性分类器预测致病性。
*   **可解释性框架（Annotation-Disruption Framework）**：
    *   **监督注释探针**：在 Evo 2 嵌入上训练 357 个探针，预测蛋白质结构、结构域、调控标记、剪接位点等生物学属性。
    *   **破坏概况（Disruption Profile）**：计算变异序列与参考序列在这些注释预测上的差异（$\Delta$），量化变异对特定生物功能的破坏程度。
*   **LLM 合成解释**：将变异元数据与前 10 个最显著的破坏信号输入大语言模型（如 Claude 3.5/4.6），生成结构化的自然语言解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV（单核苷酸变异）和 7.4 万个 Indel（插入缺失）。
    *   **DMS（深度突变扫描）**：BRCA1、BRCA2、TP53 和 LDLR 的实验功能数据。
*   **Benchmark 与对比方法**：
    *   **对比对象**：AlphaMissense、CADD v1.7、GPN-MSA、Nucleotide Transformer v3 (NTv3)、AlphaGenome 等。
    *   **去混杂基准（Deconfounded Benchmark）**：专门设计了一个平衡了后果类型（Consequence Type）的测试集，防止模型仅通过变异类型（如无义变异通常致病）来“刷分”。
*   **评估指标**：AUROC（致病性分类）、Spearman 相关系数（DMS 连续值预测）、LLM-as-judge（解释质量评分）。

### 4. 资源与算力
*   **算力消耗**：论文明确指出，提取 420 万个 ClinVar 变异的嵌入表示消耗了约 **20,000 H100-GPU 小时**。
*   **数据规模**：生成的嵌入数据集大小约为 **34 TB**（存储为 bf16 格式）。
*   **训练细节**：协方差探针使用 Muon 优化器，在 8 个分片上进行单 epoch 训练。

### 5. 实验数量与充分性
*   **实验规模**：
    *   对 83.3 万个 SNV 进行了分后果类型的详尽评估。
    *   进行了 **零样本（Zero-shot）** 泛化实验，验证了在 SNV 上训练的模型在 Indel 上的表现。
    *   针对 4 个关键致病基因进行了跨数据集的迁移验证。
    *   **消融实验**：包括模型层数选择（Layer Sweep）、上下文窗口大小（Context Window Sweep）、存储策略（Storage Ablation）等。
*   **充分性评价**：实验设计非常充分且严谨。特别是引入了“去混杂基准”，客观地证明了模型性能并非来自简单的统计偏见，而是真正学习到了生物学结构。

### 6. 主要结论与发现
*   **性能领先**：Evo 2 协方差探针在 SNV 预测上达到 **0.997 AUROC**，在 Indel 上达到 **0.991 AUROC**，全面超越现有 SOTA 方法。
*   **稳健性**：在不同进化保守水平（PhyloP 分数）下，EVEE 均保持高性能，而传统方法在极端保守或非保守区域表现下降。
*   **可解释性有效**：通过注释破坏信号，LLM 能够准确识别变异的分子机制（如剪接位点丢失、结构域破坏），解释质量显著优于仅提供元数据的基准。
*   **统一性**：证明了单一的基础模型表示可以处理编码、非编码、SNV 和 Indel 等多种变异任务。

### 7. 优点
*   **多功能性**：一个框架解决了过去需要多个专用工具（蛋白模型 vs 基因组模型）才能覆盖的变异类型。
*   **创新的池化技术**：协方差探针证明了基础模型内部隐藏的二阶结构对于功能预测至关重要。
*   **弥合鸿沟**：成功将高维向量表示转化为临床医生可理解的自然语言，具有极强的实用价值。
*   **社区贡献**：提供了 EVEE 在线交互资源，预计算了 420 万个变异。

### 8. 不足与局限
*   **多基因效应限制**：Evo 2 基于进化先验，可能对效应微弱、依赖复杂多基因背景的变异（如复杂疾病的风险位点）敏感度较低。
*   **注释依赖**：解释框架仍受限于已知的生物学注释，对于全新的、尚未被定义的分子机制可能无法捕捉。
*   **LLM 风险**：虽然 LLM 生成的解释质量很高，但仍存在“幻觉”风险，论文强调这些解释应作为假设而非最终临床诊断。
*   **算力门槛**：提取大规模嵌入的成本极高，普通实验室难以复现完整的嵌入提取过程。

（完）
