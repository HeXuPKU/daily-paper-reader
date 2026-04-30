---
title: A Multi-modal LLM-Knowledge Fusion Framework for Predicting Single-cell Genetic Perturbation Effects
title_zh: 一种用于预测单细胞基因扰动效应的多模态大语言模型与知识融合框架
authors: "LU, M., YOU, N., ZHANG, H., ZHENG, L., LI, B., JIANG, W., ZHANG, Y., SUN, H., ZHOU, Y."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720560v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于遗传扰动效应的多模态大语言模型
tldr: 针对单细胞基因扰动预测中实验成本高、现有模型泛化性差等挑战，本文提出scPert框架。该框架基于Transformer架构，通过分层融合大语言模型嵌入、结构化知识图谱表示与基因特异性编码，实现了对单细胞转录组响应的高精度预测。scPert在单基因及组合扰动预测上表现优异，能有效揭示癌症相关通路机制并识别潜在治疗靶点，为构建“虚拟细胞”和加速药物研发提供了强有力的计算基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有计算方法在处理复杂基因相互作用、生物可解释性及对未知基因的泛化能力方面存在显著局限。
method: 开发了基于Transformer的scPert框架，通过融合知识图谱、基础模型上下文嵌入和基因特异性编码进行多模态特征集成。
result: scPert在单基因和组合扰动预测性能上均优于现有模型，并成功应用于p53通路分析及42个癌症依赖基因的靶点识别。
conclusion: 该框架为虚拟细胞的构建提供了强大的计算支撑，能够有效加速药物靶点发现并深化对细胞调控机制的理解。
---

## 摘要
理解细胞对基因扰动的响应是药物发现的基础，然而实验方法在覆盖范围和成本方面面临重大局限，阻碍了对细胞行为的全面映射。这促使了虚拟细胞的发展，即通过学习细胞状态与功能之间的关系，来预测不同背景下扰动后果的计算模型。然而，目前的计算方法在复杂基因相互作用中的准确性有限，生物可解释性较差，且对未见基因的泛化能力不足，严重制约了虚拟细胞的能力。我们提出了 scPert，这是一个基于 Transformer 架构的多模态框架，它整合了大语言模型嵌入与结构化生物知识，用于预测单细胞对基因扰动的转录组响应。通过对知识图谱表示、基础模型的上下文嵌入以及基因特异性编码进行分层融合，scPert 在单基因和组合扰动预测方面均比现有方法取得了显著的性能提升。在癌症相关应用中，scPert 展示了揭示 p53 通路动态和免疫检查点调节机制的能力。对 42 个癌症依赖基因的系统评估证明了 scPert 识别关键潜在治疗靶点的能力。我们的框架为虚拟细胞构建奠定了强大的计算基础，并加速了药物靶点的发现。

## Abstract
Understanding cellular responses to genetic perturbations is fundamental for drug discovery, yet experimental approaches face significant limitations in coverage and cost that prevent comprehensive mapping of cellular behavior. This has motivated the development of virtual cells, computational models that learn the relationship between cell state and function to predict the consequences of perturbations across diverse contexts. However, current computational methods suffer from limited accuracy in complex genetic interactions, poor biological interpretability, and inadequate generalization to unseen genes, severely constraining virtual cell capabilities. We present scPert, a multi-modal framework based on Transformer architecture that integrates large language model embeddings with structured biological knowledge to predict single-cell transcriptomic responses to genetic perturbations. Through hierarchical fusion of knowledge graph representations, contextual embeddings from foundation models, and gene-specific encodings, scPert achieves significant performance improvements in both single-gene and combinatorial perturbations over existing methods. In cancer-relevant applications, scPert demonstrates the capability to reveal p53 pathway dynamics and immune checkpoint regulatory mechanisms. Systematic evaluation on 42 cancer dependency genes demonstrates scPert's ability to identify critical potential therapeutic targets. Our framework establishes a powerful computational foundation for virtual cell construction and accelerates drug target discovery.

---

## 论文详细总结（自动生成）

以下是对论文《A Multi-modal LLM-Knowledge Fusion Framework for Predicting Single-cell Genetic Perturbation Effects》的结构化深入分析总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何准确预测单细胞在基因扰动（如基因敲除或过表达）后的转录组响应。
*   **研究背景**：
    *   **实验局限**：单细胞扰动实验（如Perturb-seq）成本极高，且基因组合的搜索空间巨大，实验无法覆盖所有可能性。
    *   **现有方法不足**：
        *   **基础模型（如scGPT）**：虽能捕捉全局模式，但往往被视为“黑盒”，缺乏生物学可解释性。
        *   **知识引导方法（如GEARS）**：依赖结构化知识，但受限于先验知识的不完整性，且对未见基因的泛化能力较弱。
        *   **泛化挑战**：现有模型在处理复杂基因相互作用（非线性效应）和推广到训练集中未出现的基因时表现不佳。
*   **整体含义**：该研究旨在通过融合大语言模型（LLM）的语义理解能力与知识图谱（KG）的结构化生物学逻辑，构建一个更精准、可解释且泛化性强的“虚拟细胞”计算框架。

### 2. 方法论：scPert 框架
*   **核心思想**：采用多模态融合策略，将数据驱动的特征与知识驱动的先验相结合，利用 Transformer 架构建模基因间的复杂调控关系。
*   **关键技术细节**：
    1.  **多模态嵌入融合**：
        *   **知识图谱嵌入 (KGE)**：利用 CompGCN 算法从 Hetionet（包含 4.7 万个节点、220 万条关系）中提取基因的结构化生物学背景。
        *   **LLM 上下文嵌入**：集成 scGPT 预训练模型的嵌入，捕捉基因在实际单细胞数据中的共表达和功能模式。
        *   **基因特异性编码**：为每个基因生成独特的标识向量。
    2.  **分层交互建模**：
        *   使用 8 层 Transformer 块，通过交叉注意力机制（Cross-attention）建模基因与扰动之间的相互作用。
        *   引入**内存高效注意力机制**，以处理大规模基因集和组合扰动。
    3.  **复合损失函数 (Multi-objective Loss)**：
        *   **FocalMSE**：根据样本难度自适应调整权重，重点优化表达变化显著的基因。
        *   **方向损失 (Direction Loss)**：强制模型学习正确的基因上调/下调趋势。
        *   **余弦相似度与加权 MSE**：保持全局表达特征并处理基因异质性。

### 3. 实验设计
*   **数据集**：使用了 5 个主流单细胞扰动数据集，涵盖不同规模和细胞类型：
    *   Norman (131 个组合扰动)、Adamson、Dixit、Replogle K562、Replogle RPE1 (全基因组规模)。
*   **Benchmark 与对比方法**：
    *   **对比模型**：GEARS (当前 SOTA)、scGPT (基础模型)、scGenePT、Scouter、biolord。
    *   **评估指标**：差异表达基因的均方误差 (MSE_DE)、皮尔逊相关系数 (Pearson_DE) 以及质心准确率 (Centroid Accuracy)。
*   **泛化场景测试**：针对组合扰动，设置了“Seen 0”（两个基因均未见过）、“Seen 1”和“Seen 2”三种难度梯度。

### 4. 资源与算力
*   **模型配置**：文中提到使用了 8 层 Transformer，每层 8 个注意力头，前馈网络维度从 512 扩展到 2048。
*   **算力说明**：论文**未明确说明**具体的 GPU 型号、数量及训练总时长。但提到了采用了“内存高效（memory-efficient）”的设计，暗示其对硬件资源有一定的优化。

### 5. 实验数量与充分性
*   **实验规模**：
    *   在 5 个基准数据集上进行了全面对比。
    *   针对 125 种基因组合进行了 5 种遗传相互作用模式（协同、上位性、冗余、抑制、新形态）的预测分析。
    *   进行了消融实验（如移除知识图谱组件），验证了 KG 对提升质心准确率的关键作用。
    *   开展了 p53 通路、免疫检查点（PD-L1）和 42 个癌症依赖基因的案例研究。
*   **充分性评价**：实验设计非常充分，不仅涵盖了标准性能指标，还深入到了生物学功能验证和临床相关靶点识别，证明了模型的实用价值。

### 6. 主要结论与发现
*   **性能领先**：scPert 在单基因和组合扰动预测中均优于现有 SOTA 方法。在 Norman 数据集的“Seen 2”场景下，MSE_DE 相比 GEARS 降低了 56.6%。
*   **捕捉非线性效应**：模型能准确预测非加性遗传相互作用，成功识别出 PTPN12 和 ZBTB25 组合产生的协同上调或抑制下调效应。
*   **生物学洞察**：
    *   在 p53 通路预测中达到 0.927 的高相关性。
    *   在小样本场景下，通过靶向加权策略准确识别了 PD-L1 的正向和负向调节因子。
    *   系统性地映射了 5460 对基因的遗传相互作用网络，识别出如 RUNX1 等关键调控节点。

### 7. 优点与亮点
*   **多模态融合**：成功解决了纯数据驱动模型缺乏生物学约束和纯知识驱动模型灵活性不足的问题。
*   **泛化能力强**：通过分层嵌入，模型在面对训练集中未出现的基因组合时表现出极强的外推能力。
*   **临床应用潜力**：直接应用于癌症靶点发现和免疫治疗机制研究，证明了其作为“虚拟细胞”原型在药物研发中的价值。
*   **损失函数创新**：FocalMSE 和方向损失的设计有效解决了单细胞数据稀疏性和表达变化微弱带来的训练难题。

### 8. 不足与局限
*   **跨数据集迁移**：目前 scPert 仍需针对特定数据集进行训练，尚未实现完全的“零样本”跨数据集通用预测。
*   **知识图谱依赖**：模型的性能部分取决于知识图谱的完整性，对于 KG 中未涵盖的极少数新基因，预测能力受限。
*   **可解释性挑战**：尽管引入了知识图谱，但 Transformer 内部复杂的嵌入融合过程仍具有一定的黑盒属性，难以直观推导具体的分子调控路径。
*   **算力细节缺失**：缺乏具体的训练资源消耗数据，不便于其他研究者评估复现成本。

（完）
