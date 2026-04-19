---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异效应预测的基因组基础模型
tldr: 针对基因变异临床意义预测中存在的大量不确定性变异难题，本研究提出了EVEE框架。该框架利用70亿参数的基因组基础模型Evo 2的嵌入表示，通过训练分类探针实现了对单核苷酸变异和插入缺失的高精度致病性预测。此外，EVEE结合监督注释探针与推理模型，能生成自然语言解释，为420万个ClinVar变异提供了兼具准确性与可解释性的预测资源。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance matrix along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier. Evo 2 probes and AlphaMissense maintain performance across bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into naturallanguage explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 925, \"height\": 893}]"
motivation: 旨在解决基因组医学中大量遗传变异临床意义不明的问题，提升变异致病性预测的准确性与可解释性。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与大语言模型生成变异影响的自然语言解释。
result: 在ClinVar数据集上取得了SOTA性能（AUROC达0.997），且在插入缺失预测和深度突变扫描任务中表现优异。
conclusion: 证明了基因组基础模型能作为统一表征，将高精度变异预测与机械论解释相结合，重塑了计算基因组学的可解释性范式。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异（VUS）。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels，AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

### 论文总结：EVEE —— 基于基因组基础模型嵌入的可解释变异效应预测

#### 1. 核心问题与整体含义（研究动机和背景）
临床基因组学面临的主要瓶颈是**遗传变异的临床意义解读**。目前，大多数观察到的变异被归类为“意义不明的变异”（VUS）。现有的计算预测工具存在局限性：
*   **覆盖范围有限**：蛋白质模型（如 AlphaMissense）仅限于错义变异；非编码模型（如 AlphaGenome）侧重于调节效应。
*   **缺乏可解释性**：元预测器（如 CADD）整合了上百种特征，其输出是黑箱式的评分，无法提供符合临床指南（如 ACMG/AMP）要求的机制性解释。
*   **研究动机**：利用拥有 70 亿参数的基因组基础模型 **Evo 2**，构建一个既能实现全基因组变异（包括 SNV 和插入缺失）高精度预测，又能生成人类可读解释的统一框架。

#### 2. 方法论：核心思想与关键技术
EVEE 框架由三个核心组件组成：
*   **协方差探针（Covariance Probe）**：
    *   **核心思想**：不使用传统的均值池化（Mean-pooling），而是计算嵌入矩阵的 Gram 矩阵（$X^\top X$），捕捉模型维度间的二阶结构和序列沿线的特征共现。
    *   **技术细节**：为了处理高维数据，采用线性下投影（Linear Down-projections）将维度压缩（如 $h=64$），在保持轻量化的同时显著提升了对序列破坏的捕捉能力。
*   **监督注释探针（Supervised Annotation Probes）**：
    *   在 Evo 2 的参考序列嵌入上训练了 357 个探针，用于预测蛋白质结构、调节标记、结构域、翻译后修饰等生物学属性。
    *   通过计算变异序列与参考序列在这些属性上的预测差异（$\Delta$），生成“破坏概况”（Disruption Profile）。
*   **LLM 解释合成**：
    *   将变异元数据与前 10 个最显著的破坏信号输入前沿推理模型（如 Claude 3.5/4.6），合成自然语言形式的机制解释。

#### 3. 实验设计：数据集、Benchmark 与对比方法
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV（涵盖错义、无义、剪接、内含子等）和 7.4 万个插入缺失（Indels）。
    *   **DMS（深度突变扫描）**：BRCA1、BRCA2、TP53 和 LDLR 的实验功能数据，用于验证模型的生物学泛化能力。
*   **Benchmark**：采用分层评估（Stratified Evaluation），按变异后果类型和进化保守性（phyloP）进行细分，以避免模型仅学习后果类型先验。
*   **对比方法**：CADD v1.7、AlphaMissense、GPN-MSA、Nucleotide Transformer v3 (NTv3)、AlphaGenome 以及基于 Evo 2 损失值的零样本预测。

#### 4. 资源与算力
*   **算力消耗**：数据提取过程消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的嵌入数据集包含约 425 万个变异，存储格式为 bf16，总容量约为 **34 TB**。
*   **训练细节**：协方差探针使用 Muon 优化器训练，学习率为 0.005，Batch Size 为 4096。

#### 5. 实验数量与充分性
*   **实验规模**：论文进行了大规模的系统性评估，包括：
    *   针对 83 万个 ClinVar 变异的性能测试。
    *   针对插入缺失（Indels）的零样本泛化测试。
    *   针对 4 个关键基因的 DMS 迁移实验。
    *   **消融实验**：包括模型层数选择（Layer Sweep）、上下文窗口大小（Context Window Sweep）、存储策略对比等。
    *   **可解释性评估**：采用“LLM-as-a-judge”方法，对比了 154 个专家评审变异的解释质量。
*   **充分性与公平性**：通过基因水平的留出法（Gene-holdout）防止数据泄露，并使用去混杂（Deconfounded）数据集处理类别不平衡问题，实验设计严谨、客观。

#### 6. 主要结论与发现
*   **SOTA 性能**：Evo 2 协方差探针在 ClinVar SNV 上达到 **0.997 AUROC**，在插入缺失上达到 **0.991 AUROC**，全面超越现有工具。
*   **零样本泛化**：仅在 SNV 上训练的探针能极好地预测插入缺失，证明模型捕捉到了通用的序列破坏原则。
*   **稳健性**：在极高或极低保守性的区域，EVEE 的表现比基于进化的方法更稳健。
*   **可解释性价值**：通过 LLM 合成的解释在机制覆盖、生物学准确性和特异性上表现优异，能够将复杂的嵌入信号转化为临床可用的假设。

#### 7. 优点与亮点
*   **统一框架**：一个模型即可处理编码与非编码、SNV 与 Indel 等多种变异类型。
*   **技术创新**：引入协方差池化（Covariance Pooling），证明了基础模型内部表示的二阶结构蕴含丰富的生物学信息。
*   **实用性强**：提供了 EVEE 在线资源，预计算了 420 万个变异的预测结果，直接服务于研究社区。

#### 8. 不足与局限
*   **注释依赖**：监督注释探针受限于已知的生物学标注，可能无法捕捉全新的致病机制。
*   **多基因效应**：模型基于局部序列和进化先验，对于效应微弱、需累积作用的复杂多基因疾病变异可能校准不足。
*   **LLM 风险**：尽管有证据支持，但 LLM 生成的解释仍存在幻觉风险，需专家最终审核。
*   **算力门槛**：提取大规模嵌入所需的算力极高，普通实验室难以复现完整的数据提取流程。

（完）
