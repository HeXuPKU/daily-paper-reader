---
title: Improving genomic language model reliability under distribution shift
title_zh: 提高基因组语言模型在分布偏移下的可靠性
authors: "Hearne, G., Refahi, M. S., Polikar, R., Rosen, G. L."
date: 2026-03-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.19.712858v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基因组语言模型的可靠性与不确定性
tldr: 基因组语言模型（GLM）在预测任务中表现出色，但在面对未知物种或变异等分布偏移数据时常表现出过度自信，影响可靠性。本研究评估了多种不确定性量化（UQ）方法在GLM中的应用，发现温度缩放和认识神经网络（Epinet）能显著提升模型在分布内和分布外数据上的分类可靠性，为构建更稳健的基因组预测模型提供了参考。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712858-v1/fig-001.webp\", \"caption\": \"Fig 3. Epinet architecture. The base network produces a standard deterministic prediction along with intermediate features (for a transformer, typically a pooled hidden representation). The epinet takes these features together with a random Gaussian sampled epistemic index z and outputs an additive correction to the base prediction, which is applied at the logit level for classification. Repeating inference with different samples of z yields a distribution of predictions.\", \"page\": 6, \"index\": 1, \"width\": 663, \"height\": 435}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712858-v1/fig-002.webp\", \"caption\": \"Fig 5. Regulatory task reliability plots. Left: ID promoter all→promoter all. Right: OOD promoter all→enhancers. Curves plot empirical accuracy versus predicted confidence; the diagonal indicates perfect calibration. Percentage values denote the calculated 50-bin ECE for the respective models. Under shift (right), epinet reduces systematic overconfidence relative to Base, producing a reliability curve closer to the diagonal and lower ECE.\", \"page\": 11, \"index\": 2, \"width\": 783, \"height\": 911}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712858-v1/fig-003.webp\", \"caption\": \"Fig 8. Metagenomic reliability plots at higher taxonomic ranks (DNABERT2). Left column: Near-ID evaluation (id novel genus). Right column: Near-OOD evaluation (ood novel family). Curves plot empirical accuracy versus predicted confidence; the diagonal indicates perfect calibration. Percentage values denote the calculated 50-bin ECE for the respective models Under taxonomic novelty, epinet more closely tracks the diagonal than other methods, indicating improved calibration at both ranks.\", \"page\": 15, \"index\": 3, \"width\": 783, \"height\": 688}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712858-v1/fig-004.webp\", \"caption\": \"Table 1. Genomic language models (GLMs) evaluated in this study.\", \"page\": 3, \"index\": 4, \"width\": 833, \"height\": 440}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712858-v1/fig-005.webp\", \"caption\": \"Table 2. Datasets with BLAST alignment performance. (Hit rate = percentage of test sequences with BLAST alignments, qcov = query coverage, prec. = precision). Higher values indicate stronger sequence similarity between training and test sets. Lower E-val reflects that alignments are statistically significant even across regimes. Based on alignments and biological relation, datasets are assigned as ID, Near-ID, Near-OOD, and OOD categories.\", \"page\": 8, \"index\": 5, \"width\": 794, \"height\": 298}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712858-v1/fig-006.webp\", \"caption\": \"Fig 1. Monte Carlo approximation of the posterior predictive distribution.\", \"page\": 4, \"index\": 6, \"width\": 738, \"height\": 384}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712858-v1/fig-007.webp\", \"caption\": \"Fig 10. Reliability plots for tool-based confidence surrogates versus a GLM baseline. Reliability diagrams for Kraken2 confidence and MMseqs2 similarity surrogates (percent identity and query coverage), compared against the DNABERT2 softmax baseline, under in-distribution (ID) and out-of-distribution (OOD) settings for (A) promoter/enhancer identification, (B) class-level taxonomic classification, and (C) Phylum-level taxonomic classification. Points/bins show empirical accuracy as a function of reported confidence; the dashed diagonal denotes perfect calibration.\", \"page\": 17, \"index\": 7, \"width\": 769, \"height\": 797}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712858-v1/fig-008.webp\", \"caption\": \"Fig 9. CARMANIA OOD detection (∆AUROC vs. Base). Heatmaps report AUROC differences relative to Base (∆ = method − base total) for MC-dropout and epinet uncertainty scores (Total/Aleatoric/Epistemic). Rows correspond to ID→OOD evaluation pairs; columns group MC-dropout and epinet.\", \"page\": 16, \"index\": 8, \"width\": 582, \"height\": 295}]"
motivation: 针对基因组语言模型在处理噪声或未知基因数据时容易产生过度自信预测的问题，探索提升其在分布偏移下可靠性的方法。
method: 在多种GLM架构和基因组预测任务中，对比分析了包括温度缩放和认识神经网络在内的多种不确定性量化方法。
result: 实验表明，温度缩放和认识神经网络能有效改善模型在分布内和分布外数据上的分类可靠性。
conclusion: 通过引入合适的不确定性量化技术，可以显著增强基因组语言模型在应对现实世界复杂基因数据时的稳健性和可信度。
---

## 摘要
基于 Transformer 的基因组语言模型 (GLM) 在多种基因组预测任务中表现出色。然而，它们倾向于产生过度自信的预测——特别是在噪声或陌生数据上——这限制了其可靠性。在基因组学中，未知物种和新变异十分常见，开发对分布偏移具有鲁棒性的模型对于实现可靠预测至关重要。在本文中，我们分析了几种常用及新型不确定性量化 (UQ) 方法在 GLM 背景下的影响，并评估了它们在多种下游基因组和宏基因组预测任务中的表现。通过比较模型在分布内 (ID) 和分布外 (OOD) 数据上的行为，我们证明了温度缩放 (temperature scaling) 和认知神经网络 (epistemic neural networks) 能够提高多种 GLM 架构和领域的分类可靠性。软件代码可在以下地址获取：https://github.com/EESI/glm-epinet-pyt

## Abstract
Transformer-based Genomic Language Models (GLMs) have achieved strong performance across diverse genomic prediction tasks. However, their tendency toward overconfident predictions--particularly on noisy or unfamiliar data--limits reliability. In genomics, where unknown species and novel variants are common, developing models robust to distribution shift is crucial for dependable predictions. Here, we analyze the impact of several common and novel uncertainty quantification (UQ) methods in the context of GLMs, evaluating their performance across diverse downstream genomic and metagenomic prediction tasks. Comparing model behavior on both in-distribution (ID) and out-of-distribution (OOD) data, we show that temperature scaling and epistemic neural networks are capable of improving classification reliability across multiple GLM architectures and domains. The software is available at: https://github.com/EESI/glm-epinet-pyt

---

## 论文详细总结（自动生成）

这是一份关于论文《Improving genomic language model reliability under distribution shift》（提高基因组语言模型在分布偏移下的可靠性）的结构化分析报告：

### 1. 核心问题与整体含义
*   **核心问题**：基因组语言模型（GLMs，如 DNABERT2、HyenaDNA 等）虽然在预测任务中表现优异，但在面对**分布偏移（Distribution Shift）**——即遇到训练集中未见过的物种、新变异或噪声数据时，往往会表现出“过度自信”的错误预测。
*   **研究背景**：在基因组学和宏基因组学中，未知序列是常态。如果模型无法准确评估自身预测的不确定性，其在临床诊断或生物发现中的可靠性将大打折扣。本研究旨在探索如何通过不确定性量化（UQ）技术，让模型在“不知道”时能够诚实地表达“不知道”。

### 2. 论文提出的方法论
论文对比并评估了多种提升模型可靠性的技术，核心思想是区分**偶然不确定性**（数据噪声）和**认知不确定性**（模型知识盲区）：
*   **温度缩放 (Temperature Scaling)**：一种后处理技术，通过在 Softmax 层引入一个可调参数 $T$ 来平滑概率分布，主要用于改善分布内（ID）数据的校准度。
*   **认识神经网络 (Epistemic Neural Networks, Epinet)**：这是本文的重点。它在基础网络（Base Network）旁增加一个轻量级的附加网络。
    *   **机制**：输入基础网络的中间特征和随机采样指数 $z$，输出一个加性修正值作用于 Logits。
    *   **流程**：通过多次采样不同的 $z$，模型可以产生预测分布，从而通过方差等指标衡量认知不确定性。
*   **蒙特卡洛 Dropout (MC-Dropout)**：在推理阶段随机关闭神经元，通过多次前向传播的统计特性来估计不确定性。

### 3. 实验设计
*   **基础模型 (Benchmarks)**：评估了三种主流 GLM 架构：**DNABERT2**（基于 Transformer）、**HyenaDNA**（基于卷积/长序列算子）和 **NT-v2**（Nucleotide Transformer）。
*   **实验任务**：
    1.  **调控元件识别**：区分启动子（Promoters）与增强子（Enhancers）。
    2.  **宏基因组分类**：对不同分类层级（界、门、纲等）的基因序列进行物种分类。
*   **分布偏移设定**：利用 BLAST 比对和分类学距离，将测试集严格划分为：
    *   **ID (In-distribution)**：与训练集高度相似。
    *   **Near-ID / Near-OOD**：中等相似度或近缘物种。
    *   **OOD (Out-of-distribution)**：完全陌生的序列或远缘物种。
*   **对比基准**：除了 GLM 自身，还对比了传统的生物信息学工具如 **Kraken2**（基于 k-mer）和 **MMseqs2**（基于序列比对）。

### 4. 资源与算力
*   **算力说明**：论文中**未明确列出**具体的 GPU 型号、数量或总训练时长。
*   **实现细节**：作者提供了 GitHub 代码库，提到 Epinet 相比于集成模型（Ensembles）具有极低的计算开销，仅在基础模型之上增加了少量参数（约 1-5%），这表明该方法对算力的需求相对友好。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了 3 种不同的模型架构、2 大类核心任务、以及从种到界的多个分类层级。
*   **充分性**：实验设计非常严谨。作者不仅使用了标准的机器学习指标（ECE 校准误差、AUROC），还引入了生物信息学特有的序列相似度分析来定义 OOD。
*   **公平性**：通过在相同的数据分割下对比多种 UQ 方法，并与传统工具进行横向对比，确保了评估的客观性。

### 6. 主要结论与发现
*   **Epinet 表现最优**：在处理 OOD 数据时，Epinet 显著降低了系统性过度自信，其校准曲线最接近理想对角线，且在 OOD 检测任务中表现最稳健。
*   **温度缩放的局限性**：虽然能改善 ID 数据的校准，但在面对严重的分布偏移（OOD）时效果有限。
*   **GLM vs 传统工具**：GLM 在处理陌生序列时往往比传统工具（如 Kraken2）更自信，但这种自信往往是错误的。引入 UQ 后，GLM 的可靠性可以接近甚至在某些场景下超过传统工具的启发式得分。

### 7. 优点
*   **针对性强**：直接解决了基因组 AI 应用中的痛点——分布偏移下的不可信问题。
*   **方法高效**：引入的 Epinet 避免了昂贵的模型集成（Ensemble）开销，适合大规模基因组序列处理。
*   **评估维度全面**：结合了生物学意义（分类学距离）和统计学指标，使结论对生物学家更具说服力。

### 8. 不足与局限
*   **任务覆盖面**：主要集中在分类任务（Classification），未深入探讨回归任务（如预测基因表达水平）中的不确定性。
*   **推理延迟**：虽然 Epinet 比集成模型快，但相比于单次前向传播，多次采样推理（MC sampling）仍会增加一定的计算延迟。
*   **预训练影响**：研究主要关注微调阶段的 UQ，未深入探讨大规模预训练过程本身如何影响模型最终的鲁棒性。

（完）
