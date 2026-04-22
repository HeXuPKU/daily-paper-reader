---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异致病性预测的基因组基础模型
tldr: 本研究开发了EVEE，利用70亿参数的基因组基础模型Evo 2的嵌入表示进行基因变异致病性预测。通过在Evo 2嵌入上训练分类器，该方法在ClinVar数据集的单核苷酸变异（AUROC 0.997）和插入缺失变异（AUROC 0.991）预测中均达到SOTA水平，优于现有元预测器和蛋白质模型。此外，EVEE结合监督注释探针与推理模型，为变异影响提供自然语言解释，并推出了涵盖420万个变异的交互式Web资源，实现了高精度与强可解释性的统一。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance matrix along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier. Evo 2 probes and AlphaMissense maintain performance across bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into naturallanguage explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 925, \"height\": 893}]"
motivation: 临床上大量基因变异被归类为意义不明，亟需开发能同时兼顾高预测精度与生物学机制解释性的工具。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与前沿推理模型生成自然语言解释。
result: 在ClinVar和深度突变扫描数据集上表现卓越，SNV预测AUROC达0.997，且能零样本泛化至插入缺失变异。
conclusion: 该工作证明了基因组基础模型可作为变异效应预测与机制解释的统一基质，将可解释性转化为模型学习生物结构的必然产物。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上达到 0.997 的总 AUROC），并能零样本泛化到插入缺失（0.991 AUROC），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。其性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异导致的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作确立了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

这篇论文介绍了 **EVEE**，一个基于基因组基础模型 Evo 2 的变异效应预测与解释框架。以下是对该论文的深度结构化总结：

### 1. 核心问题与研究动机
*   **核心问题**：临床基因组学中，大量遗传变异被归类为“意义不明的变异”（VUS），缺乏准确且可解释的预测工具。
*   **研究动机**：
    *   **现有工具局限性**：蛋白质模型（如 AlphaMissense）仅限错义变异；非编码模型（如 AlphaGenome）侧重调控效应；元预测器（如 CADD）虽覆盖全基因组但黑盒化严重。
    *   **缺乏解释性**：临床指南（ACMG/AMP）要求提供分类证据，而现有模型通常只输出一个不透明的分数，无法解释“为什么”该变异具有致病性。
    *   **基础模型潜力**：大规模预训练的基因组模型（如 Evo 2）学习了丰富的生物结构，但如何将其内部表示转化为准确且人类可读的临床见解尚待研究。

### 2. 方法论
*   **核心思想**：利用 Evo 2 的嵌入表示（Embeddings）作为统一基质，通过“协方差探针”进行高精度预测，并通过“注释破坏概况”结合大语言模型（LLM）生成解释。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：不同于传统的均值池化，该方法计算嵌入矩阵的 Gram 矩阵（$X^\top X$），捕捉维度间的二阶相关性和序列沿线的特征共现。为了降低维度，采用了线性下投影技术。
    *   **双向嵌入**：连接基因正义链和反义链的嵌入，以获得更全面的上下文。
    *   **监督注释探针**：在 Evo 2 嵌入上训练了 357 个分类/回归探针，用于预测蛋白质结构、调控标记、结构域、剪接位点等生物学特性。
    *   **破坏概况（Disruption Profile）**：计算变异序列与参考序列在这些注释探针输出上的差异（$\Delta$），量化变异对特定生物功能的破坏程度。
    *   **LLM 合成解释**：将前 10 个最显著的破坏信号、变异元数据（基因名、HGVS 符号等）输入前沿推理模型（如 Claude 3.5/4.6），生成自然语言形式的机制解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV（单核苷酸变异）和 7.4 万个 Indel（插入缺失）。
    *   **DMS（深度突变扫描）**：针对 BRCA1、BRCA2、TP53 和 LDLR 四个基因的实验功能数据。
    *   **去混杂基准（Deconfounded Benchmark）**：为了防止模型仅通过变异类型（如无义变异通常致病）来“刷分”，构建了平衡致病/良性标签的子集。
*   **对比方法（Baselines）**：
    *   元预测器：CADD v1.7。
    *   蛋白质模型：AlphaMissense、EVE。
    *   基因组基础模型：NTv3、GPN-MSA、AlphaGenome、Evo 2 原生 Loss 评分。

### 4. 资源与算力
*   **算力消耗**：论文明确提到，提取 420 万个变异的嵌入数据消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的中间数据集（包含参考和变异序列的嵌入）大小约为 **34 TB**（采用 bf16 格式存储）。
*   **模型规模**：使用了拥有 70 亿参数（7B）的 Evo 2 模型。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖了 ClinVar 全量变异的预测。
    *   进行了**层扫频（Layer Sweep）**实验，确定第 27 层嵌入效果最佳。
    *   进行了**上下文窗口扫频**，发现 65kb 窗口能捕捉长程效应。
    *   **消融实验**：对比了均值池化与协方差池化、不同存储策略（Top-k vs 连续窗口）的效果。
*   **客观性与公平性**：
    *   采用了**基因级留出法（Gene-holdout）**交叉验证，确保训练集和测试集没有基因重叠。
    *   使用了“LLM-as-a-judge”方法，由独立的大模型根据 ClinVar 专家评审证据对生成的解释进行评分，并设置了 5 级评分准则。

### 6. 主要结论与发现
*   **性能领先**：EVEE 在 SNV 预测上达到 0.997 AUROC，在 Indel 上达到 0.991 AUROC（零样本泛化），全面超越现有 SOTA 工具。
*   **稳健性**：在不同进化保守水平（phyloP 分数）下性能保持稳定，而传统方法在极高或极低保守区域表现下降。
*   **解释性有效**：通过加入 Evo 2 的破坏信号，LLM 生成的解释在机制覆盖度、生物学准确性和特异性上显著提升（复合评分从 1.31 升至 3.80/5）。
*   **统一框架**：证明了单一的基础模型表示可以同时处理编码和非编码、SNV 和 Indel 等多种变异类型。

### 7. 优点
*   **高精度与可解释性并存**：打破了以往“性能越强越黑盒”的僵局。
*   **零样本泛化能力**：仅在 SNV 上训练的探针能极好地预测 Indel，显示模型捕捉到了深层的序列破坏规律。
*   **社区贡献**：推出了 **EVEE 交互式 Web 资源**，预计算了 420 万个变异的预测和解释，极具实用价值。

### 8. 不足与局限
*   **多基因效应限制**：Evo 2 基于进化先验，可能对效应微弱、不留进化痕迹的复杂多基因疾病变异敏感度较低。
*   **监督偏置**：注释探针依赖于已知的生物学标注，可能无法捕捉全新的、尚未被人类定义的致病机制。
*   **LLM 风险**：尽管有证据支持，LLM 生成的解释仍可能存在幻觉，应视为“假设”而非最终临床诊断证据。
*   **算力门槛**：提取大规模嵌入的算力成本极高，普通实验室难以复现全量数据的提取过程。

（完）
