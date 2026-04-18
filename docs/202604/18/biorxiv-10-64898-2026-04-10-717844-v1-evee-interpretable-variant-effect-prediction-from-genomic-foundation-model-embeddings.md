---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异致病性预测的基因组基础模型
tldr: 针对基因变异临床意义预测中存在的大量不确定性变异难题，本研究提出了EVEE框架。该框架利用70亿参数的基因组基础模型Evo 2的嵌入表示，通过训练分类探针实现了对单核苷酸变异和插入缺失的高精度致病性预测。此外，EVEE结合监督注释探针与大语言模型，为预测结果提供可解释的自然语言说明，并发布了涵盖420万个ClinVar变异的交互式资源。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC heatmap for Evo 2 covariance probe, Evo 2 mean probe, Evo 2 loss, CADD v1.7, AlphaMissense, GPN-MSA, NTv3, and AlphaGenome composite on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC for Evo 2 covariance probe, Evo 2 mean probe, CADD v1.7, and NTv3 probe on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier for Evo 2 probes, AlphaMissense, CADD v1.7, Evo 2 loss, and GPN-MSA. Evo 2 probes and AlphaMissense maintain performance across all bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Methods compared: CADD, AlphaMissense, Evo 2 loss, ClinVar-trained mean-pooled probe (ClinVar probe), ClinVar-trained covariance probe (ClinVar cov probe), DMS-trained mean-pooled probe from held-out genes (DMS probe), and DMS covariance probe (DMS cov probe). Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into natural-language explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 918, \"height\": 987}]"
motivation: 旨在解决基因组医学中大量遗传变异临床意义不明的问题，提升变异效应预测的准确性与可解释性。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与推理模型生成自然语言解释。
result: 在ClinVar数据集上取得了SOTA性能（AUROC达0.997），且在零样本迁移至插入缺失变异及深度突变扫描数据时表现优异。
conclusion: 证明了基因组基础模型能统一实现高精度预测与机制解释，将可解释性从权衡转变为生物结构学习的互补产物。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异（VUS）。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels，AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

这篇论文介绍了 **EVEE**，一个基于 70 亿参数基因组基础模型 **Evo 2** 的变异效应预测与解释框架。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：临床基因组学中，大部分观察到的遗传变异被归类为“意义不明的变异”（VUS），缺乏准确的致病性预测工具。
*   **研究动机**：现有的预测工具存在局限性：蛋白质模型（如 AlphaMissense）仅限于错义变异；元预测器（如 CADD）虽然覆盖全基因组但黑盒化严重；且所有工具都无法提供符合临床指南（ACMG/AMP）要求的、人类可读的致病机制解释。
*   **整体含义**：本研究旨在利用基础模型的表征能力，构建一个既能实现全变异类型（SNV 和 Indel）高精度预测，又能生成自动化机制解释的统一框架。

### 2. 方法论：核心思想与关键技术
*   **核心思想**：利用 Evo 2 模型的中间层嵌入（Embedding）作为生物信息的“通用底座”，通过轻量级的“探针”（Probes）提取致病性信号和生物学特征。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：不同于传统的均值池化（Mean-pooling），该方法计算嵌入矩阵的 Gram 矩阵（$X^\top X$），捕捉维度间的二阶相关性和序列沿线的稀疏特征。为了降低计算量，使用了线性下投影技术。
    *   **双向嵌入**：连接基因正义链和反义链的嵌入，以获得更全面的上下文。
    *   **可解释性框架**：
        1.  **监督注释探针**：在 Evo 2 嵌入上训练 251 个独立的探针，预测蛋白质结构、调节标记、结构域等已知生物学属性。
        2.  **破坏概况（Disruption Profiling）**：计算变异序列与参考序列在这些注释预测值上的差异（$\Delta$）。
        3.  **LLM 合成**：将前 10 个最显著的破坏特征连同变异元数据输入大语言模型（如 Claude 3.5/4.6），生成自然语言解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV 和 7.4 万个插入缺失（Indel）。
    *   **去混杂基准（Deconfounded Benchmark）**：为了防止模型仅通过变异类型（如无义变异通常致病）来“刷分”，构建了平衡致病/良性标签的子集。
    *   **深度突变扫描（DMS）**：BRCA1、BRCA2、TP53 和 LDLR 四个基因的实验功能数据。
*   **对比方法**：CADD v1.7、AlphaMissense、GPN-MSA、Nucleotide Transformer v3 (NTv3)、AlphaGenome、以及基于 Evo 2 损失值的零样本预测。

### 4. 资源与算力
*   **算力消耗**：论文明确指出，提取 420 万个变异的嵌入数据消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的嵌入数据集约为 **34 TB**。
*   **训练细节**：探针训练使用 Muon 优化器，在 8 个分片上进行单轮（1 epoch）训练，批大小为 512×8。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了从全基因组 SNV 到 Indel 的零样本泛化，再到跨基因的 DMS 迁移实验，实验组数非常庞大。
*   **充分性与公平性**：
    *   采用了**基因水平的留出法（Gene-holdout）**交叉验证，确保训练集和测试集没有基因重叠。
    *   针对 Indel 进行了专门的零样本测试，验证了模型的泛化能力。
    *   使用了“LLM-as-a-judge”方法，对比专家评审文本，客观评估了解释生成的准确性。

### 6. 主要结论与发现
*   **性能领先**：Evo 2 协方差探针在 ClinVar SNV 上达到 **0.997 AUROC**，在 Indel 上达到 **0.991 AUROC**，全面超越现有 SOTA 方法。
*   **零样本泛化**：仅在 SNV 上训练的探针能极好地预测 Indel 的效应，证明模型捕捉到了通用的序列破坏原则。
*   **解释性有效**：通过注释破坏概况，LLM 能够准确识别如剪接位点丢失、结构域破坏等具体机制，解释质量随上下文信息的增加而显著提升。
*   **稳健性**：在不同进化保守水平的位点上，EVEE 均保持高准确度，而传统方法在极高或极低保守区域表现下降。

### 7. 优点
*   **统一性**：一个模型解决所有变异类型，无需为错义、非编码或 Indel 分别建模。
*   **高可解释性**：将“黑盒”嵌入转化为人类可理解的生物学语言，直接辅助临床决策。
*   **实用性**：发布了 **EVEE 交互式 Web 资源**，涵盖 420 万个变异，具有极高的社区价值。
*   **技术创新**：协方差池化方法证明了基础模型高阶特征在基因组任务中的重要性。

### 8. 不足与局限
*   **孟德尔疾病偏向**：模型基于进化先验，更擅长检测强效的致病变异，对效应微弱的复杂多基因疾病变异可能不够敏感。
*   **注释依赖**：可解释性框架受限于已知的 251 个注释类别，可能无法解释全新的、尚未被定义的分子机制。
*   **LLM 幻觉风险**：生成的自然语言解释虽经评估，但仍需专家审核，不能直接作为最终临床证据。
*   **算力门槛**：基础模型嵌入的提取成本极高，普通实验室难以复现大规模特征提取。

（完）
