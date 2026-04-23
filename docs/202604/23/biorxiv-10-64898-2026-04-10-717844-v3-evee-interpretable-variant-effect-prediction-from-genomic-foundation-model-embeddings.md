---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基因组基础模型用于变异致病性预测
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
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异（VUS）。在此，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels，AUROC 为 0.991），优于生物信息学元预测因子、蛋白质模型以及现有的基础模型方法。其性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的补充产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

### 论文总结：EVEE——基于基因组基础模型嵌入的可解释变异效应预测

#### 1. 核心问题与研究动机
*   **核心问题**：临床基因组学中，大量遗传变异被归类为“意义不明的变异”（VUS），缺乏准确且可解释的致病性预测工具。
*   **研究动机**：现有的预测工具存在局限性：蛋白质模型（如 AlphaMissense）仅限于错义变异；元预测因子（如 CADD）虽然覆盖全基因组但属于“黑盒”模型，无法提供符合临床指南（如 ACMG/AMP）要求的机械论解释。本研究旨在利用基因组基础模型（GFM）的表征能力，构建一个既能跨变异类型（SNV、Indel）高精度预测，又能生成人类可读解释的统一框架。

#### 2. 方法论
*   **核心思想**：利用 70 亿参数的基因组基础模型 **Evo 2** 的中间层嵌入（Embedding）作为生物学特征的统一基质，通过轻量级“探针”（Probes）实现预测与解释。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：不同于传统的均值池化（Mean-pooling），该方法计算嵌入矩阵的 Gram 矩阵（$X^\top X$），捕捉维度间的二阶相关性和序列中的稀疏特征。为了降低计算量，采用了线性下投影压缩技术。
    *   **监督注释探针（Supervised Annotation Probes）**：在 Evo 2 嵌入上训练了 357 个分类器，用于预测蛋白质结构、结构域、剪接位点、翻译后修饰等生物学属性。
    *   **破坏概况（Disruption Profiling）**：计算变异序列与参考序列在各注释探针输出上的差异（$\Delta$），识别变异对特定生物功能的破坏。
    *   **LLM 合成解释**：将量化的破坏概况、变异元数据（基因名、HGVS 符号等）输入前沿推理模型（如 Claude 3.5/4.6），生成结构化的自然语言解释。

#### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV 和 7.4 万个插入缺失（Indels）。
    *   **深度突变扫描（DMS）**：针对 BRCA1、BRCA2、TP53 和 LDLR 四个基因的实验功能数据。
    *   **去混淆基准（Deconfounded Benchmark）**：通过平衡各后果类型中的致病/良性标签，消除模型仅学习“后果类型先验”的偏见。
*   **对比方法（Baselines）**：
    *   **生物信息学元预测器**：CADD v1.7。
    *   **蛋白质语言模型**：AlphaMissense、EVE。
    *   **基因组基础模型**：Nucleotide Transformer v3 (NTv3)、GPN-MSA、AlphaGenome、Evo 2 原生 Loss 评分。

#### 4. 资源与算力
*   **算力消耗**：数据提取过程消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的嵌入数据集大小约为 **34 TB**，涵盖 425 万个变异。
*   **训练细节**：协方差探针使用 Muon 优化器，在 8 个分片上以 512 的批次大小训练 1 个 Epoch。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了 ClinVar 全量变异、跨物种保守性分析、Indel 零样本迁移实验、以及四个关键基因的 DMS 验证。
*   **消融实验**：进行了层扫（Layer Sweep）、上下文窗口大小扫（Context Window Sweep）、存储策略消融（Storage Ablation）以及 LLM 解释背景信息的阶梯式消融（Context Stratification）。
*   **客观性**：采用了基因水平的留出交叉验证（Gene-holdout CV），确保训练集和测试集无基因重叠；通过“LLM-as-a-judge”引入双盲评估机制，对比专家评审意见，实验设计较为严谨、公平。

#### 6. 主要结论与发现
*   **性能领先**：Evo 2 协方差探针在 ClinVar SNV 上达到 **0.997 AUROC**，在 Indel 上实现 **0.991 AUROC** 的零样本泛化，全面超越现有 SOTA 方法。
*   **稳健性**：在极高或极低保守性的区域，性能依然保持稳定，而传统基于注释的方法在这些区域表现较差。
*   **可解释性突破**：通过注释破坏概况，LLM 能够准确识别如“剪接接纳位点丢失”、“激酶结构域破坏”等具体分子机制，解释质量随 Evo 2 特征的加入显著提升。

#### 7. 优点
*   **统一框架**：一个模型即可处理编码区、非编码区、SNV 及不同长度的 Indel。
*   **二阶特征提取**：协方差池化有效保留了均值池化会丢失的功能信息。
*   **实用性强**：提供了 EVEE 在线交互资源，为 420 万个变异预计算了结果，极具临床参考价值。

#### 8. 不足与局限
*   **监督偏见**：注释探针依赖于已知的生物学标注，可能无法识别全新的致病机制。
*   **LLM 风险**：尽管有破坏概况约束，LLM 仍存在幻觉风险或对训练数据中已知变异的记忆效应。
*   **复杂效应局限**：对于多基因微效变异（Polygenic effects），由于其演化信号微弱，该方法的敏感性可能受限。
*   **临床应用限制**：生成的解释目前应视为“假设”，仍需专家审核，不能直接替代临床金标准。

（完）
