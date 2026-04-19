---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异致病性预测的基因组基础模型
tldr: 针对基因变异临床意义预测中存在的大量“意义不明变异”挑战，本研究提出了EVEE框架。该框架利用拥有70亿参数的基因组基础模型Evo 2的嵌入表示，通过训练分类探针，实现了对单核苷酸变异和插入缺失的高精度致病性预测。此外，EVEE结合监督注释探针与推理模型生成自然语言解释，为420万个ClinVar变异提供可解释的预测结果，实现了准确性与可解释性的统一。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC heatmap for Evo 2 covariance probe, Evo 2 mean probe, Evo 2 loss, CADD v1.7, AlphaMissense, GPN-MSA, NTv3, and AlphaGenome composite on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC for Evo 2 covariance probe, Evo 2 mean probe, CADD v1.7, and NTv3 probe on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier for Evo 2 probes, AlphaMissense, CADD v1.7, Evo 2 loss, and GPN-MSA. Evo 2 probes and AlphaMissense maintain performance across all bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Methods compared: CADD, AlphaMissense, Evo 2 loss, ClinVar-trained mean-pooled probe (ClinVar probe), ClinVar-trained covariance probe (ClinVar cov probe), DMS-trained mean-pooled probe from held-out genes (DMS probe), and DMS covariance probe (DMS cov probe). Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into natural-language explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 918, \"height\": 987}]"
motivation: 旨在解决基因组医学中大量遗传变异临床意义不明的问题，提升变异致病性预测的准确性与可解释性。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与大语言模型生成自然语言解释。
result: 在ClinVar数据集上，SNV预测AUROC达0.997，indel零样本预测AUROC达0.991，性能全面超越现有主流模型。
conclusion: 基因组基础模型的表征可作为统一基质，同时实现高精度的变异效应预测与深度的生物学机制解释。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异（VUS）。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异（SNV）后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels）（AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

这是一份关于论文《EVEE: Interpretable variant effect prediction from genomic foundation model embeddings》的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：在基因组医学中，临床观察到的大多数遗传变异被归类为“意义不明变异”（VUS），缺乏明确的致病性证据。
*   **研究背景**：现有的计算预测工具存在局限性：
    *   **覆盖范围窄**：如 AlphaMissense 仅限错义变异，AlphaGenome 侧重非编码调控区。
    *   **缺乏可解释性**：如 CADD 等元预测器整合了上百种特征，输出的是黑盒评分，无法提供符合临床指南（如 ACMG/AMP）要求的机制性解释。
*   **整体含义**：本研究旨在利用 70 亿参数的基因组基础模型 **Evo 2** 的内部表示（Embeddings），构建一个既能高精度预测各类变异（SNV 和 Indel），又能生成人类可读解释的统一框架 **EVEE**。

### 2. 方法论
*   **核心思想**：将变异效应预测转化为对基础模型嵌入表示的“探测”（Probing），并利用监督学习将抽象的向量空间映射到已知的生物学功能。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：不同于传统的平均池化（Mean-pooling），该方法计算嵌入矩阵 $X$ 的 Gram 矩阵 $X^\top X$。这种二阶结构能捕捉模型维度间的相关性及序列沿线的特征共现。为了降低计算量，使用了线性下投影技术。
    *   **双向嵌入**：由于 Evo 2 是自回归模型，研究者拼接了基因正义链和反义链的嵌入以获得双向上下文。
    *   **注释破坏框架（Annotation-disruption Framework）**：
        1.  在 Evo 2 嵌入上训练 357 个监督探针，预测蛋白质结构、调控标记、结构域等生物学属性。
        2.  计算变异序列与参考序列在这些预测值上的差异（$\Delta$），量化变异对特定生物功能的破坏程度。
    *   **LLM 合成解释**：将 Top-10 的破坏特征、变异元数据输入大语言模型（如 Claude 4.6），生成结构化的自然语言解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV 和 7.4 万个插入缺失（Indel）。
    *   **去混杂基准（Deconfounded Benchmark）**：为了消除变异后果类型（如无义变异天然致病率高）带来的先验偏差，构建了标签平衡的子集。
    *   **深度突变扫描（DMS）**：BRCA1、BRCA2、TP53 和 LDLR 四个基因的实验功能数据。
*   **对比方法**：
    *   **蛋白质模型**：AlphaMissense, EVE。
    *   **基因组基础模型**：NTv3, GPN-MSA, AlphaGenome。
    *   **元预测器**：CADD v1.7。
    *   **基准线**：Evo 2 自身的 Loss（似然比）评分。

### 4. 资源与算力
*   **算力消耗**：论文明确提到，提取 425 万个变异的嵌入数据消耗了约 **20,000 H100-GPU 小时**。
*   **数据规模**：生成的嵌入数据集大小约为 **34 TB**（存储为 bf16 格式）。
*   **训练细节**：探针训练使用了 Muon 优化器，在 H100 集群上进行。

### 5. 实验数量与充分性
*   **实验规模**：
    *   进行了全基因组规模的 ClinVar 验证（>80 万变异）。
    *   针对 Indel 进行了零样本（Zero-shot）泛化实验。
    *   进行了层扫描（Layer sweep）消融实验，确定第 27 层嵌入效果最佳。
    *   进行了上下文窗口大小（Context window）的灵敏度分析。
    *   使用 LLM-as-a-judge 对 154 个专家评审变异的解释质量进行了量化评估。
*   **充分性评价**：实验设计非常充分且严谨。通过“去混杂基准”解决了模型可能通过变异类型走捷径的问题，并通过 DMS 独立数据集验证了模型的生物学泛化能力，而非仅仅拟合 ClinVar 标签。

### 6. 主要结论与发现
*   **性能 SOTA**：Evo 2 协方差探针在 SNV 预测上达到 0.997 AUROC，在 Indel 上达到 0.991 AUROC，全面超越现有模型。
*   **零样本泛化**：仅在 SNV 上训练的探针能极好地预测 Indel 的效应，说明模型捕捉到了通用的序列破坏规律。
*   **稳健性**：在进化极度保守和极不保守的区域，EVEE 的表现均优于依赖多序列比对（MSA）的方法。
*   **可解释性价值**：通过 LLM 合成的解释在机制覆盖率、生物学准确性和特异性上得分很高，证明基础模型内部确实编码了复杂的生物学结构。

### 7. 优点
*   **统一性**：一个框架解决所有变异类型（编码/非编码、SNV/Indel），无需为不同任务切换模型。
*   **二阶特征提取**：协方差池化技术显著提升了从基础模型中提取功能信息的能力。
*   **临床友好**：将枯燥的数值评分转化为符合临床逻辑的自然语言证据，极大地提升了实用性。
*   **开源贡献**：提供了 EVEE 在线探索工具，预计算了 420 万个变异的结果。

### 8. 不足与局限
*   **多基因效应限制**：Evo 2 基于进化先验，可能对效应微弱、不影响进化适应度的多基因复杂疾病变异预测不够敏感。
*   **注释依赖**：解释框架仍依赖于已知的生物学注释（如 Pfam 结构域），对于完全未知的全新致病机制，监督探针可能无法捕捉。
*   **LLM 幻觉风险**：尽管经过评估，但 LLM 生成的解释仍可能存在错误，必须作为“假设”而非最终临床诊断依据。
*   **算力门槛**：提取大规模嵌入的算力成本极高，普通实验室难以复现全量数据的提取过程。

（完）
