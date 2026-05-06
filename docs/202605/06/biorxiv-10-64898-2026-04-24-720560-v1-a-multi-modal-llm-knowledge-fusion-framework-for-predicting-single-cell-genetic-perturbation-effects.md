---
title: A Multi-modal LLM-Knowledge Fusion Framework for Predicting Single-cell Genetic Perturbation Effects
title_zh: 一种用于预测单细胞基因扰动效应的多模态大语言模型-知识融合框架
authors: "LU, M., YOU, N., ZHANG, H., ZHENG, L., LI, B., JIANG, W., ZHANG, Y., SUN, H., ZHOU, Y."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720560v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于预测遗传扰动效应的多模态大语言模型框架
tldr: 了解基因扰动对细胞的影响对药物研发至关重要，但现有计算模型在复杂交互预测和泛化能力上存在不足。本文提出scPert，一个基于Transformer的多模态框架，通过融合大语言模型（LLM）嵌入与结构化生物知识图谱，预测单细胞转录组对基因扰动的响应。scPert在单基因和组合扰动预测中表现优异，能揭示癌症相关通路机制并识别潜在治疗靶点，为构建“虚拟细胞”提供了强有力的计算基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因扰动预测模型在处理复杂遗传相互作用、生物可解释性及对未知基因的泛化能力方面存在局限。
method: 提出scPert框架，利用Transformer架构层级化地融合知识图谱表示、基础模型上下文嵌入及基因特异性编码。
result: scPert在单基因和组合扰动预测性能上显著优于现有方法，并成功应用于p53通路分析和癌症治疗靶点识别。
conclusion: 该框架为虚拟细胞构建奠定了计算基础，并能有效加速药物靶点的发现过程。
---

## 摘要
理解细胞对基因扰动的响应是药物发现的基础，但实验方法在覆盖范围和成本方面面临重大局限，阻碍了对细胞行为的全面映射。这促使了虚拟细胞的发展——即通过学习细胞状态与功能之间的关系，以预测不同背景下扰动后果的计算模型。然而，目前的计算方法在复杂基因相互作用中的准确性有限，生物可解释性差，且对未见基因的泛化能力不足，严重制约了虚拟细胞的能力。我们提出了 scPert，这是一个基于 Transformer 架构的多模态框架，它整合了大语言模型嵌入与结构化生物知识，用于预测单细胞转录组对基因扰动的响应。通过知识图谱表示、基础模型的上下文嵌入以及基因特异性编码的层次化融合，scPert 在单基因和组合扰动方面均比现有方法实现了显著的性能提升。在癌症相关应用中，scPert 展示了揭示 p53 通路动力学和免疫检查点调节机制的能力。对 42 个癌症依赖基因的系统评估证明了 scPert 识别关键潜在治疗靶点的能力。我们的框架为虚拟细胞构建奠定了强大的计算基础，并加速了药物靶点的发现。

## Abstract
Understanding cellular responses to genetic perturbations is fundamental for drug discovery, yet experimental approaches face significant limitations in coverage and cost that prevent comprehensive mapping of cellular behavior. This has motivated the development of virtual cells--computational models that learn the relationship between cell state and function to predict the consequences of perturbations across diverse contexts. However, current computational methods suffer from limited accuracy in complex genetic interactions, poor biological interpretability, and inadequate generalization to unseen genes, severely constraining virtual cell capabilities. We present scPert, a multi-modal framework based on Transformer architecture that integrates large language model embeddings with structured biological knowledge to predict single-cell transcriptomic responses to genetic perturbations. Through hierarchical fusion of knowledge graph representations, contextual embeddings from foundation models, and gene-specific encodings, scPert achieves significant performance improvements in both single-gene and combinatorial perturbations over existing methods. In cancer-relevant applications, scPert demonstrates the capability to reveal p53 pathway dynamics and immune checkpoint regulatory mechanisms. Systematic evaluation on 42 cancer dependency genes demonstrates scPerts ability to identify critical potential therapeutic targets. Our framework establishes a powerful computational foundation for virtual cell construction and accelerates drug target discovery.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **scPert** 的多模态深度学习框架，旨在通过融合大语言模型（LLM）的表示能力与结构化生物知识，预测单细胞在基因扰动后的转录组响应。以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何准确预测基因扰动（特别是多基因组合扰动）对细胞状态的影响？
*   **研究背景**：药物研发成本高、周期长，理解基因调控机制是关键。虽然单细胞扰动测序（如 Perturb-seq）提供了高分辨率数据，但实验覆盖范围有限且成本高昂。
*   **研究动机**：现有的计算模型存在局限性：基础模型（如 scGPT）往往是“黑盒”，缺乏生物可解释性；而基于知识的方法（如 GEARS）受限于先验知识的不完整性。此外，现有模型在处理未见基因（unseen genes）和复杂组合扰动时的泛化能力较弱。

### 2. 方法论
scPert 采用基于 Transformer 的多模态融合架构，核心思想是将语义信息与结构化生物知识相结合：
*   **多模态嵌入融合**：
    *   **知识图谱嵌入 (KGE)**：利用 CompGCN 算法从 Hetionet（包含 4.7 万个节点和 220 万个关系）中提取基因的结构化生物背景。
    *   **LLM 上下文嵌入**：使用预训练的单细胞基础模型 scGPT 提取基因的功能表示。
    *   **基因特异性编码**：针对每个基因生成独特的标识向量。
*   **关键技术细节**：
    *   **层级融合机制**：通过多层感知机（MLP）将上述三种嵌入融合，并设计了专门的组合扰动融合模块来处理非叠加效应。
    *   **Transformer 架构**：包含 8 层 Transformer 块，使用内存高效的注意力机制处理大规模基因集。
    *   **复合损失函数 (Composite Loss)**：
        *   **FocalMSE**：根据样本难度自适应调整权重，重点关注表达量变化显著的基因。
        *   **方向损失 (Direction Loss)**：强制模型学习正确的基因上调/下调趋势。
        *   **余弦相似度与加权 MSE**：保持全局表达特征并处理基因异质性。

### 3. 实验设计
*   **数据集**：涵盖了 5 个主流单细胞扰动数据集，包括 Norman (组合扰动)、Adamson、Dixit 以及大规模全基因组筛选数据集 Replogle (K562 和 RPE1)。
*   **Benchmark 策略**：采用“留出基因（held-out gene）”策略，测试模型对训练中未见过的扰动基因的预测能力。
*   **对比方法**：
    *   **GEARS**（当前最先进的基于知识图谱的方法）。
    *   **scGPT**（单细胞基础模型）。
    *   **scGenePT / Scouter**（利用 LLM 嵌入的方法）。
    *   **biolord**（深度生成框架）。
*   **评估指标**：差异表达基因的均方误差 (MSE_DE)、皮尔逊相关系数 (Pearson_DE) 以及质心准确率 (Centroid Accuracy)。

### 4. 资源与算力
*   **模型配置**：Transformer 包含 8 层，每层 8 个注意力头，前馈网络维度从 512 扩展至 2048。
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量及训练总时长。但提到了使用了“内存高效的注意力机制”来优化大规模基因集的计算。

### 5. 实验数量与充分性
*   **实验规模**：在 5 个不同规模（从 20 个扰动到 1543 个扰动）的数据集上进行了测试，涵盖了超过 16 万个细胞。
*   **消融实验**：专门针对知识图谱（Hetionet）进行了消融研究，证明移除 KG 后质心准确率大幅下降（如在 Replogle K562 中从 0.754 降至 0.522）。
*   **场景覆盖**：针对组合扰动划分了“Seen 0/1/2”三种泛化场景（即扰动对中的基因在训练集中出现过 0、1 或 2 个），实验设计较为全面、客观，能够体现模型在不同难度下的鲁棒性。

### 6. 主要结论与发现
*   **性能领先**：scPert 在所有基准测试中均表现出竞争性或领先的性能，尤其在 Norman 和 Replogle RPE1 数据集上取得了最低的预测误差。
*   **组合扰动优势**：在最难的“Seen 2”组合扰动场景下，scPert 比 GEARS 的 MSE_DE 降低了 **56.6%**。
*   **生物发现能力**：
    *   成功预测了 p53 通路的动力学特征（相关性 r=0.927）。
    *   在小规模数据下准确识别了免疫检查点 PD-L1 的正向和负向调节因子。
    *   通过 DepMap 数据验证，成功识别了 42 个癌症依赖基因的潜在治疗靶点（如 RUNX1）。

### 7. 优点
*   **多模态融合**：巧妙结合了 LLM 的语义理解能力和知识图谱的生物约束，弥补了纯数据驱动模型的“黑盒”缺陷。
*   **损失函数创新**：引入方向损失和 FocalMSE，解决了基因表达数据稀疏且方向性关键的问题。
*   **泛化能力强**：在处理未见过的基因组合时表现优异，这对实际药物靶点筛选具有极高价值。

### 8. 不足与局限
*   **跨数据集泛化**：目前 scPert 仍需要在特定数据集上进行训练，尚未实现无需重训的跨组织、跨物种通用预测（这是全行业的共同挑战）。
*   **知识图谱依赖**：模型的性能高度依赖于现有知识图谱的完整性，对于研究极少的“暗基因”，预测能力可能受限。
*   **可解释性挑战**：尽管引入了生物知识，但多层 Transformer 的复杂嵌入融合过程仍难以提供直观的分子机制解释。
*   **算力门槛**：虽然优化了内存，但处理全基因组规模的扰动预测仍需要较高的计算资源。

（完）
