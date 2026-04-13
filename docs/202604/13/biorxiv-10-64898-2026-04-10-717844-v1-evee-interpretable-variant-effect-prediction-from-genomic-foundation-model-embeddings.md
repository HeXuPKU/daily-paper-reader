---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异致病性预测的基因组基础模型
tldr: 本研究提出EVEE，利用70亿参数的基因组基础模型Evo 2的嵌入表示，实现了高精度且可解释的遗传变异致病性预测。通过在Evo 2嵌入上训练分类器，EVEE在ClinVar数据集上达到了SOTA性能，并能零样本泛化至插入缺失变异。此外，该工具结合监督注释探针与推理模型，为变异影响提供自然语言解释，为基因组医学提供了统一的预测与解释框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC heatmap for Evo 2 covariance probe, Evo 2 mean probe, Evo 2 loss, CADD v1.7, AlphaMissense, GPN-MSA, NTv3, and AlphaGenome composite on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC for Evo 2 covariance probe, Evo 2 mean probe, CADD v1.7, and NTv3 probe on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier for Evo 2 probes, AlphaMissense, CADD v1.7, Evo 2 loss, and GPN-MSA. Evo 2 probes and AlphaMissense maintain performance across all bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Methods compared: CADD, AlphaMissense, Evo 2 loss, ClinVar-trained mean-pooled probe (ClinVar probe), ClinVar-trained covariance probe (ClinVar cov probe), DMS-trained mean-pooled probe from held-out genes (DMS probe), and DMS covariance probe (DMS cov probe). Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into natural-language explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 918, \"height\": 987}]"
motivation: 旨在解决基因组医学中大量遗传变异临床意义不明的问题，提升变异致病性预测的准确性与可解释性。
method: 基于Evo 2基础模型的嵌入表示训练分类探针，并结合监督注释探针与大语言模型生成自然语言解释。
result: 在ClinVar变异预测中达到0.997的AUROC，在插入缺失变异上表现优异，并成功应用于多个关键基因的深度突变扫描数据。
conclusion: 证明了基因组基础模型可以作为变异效应预测和机制解释的统一基础，将可解释性从权衡转变为生物结构的互补产物。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义未明的变异。在本文中，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在单一框架下支持对各种变异类型进行准确且可解释的致病性预测。一种在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.9 万个 ClinVar 变异上总体 AUROC 达到 0.997），并能零样本泛化到插入缺失（AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产底物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo 2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or "probe", trained on Evo 2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 839k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2 million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

以下是对论文《EVEE: Interpretable variant effect prediction from genomic foundation model embeddings》的结构化深入总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：在基因组医学中，大量观察到的遗传变异被归类为“意义未明变异”（VUS），缺乏临床解释。现有的预测工具要么准确性不足，要么是“黑盒”模型，无法提供生物学上的解释。
*   **研究背景**：虽然蛋白质语言模型（如 AlphaMissense）在编码区表现优异，但在非编码区和插入缺失（Indels）变异上能力有限。
*   **整体含义**：本研究旨在利用大规模基因组基础模型（Evo 2）的深度表示，构建一个统一的框架 EVEE，既能实现跨变异类型（SNV、Indel）的高精度致病性预测，又能通过自然语言提供可理解的生物学机制解释。

### 2. 论文提出的方法论
*   **核心思想**：利用 70 亿参数的基因组基础模型 **Evo 2** 生成的嵌入（Embeddings）作为特征，通过轻量级的“探针”（Probes）实现分类和解释。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：处理参考序列和突变序列的嵌入差异。它计算序列维度上的压缩协方差矩阵，通过线性层输出致病性概率。这种设计能捕捉序列内的长程依赖关系。
    *   **监督注释探针（Supervised Annotation Probes）**：在 Evo 2 嵌入上训练了 357 个二元分类器，用于预测多种生物学注释（如剪接位点、蛋白质结构域、转录因子结合位点等）。
    *   **可解释性合成（LLM-based Synthesis）**：计算变异引起的注释预测变化（破坏概况），并将其输入大语言模型（如 Claude 3.5/4.6），生成关于变异如何影响生物功能的自然语言解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 833,970 个单核苷酸变异（SNV）和 73,961 个插入缺失变异（Indels）。
    *   **DMS（深度突变扫描）**：针对 BRCA1、BRCA2、TP53 和 LDLR 等关键基因的功能性读数。
*   **Benchmark 与对比方法**：
    *   对比了 **CADD v1.7**（生物信息学元预测器）、**AlphaMissense**（蛋白质模型）、**GPN-MSA**、**NTv3**（核苷酸变异模型）以及 **Evo 2 原始损失函数**。
*   **评估指标**：AUROC（受试者工作特征曲线下面积）、Spearman 相关系数（用于 DMS 数据）。

### 4. 资源与算力
*   **模型规模**：使用了 70 亿参数（7B）的 Evo 2 模型。
*   **算力说明**：论文摘要和核心内容中**未明确说明**具体的 GPU 型号、数量或训练总时长。但考虑到 7B 参数模型的推理和大规模探针训练，通常需要高性能计算集群（如 A100 或 H100 显卡）。

### 5. 实验数量与充分性
*   **实验规模**：实验涵盖了超过 90 万个临床变异，数据量巨大。
*   **充分性**：
    *   **跨类型验证**：不仅测试了 SNV，还验证了对 Indels 的零样本泛化能力。
    *   **稳健性测试**：在不同进化保守性水平（phyloP100way）下进行了分层评估。
    *   **外部验证**：通过 DMS 实验验证了模型在连续功能读数上的预测能力，而非仅仅依赖二元临床标签。
    *   **解释性评估**：采用“LLM-as-a-judge”方法，将生成的解释与 ClinVar 专家评审摘要进行对比，评估其准确性和特异性。

### 6. 论文的主要结论与发现
*   **性能领先**：EVEE 在 ClinVar SNV 预测上达到了 **0.997 的 AUROC**，显著优于现有所有方法。
*   **强大的泛化力**：在未见过的 Indels 变异上表现极佳（AUROC 0.991），证明了基础模型捕捉到了通用的基因组语法。
*   **解释的有效性**：通过注释破坏概况，模型能够准确识别变异对剪接、蛋白质结构域等具体生物过程的影响，生成的自然语言解释在生物学准确性上得到了验证。
*   **统一框架**：证明了基因组基础模型可以作为变异预测和机制解释的统一基质。

### 7. 优点
*   **多功能性**：一个模型处理所有变异类型（编码/非编码，SNV/Indel），无需为特定任务定制架构。
*   **可解释性突破**：将复杂的模型内部状态转化为人类可读的生物学逻辑，弥合了 AI 预测与临床决策之间的鸿沟。
*   **零样本能力**：对 Indels 的处理不需要专门的微调，展示了基础模型的涌现能力。

### 8. 不足与局限
*   **基因长度限制**：实验主要针对长度 $\le$ 100 kb 的基因，对于超长基因的处理能力尚待验证。
*   **LLM 风险**：尽管使用了推理模型，但自然语言生成仍存在“幻觉”风险，需要结合原始注释数据进行校验。
*   **数据偏差**：模型训练依赖于 ClinVar 标注，可能继承了现有数据库中的标注偏差。
*   **计算成本**：运行 7B 参数模型进行实时解释和预测对本地部署的硬件要求较高。

（完）
