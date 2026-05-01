---
title: A Multi-modal LLM-Knowledge Fusion Framework for Predicting Single-cell Genetic Perturbation Effects
title_zh: 一种用于预测单细胞基因扰动效应的多模态大语言模型与知识融合框架
authors: "LU, M., YOU, N., ZHANG, H., ZHENG, L., LI, B., JIANG, W., ZHANG, Y., SUN, H., ZHOU, Y."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720560v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 多模态大语言模型用于遗传扰动效应预测
tldr: 针对实验方法在基因扰动研究中的高成本和局限性，本文提出scPert框架。该框架基于Transformer架构，融合了大语言模型嵌入、结构化生物知识图谱和基因特定编码。scPert在预测单细胞转录组对单基因及组合扰动的响应方面表现优异，能有效揭示癌症相关通路机制并识别潜在治疗靶点，为构建“虚拟细胞”和加速药物研发奠定了基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的计算模型在处理复杂基因相互作用、生物可解释性及对未知基因的泛化能力方面存在不足。
method: 提出scPert框架，通过分层融合知识图谱表示、基础模型上下文嵌入和基因特定编码来预测单细胞转录组响应。
result: scPert在单基因和组合扰动预测上显著优于现有方法，并成功识别了42个癌症依赖基因中的关键治疗靶点。
conclusion: 该框架为虚拟细胞构建提供了强大的计算基础，并能有效加速药物靶点的发现过程。
---

## 摘要
理解细胞对基因扰动的响应是药物发现的基础，然而实验方法在覆盖范围和成本方面面临显著局限，阻碍了对细胞行为的全面映射。这促使了虚拟细胞（virtual cells）的发展——即通过学习细胞状态与功能之间的关系，来预测不同背景下扰动后果的计算模型。然而，目前的计算方法在复杂基因相互作用中的准确性有限，生物可解释性较差，且对未见基因的泛化能力不足，严重制约了虚拟细胞的能力。我们提出了 scPert，这是一个基于 Transformer 架构的多模态框架，它整合了大语言模型嵌入与结构化生物知识，用于预测单细胞对基因扰动的转录组响应。通过对知识图谱表示、基础模型的上下文嵌入以及基因特异性编码进行分层融合，scPert 在单基因和组合扰动预测方面均比现有方法实现了显著的性能提升。在癌症相关应用中，scPert 展示了揭示 p53 通路动力学和免疫检查点调节机制的能力。对 42 个癌症依赖基因的系统评估证明了 scPert 识别关键潜在治疗靶点的能力。我们的框架为虚拟细胞构建奠定了强大的计算基础，并加速了药物靶点的发现。

## Abstract
Understanding cellular responses to genetic perturbations is fundamental for drug discovery, yet experimental approaches face significant limitations in coverage and cost that prevent comprehensive mapping of cellular behavior. This has motivated the development of virtual cells--computational models that learn the relationship between cell state and function to predict the consequences of perturbations across diverse contexts. However, current computational methods suffer from limited accuracy in complex genetic interactions, poor biological interpretability, and inadequate generalization to unseen genes, severely constraining virtual cell capabilities. We present scPert, a multi-modal framework based on Transformer architecture that integrates large language model embeddings with structured biological knowledge to predict single-cell transcriptomic responses to genetic perturbations. Through hierarchical fusion of knowledge graph representations, contextual embeddings from foundation models, and gene-specific encodings, scPert achieves significant performance improvements in both single-gene and combinatorial perturbations over existing methods. In cancer-relevant applications, scPert demonstrates the capability to reveal p53 pathway dynamics and immune checkpoint regulatory mechanisms. Systematic evaluation on 42 cancer dependency genes demonstrates scPerts ability to identify critical potential therapeutic targets. Our framework establishes a powerful computational foundation for virtual cell construction and accelerates drug target discovery.

---

## 论文详细总结（自动生成）

## 论文总结：scPert 多模态大语言模型与知识融合框架

### 1. 核心问题与研究动机
*   **核心问题**：如何准确预测单细胞在受到基因扰动（如基因敲除）后的转录组响应，特别是针对未见过的基因组合及复杂的非线性相互作用。
*   **研究动机**：
    *   **实验局限性**：单细胞扰动实验（如 Perturb-seq）成本极高且数据稀疏，无法覆盖数以万计的基因组合。
    *   **现有模型不足**：基础模型（如 scGPT）虽能捕捉全局模式但缺乏生物可解释性；知识引导模型（如 GEARS）受限于先验知识的不完整性；且大多数模型对未见基因的泛化能力较差。
    *   **虚拟细胞愿景**：构建能够模拟细胞行为的计算模型，加速药物靶点发现和精准医疗。

### 2. 方法论
*   **核心思想**：通过分层融合策略，将**结构化生物知识图谱（KG）**的精确性与**大语言模型（LLM）**的上下文理解能力相结合。
*   **关键技术细节**：
    *   **多模态嵌入融合**：
        *   **KG 嵌入**：利用 CompGCN（组合图卷积网络）从 Hetionet 知识图谱中提取基因的结构化关系。
        *   **LLM 嵌入**：利用预训练的单细胞基础模型 scGPT 提取基因的上下文功能表示。
        *   **融合机制**：通过多层感知机（MLP）将两种嵌入结合，生成增强的扰动表示。
    *   **模型架构**：基于 Transformer 架构，包含 8 层编码器，设计了专门的基因交互层和自注意力机制，以捕捉基因调控网络中的长程依赖。
    *   **组合扰动处理**：引入专门的扰动融合模块，通过非线性变换建模多基因扰动间的协同或拮抗效应，而非简单的线性加和。
    *   **复合损失函数**：
        *   **FocalMSE**：根据样本预测难度自动调整权重，重点关注表达量变化剧烈的基因。
        *   **方向损失（Direction Loss）**：强制模型学习正确的上调/下调趋势。
        *   **余弦相似度与加权 MSE**：保持全局表达谱的相似性并处理基因异质性。

### 3. 实验设计
*   **数据集**：使用了 5 个大规模公开单细胞扰动数据集：Norman（组合扰动）、Adamson、Dixit、Replogle K562 和 Replogle RPE1（全基因组规模）。
*   **Benchmark 与对比方法**：
    *   **对比模型**：GEARS（SOTA 知识图谱方法）、scGPT（基础模型）、scGenePT、Scouter、biolord。
    *   **评估指标**：差异表达基因的均方误差（MSE_DE）、皮尔逊相关系数（Pearson_DE）以及质心准确率（Centroid Accuracy，衡量区分不同扰动信号的能力）。
*   **泛化场景**：设置了“Seen 0”（扰动基因均未在训练集中出现）、“Seen 1”和“Seen 2”三种难度递增的测试场景。

### 4. 资源与算力
*   **算力说明**：论文中**未明确指出**具体的 GPU 型号、数量或训练总时长。
*   **模型规模**：提到使用了 8 层 Transformer，每层 8 个注意力头，隐藏层维度为 512，前馈网络维度为 2048。

### 5. 实验数量与充分性
*   **实验规模**：在 5 个不同背景、不同规模（从几十个到上千个扰动）的数据集上进行了全面测试。
*   **消融实验**：专门移除了 Hetionet 知识图谱组件进行对比，证明了结构化知识在区分扰动特异性信号中的核心作用。
*   **生物学验证**：针对 p53 通路、PD-L1 免疫检查点以及 42 个 DepMap 癌症依赖基因进行了深入的案例研究。
*   **充分性评价**：实验设计严谨，涵盖了从数值准确性到生物学功能发现的多个维度，对比基准全面，实验结果具有统计学意义。

### 6. 主要结论与发现
*   **性能卓越**：scPert 在所有基准数据集上的表现均达到或超过了现有 SOTA 模型。在 Norman 数据集的“Seen 2”场景下，MSE_DE 比 GEARS 降低了 56.6%。
*   **质心准确率领先**：在 Dixit 等挑战性数据集上，scPert 展现了极强的区分扰动特异性响应的能力，远超 Scouter 等模型。
*   **生物学洞察**：
    *   成功预测了 p53 通路的复杂动力学（相关性 r=0.927）。
    *   在小样本情况下，通过加权优化准确识别了 PD-L1 的所有正负调节因子。
    *   系统性地识别了 RUNX1 等癌症关键治疗靶点。

### 7. 优点与亮点
*   **多模态融合创新**：成功解决了纯数据驱动模型缺乏生物约束和纯知识驱动模型灵活性不足的问题。
*   **非线性建模**：在处理组合基因扰动时，能够捕捉到非加性的生物学效应（如协同作用）。
*   **鲁棒性强**：复合损失函数的设计使其在处理稀疏、高噪声的单细胞数据时表现稳健。

### 8. 不足与局限
*   **跨数据集迁移**：目前仍需在特定数据集上进行训练，尚未实现完全通用的、无需重训的跨组织/跨物种零样本预测。
*   **知识图谱依赖**：模型的上限受限于现有生物知识图谱的完整性和准确性，对于研究极少的“暗基因”预测能力受限。
*   **计算开销**：虽然引入了内存高效机制，但大规模 Transformer 架构在超大规模基因集上的训练和推理仍需较高算力支持。

（完）
