---
title: "EVEE: Interpretable variant effect prediction from genomic foundation model embeddings"
title_zh: EVEE：基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Meehl, J., Molnar, C., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Ryu, A., Ayanian, S., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-04-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于变异致病性预测的大规模基因组基础模型
tldr: 本研究提出EVEE，利用70亿参数的基因组基础模型Evo 2的嵌入表示，实现了高精度且可解释的遗传变异致病性预测。通过在Evo 2嵌入上训练分类器，EVEE在ClinVar单核苷酸变异和插入缺失预测上均达到SOTA水平，并能通过监督注释探针和推理模型生成自然语言解释。该工具为420万个ClinVar变异提供了预测和解释，将基因组学的可解释性从权衡转变为互补产物。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-001.webp\", \"caption\": \"Figure 1. Evo 2 covariance probe achieves state-of-the-art variant effect prediction across variant types. (a) Experimental design. Evo 2 processes reference and alternate DNA sequences, producing per-position embeddings. The difference between the embeddings are then input into a covariance probe that is trained to predict pathogenicity. For each input, the covariance probe computes a compressed covariance matrix along the sequence dimension that is flattened and passed through a linear layer to obtain the prediction logits. (b) ClinVar pathogenicity prediction across SNV consequence types. AUROC on 833,970 variants from genes ≤100 kb with ≥1 star review status. Blank cells indicate methods without predictions for that variant type. (c) Zero-shot generalization to indels. AUROC on 73,961 ClinVar indels stratified by consequence type and insertion vs. deletion. (d) Performance robustness across conservation levels. AUROC by phyloP100way conservation tier. Evo 2 probes and AlphaMissense maintain performance across bins, while loss-based and annotation-based approaches show degraded performance at conservation extremes. (e) UMAP of variant covariance embeddings colored by ClinVar pathogenicity label (benign, VUS, pathogenic) for SNVs and indels. (f) UMAP of variant covariance embeddings colored by VEP consequence type, showing organized structure by variant class for both SNVs and indels. (g) DMS generalization. Spearman |ρ| between predicted scores and continuous DMS functional readouts for BRCA1, BRCA2, TP53, and LDLR. Error bars show 95% bootstrap confidence intervals.\", \"page\": 3, \"index\": 1, \"width\": 870, \"height\": 1068}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v2/fig-002.webp\", \"caption\": \"Figure 2. Interpretable predictions through annotation disruption profiling and LLM-based synthesis. (a) Schematic of the interpretability framework. Supervised annotation probes are trained on Evo 2 reference-sequence embeddings to predict a panel of biological annotations. For each variant, disruptions (∆ between variant and reference predictions) are computed across all annotations. Top disruptions are synthesized into naturallanguage explanations by an LLM. (b) Annotation probe performance across annotation categories. Horizontal boxplot with jittered scatter of per-head AUROC values, grouped by annotation category for 357 binary annotation probes. (c, e) Evaluation of variant interpretations using an LLM-as-a-judge approach against ClinVar (≥3 star) expert review summaries. (c) shows composite scores across cumulative context configurations for three Claude model tiers (Haiku 4.5, Sonnet 4.6, Opus 4.6); (e) shows the breakdown by individual criteria: mechanism coverage, biological accuracy, and specificity. Error bars show 95% confidence intervals. (d) Example interpretation for a BRCA1 splice-disrupting intronic variant. Disruption profile showing predicted changes in exon–intron boundaries, splicing donor, zinc finger domain, and variant effect annotations, with LLM-generated natural-language explanation contextualizing the disruption profile against known biology.\", \"page\": 5, \"index\": 2, \"width\": 925, \"height\": 893}]"
motivation: 针对大量临床遗传变异意义不明（VUS）的挑战，旨在开发一种统一且可解释的高精度致病性预测框架。
method: 基于Evo 2基础模型的嵌入训练分类探针，并结合监督注释探针与大语言模型生成自然语言解释。
result: 在ClinVar数据集上，SNV预测AUROC达0.997，Indel零样本预测达0.991，性能优于现有元预测器和蛋白质模型。
conclusion: 基因组基础模型的表征可作为变异效应预测与机制解释的统一基石，实现了预测精度与可解释性的有机结合。
---

## 摘要
预测遗传变异的临床意义仍是基因组医学面临的核心挑战，目前观察到的大多数变异被归类为意义未明的变异。在此，我们展示了来自 Evo 2（一个拥有 70 亿参数的基因组基础模型）的表示，能够在一个统一框架内支持跨变异类型的准确且可解释的致病性预测。在 Evo 2 嵌入上训练的基于嵌入的分类器（或称“探针”）在单核苷酸变异后果类型中实现了最先进的性能（在 83.3 万个 ClinVar 变异上达到 0.997 的总 AUROC），并能零样本泛化到插入缺失（0.991 AUROC），优于生物信息学元预测器、蛋白质模型以及现有的基础模型方法。其性能在不同保守水平下均表现稳健，并可迁移至 BRCA1、BRCA2、TP53 和 LDLR 的深度突变扫描数据集。为了使这些预测具有可解释性，我们训练了监督注释探针来量化每个变异引起的预测破坏，然后使用前沿推理模型将这些破坏概况合成为自然语言解释。我们通过 Evo 变异效应探索器（EVEE）为所有 420 万个 ClinVar 变异提供预计算的预测和按需解释，这是一个面向社区的交互式网络资源。这项工作证明了基因组基础模型的表示可以作为准确变异效应预测和机制解释的统一基质，将计算基因组学中的可解释性从一种权衡重新定义为学习到的生物结构的互补产物。

## Abstract
Predicting the clinical significance of genetic variants remains a central challenge in genomic medicine, with most observed variants classified as variants of uncertain significance. Here we show that representations from Evo~2, a 7-billion-parameter genomic foundation model, support accurate and interpretable pathogenicity prediction across variant types from a single framework. An embedding-based classifier, or ``probe'', trained on Evo~2 embeddings achieves state-of-the-art performance across single nucleotide variant consequence types (0.997 overall AUROC on 833k ClinVar variants) and generalizes zero-shot to indels (0.991 AUROC), outperforming bioinformatic meta-predictors, protein models, and existing foundation model approaches. Performance is robust across conservation levels and transfers to deep mutational scanning datasets for BRCA1, BRCA2, TP53, and LDLR. To make these predictions interpretable, we train supervised annotation probes to quantify predicted disruptions caused by each variant, then synthesize these disruption profiles into natural language explanations using a frontier reasoning model. We provide pre-computed predictions and on-demand explanations for all 4.2~million ClinVar variants through the Evo Variant Effect Explorer (EVEE), an interactive web resource for the community. This work establishes that representations from genomic foundation models can serve as a unified substrate for both accurate variant effect prediction and mechanistic interpretation, reframing interpretability in computational genomics from a trade-off into a complementary product of learned biological structure.

---

## 论文详细总结（自动生成）

这是一份关于论文《EVEE: Interpretable variant effect prediction from genomic foundation model embeddings》的深度结构化总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：临床基因组学面临的主要瓶颈是变异解释。尽管测序技术飞速发展，但绝大多数观察到的遗传变异仍被归类为“意义未明变异”（VUS）。
*   **核心挑战**：现有的计算预测工具存在局限性：蛋白质模型（如 AlphaMissense）仅限于错义变异；元预测器（如 CADD）虽然覆盖全基因组但属于“黑盒”模型，无法提供符合临床指南（如 ACMG/AMP）要求的、人类可读的致病机制解释。
*   **整体含义**：本研究旨在利用大规模基因组基础模型（Evo 2）的内部表示，构建一个统一的框架，既能实现跨变异类型（SNV 和 Indel）的高精度致病性预测，又能生成基于生物学机制的自然语言解释。

### 2. 方法论
*   **核心思想**：利用 70 亿参数的 Evo 2 模型提取 DNA 序列的嵌入表示（Embeddings），通过“协方差探针”捕捉序列特征的二阶结构，并结合“监督注释探针”与大语言模型（LLM）实现可解释性。
*   **关键技术细节**：
    *   **协方差探针（Covariance Probe）**：不同于传统的均值池化（Mean-pooling），该方法计算嵌入矩阵的 Gram 矩阵（$X^T X$），捕捉模型维度间的相关性和沿序列的特征共现。为了降低计算量，采用了低维线性投影技术。
    *   **双向嵌入**：由于 Evo 2 是自回归模型，研究者拼接了基因正义链和反义链的嵌入，以获得完整的上下文信息。
    *   **注释破坏框架**：在 Evo 2 的参考序列嵌入上训练了 357 个监督探针，用于预测蛋白质结构域、剪接位点、翻译后修饰等生物学特征。
    *   **LLM 合成解释**：计算变异序列与参考序列在这些注释上的预测差异（$\Delta$），选取破坏最严重的特征，输入前沿推理模型（如 Claude 3.5/4.6）生成结构化的自然语言解释。

### 3. 实验设计
*   **数据集**：
    *   **ClinVar**：包含 833,970 个 SNV 和 73,961 个插入缺失（Indel）。
    *   **DMS（深度突变扫描）**：BRCA1、BRCA2、TP53 和 LDLR 四个基因的实验功能数据。
*   **Benchmark 与对比方法**：
    *   **对比方法**：AlphaMissense（蛋白质模型）、CADD v1.7（元预测器）、GPN-MSA、Nucleotide Transformer v3 (NTv3)、AlphaGenome 以及基于 Evo 2 损失值的零样本评分。
    *   **评估指标**：AUROC（用于致病性分类）、Spearman 相关系数（用于 DMS 连续分值相关性）。
    *   **去混淆基准**：专门设计了平衡变异后果类型（Consequence type）的测试集，以防止模型仅通过变异类型（如无义突变通常致病）来获取高分。

### 4. 资源与算力
*   **算力消耗**：论文明确指出，提取 420 万个变异的嵌入数据消耗了约 **20,000 H100-GPU 小时**。
*   **数据规模**：生成的嵌入数据集大小约为 **34 TB**（存储为 bf16 格式）。
*   **模型规模**：使用了 7B 参数的 Evo 2 模型，提取的是第 27 层的嵌入表示。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了超过 420 万个 ClinVar 变异的预测，实验设计非常大规模且系统。
*   **充分性与公平性**：
    *   **分层评估**：对错义、无义、同义、剪接、内含子等多种变异后果进行了细分评估。
    *   **零样本泛化**：在仅用 SNV 训练的情况下，测试了对 Indel 的泛化能力。
    *   **消融实验**：对比了均值池化与协方差池化、不同窗口大小、不同模型层数对性能的影响。
    *   **解释质量评估**：采用“LLM-as-a-judge”方法，对比专家提交的 ClinVar 证据，对生成的解释进行了机制覆盖度、准确性和特异性的量化评分。
*   **客观性**：通过“去混淆”实验和基因水平的留出法（Hold-out）交叉验证，确保了评估的客观性，避免了数据泄露。

### 6. 主要结论与发现
*   **性能领先**：EVEE 在 SNV 致病性预测上达到 0.997 AUROC，在 Indel 上达到 0.991 AUROC，全面超越现有 SOTA 工具。
*   **跨领域泛化**：模型在不同进化保守水平的位点上表现稳健，且能有效迁移至实验性的 DMS 数据集。
*   **可解释性突破**：证明了基因组基础模型的内部表示不仅包含预测信息，还编码了丰富的生物学结构。通过 LLM 合成的解释在机制覆盖度和特异性上显著优于仅依赖基因组坐标的基准。
*   **统一框架**：一个模型即可处理编码区、非编码区、SNV 和 Indel，解决了过去工具碎片化的问题。

### 7. 优点
*   **高精度与广覆盖**：在保持极高准确率的同时，覆盖了几乎所有类型的遗传变异。
*   **机制透明化**：将“黑盒”嵌入转化为人类可读的生物学逻辑，极具临床应用潜力。
*   **稳健性**：不依赖于系统发育保守性评分，在快速进化区域依然保持高性能。
*   **社区贡献**：提供了 EVEE 交互式 Web 资源，开放了 420 万个变异的预计算结果。

### 8. 不足与局限
*   **多基因效应限制**：Evo 2 基于局部序列上下文，可能难以捕捉由大量微效变异累积导致的复杂多基因疾病风险。
*   **注释依赖性**：监督探针框架受限于已知的生物学注释，对于全新的、尚未被定义的致病机制可能无法提供详细解释。
*   **LLM 幻觉风险**：尽管经过评估，但 LLM 生成的解释仍可能存在错误，目前只能作为科研假设，不能直接替代临床专家的最终审核。
*   **计算成本**：基础模型的推理和嵌入提取需要极高的算力支持，普通实验室难以独立运行全基因组规模的分析。

（完）
