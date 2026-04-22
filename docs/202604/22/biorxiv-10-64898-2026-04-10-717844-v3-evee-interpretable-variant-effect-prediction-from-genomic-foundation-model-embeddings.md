---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于可解释变异效应预测的基因组基础模型嵌入
tldr: 本研究提出EVEE框架，利用70亿参数的基因组基础模型Evo 2的嵌入表示，实现了对遗传变异致病性的高精度且可解释的预测。通过在Evo 2嵌入上训练分类器，该方法在ClinVar变异预测中达到SOTA性能，并能零样本泛化至插入缺失变异。此外，研究结合监督注释探针与推理模型，为变异预测提供自然语言解释，并发布了涵盖420万个变异的交互式资源。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v3/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance matrix along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier. Evo 2 probes and AlphaMissense maintain performance across bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v3/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into naturallanguage explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 925, \"height\": 893}]"
motivation: 针对大量遗传变异临床意义不明的挑战，旨在开发一种统一且可解释的变异效应预测框架。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与大语言模型生成自然语言解释。
result: 在ClinVar数据集上，单核苷酸变异预测AUROC达0.997，插入缺失变异零样本预测AUROC达0.991，显著优于现有模型。
conclusion: 基因组基础模型的表征可作为变异效应预测与机制解释的统一基础，将可解释性从权衡转变为生物结构的互补产物。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上达到 0.997 的总 AUROC），并能零样本泛化到插入缺失（0.991 AUROC），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异导致的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作确立了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

以下是对论文《EVEE: Interpretable variant effect prediction from genomic foundation model embeddings》的结构化深入总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：临床基因组学面临的主要瓶颈是变异解释。尽管测序技术飞速发展，但大多数观察到的遗传变异仍被归类为“意义不明的变异”（VUS）。
*   **核心问题**：现有的预测工具存在局限性：要么仅限于特定变异类型（如 AlphaMissense 仅限错义变异），要么缺乏可解释性（如 CADD 整合了百余种特征但过程不透明），无法满足临床指南（如 ACMG/AMP）对“分类证据”而非“孤立评分”的需求。
*   **整体含义**：本研究旨在利用大规模基因组基础模型（Evo 2）的内部表示，构建一个既能实现全基因组、多类型变异高精度预测，又能提供人类可读机制解释的统一框架。

### 2. 论文提出的方法论
*   **核心思想**：将变异效应预测建模为对基因组基础模型嵌入（Embeddings）的“探测（Probing）”，并利用监督学习将抽象的向量转化为具体的生物学功能破坏描述。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：不同于传统的均值池化，该方法计算嵌入矩阵的 Gram 矩阵（$X^\top X$），捕捉模型维度间的二阶结构和序列中的稀疏特征共现。通过线性下投影压缩维度，实现轻量化训练。
    *   **注释破坏框架（Annotation-Disruption Framework）**：在 Evo 2 嵌入上训练 357 个监督探针，预测蛋白质结构、调节标记、结构域、翻译后修饰等生物属性。
    *   **破坏概况（Disruption Profile）**：计算变异序列与参考序列在这些注释探针输出上的差异（$\Delta$），识别变异导致的分子功能丧失或改变。
    *   **LLM 合成解释**：将前 10 个最显著的破坏信号连同变异元数据输入大语言模型（如 Claude 3.5/4.6），生成自然语言形式的致病机制解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV（单核苷酸变异）和 7.4 万个 Indel（插入缺失变异）。
    *   **DMS（深度突变扫描）**：针对 BRCA1、BRCA2、TP53 和 LDLR 四个基因的实验功能数据。
*   **Benchmark 与对比方法**：
    *   **对比方法**：AlphaMissense、CADD (v1.7)、GPN-MSA、Nucleotide Transformer v3 (NTv3)、AlphaGenome。
    *   **评估策略**：按后果类型（错义、无义、剪接、内含子等）分层评估 AUROC；在 Indel 上进行零样本（Zero-shot）泛化测试；使用“去混淆（Deconfounded）”基准消除后果类型先验的影响。

### 4. 资源与算力
*   **算力消耗**：论文明确提到，提取 425 万个变异的嵌入数据消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的嵌入数据集大小约为 **34 TB**（存储为 bf16 格式）。
*   **模型规模**：基于 70 亿参数（7B）的 Evo 2 模型。

### 5. 实验数量与充分性
*   **实验规模**：实验涵盖了 ClinVar 的全量变异（420 万个），并在多个独立数据集（DMS）上进行了验证，实验组数非常充分。
*   **消融与鲁棒性**：
    *   进行了层扫（Layer Sweep）和上下文窗口大小扫频实验。
    *   对比了均值池化与协方差池化的性能差异。
    *   通过 LLM-as-a-judge 方法，对 154 个专家评审变异的解释质量进行了多维度（机制覆盖度、准确性、特异性）的量化评估。
*   **客观性**：采用了基因水平的留出交叉验证（Gene-holdout cross-validation），确保训练集和测试集无基因重叠，避免了过拟合。

### 6. 论文的主要结论与发现
*   **性能领先**：Evo 2 协方差探针在 SNV 预测上达到 0.997 AUROC，在 Indel 零样本预测上达到 0.991 AUROC，全面超越现有 SOTA 模型。
*   **泛化能力强**：仅在 SNV 上训练的探针能完美预测 Indel 的效应，且在不同进化保守水平下表现稳健。
*   **可解释性突破**：证明了基础模型的嵌入空间蕴含丰富的生物学注释信息，通过 LLM 合成的解释在机制覆盖度和特异性上显著优于仅依赖元数据的基准。
*   **统一基质**：基因组基础模型的表示可以同时作为高精度预测和机制解释的统一基础。

### 7. 优点
*   **全能性**：一个框架处理所有变异类型（编码区、非编码区、SNV、Indel），打破了蛋白质模型与基因组模型的界限。
*   **深度解释**：不仅给出致病概率，还能指出具体的生物学破坏（如剪接位点丢失、特定结构域破坏），极具临床参考价值。
*   **交互性资源**：发布了 EVEE 在线工具，预计算了 420 万个变异的结果，对社区贡献巨大。

### 8. 不足与局限
*   **多基因效应限制**：Evo 2 基于进化先验，可能对效应微弱、不产生明显进化特征的复杂多基因疾病变异敏感度较低。
*   **监督注释依赖**：解释框架依赖于已知的生物学注释，对于全新的、尚未被定义的致病机制可能无法捕捉。
*   **LLM 风险**：尽管经过评估，但 LLM 生成的解释仍可能存在幻觉或误导，需专家最终审核。
*   **算力门槛**：提取大规模嵌入的算力需求极高，普通实验室难以复现或扩展到更大规模的变异库。

（完）
