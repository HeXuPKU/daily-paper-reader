---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异效应预测的基因组基础模型
tldr: 针对基因变异临床意义预测中存在的大量不确定性变异难题，本研究提出了EVEE框架。该框架利用70亿参数的基因组基础模型Evo 2的嵌入表示，通过训练分类探针实现了对单核苷酸变异和插入缺失的高精度致病性预测。此外，EVEE结合监督注释探针与大语言模型，为预测结果提供可解释的自然语言说明，并发布了涵盖420万个ClinVar变异的交互式资源。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance matrix along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier. Evo 2 probes and AlphaMissense maintain performance across bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into naturallanguage explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 925, \"height\": 893}]"
motivation: 旨在解决基因组医学中大量遗传变异临床意义不明的问题，提升变异效应预测的准确性与可解释性。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与推理模型生成自然语言解释。
result: 在ClinVar数据集上取得了SOTA性能（AUROC达0.997），且在零样本迁移至插入缺失变异及深度突变扫描数据时表现优异。
conclusion: 证明了基因组基础模型能统一实现高精度预测与机制解释，将可解释性从权衡转变为生物结构学习的互补产物。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异（VUS）。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异（SNV）后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels）（AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

这是一份关于论文《EVEE: Interpretable variant effect prediction from genomic foundation model embeddings》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心挑战**：在基因组医学中，临床变异的解释是主要瓶颈。尽管测序技术飞速发展，但大多数观察到的变异仍被归类为“意义不明的变异”（VUS）。
*   **现有工具局限性**：
    *   **范围受限**：蛋白质模型（如 AlphaMissense）仅限于错义变异；调控模型（如 AlphaGenome）侧重于非编码区。
    *   **黑盒性质**：元预测器（如 CADD）整合了上百种特征，但无法提供人类可读的致病性解释，不符合临床指南（ACMG/AMP）对证据分类的要求。
*   **研究目标**：利用基因组基础模型（Evo 2）的表示能力，构建一个既能跨变异类型（SNV、插入缺失）准确预测，又能提供机制性解释的统一框架。

### 2. 方法论：核心思想与关键技术
*   **基础模型**：使用拥有 70 亿参数的基因组基础模型 **Evo 2**。
*   **协方差探针（Covariance Probe）**：
    *   不同于传统的均值池化（Mean-pooling），研究者提取 Evo 2 第 27 层的嵌入表示，计算参考序列与变异序列嵌入的差异矩阵 $X$。
    *   训练一个基于 **Gram 矩阵 ($X^\top X$)** 的分类器。这种方法能捕捉维度间的二阶结构和序列沿线的特征共现，显著提升了对复杂变异效应的捕捉能力。
*   **可解释性框架（Annotation-Disruption Framework）**：
    *   **监督注释探针**：在 Evo 2 嵌入上预训练了 357 种生物学注释探针（涵盖蛋白质结构、结构域、剪接位点、翻译后修饰等）。
    *   **破坏概况（Disruption Profile）**：量化变异序列相对于参考序列在这些注释预测上的变化（$\Delta$ 值）。
    *   **LLM 合成解释**：将排名前 10 的破坏信号、基因元数据和变异信息输入前沿推理模型（如 Claude 3.5/4.6），生成上下文相关的自然语言解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV 和 7.4 万个插入缺失（Indels）。
    *   **深度突变扫描（DMS）**：针对 BRCA1、BRCA2、TP53 和 LDLR 四个基因的实验功能数据。
    *   **去混淆基准（Deconfounded Benchmark）**：为了防止模型仅通过变异类型（如无义变异通常致病）来“作弊”，构建了平衡致病/良性标签的子集。
*   **对比方法（Baselines）**：
    *   **蛋白质模型**：AlphaMissense, EVE。
    *   **基因组基础模型**：NTv3, GPN-MSA, Evo 2 (loss-based)。
    *   **元预测器/监督模型**：CADD v1.7, AlphaGenome。
*   **评估指标**：AUROC（致病性分类）、Spearman 相关系数（DMS 功能评分相关性）、LLM-as-judge（解释质量评分）。

### 4. 资源与算力
*   **数据提取算力**：提取 420 万个变异的嵌入表示消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的嵌入数据集大小约为 **34 TB**（存储为 bf16 格式）。
*   **探针训练**：协方差探针相对轻量（约 50 万参数），使用 Muon 优化器在单次训练周期（1 epoch）内完成。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了 ClinVar 全量变异（420 万），并在 83 万个带标签变异上进行了详尽测试。
*   **消融与验证**：
    *   进行了层扫（Layer sweep）以确定最佳嵌入层（第 27 层）。
    *   进行了上下文窗口大小的消融实验。
    *   **零样本泛化**：在仅使用 SNV 训练的情况下，直接在插入缺失（Indels）上测试，验证了模型的泛化能力。
*   **客观性**：通过“去混淆基准”和“基因水平留出法（Gene-holdout）”交叉验证，确保模型没有记住特定基因或仅依赖变异类型先验，实验设计严谨、公平。

### 6. 主要结论与发现
*   **性能领先**：Evo 2 协方差探针在 SNV 致病性预测上达到 **0.997 AUROC**，在插入缺失上达到 **0.991 AUROC**，全面超越现有工具。
*   **跨领域泛化**：模型在不同进化保守水平的位点上表现稳健，且能有效迁移至实验性的 DMS 数据集。
*   **可解释性突破**：通过注释破坏概况，LLM 能够准确识别如“剪接接纳位点丢失”、“蛋白质结构域截断”或“激酶活性中心破坏”等具体分子机制。

### 7. 优点
*   **统一性**：一个框架处理所有变异类型（编码/非编码，SNV/Indel），无需为不同任务切换模型。
*   **高精度与可解释性并存**：打破了“性能越高越不可解释”的传统僵局，将深度学习特征转化为生物学语言。
*   **社区贡献**：发布了 **EVEE 交互式 Web 资源**，预计算了 420 万个变异的得分和解释，极具实用价值。

### 8. 不足与局限
*   **进化先验偏差**：Evo 2 基于进化约束训练，可能对不影响进化适应度但影响人类复杂疾病的微效多基因变异（Polygenic effects）敏感度较低。
*   **注释依赖**：目前的解释框架受限于已知的 357 种注释，对于全新的、尚未被人类定义的分子机制，该监督方法无法捕捉。
*   **LLM 幻觉风险**：尽管经过评估，但 LLM 生成的解释仍应视为“假设”，在临床决策中仍需专家审核。
*   **算力门槛**：提取大规模基因组嵌入的计算成本极高，普通研究机构难以复现全量特征提取。

（完）
