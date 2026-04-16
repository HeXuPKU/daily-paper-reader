---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异致病性预测的大规模基因组基础模型
tldr: 本研究提出EVEE，利用70亿参数的基因组基础模型Evo 2的嵌入表示，实现了高精度且可解释的遗传变异致病性预测。通过在Evo 2嵌入上训练分类器，EVEE在ClinVar数据集的单核苷酸变异和插入缺失预测上均达到SOTA水平，并能通过监督注释探针和推理模型生成自然语言解释，为基因组医学提供了统一的预测与解释框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC heatmap for Evo 2 covariance probe, Evo 2 mean probe, Evo 2 loss, CADD v1.7, AlphaMissense, GPN-MSA, NTv3, and AlphaGenome composite on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC for Evo 2 covariance probe, Evo 2 mean probe, CADD v1.7, and NTv3 probe on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier for Evo 2 probes, AlphaMissense, CADD v1.7, Evo 2 loss, and GPN-MSA. Evo 2 probes and AlphaMissense maintain performance across all bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Methods compared: CADD, AlphaMissense, Evo 2 loss, ClinVar-trained mean-pooled probe (ClinVar probe), ClinVar-trained covariance probe (ClinVar cov probe), DMS-trained mean-pooled probe from held-out genes (DMS probe), and DMS covariance probe (DMS cov probe). Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v1/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into natural-language explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 918, \"height\": 987}]"
motivation: 临床中大量遗传变异的致病性尚不明确，亟需一种能统一处理多种变异类型且具备可解释性的高精度预测工具。
method: 基于Evo 2基础模型的嵌入向量训练分类探针，并结合监督注释探针与大语言模型生成变异影响的自然语言解释。
result: 在ClinVar数据集上，SNV预测AUROC达0.997，indel零样本预测达0.991，性能优于现有的元预测器和蛋白质模型。
conclusion: 基因组基础模型的表征可作为变异效应预测与机制解释的统一基础，将可解释性从性能权衡转变为生物结构的互补产物。
---

## 摘要
预测遗传变异的临床意义仍然是基因组医学中的一个核心挑战，大多数观察到的变异被归类为意义不明的变异。在此，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上达到 0.997 的总 AUROC），并能零样本泛化至插入缺失（0.991 AUROC），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。其性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后利用前沿推理模型将这些破坏谱合成自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需生成的解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo~2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or ``probe'', trained on Evo~2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2~million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

以下是对论文《EVEE: Interpretable variant effect prediction from genomic foundation model embeddings》的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
在基因组医学中，准确预测遗传变异（尤其是单核苷酸变异 SNV 和插入缺失 Indel）的临床致病性至关重要。然而，目前临床上仍有大量变异被归类为“意义不明的变异”（VUS）。现有的预测工具通常存在以下局限：
*   **碎片化**：不同类型的变异（如编码区 vs 非编码区，SNV vs Indel）往往需要不同的模型。
*   **黑盒化**：高精度的深度学习模型往往缺乏可解释性，医生难以理解预测背后的生物学逻辑。
*   **性能瓶颈**：传统元预测器或蛋白质模型在处理非编码区或复杂变异时表现有限。
**EVEE 的目标**是利用大规模基因组基础模型（Evo 2）的表征能力，构建一个统一、高精度且具备自然语言解释能力的变异效应预测框架。

### 2. 论文提出的方法论
EVEE 的核心基于 **Evo 2**（一个拥有 70 亿参数、基于长上下文架构的基因组基础模型），其方法论分为两个主要部分：
*   **致病性预测（Covariance Probe）**：
    *   输入参考序列（Ref）和变异序列（Alt）到 Evo 2 中获取每一层的嵌入向量（Embeddings）。
    *   计算两者嵌入的差异，并引入一种“协方差探针”（Covariance Probe）。该探针在序列维度上计算压缩协方差，通过线性层捕捉变异对序列长程依赖关系的影响。
*   **可解释性框架（Annotation Disruption Profiling）**：
    *   **监督注释探针**：在 Evo 2 嵌入上预训练 357 个二元分类探针，用于预测多种生物学注释（如剪接位点、蛋白质结构域、外显子-内含子边界等）。
    *   **破坏谱分析**：计算变异前后这些注释预测值的变化（$\Delta$），量化变异对特定生物学功能的破坏程度。
    *   **LLM 合成解释**：将显著的破坏谱数据输入前沿大语言模型（如 Claude 3.5/4.6），生成符合逻辑的自然语言解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 83.3 万个 SNV 和 7.4 万个 Indel（≥1 星评审标准）。
    *   **DMS（深度突变扫描）**：针对 BRCA1、BRCA2、TP53 和 LDLR 基因的功能性实验数据。
*   **Benchmark（对比方法）**：
    *   **元预测器**：CADD v1.7。
    *   **蛋白质模型**：AlphaMissense。
    *   **基因组基础模型**：GPN-MSA、NTv3、AlphaGenome、Evo 2 Loss（零样本）。
*   **评估指标**：AUROC（致病性分类）、Spearman 相关系数（DMS 功能预测）。

### 4. 资源与算力
*   **模型规模**：使用了 7B（70 亿）参数的 Evo 2 模型。
*   **算力细节**：论文摘要和提取文本中未明确给出训练探针的具体 GPU 型号、数量或总时长。但考虑到 Evo 2 本身的规模以及对 83 万个变异进行嵌入提取和探针训练，该研究需要大规模的计算集群支持（通常为 A100 或 H100 级别）。

### 5. 实验数量与充分性
实验设计非常充分且具有多维度：
*   **覆盖面广**：涵盖了 SNV 的各种后果类型（错义、无义、剪接等）以及 Indel。
*   **稳健性测试**：按进化保守性（phyloP100way）分层评估，证明模型在非保守区域依然保持高性能。
*   **泛化性验证**：在 ClinVar 上训练，在完全独立的 DMS 实验数据集上验证。
*   **可解释性评估**：采用“LLM-as-a-judge”方法，将生成的解释与 ClinVar 专家评审摘要进行对比，评估其生物学准确性和特异性。

### 6. 主要结论与发现
*   **性能领先**：EVEE 在 SNV 预测上达到 0.997 AUROC，在 Indel 零样本预测上达到 0.991 AUROC，全面超越 AlphaMissense 和 CADD。
*   **统一框架**：证明了单一的基因组基础模型可以同时处理编码和非编码变异，且无需针对特定变异类型定制架构。
*   **可解释性突破**：通过注释探针，模型能够将抽象的向量差异转化为具体的生物学破坏（如“破坏了剪接供体位点”），并生成高质量的自然语言报告。
*   **保守性无关性**：与依赖进化比对的方法不同，EVEE 在进化不保守的区域表现依然稳健。

### 7. 优点
*   **高精度与通用性**：在处理 Indel 这一传统难点上表现极其出色。
*   **创新的解释机制**：将“预测破坏”与“LLM 合成”结合，弥合了深度学习与临床决策之间的鸿沟。
*   **社区贡献**：提供了 EVEE 在线资源库，包含 420 万个 ClinVar 变异的预计算结果。

### 8. 不足与局限
*   **数据偏差风险**：模型训练依赖 ClinVar 标签，可能继承该数据库现有的标注偏差。
*   **计算成本**：运行 7B 参数的模型进行推理和嵌入提取对本地部署的硬件要求极高。
*   **LLM 幻觉风险**：虽然经过了评估，但 LLM 生成的自然语言解释仍可能存在生物学事实错误，需人工复核。
*   **长程依赖限制**：尽管 Evo 2 支持长上下文，但对于极远距离（如超长增强子）的变异效应预测能力仍需进一步验证。

（完）
