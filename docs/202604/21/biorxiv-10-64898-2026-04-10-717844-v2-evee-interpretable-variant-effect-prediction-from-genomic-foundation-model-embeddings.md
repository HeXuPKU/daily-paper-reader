---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异致病性预测的基因组基础模型
tldr: 针对基因变异临床意义预测中存在的大量不确定性变异难题，本研究提出了EVEE框架。该框架利用70亿参数的基因组基础模型Evo 2的嵌入表示，通过训练分类探针实现了对单核苷酸变异和插入缺失的高精度致病性预测。此外，EVEE结合监督注释探针与大语言模型，为预测结果提供可解释的自然语言说明，并在ClinVar数据集上达到了SOTA性能，为基因组医学提供了强大的交互式工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance matrix along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier. Evo 2 probes and AlphaMissense maintain performance across bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into naturallanguage explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 925, \"height\": 893}]"
motivation: 旨在解决基因组医学中大量遗传变异临床意义不明的问题，提升变异致病性预测的准确性与可解释性。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与推理模型生成自然语言解释。
result: 在ClinVar变异预测中达到SOTA水平（AUROC达0.997），且在插入缺失变异的零样本迁移中表现优异。
conclusion: 证明了基因组基础模型的表征可作为变异效应预测与机制解释的统一基础，消除了计算基因组学中准确性与可解释性的权衡。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异（VUS）。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异（SNV）后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels）（AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

### 论文结构化总结：EVEE —— 基于基因组基础模型嵌入的可解释变异效应预测

#### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：临床遗传变异的解释存在严重瓶颈。尽管测序技术飞速发展，但绝大多数观察到的变异仍被归类为“意义不明的变异”（VUS）。
*   **研究背景**：现有的计算预测工具（如 AlphaMissense、CADD）存在局限性：要么仅限于错义变异，要么是黑箱模型，无法提供符合临床指南（如 ACMG/AMP）要求的、人类可读的致病机制解释。
*   **整体含义**：本研究旨在利用大规模基因组基础模型（Evo 2）的内部表示，构建一个统一的框架，既能实现跨变异类型（SNV 和 Indel）的高精度预测，又能通过自然语言生成变异影响的生物学解释。

#### 2. 方法论
*   **核心思想**：将基因组基础模型的嵌入（Embeddings）作为生物学特征的“统一基质”，通过轻量级的“探针”（Probes）提取致病性信息和生物学注释。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：不同于传统的均值池化，该方法计算嵌入矩阵的 Gram 矩阵（$X^\top X$），捕捉维度间的二阶相关性和序列沿线的特征共现。为了降低计算量，使用了线性下投影（维度 $h=64$）。
    *   **注释-破坏框架（Annotation-Disruption Framework）**：在 Evo 2 的参考序列嵌入上训练 251+ 个监督探针，预测蛋白质结构、调节标记、结构域等。通过计算变异序列与参考序列之间的预测差异（$\Delta$），量化变异对生物学功能的破坏程度。
    *   **LLM 合成解释**：将得分最高的破坏特征（Disruption Profile）连同变异元数据输入前沿推理模型（如 Claude 3.5/4.6），生成结构化的自然语言解释。

#### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV 和 7.4 万个插入缺失（Indels）。
    *   **深度突变扫描（DMS）**：针对 BRCA1、BRCA2、TP53 和 LDLR 四个基因的实验功能数据。
    *   **去混淆基准（Deconfounded Benchmark）**：通过平衡各类后果（Consequence types）中的致病/良性标签，排除模型仅学习“后果先验”的干扰。
*   **对比方法（Benchmarks）**：
    *   元预测器：CADD v1.7。
    *   蛋白质模型：AlphaMissense、EVE。
    *   基因组基础模型：Nucleotide Transformer v3 (NTv3)、GPN-MSA、AlphaGenome、Evo 2（基于损失值的零样本预测）。

#### 4. 资源与算力
*   **算力消耗**：论文明确指出，提取嵌入表示的过程消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的中间数据集（包含 425 万个变异的参考/变异嵌入）大小约为 **34 TB**。
*   **模型规模**：使用了拥有 70 亿参数（7B）的 Evo 2 模型。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了 ClinVar 全量变异的预测，并在多个独立基因的 DMS 数据集上进行了验证。
*   **充分性与公平性**：
    *   采用了**基因水平的留出法（Gene-holdout）**进行交叉验证，确保训练集和测试集没有基因重叠。
    *   针对 Indel 进行了**零样本泛化实验**（仅在 SNV 上训练）。
    *   使用了专门的“去混淆”数据集来验证模型是否真正学到了生物学约束，而非简单的统计相关性。
    *   通过“LLM-as-a-judge”方法，利用专家评审的 ClinVar 证据作为金标准，对解释的可信度进行了量化评估。

#### 6. 主要结论与发现
*   **性能领先**：EVEE 协方差探针在 SNV 预测上达到了 **0.997 AUROC**，在 Indel 零样本预测上达到 **0.991 AUROC**，全面超越现有 SOTA 模型。
*   **稳健性**：在不同进化保守水平（PhyloP 分数）下表现稳定，而传统方法在极高或极低保守区域性能会下降。
*   **可解释性突破**：通过注释破坏概况，LLM 能够准确识别剪接位点丢失、结构域截断或关键残基柔性改变等机制，解释质量显著优于仅提供基因名称的基准配置。

#### 7. 优点
*   **统一性**：一个模型框架同时处理编码区、非编码区、SNV 和 Indel，无需针对特定变异类型切换工具。
*   **二阶特征提取**：协方差池化有效保留了均值池化会丢失的功能信息。
*   **交互式资源**：提供了 EVEE Web 资源，为 420 万个变异提供预计算结果，极大地便利了社区使用。

#### 8. 不足与局限
*   **进化先验偏差**：Evo 2 基于进化约束训练，可能对缺乏进化信号的微效多基因变异（Polygenic effects）敏感度较低。
*   **监督限制**：注释探针仅能识别已知的生物学特征，对于全新的、尚未被定义的致病机制可能无法捕捉。
*   **LLM 风险**：尽管经过评估，LLM 生成的解释仍可能存在幻觉或推测性结论，在临床应用中必须经过专家审核。
*   **算力门槛**：提取大规模嵌入的计算成本极高，普通实验室难以复现完整的嵌入提取流程。

（完）
