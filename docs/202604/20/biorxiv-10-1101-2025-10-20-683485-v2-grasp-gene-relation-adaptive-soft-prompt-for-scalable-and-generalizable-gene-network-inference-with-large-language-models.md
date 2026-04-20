---
title: "GRASP: Gene-relation adaptive soft prompt for scalable and generalizable gene network inference with large language models"
title_zh: GRASP：用于大语言模型可扩展且泛化基因网络推理的基因关系自适应软提示
authors: "Feng, Y., Deng, K., Guan, Y."
date: 2026-04-14
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.20.683485v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于基因网络推理和生物知识整合的大语言模型
tldr: 基因网络（GN）推理对理解细胞功能至关重要，但现有方法受限于特定背景且大语言模型（LLM）对提示词敏感。本文提出GRASP框架，通过三个虚拟标记构建可训练的软提示，结合基因特定和关系感知组件，将生物上下文映射为紧凑提示。GRASP在多种GN推理任务中表现优异，能有效识别未标注的生物关系，为基于LLM的基因网络推理提供了可扩展且泛化性强的解决方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-20-683485-v2/fig-001.webp\", \"caption\": \"Figure 1. Framework overview. (A) Domain-specific continual pretraining. Approximately 6.3 million gene-related articles were curated from PubMed. Titles and abstracts were extracted to form a gene-focused corpus for continual pretraining. (B) Baseline methods. Few-shot inference relies on\", \"page\": 11, \"index\": 1, \"width\": 848, \"height\": 956}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-20-683485-v2/fig-002.webp\", \"caption\": \"Figure 4. Comparative performance on the kinase-substrate relationship inference. (A)\", \"page\": 14, \"index\": 2, \"width\": 840, \"height\": 545}]"
motivation: 旨在解决大语言模型在基因网络推理中对提示词设计高度敏感，以及现有计算方法难以跨多种交互类型通用化的问题。
method: 引入一种参数高效的GRASP框架，通过分解的基因特定和关系感知组件，利用三个虚拟标记为每对基因生成自适应软提示。
result: 实验表明GRASP在多项推理任务中优于其他提示策略，并能从负样本中识别出未标注的潜在生物相互作用。
conclusion: GRASP证明了通过可训练的软提示可以显著提升大语言模型在基因网络推理中的可扩展性、准确性和泛化能力。
---

## 摘要
基因网络 (GNs) 编码了多种分子关系，是解释细胞功能和疾病的核心。相互作用类型的异质性导致了针对特定网络背景的专门计算方法。大语言模型 (LLMs) 通过利用大规模文本语料库中的生物学知识，为基因网络推理提供了一种统一的、基于语言的表述方式，但其有效性仍对提示词设计较为敏感。在此，我们介绍了基因关系自适应软提示 (GRASP)，这是一个参数高效且可训练的框架，它仅通过三个虚拟标记（virtual tokens）来调节针对每个基因对的推理。通过使用分解的基因特异性和关系感知组件，GRASP 学习将每个基因对的生物学背景映射为紧凑的软提示，这些提示结合了特定于基因对的信号和共享的相互作用模式。在多种基因网络推理任务中，GRASP 的表现始终优于其他提示策略。它还表现出更强的从合成负集中恢复未标注相互作用的能力，这表明它具有识别现有数据库之外具有生物学意义的关系的能力。综上所述，这些结果确立了 GRASP 作为一种用于基于大语言模型的基因网络推理的可扩展且泛化性强的提示框架。

## Abstract
Gene networks (GNs) encode diverse molecular relationships and are central to interpreting cellular function and disease. The heterogeneity of interaction types has led to computational methods specialized for particular network contexts. Large language models (LLMs) offer a unified, language-based formulation of GN inference by leveraging biological knowledge from large-scale text corpora, yet their effectiveness remains sensitive to prompt design. Here, we introduce Gene-Relation Adaptive Soft Prompt (GRASP), a parameter-efficient and trainable framework that conditions inference on each gene pair through only three virtual tokens. Using factorized gene-specific and relation-aware components, GRASP learns to map each pairs biological context into compact soft prompts that combine pair-specific signals with shared interaction patterns. Across diverse GN inference tasks, GRASP consistently outperforms alternative prompting strategies. It also shows a stronger ability to recover unannotated interactions from synthetic negative sets, suggesting its capacity to identify biologically meaningful relationships beyond existing databases. Together, these results establish GRASP as a scalable and generalizable prompting framework for LLM-based GN inference.

---

## 论文详细总结（自动生成）

以下是对论文《GRASP: Gene-relation adaptive soft prompt for scalable and generalizable gene network inference with large language models》的结构化深度总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何利用大语言模型（LLM）中内化的生物学知识，高效且准确地推理复杂的基因网络（如蛋白质相互作用 PPI、基因调控网络 GRN、磷酸化网络等）。
*   **研究背景**：
    *   基因网络具有高度异质性，传统方法通常针对特定任务（如仅针对序列或表达数据）进行设计。
    *   LLM 虽然能统一处理这些任务，但对**提示词（Prompt）设计高度敏感**。
    *   现有的固定提示词（Fixed Prompts）无法捕捉基因对的特异性，而冗长的文本描述（BioContext）可能引入噪声且难以扩展到数百万级别的基因对推理。
*   **整体含义**：提出了一种名为 **GRASP** 的参数高效框架，通过自适应生成软提示（Soft Prompt），在保持模型可扩展性的同时，显著提升了 LLM 在基因网络推理中的泛化能力。

### 2. 论文提出的方法论：GRASP 框架
GRASP 的核心思想是将基因的生物学背景压缩为少量的、针对特定基因对自适应生成的虚拟标记（Virtual Tokens）。
*   **两阶段流程**：
    1.  **基因向量编码**：利用 LLM 生成基因的简短摘要，并通过冻结的 LLM 骨干网络将其编码为固定维度的向量 $s_g$。
    2.  **因子化软提示合成**：
        *   **输入**：对于基因对 $(a, b)$，构建三个上下文向量：$s_a$、$s_b$ 以及它们的绝对差值 $|s_a - s_b|$（代表关系特征）。
        *   **因子化映射**：通过一个线性投影层生成“基因特异性系数矩阵”，并结合一个“共享原型矩阵”（由多个可学习的基矩阵加权组合而成）。
        *   **输出**：最终为每个基因对生成仅 **3个自适应虚拟标记**，作为提示词后缀输入 LLM。
*   **分类头**：在冻结的 LLM 骨干之上添加一个轻量级的多层感知机（MLP）分类头，用于输出相互作用的概率。

### 3. 实验设计
*   **骨干模型**：使用了 Gemma-3-4B-IT 和 Llama-3.1-8B-Instruct，并包含了在 630 万篇 PubMed 文献上进行领域自适应预训练（CPT）后的变体。
*   **数据集与场景**：
    1.  **大规模人类 PPI 推理**：包含 212 万个基因对（BioGRID, STRING 等数据库）。
    2.  **跨物种迁移**：在人类数据上训练，直接测试鸡、牛、狗的 PPI 数据。
    3.  **单细胞扰动基准（CausalBench）**：在 K562 和 RPE1 细胞系上进行零样本（Zero-shot）推理。
    4.  **磷酸化网络推理**：针对激酶-底物关系（PhosphoNetworks）。
*   **对比方法（Benchmarks）**：
    *   Few-shot 推理（少样本学习）。
    *   固定提示词：仅符号（Symbol-only）和包含生物背景描述（BioContext-informed）。
    *   任务特定软提示（Task-specific soft prompt）：所有输入共享相同的虚拟标记。

### 4. 资源与算力
*   **算力说明**：文中**未明确说明**具体的 GPU 型号、数量或总训练时长。
*   **训练细节**：提到了使用 `bfloat16` 精度、AdamW 优化器、学习率为 $1 \times 10^{-4}$、训练 15 个 Epoch。PPI 任务 Batch Size 为 128，磷酸化任务为 64。

### 5. 实验数量与充分性
*   **实验规模**：实验设计非常广泛，涵盖了从百万级的大规模训练到小样本的磷酸化网络推理。
*   **充分性评价**：
    *   **多维度验证**：不仅测试了准确率、ROC-AUC 等标准指标，还进行了跨物种迁移实验和单细胞扰动数据的生物学验证。
    *   **客观性**：通过 5 次随机划分取平均值，并对比了多种主流提示策略。
    *   **发现未标注关系**：特别设计了实验证明 GRASP 能从合成负样本中识别出“隐藏的正样本”（即数据库未记录但实际存在的相互作用），这增强了结果的说服力。

### 6. 主要结论与发现
*   **性能领先**：GRASP 在所有任务中均优于固定提示词和标准软提示，ROC-AUC 在 PPI 任务中达到 0.92-0.94。
*   **抗噪能力**：相比于直接在提示词中加入冗长的基因描述（BioContext），GRASP 通过向量压缩避免了无关文本带来的干扰。
*   **生物学发现能力**：GRASP 能够有效区分真正的负样本和尚未被数据库标注的潜在正样本（Cohen’s d 达到 1.88），具备辅助实验发现的潜力。
*   **零样本迁移**：在没有接触过表达数据的情况下，GRASP 在 CausalBench 上的生物学 F1 分数超过了基于表达数据的传统方法（如 GRNBoost）。

### 7. 优点与亮点
*   **参数高效**：仅通过 3 个虚拟标记就实现了高度的实例自适应性，计算开销极小。
*   **因子化设计**：巧妙地结合了“基因特异性”和“共享模式”，既能捕捉个体差异，又能学习通用的生物相互作用规律。
*   **通用性强**：一个框架即可处理物理接触（PPI）、化学修饰（磷酸化）和功能调控（GRN）等多种网络。

### 8. 不足与局限
*   **知识偏差**：模型性能高度依赖于 LLM 预训练阶段吸收的文献量，对于研究较少的“冷门基因”，预测准确性可能受限。
*   **方向性缺失**：目前的实验主要将相互作用视为无向二元关系，尚未充分探讨有向调控网络（如 A 抑制 B）的推理。
*   **模态单一**：完全依赖文本知识，没有整合基因表达谱、蛋白质结构等实验模态数据，在某些缺乏文献支持的场景下可能失效。

（完）
