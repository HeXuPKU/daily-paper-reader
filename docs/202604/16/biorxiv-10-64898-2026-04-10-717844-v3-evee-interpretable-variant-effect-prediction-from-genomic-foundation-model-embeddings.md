---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基于基因组基础模型嵌入的可解释变异效应预测
tldr: 本研究提出EVEE，利用70亿参数的基因组基础模型Evo 2的嵌入表示，实现了高精度且可解释的遗传变异致病性预测。通过在Evo 2嵌入上训练分类器，EVEE在ClinVar数据集的单核苷酸变异和插入缺失预测上均达到SOTA水平，并能通过监督注释探针和推理模型生成自然语言解释，为基因组医学提供了统一的预测与解释框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v3/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance matrix along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier. Evo 2 probes and AlphaMissense maintain performance across bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v3/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into naturallanguage explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 925, \"height\": 893}]"
motivation: 临床中大量遗传变异的致病性尚不明确，亟需一种能统一处理多种变异类型且具备可解释性的高精度预测工具。
method: 基于Evo 2基础模型的嵌入向量训练分类探针，并结合监督注释探针与大语言模型生成变异影响的自然语言解释。
result: 在ClinVar数据集上，SNV预测AUROC达0.997，indel零样本预测达0.991，性能优于现有的元预测器和蛋白质模型。
conclusion: 基因组基础模型的表征可作为变异效应预测与机制解释的统一基础，将可解释性从性能权衡转变为模型的互补产物。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异。在此，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够支持在单一框架下对各种变异类型进行准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上总体 AUROC 为 0.997），并能零样本泛化到插入缺失（indels，AUROC 为 0.991），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。该性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作确立了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo~2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or ``probe'', trained on Evo~2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2~million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

以下是对论文《EVEE: Interpretable variant effect prediction from genomic foundation model embeddings》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
在基因组医学中，准确预测遗传变异（尤其是单核苷酸变异 SNV 和插入缺失 Indel）的临床致病性至关重要。然而，目前临床上观察到的大多数变异仍被归类为“意义不明的变异”（VUS）。
*   **现有挑战**：现有的预测工具通常存在局限性，要么仅针对蛋白质编码区（如 AlphaMissense），要么在处理非编码区或 Indel 时表现不佳，且大多数模型缺乏透明的生物学解释，难以在临床决策中提供说服力。
*   **研究目标**：利用大规模基因组基础模型（Evo 2）的强大表征能力，构建一个统一的框架，既能实现跨变异类型的高精度预测，又能生成人类可读的生物学解释。

### 2. 核心方法论
论文提出了 **EVEE (Evo Variant Effect Explorer)** 框架，其核心技术流程如下：
*   **基础模型嵌入**：利用拥有 70 亿参数的基因组基础模型 **Evo 2**。该模型在海量基因组序列上预训练，能够捕捉复杂的序列依赖关系。
*   **协方差探针 (Covariance Probe)**：
    *   输入参考序列和变异序列，提取每位置的嵌入向量（Embeddings）。
    *   计算两者嵌入差异，通过一个“协方差探针”在序列维度上计算压缩协方差矩阵。
    *   将矩阵展平后通过线性层，输出致病性预测概率。
*   **可解释性框架 (Annotation Disruption Profiling)**：
    *   **监督注释探针**：在 Evo 2 嵌入上训练了 357 个二元分类探针，用于预测多种生物学注释（如剪接位点、蛋白质结构域、外显子-内含子边界等）。
    *   **破坏概况分析**：计算变异前后这些注释预测值的变化（$\Delta$），量化变异对特定生物学功能的影响。
    *   **LLM 综合解释**：将上述“破坏概况”输入前沿大语言模型（如 Claude 4.5/4.6），由其合成自然语言形式的机制解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 833,970 个 SNV 和 73,961 个 Indel，涵盖了不同的临床评价等级（1星至4星）。
    *   **DMS (深度突变扫描)**：针对 BRCA1、BRCA2、TP53 和 LDLR 等关键基因的功能读数数据集。
*   **Benchmark (对比方法)**：
    *   **元预测器**：CADD, REVEL, SpliceAI。
    *   **蛋白质模型**：AlphaMissense, ESM-1b, ESM-2。
    *   **基因组基础模型**：Caduceus, HyenaDNA。
*   **评估指标**：AUROC（用于分类）、Spearman 相关系数（用于 DMS 连续值预测）。

### 4. 资源与算力
*   **模型规模**：使用了 70 亿（7B）参数的 Evo 2 模型。
*   **算力说明**：论文中未明确给出训练这些“探针”的具体 GPU 型号、数量或总训练时长。但考虑到探针通常是基于冻结的基础模型嵌入进行轻量化训练，其算力需求远低于基础模型的预训练。

### 5. 实验数量与充分性
*   **实验规模**：实验涵盖了超过 90 万个临床变异，规模巨大。
*   **多样性**：不仅测试了 SNV，还重点评估了 Indel 的零样本泛化能力，并跨越了不同的进化保守水平（phyloP100way）。
*   **消融与验证**：通过 LLM-as-a-judge 方法，对比了不同规模的 Claude 模型在生成解释方面的表现，并与 ClinVar 专家评审摘要进行了对比验证。实验设计较为全面、客观，涵盖了从预测精度到解释质量的多个维度。

### 6. 主要结论与发现
*   **性能领先**：EVEE 在 ClinVar SNV 预测上达到了 **0.997 的 AUROC**，在 Indel 上达到了 **0.991**，全面超越了 AlphaMissense 和现有的元预测器。
*   **零样本泛化**：尽管主要在 SNV 上训练，模型对 Indel 表现出极强的零样本迁移能力。
*   **稳健性**：在进化保守性极高或极低的区域，EVEE 的表现比基于保守性的传统方法更稳健。
*   **可解释性有效性**：通过注释探针和 LLM 的结合，能够生成与专家共识高度一致的生物学解释，成功将“黑盒”预测转化为可理解的机制描述。

### 7. 优点
*   **统一框架**：一个模型同时处理编码区、非编码区、SNV 和 Indel，打破了以往工具的碎片化。
*   **解释性创新**：不再依赖于简单的特征重要性评分，而是通过“预测破坏”+“LLM 合成”的方式提供具有生物学意义的叙述性解释。
*   **高性能**：利用 7B 参数模型的深层表征，刷新了多项变异效应预测的基准记录。

### 8. 不足与局限
*   **序列长度限制**：目前主要针对长度 $\le 100$ kb 的基因进行评估，对于超长基因或远距离调控元件的处理能力尚待验证。
*   **LLM 风险**：尽管使用了推理模型，但 LLM 在合成解释时仍存在潜在的幻觉风险，需结合原始探针数据进行校验。
*   **数据偏差**：模型训练依赖于 ClinVar 等标注数据集，这些数据集本身可能存在研究偏差（如对某些热门基因的过度表征）。
*   **实时性**：虽然提供了预计算结果，但对于新发现的罕见变异，生成实时解释可能需要一定的计算开销。

（完）
