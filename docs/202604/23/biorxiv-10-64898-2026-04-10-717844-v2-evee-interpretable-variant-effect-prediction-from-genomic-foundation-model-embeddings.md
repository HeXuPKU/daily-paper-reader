---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基因组基础模型用于变异致病性预测
tldr: 针对基因变异临床意义预测中存在的大量不确定性变异难题，本研究提出了EVEE框架。该框架利用70亿参数的基因组基础模型Evo 2的嵌入表示，通过训练分类探针实现了对单核苷酸变异和插入缺失的高精度致病性预测。此外，EVEE结合监督注释探针与大语言模型，为预测结果提供可解释的自然语言说明，并发布了涵盖420万个ClinVar变异的交互式资源。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance matrix along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier. Evo 2 probes and AlphaMissense maintain performance across bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into naturallanguage explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 925, \"height\": 893}]"
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

以下是对论文《EVEE: Interpretable variant effect prediction from genomic foundation model embeddings》的深度结构化总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：在基因组医学中，大量观察到的遗传变异被归类为“意义不明的变异”（VUS），这阻碍了临床诊断和精准医疗。现有的预测工具往往在准确性（如深度学习黑盒模型）与可解释性（如传统的生物信息学评分）之间存在权衡，且难以同时处理单核苷酸变异（SNV）和插入缺失（Indels）。
*   **研究背景**：基因组基础模型（如 Evo 2）通过大规模序列预训练学习了深层的生物学结构。本研究旨在利用这些预训练的嵌入表示（Embeddings），构建一个既能实现最先进预测精度，又能提供人类可读解释的统一框架。

### 2. 论文提出的方法论
EVEE 框架主要由三个核心组件组成：
*   **协方差探针（Covariance Probe）**：
    *   **输入**：Evo 2（70亿参数）生成的参考序列和变异序列的逐位置嵌入。
    *   **处理**：计算两者嵌入的差异，通过一个压缩协方差矩阵捕捉序列维度的交互信息，最后通过线性层输出致病性概率。
*   **监督注释探针（Supervised Annotation Probes）**：
    *   在 Evo 2 嵌入上训练了 357 个二元分类探针，用于预测多种生物学注释（如剪接位点、蛋白质结构域、外显子-内显子边界等）。
    *   通过计算变异前后注释预测值的变化（$\Delta$），量化变异对特定生物功能的“破坏程度”（Disruption Profile）。
*   **LLM 解释合成**：
    *   将上述破坏概况（Disruption Profile）输入前沿大语言模型（如 Claude 4.5/4.6），结合已知生物学背景，生成自然语言形式的机制解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 833,970 个 SNV 和 73,961 个插入缺失（Indels）。
    *   **DMS（深度突变扫描）**：针对 *BRCA1, BRCA2, TP53, LDLR* 等关键基因的功能性读数。
*   **Benchmark 与对比方法**：
    *   **元预测器**：CADD, REVEL。
    *   **蛋白质模型**：AlphaMissense, ESM-1b。
    *   **基因组模型**：Enformer, Caduceus, GPN-MSA。
*   **评估指标**：AUROC（致病性分类）、Spearman 相关系数（DMS 功能预测）、LLM-as-a-judge（解释质量评估）。

### 4. 资源与算力
*   **模型规模**：使用了 7B 参数的 Evo 2 作为基础模型。
*   **算力说明**：论文中未明确给出训练探针的具体 GPU 小时数。但提到探针是基于冻结的基础模型嵌入进行训练的，这种“探针训练”方法通常比全参数微调更节省算力。
*   **资源发布**：发布了 EVEE 在线资源，涵盖 420 万个 ClinVar 变异的预计算结果。

### 5. 实验数量与充分性
*   **实验规模**：实验涵盖了超过 90 万个临床变异，规模巨大。
*   **多样性**：不仅测试了 SNV，还专门评估了模型在 Indels 上的零样本泛化能力，并跨越了不同的进化保守水平（phyloP100way）。
*   **消融与验证**：通过 DMS 数据集验证了模型在连续功能值预测上的迁移能力，并通过专家评审（ClinVar 3星摘要）对比验证了 LLM 生成解释的准确性。实验设计全面且具有较强的客观性。

### 6. 论文的主要结论与发现
*   **性能巅峰**：EVEE 在 ClinVar SNV 预测上达到了 **0.997 的 AUROC**，刷新了 SOTA 记录。
*   **跨类型泛化**：在未见过的 Indels 上表现优异（AUROC 0.991），证明了基础模型对 DNA 结构变化的深刻理解。
*   **稳健性**：在进化不保守的区域，传统方法性能大幅下降，而 EVEE 依然保持高准确度。
*   **可解释性突破**：证明了可以通过探测嵌入空间来提取变异的生物学影响，将“黑盒”预测转化为逻辑清晰的自然语言报告。

### 7. 优点
*   **统一框架**：一个模型同时解决 SNV 和 Indels 的预测，无需针对特定变异类型定制。
*   **高精度与高解释性并存**：通过注释破坏分析，成功解决了深度学习模型难以解释的痛点。
*   **零样本能力**：在处理 Indels 和 DMS 数据时展现出极强的泛化性能。
*   **实用性强**：提供了交互式 Web 工具，直接服务于临床和科研社区。

### 8. 不足与局限
*   **数据偏差风险**：训练主要依赖 ClinVar，可能存在标签泄露或数据分布偏差（如良性变异多分布在非编码区）。
*   **LLM 幻觉风险**：虽然使用了推理模型合成解释，但在处理极罕见变异时，LLM 仍可能产生生物学上的误导性描述。
*   **推理成本**：运行 7B 参数的模型进行大规模变异扫描对本地算力有一定要求。
*   **长程依赖限制**：尽管 Evo 2 支持长序列，但探针预测可能仍受限于局部上下文窗口（如 100kb 限制）。

（完）
