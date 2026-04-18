---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异致病性预测的基因组基础模型
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
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异（VUS）。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels，AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

### 论文总结：EVEE —— 基于基因组基础模型嵌入的可解释变异效应预测

#### 1. 核心问题与整体含义（研究动机和背景）
在基因组医学中，临床解释遗传变异的主要瓶颈在于存在大量“意义不明变异”（VUS）。现有的计算预测工具存在局限性：
*   **覆盖范围有限**：如 AlphaMissense 仅限于错义变异，AlphaGenome 侧重于非编码调控效应。
*   **缺乏可解释性**：元预测器（如 CADD）整合了上百种特征，但其复杂的非线性转换使得预测结果如同“黑盒”，无法提供符合临床指南（如 ACMG/AMP）要求的机制性解释。
*   **研究动机**：利用拥有 70 亿参数的基因组基础模型 **Evo 2** 的强大表征能力，构建一个既能实现跨变异类型（SNV 和 Indel）高精度预测，又能生成人类可读机制解释的统一框架。

#### 2. 方法论：核心思想与技术细节
EVEE 框架的核心由三个部分组成：
*   **协方差探针（Covariance Probe）**：
    *   **核心思想**：不使用传统的均值池化（Mean-pooling），而是计算嵌入矩阵的 Gram 矩阵（$X^\top X$），捕捉模型维度间的二阶结构和序列中的特征共现。
    *   **技术细节**：为了处理高维数据，采用线性下投影将维度压缩至 $h=64$，生成轻量级的线性探针。该探针在 Evo 2 第 27 层的双向嵌入（正义链和反义链拼接）上进行训练。
*   **监督注释探针（Supervised Annotation Probes）**：
    *   在 Evo 2 嵌入上训练了 357 种独立的探针，用于预测蛋白质结构、调控标记、结构域、翻译后修饰等生物学属性。
    *   通过计算变异序列与参考序列之间的预测差异（$\Delta$），生成“破坏概况”（Disruption Profile），量化变异对特定生物功能的干扰。
*   **LLM 解释合成**：
    *   将变异元数据（基因名、HGVS 符号等）与破坏概况中排名前 10 的特征输入大语言模型（如 Claude 4.6）。
    *   LLM 负责将结构化的破坏数据合成为符合逻辑的自然语言解释，描述变异的分子机制。

#### 3. 实验设计：数据集、Benchmark 与对比方法
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV（涵盖错义、无义、剪接、内含子等类型）和 7.4 万个插入缺失（Indel）。
    *   **DMS（深度突变扫描）**：针对 BRCA1、BRCA2、TP53 和 LDLR 四个基因的实验功能数据。
    *   **去混淆基准（Deconfounded Benchmark）**：为了消除变异后果类型（Consequence type）带来的先验偏差，构建了标签平衡的子集。
*   **Benchmark**：AUROC（致病性分类）、Spearman 相关系数（DMS 功能评分相关性）。
*   **对比方法**：AlphaMissense、CADD v1.7、GPN-MSA、Nucleotide Transformer v3 (NTv3)、AlphaGenome 以及 Evo 2 自身的 Loss-based 评分。

#### 4. 资源与算力
*   **算力消耗**：论文明确指出，提取 425 万个变异的嵌入数据消耗了约 **20,000 个 H100 GPU 小时**。
*   **存储规模**：生成的嵌入数据集规模约为 **34 TB**（采用 bf16 格式存储）。
*   **训练细节**：协方差探针使用 Muon 优化器，在 8 个分片上以 512 的批次大小训练 1 个 epoch。

#### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了 ClinVar 全量变异的预测、针对不同后果类型的分层评估、Indel 的零样本泛化实验、跨保守水平的稳健性测试，以及在四个独立基因上的 DMS 迁移实验。
*   **充分性与公平性**：
    *   采用了**基因水平的留出法（Gene-holdout）**进行交叉验证，确保训练集和测试集无基因重叠。
    *   特别设计了“去混淆基准”，证明了模型性能并非依赖于简单的后果类型先验（如“无义变异通常致病”），而是真正学习到了变异层面的判别特征。
    *   使用了 LLM-as-judge 方法，通过 154 个专家评审变异对生成的解释进行了多维度（机制覆盖度、准确性、特异性）的量化评估。

#### 6. 主要结论与发现
*   **性能领先**：Evo 2 协方差探针在 SNV 预测上达到 0.997 AUROC，在 Indel 零样本泛化上达到 0.991 AUROC，全面超越现有工具。
*   **跨领域泛化**：模型在 Indel 上的表现证明其捕捉到了通用的序列破坏原则；在 DMS 数据上的高相关性证明其表征超出了简单的临床标签拟合。
*   **可解释性突破**：通过注释破坏概况，LLM 能够准确识别如“剪接受体丢失”、“激酶结构域破坏”或“信号肽丢失”等具体机制，且解释质量随上下文信息的增加而显著提升。

#### 7. 优点：亮点总结
*   **统一框架**：一个模型同时处理编码与非编码、SNV 与 Indel，解决了变异类型覆盖不全的问题。
*   **二阶特征提取**：引入协方差池化（Covariance pooling），相比传统的均值池化，能更有效地提取基础模型中的复杂生物学结构。
*   **实用的解释生成**：将抽象的向量差异转化为具体的生物学语言，极大地降低了临床医生理解 AI 预测结果的门槛。
*   **社区贡献**：提供了 EVEE 在线资源，预计算了 420 万个变异的预测结果。

#### 8. 不足与局限
*   **多基因效应限制**：Evo 2 基于进化先验，可能对效应微弱、依赖复杂多基因背景的变异（如复杂疾病的风险位点）敏感度不足。
*   **监督注释的局限**：解释能力受限于预定义的 357 种注释探针，对于全新的、尚未被标注的分子机制可能无法识别。
*   **LLM 幻觉风险**：尽管评估表现良好，但 LLM 生成的解释仍可能包含错误，必须作为“假设”而非最终临床证据，需专家审核。
*   **算力门槛**：嵌入提取过程对算力和存储的要求极高，普通研究机构难以复现大规模的嵌入生成过程。

（完）
