---
title: "LAMBDA: A Prophage Detection Benchmark for Genomic Language Models"
title_zh: LAMBDA：用于基因组语言模型的前噬菌体检测基准
authors: "Lindsey, L. M., Pershing, N. L., Dufault-Thompson, K., Gwak, H.-j., Habib, A., Schindler, A., Rakheja, A., Round, J., Stephens, W. Z., Blaschke, A. J., Sundar, H., Jiang, X."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.26.714501v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基因组语言模型的基准测试
tldr: 针对基因组语言模型在预测能力上落后于蛋白质模型的现状，本文提出了 LAMBDA 基准测试。该基准通过噬菌体-细菌序列区分任务，从探测、微调、诊断和全基因组原噬菌体检测四个维度评估模型。研究揭示了训练数据质量优于模型规模的重要性，并强调了领域特定训练的必要性，为微生物学和医学中的基因组注释提供了重要工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-26-714501-v1/fig-001.webp\", \"caption\": \"Fig. 1. Overview of the LAMBDA benchmark for evaluating genomic language models. Models are trained on bacteria and phage genome segments (GTDB and INPHARED) and evaluated across three complementary axes: (i) embedding strength using linear probes and a shallow neural network over frozen embeddings, (ii) peak performance via fine-tuning, and (iii) diagnostic tests to determine sources of error (false positive/negative rates, GC bias, and PHROG-based functional analysis). Genome-wide evaluation is performed by using the pre-trained models to scan complete bacterial assemblies with overlapping windows, producing raw predictions that are subsequently filtered to identify high-confidence prophage regions.\", \"page\": 2, \"index\": 1, \"width\": 1028, \"height\": 408}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-26-714501-v1/fig-002.webp\", \"caption\": \"Table 5. Comparison of genomic language models with traditional prophage detection tools. Models are evaluated on genome-wide prophage detection and ranked by Matthews Correlation Coefficient (MCC). Shaded rows indicate genomic language models (gLMs) fine-tuned for prophage detection (blue); a protein language model-based approach (pink) is included for reference. Traditional tools (unshaded) represent current state-of-the-art methods for prophage identification.\", \"page\": 7, \"index\": 2, \"width\": 571, \"height\": 377}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-26-714501-v1/fig-003.webp\", \"caption\": \"Table 2. Linear Probe and 3-Layer Neural Network Classification Results (MCC)\", \"page\": 4, \"index\": 3, \"width\": 528, \"height\": 464}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-26-714501-v1/fig-004.webp\", \"caption\": \"Table 4. Phage gene detection sensitivity stratified by PHROG functional categories across genomic language models. PHROG (Phage Orthologous Groups) categories represent curated functional groupings of phage genes based on sequence homology. Evaluation is performed on a fully annotated phage dataset, where each gene is assigned to a PHROG category. “% of Total” indicates the fraction of annotated phage genes belonging to each category in this dataset. Sensitivity is defined as the fraction of annotated phage genes in each category that the model correctly identifies as phage. Results are reported for six models, with categories ordered by average sensitivity across models (highest to lowest).\", \"page\": 5, \"index\": 4, \"width\": 883, \"height\": 383}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-26-714501-v1/fig-005.webp\", \"caption\": \"Table 3. Detailed performance of genomic language models across fragment-level diagnostic tests and genome-wide prophage detection in the LAMBDA benchmark. Fragment classification metrics assess model bias and error modes using GC-bias (Matthews correlation coefficient, MCC, on nucleotide-shuffled sequences that preserve GC composition; ideal≈ 0), false positive rate (FPR; bacteria-only), and false negative rate (FNR; phage-only). Peak MCC denotes the maximum MCC achieved on the full fragment classification test set. Genome-wide evaluation is performed by scanning complete bacterial genomes with overlapping windows to generate per-segment predictions. “Raw” results correspond to unprocessed predictions at a fixed threshold (0.5). “Filtered” results apply postprocessing, including per-genome z-score normalization, bidirectional smoothing, density-based clustering, and size filtering, to identify contiguous prophage regions. Genome-wide FPR, recall, and MCC are computed at the region level and macro-averaged across genomes.\", \"page\": 5, \"index\": 5, \"width\": 946, \"height\": 498}]"
motivation: 现有的 DNA 语言模型基准主要集中在真核生物调控元件，缺乏对全基因组序列特征学习能力的评估。
method: 提出 LAMBDA 基准，通过四个复杂程度递增的类别评估模型对噬菌体与细菌序列的辨别能力。
result: 分析表明训练数据的质量比模型规模更关键，且领域特定的训练对于提升基因组语言模型的性能至关重要。
conclusion: LAMBDA 为细菌基因组注释提供了极具挑战性的任务，并为利用语言模型解决微生物学中的原噬菌体检测问题提供了新见解。
---

## 摘要
基于 Transformer 的基因组序列模型代表了计算生物学的一个新兴前沿。然而，它们的嵌入（embeddings）尚未表现出与自然语言和蛋白质语言模型相同水平的预测能力，这表明当前实现与理论前景之间存在差距。现有的 DNA 语言模型基准主要集中在真核基因组中调控元件的分类，留下了一个基本问题：这些模型是否学习了全基因组范围内的序列级特征。我们推出了 LAMBDA，这是一个旨在通过噬菌体-细菌序列区分，在四个复杂度递增的类别中严格评估基因组语言模型嵌入的基准：探测任务（probing tasks）、微调评估、诊断测试和全基因组前噬菌体检测。我们对当前基因组语言模型的全面分析，为训练数据质量相对于模型规模的重要性、领域特定训练的必要性以及基因组语言模型在检测前噬菌体序列中的应用提供了新的见解。该基准代表了细菌领域中一项具有挑战性的基因组注释任务，并解决了一个与微生物学和医学直接相关的关键计算问题。

## Abstract
Transformer-based genomic sequence models represent an emerging frontier in computational biology. Yet, their embeddings have not yet shown the same level of predictive power as natural and protein language models, indicating a gap between current implementations and theoretical promise. Existing benchmarks for DNA language models primarily focus on classifying regulatory elements in eukaryotic genomes, leaving open the fundamental question of whether these models learn sequence-level features across whole genomes. We introduce LAMBDA, a benchmark designed to rigorously evaluate genome language model embeddings through phage-bacteria sequence discrimination across four categories of increasing complexity: probing tasks, fine-tuning assessments, diagnostic tests, and genome-wide prophage detection. Our comprehensive analysis of current genomic language models provides novel insights into the importance of training data quality relative to model size, the need for domain-specific training, and the application of genomic language models for detecting prophage sequences. This benchmark represents a challenging genomic annotation task in the bacterial domain and addresses a key computational problem with direct relevance to microbiology and medicine.

---

## 论文详细总结（自动生成）

以下是对论文《LAMBDA: A Prophage Detection Benchmark for Genomic Language Models》的结构化深入总结：

### 1. 论文的核心问题与整体含义
*   **研究背景**：尽管基于 Transformer 的基因组语言模型（gLMs）在计算生物学领域迅速发展，但其预测能力尚未达到自然语言模型或蛋白质语言模型的高度。
*   **核心问题**：现有的 DNA 模型基准测试（如针对真核生物调控元件的分类）主要集中在短序列特征上，缺乏对模型是否能学习全基因组范围、复杂序列特征（如区分宿主细菌与整合其中的病毒序列）的评估。
*   **整体含义**：本文提出了 **LAMBDA** 基准，利用“前噬菌体（Prophage）检测”这一具有挑战性的生物学任务，系统性地评估基因组语言模型捕捉复杂基因组结构的能力。

### 2. 论文提出的方法论
LAMBDA 基准通过四个维度对模型进行多层次评估：
*   **线性探测（Linear Probing）**：在冻结模型参数的情况下，使用简单的线性层或浅层神经网络评估嵌入向量（Embeddings）中包含的原始分类信息。
*   **微调评估（Fine-tuning）**：通过全参数微调，测试模型在特定任务上的性能上限。
*   **诊断测试（Diagnostic Tests）**：
    *   **GC 偏好性分析**：检测模型是否仅通过核苷酸组成（GC 含量）而非序列模式来区分序列。
    *   **功能敏感性分析**：利用 PHROG（噬菌体同源组）分类，评估模型对不同功能类别（如裂解、整合、结构蛋白）噬菌体基因的识别能力。
*   **全基因组检测流程**：模拟真实应用场景，使用滑动窗口扫描完整细菌基因组，并结合后处理步骤（Z-score 标准化、双向平滑、密度聚类和大小过滤）来识别连续的前噬菌体区域。

### 3. 实验设计
*   **数据集**：
    *   **细菌序列**：来自 GTDB（基因组分类数据库）。
    *   **噬菌体序列**：来自 INPHARED 数据库。
    *   **全基因组测试**：使用完全注释的细菌组装体进行端到端评估。
*   **对比方法（Benchmark 对象）**：
    *   **基因组语言模型**：包括 Evo、HyenaDNA、Caduceus、DNABERT-2、GPN-MSA、Nucleotide Transformer v2 (NT-v2) 等。
    *   **传统工具与基准**：对比了传统的前噬菌体检测工具（如 PhageFinder, VIBRANT 等）以及基于蛋白质语言模型的方法（如 ProphageD）。

### 4. 资源与算力
*   **算力说明**：论文摘要和提供的文本片段中**未明确说明**具体的 GPU 型号、数量或总训练时长。但考虑到涉及 Evo（7B 参数）和 NT-v2 等大型模型的微调与推理，该研究显然依赖于高性能计算集群。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了多种主流的基因组模型架构（Transformer、状态空间模型 SSM 等），并在片段级别和全基因组级别进行了双重验证。
*   **充分性**：实验设计较为全面，不仅关注准确率（MCC 指标），还通过“核苷酸随机打乱”实验排除了 GC 含量的干扰，并通过 PHROG 功能分类深入探讨了模型“学到了什么”，实验逻辑严密且具有统计学意义。

### 6. 论文的主要结论与发现
*   **数据质量胜过模型规模**：模型在特定领域（如微生物基因组）的训练数据质量比单纯增加参数量更重要。
*   **领域特定训练的必要性**：在细菌和病毒数据上预训练的模型（如 GPN-MSA）在 LAMBDA 任务中表现优异，而主要在真核生物数据上训练的模型表现较弱。
*   **GC 偏好性风险**：许多模型容易受到 GC 含量的误导，在处理 GC 含量异常的序列时假阳性率较高。
*   **gLM 的潜力**：经过微调的 gLM 在前噬菌体检测任务上可以达到甚至超过传统生物信息学工具的水平，展现了端到端基因组注释的前景。

### 7. 优点
*   **生物学意义明确**：将 AI 模型评估与实际的微生物学问题（前噬菌体检测）紧密结合，解决了现有基准过于“人工化”的问题。
*   **多维度评估**：从冻结嵌入到全基因组扫描，提供了从理论表征到实际应用的完整评价链条。
*   **诊断深入**：通过 PHROG 分析和 GC 偏好性测试，揭示了深度学习模型的黑盒机制。

### 8. 不足与局限
*   **领域局限性**：目前主要集中在细菌和噬菌体，尚不清楚该基准的结论是否能直接推广到真核生物的复杂重复序列识别。
*   **计算成本**：全基因组扫描和大型模型微调对计算资源要求极高，限制了普通研究者的复现能力。
*   **后处理依赖**：全基因组检测的性能在很大程度上依赖于人工设计的后处理算法（如聚类和过滤），这可能掩盖了模型本身的某些缺陷。

（完）
