---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异致病性预测的基因组基础模型
tldr: 本研究开发了EVEE框架，利用70亿参数的基因组基础模型Evo 2的嵌入表示，实现了高精度且可解释的遗传变异致病性预测。该方法在ClinVar数据集的单核苷酸变异和插入缺失预测上均达到SOTA水平，并能通过监督注释探针和推理模型生成自然语言解释。研究提供了涵盖420万个变异的在线资源，证明了基础模型在统一变异效应预测与机制解释方面的巨大潜力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC heatmap for Evo 2 covariance probe, Evo 2 mean probe, Evo 2 loss, CADD v1.7, AlphaMissense, GPN-MSA, NTv3, and AlphaGenome composite on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC for Evo 2 covariance probe, Evo 2 mean probe, CADD v1.7, and NTv3 probe on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier for Evo 2 probes, AlphaMissense, CADD v1.7, Evo 2 loss, and GPN-MSA. Evo 2 probes and AlphaMissense maintain performance across all bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Methods compared: CADD, AlphaMissense, Evo 2 loss, ClinVar-trained mean-pooled probe (ClinVar probe), ClinVar-trained covariance probe (ClinVar cov probe), DMS-trained mean-pooled probe from held-out genes (DMS probe), and DMS covariance probe (DMS cov probe). Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into natural-language explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 918, \"height\": 987}]"
motivation: 临床医学中大量遗传变异的临床意义尚不明确，亟需一种能统一处理多种变异类型且具备可解释性的高精度预测工具。
method: 基于Evo 2模型的嵌入向量训练分类探针，并结合监督注释探针与大语言模型，将变异导致的生物学破坏转化为自然语言解释。
result: 在83.3万个ClinVar变异上达到0.997的AUROC，且在插入缺失变异的零样本预测中表现优异，全面超越了现有的生物信息学预测器和蛋白质模型。
conclusion: 基因组基础模型的内部表示可作为变异效应预测与机制解释的统一基石，将计算基因组学的可解释性从权衡转变为模型学习能力的互补产物。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异。在此，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。其性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作确立了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo~2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or ``probe'', trained on Evo~2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2~million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **EVEE**（Evo Variant Effect Explorer）的框架，旨在利用大规模基因组基础模型的嵌入表示（Embeddings）来实现高精度且可解释的遗传变异致病性预测。

以下是对该论文的结构化总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：临床基因组学面临的主要瓶颈是大量遗传变异被归类为“意义不明的变异”（VUS）。现有的预测工具存在局限性：要么仅限于蛋白质编码区的错义变异（如 AlphaMissense），要么虽然覆盖全基因组但缺乏可解释性（如 CADD），无法提供符合临床指南（如 ACMG/AMP）要求的机制性证据。
*   **核心目标**：开发一个统一的框架，既能准确预测各类变异（SNV、插入缺失等）的致病性，又能生成人类可读的生物学解释。

### 2. 论文提出的方法论
*   **核心思想**：利用 70 亿参数的基因组基础模型 **Evo 2** 的内部表示作为生物学特征的“统一基质”，通过轻量级的“探针”（Probes）提取信息。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：不同于传统的均值池化（Mean-pooling），该方法计算嵌入矩阵的 Gram 矩阵（$X^\top X$），捕捉模型维度间的二阶结构和序列中的特征共现。为了降低计算量，使用了线性下投影技术。
    *   **监督注释探针（Supervised Annotation Probes）**：在 Evo 2 的参考序列嵌入上训练了 357 个分类器，用于预测蛋白质结构、调控标记、结构域等生物学属性。
    *   **破坏概况（Disruption Profiling）**：通过计算变异序列与参考序列在这些注释探针预测值上的差异（$\Delta$），量化变异对特定生物功能的破坏程度。
    *   **LLM 合成解释**：将得分最高的破坏特征、变异元数据输入前沿推理模型（如 Claude 3.5/4.6），生成自然语言形式的致病机制解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV 和 7.4 万个插入缺失（Indels）。
    *   **深度突变扫描（DMS）**：针对 BRCA1、BRCA2、TP53 和 LDLR 四个关键基因的实验功能数据。
*   **Benchmark 与对比方法**：
    *   对比了 **CADD v1.7**、**AlphaMissense**、**GPN-MSA**、**Nucleotide Transformer v3 (NTv3)** 和 **AlphaGenome**。
    *   使用了**去混淆基准（Deconfounded benchmark）**，通过平衡各类后果类型（如无义、同义）中的致病/良性标签，防止模型仅通过变异类型（Consequence type）来“刷分”。

### 4. 资源与算力
*   **算力消耗**：论文明确提到，提取 420 万个变异的嵌入数据消耗了约 **20,000 个 H100 GPU 小时**。
*   **数据规模**：生成的中间嵌入数据集大小约为 **34 TB**（bf16 格式）。
*   **模型规模**：基于 7B 参数的 Evo 2 模型，探针训练相对轻量（约 50 万参数）。

### 5. 实验数量与充分性
*   **实验规模**：非常充分。涵盖了全基因组范围的 SNV、跨长度的插入缺失（1bp 到 >20bp）、四个独立基因的 DMS 迁移实验。
*   **消融与鲁棒性**：进行了层扫（Layer sweep）、上下文窗口大小扫频、存储策略对比以及针对 LLM 解释质量的“LLM-as-a-judge”评估。
*   **客观性**：通过基因水平的留出法（Gene-holdout cross-validation）确保训练集和测试集无重叠，并使用去混淆数据集验证了模型在排除先验分布干扰下的真实判别能力。

### 6. 论文的主要结论与发现
*   **性能领先**：Evo 2 协方差探针在 ClinVar SNV 上达到 **0.997 AUROC**，在插入缺失上实现 **0.991 AUROC**（零样本泛化），全面超越现有 SOTA。
*   **鲁棒性**：在不同进化保守水平（Conservation levels）下性能保持稳定，而传统方法在极高或极低保守区域表现下降。
*   **可解释性有效**：通过 LLM 合成的解释在机制覆盖范围、生物学准确性和特异性上均表现优异，能够识别如剪接位点破坏、结构域丢失等具体机制。

### 7. 优点
*   **统一性**：一个模型处理所有变异类型，打破了编码区与非编码区预测工具的隔阂。
*   **二阶特征提取**：证明了协方差矩阵比简单的均值池化能捕获更多深层生物学结构信息。
*   **弥合鸿沟**：成功将深度学习的高维嵌入转化为临床医生可理解的自然语言，具有极强的实用价值。

### 8. 不足与局限
*   **监督限制**：注释探针依赖于已知的生物学标注，对于全新的、尚未被人类定义的致病机制可能无法识别。
*   **多基因效应**：Evo 2 基于进化先验，更擅长检测孟德尔遗传病中的强效有害变异，对效应微弱的复杂多基因疾病变异可能不够敏感。
*   **LLM 风险**：尽管经过评估，但 LLM 生成的解释仍存在幻觉风险，必须作为“假设”而非最终临床诊断证据。
*   **算力门槛**：嵌入提取过程对算力要求极高，普通实验室难以复现大规模特征提取。

（完）
