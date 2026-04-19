---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异效应预测和致病性分析的基因组基础模型
tldr: 针对基因变异临床意义预测中存在的大量“意义不明变异”挑战，本研究提出了EVEE框架。该框架利用拥有70亿参数的基因组基础模型Evo 2的嵌入表示，通过训练嵌入分类器实现了对单核苷酸变异和插入缺失的高精度致病性预测。EVEE不仅在性能上超越了现有元预测器和蛋白质模型，还通过监督注释探针和推理模型生成自然语言解释，实现了预测结果的高度可解释性，并为ClinVar中的420万个变异提供了在线资源。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v3/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance matrix along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier. Evo 2 probes and AlphaMissense maintain performance across bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v3/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into naturallanguage explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 925, \"height\": 893}]"
motivation: 旨在解决基因组医学中大量遗传变异临床意义不明的问题，提升变异致病性预测的准确性与可解释性。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与大语言模型生成自然语言解释。
result: 在ClinVar数据集上，SNV预测AUROC达到0.997，indel零样本预测AUROC达0.991，性能全面超越现有主流模型。
conclusion: 基因组基础模型的表征可作为统一基质，同时实现高精度变异效应预测与机制性解释，消除了计算基因组学中性能与可解释性的权衡。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异（VUS）。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异（SNV）后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels）（AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

### 论文总结：EVEE —— 基于基因组基础模型嵌入的可解释变异效应预测

#### 1. 论文的核心问题与整体含义
*   **研究动机**：临床基因组学面临的主要瓶颈是“意义不明变异”（VUS）的大量存在。现有的计算预测工具（如 AlphaMissense、CADD）存在局限性：要么仅限于错义变异，要么缺乏透明度，无法提供符合临床指南（如 ACMG/AMP）要求的机制性解释。
*   **核心问题**：如何利用大规模基因组基础模型（GFM）的内部表示，构建一个既能覆盖多种变异类型（SNV、Indel、非编码区），又能提供人类可读解释的统一预测框架。

#### 2. 论文提出的方法论
*   **核心思想**：利用 70 亿参数的基因组基础模型 **Evo 2** 的嵌入表示（Embeddings）作为生物学特征的统一基质，通过轻量级的“探针”（Probes）实现预测与解释。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：不同于传统的均值池化（Mean-pooling），该方法计算嵌入矩阵的 Gram 矩阵（$X^\top X$），捕捉维度间的二阶相关性和序列中的稀疏特征。为了降低计算量，采用了线性下投影压缩技术。
    *   **注释破坏框架（Annotation-Disruption Framework）**：在 Evo 2 参考序列嵌入上训练 357 种监督注释探针（涵盖蛋白质结构、结构域、调控标记等）。通过计算变异序列与参考序列之间的预测差异（$\Delta$），量化变异对特定生物学功能的破坏程度。
    *   **LLM 解释合成**：将得分最高的破坏特征（Disruption Profile）连同变异元数据输入前沿大语言模型（如 Claude 3.5/4.6），生成结构化的自然语言解释。

#### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV 和 7.4 万个插入缺失（Indels）。
    *   **DMS（深度突变扫描）**：针对 BRCA1、BRCA2、TP53 和 LDLR 四个基因的实验功能数据。
*   **Benchmark 与对比方法**：
    *   **对比模型**：AlphaMissense（蛋白质模型）、CADD v1.7（元预测器）、GPN-MSA（进化模型）、Nucleotide Transformer v3 (NTv3)、AlphaGenome。
    *   **评估指标**：AUROC（用于致病性分类）、Spearman 相关系数（用于 DMS 功能评分相关性）。
    *   **公平性处理**：采用了分层评估（按后果类型分层）和“去混淆”基准（平衡致病与良性标签），防止模型仅通过学习后果类型先验（如无义变异通常致病）来刷分。

#### 4. 资源与算力
*   **算力消耗**：论文明确提到，提取 420 万个变异的嵌入数据消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的中间数据集（包含参考/变异序列的双向嵌入）大小约为 **34 TB**。
*   **模型规模**：核心模型 Evo 2 拥有 70 亿（7B）参数。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了 ClinVar 全量变异的预测、跨变异类型（错义、同义、无义、剪接、内含子、UTR 等）的细分评估、Indel 的零样本泛化实验、以及四个关键基因的 DMS 迁移实验。
*   **充分性与客观性**：
    *   进行了**消融实验**（如上下文窗口大小、存储策略、池化方式对比）。
    *   使用了 **LLM-as-judge** 方法，通过 154 个专家评审的 ClinVar 变异对生成的解释进行了盲测评估。
    *   实验设计考虑了基因水平的 Hold-out 交叉验证，确保测试集基因未出现在训练中，实验结果较为客观、公平。

#### 6. 论文的主要结论与发现
*   **性能领先**：Evo 2 协方差探针在 SNV 致病性预测上达到 0.997 AUROC，全面超越现有 SOTA 模型。
*   **强大的泛化力**：仅在 SNV 上训练的探针能**零样本（Zero-shot）**准确预测 Indel 的致病性（0.991 AUROC）。
*   **稳健性**：在不同进化保守水平下性能保持稳定，而传统基于注释的方法在极高或极低保守区域性能会下降。
*   **可解释性突破**：证明了基础模型的内部表示确实编码了丰富的生物学注释，通过 LLM 合成的解释在机制覆盖度和生物学准确性上得到了专家证据的验证。

#### 7. 优点
*   **统一性**：一个框架解决了编码区、非编码区、SNV 和 Indel 的预测问题，无需为不同变异类型切换模型。
*   **高性能与可解释性的结合**：打破了“黑盒模型性能高但不可解释”的固有印象，将可解释性转化为模型学习到的生物结构的直接产物。
*   **社区贡献**：提供了 **EVEE 交互式 Web 资源**，预计算了 420 万个变异的得分和解释，具有极高的实用价值。

#### 8. 不足与局限
*   **多基因效应限制**：Evo 2 基于进化先验，可能对效应微弱、不产生明显进化特征的复杂多基因疾病变异敏感度较低。
*   **监督偏置**：注释探针依赖于已知的生物学标注，对于全新的、尚未被人类定义的致病机制可能无法捕捉。
*   **LLM 风险**：尽管经过验证，LLM 生成的解释仍存在“幻觉”风险，在临床决策中必须作为假设而非最终诊断依据。
*   **算力门槛**：虽然推理和探针训练较快，但基础模型的预训练和大规模嵌入提取需要极高的算力资源。

（完）
