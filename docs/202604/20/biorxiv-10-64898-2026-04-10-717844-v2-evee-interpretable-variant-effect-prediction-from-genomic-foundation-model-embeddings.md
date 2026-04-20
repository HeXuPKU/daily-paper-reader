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
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异（VUS）。在此，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels，AUROC 为 0.991），优于生物信息学元预测因子、蛋白质模型以及现有的基础模型方法。其性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的补充产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

以下是对论文《EVEE: Interpretable variant effect prediction from genomic foundation model embeddings》的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
临床基因组学面临的主要瓶颈是遗传变异的解释，目前大多数观察到的变异被标记为“意义不明的变异”（VUS）。现有的预测工具存在局限性：蛋白质模型（如 AlphaMissense）仅限于错义变异；非编码模型（如 AlphaGenome）侧重于调节效应；而元预测因子（如 CADD）虽然覆盖面广，但其复杂的特征整合过程导致预测结果像“黑盒”一样不可解释。本研究旨在利用基因组基础模型 **Evo 2** 的强大表征能力，构建一个统一的框架 **EVEE**，既能实现跨变异类型（SNV 和 Indel）的高精度致病性预测，又能生成人类可读的生物学机制解释。

### 2. 方法论
*   **核心思想**：利用预训练的 70 亿参数模型 Evo 2 提取 DNA 序列的嵌入表示（Embeddings），通过在其上训练轻量级的“探针”（Probes）来提取生物学信息。
*   **协方差探针（Covariance Probe）**：
    *   不同于传统的均值池化（Mean-pooling），该方法计算嵌入矩阵的 Gram 矩阵（$X^\top X$），捕捉维度间的二阶相关性和序列沿线的特征共现。
    *   为了降低维度，使用了线性下投影技术，将高维矩阵压缩后输入线性分类器预测致病性。
*   **注释破坏框架（Annotation-Disruption Framework）**：
    *   在 Evo 2 的参考序列嵌入上训练了 357 个监督注释探针，涵盖蛋白质结构、调节标记、结构域、翻译后修饰等。
    *   通过计算变异序列与参考序列在这些注释预测上的差异（$\Delta$），生成“破坏概况”（Disruption Profile）。
*   **LLM 合成解释**：将前 10 个最显著的破坏信号、变异元数据（基因名、后果类型等）输入前沿推理模型（如 Claude 3.5/3.6），生成结构化的自然语言解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV 和 7.4 万个插入缺失（Indel）。
    *   **DMS（深度突变扫描）**：BRCA1、BRCA2、TP53 和 LDLR 的实验功能数据，用于验证模型的生物学泛化能力。
*   **Benchmark 与对比方法**：
    *   对比了 CADD v1.7、AlphaMissense、GPN-MSA、Nucleotide Transformer v3 (NTv3)、AlphaGenome 以及基于 Evo 2 损失值的零样本预测。
    *   使用了“去混淆”（Deconfounded）基准，通过平衡不同后果类型的标签，防止模型仅通过变异类型（如无义变异通常致病）来“刷分”。
*   **评估指标**：AUROC（致病性分类）、Spearman 相关系数（DMS 相关性）、LLM-as-judge（解释质量评分）。

### 4. 资源与算力
*   **算力消耗**：论文明确提到，提取 420 万个变异的嵌入表示消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的嵌入数据集大小约为 **34 TB**（存储为 bf16 格式）。
*   **训练细节**：探针训练相对轻量，使用了 Muon 优化器，在 8 个分片上进行单轮（1 epoch）训练。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了 ClinVar 全量变异的预测，并针对 SNV 的 7 种后果类型和 Indel 的不同长度/类型进行了细分评估。
*   **充分性**：
    *   进行了**消融实验**，验证了窗口大小、存储策略和模型层数对性能的影响。
    *   通过 **DMS 外部验证** 证明了模型不仅记住了 ClinVar 标签，还捕捉到了真实的生物功能。
    *   引入了 **LLM-as-judge** 机制，由独立的大模型根据专家评审证据对生成的解释进行多维度评分，实验设计较为客观、严谨。

### 6. 主要结论与发现
*   **性能领先**：Evo 2 协方差探针在 SNV 预测上达到了 **0.997 AUROC**，在 Indel 上实现了 **0.991 AUROC** 的零样本泛化性能，全面超越现有工具。
*   **稳健性**：该方法在不同进化保守水平的位点上表现稳定，而传统方法在极高或极低保守区域性能会下降。
*   **可解释性突破**：通过注释破坏信号，LLM 能够准确识别如剪接位点丢失、结构域截断或关键氨基酸柔性改变等分子机制。
*   **统一基质**：证明了基因组基础模型的内部表示足以作为变异预测和机制解释的统一基础。

### 7. 优点
*   **全基因组覆盖**：一个框架同时处理编码和非编码、SNV 和 Indel 变异。
*   **高精度与可解释性并存**：打破了以往“准确模型不可解释，可解释模型不准确”的僵局。
*   **零样本迁移能力**：仅在 SNV 上训练的探针能极好地预测 Indel，显示了模型捕捉到了深层的序列破坏规律。
*   **社区贡献**：提供了 EVEE 在线交互资源，方便研究者查询 420 万个变异的详细解释。

### 8. 不足与局限
*   **多基因效应限制**：Evo 2 基于进化先验，可能更擅长检测强效的孟德尔致病变异，而对效应微弱的复杂多基因变异敏感度可能不足。
*   **注释依赖性**：目前的解释框架依赖于已知的生物学注释，对于全新的、尚未被定义的分子机制，该监督方法可能无法捕捉。
*   **LLM 幻觉风险**：虽然经过评估，但 LLM 生成的解释仍应视为“假设”，在临床决策中仍需专家审核。
*   **算力门槛**：提取大规模嵌入表示的算力成本极高，普通实验室难以复现全量数据的特征提取过程。

（完）
