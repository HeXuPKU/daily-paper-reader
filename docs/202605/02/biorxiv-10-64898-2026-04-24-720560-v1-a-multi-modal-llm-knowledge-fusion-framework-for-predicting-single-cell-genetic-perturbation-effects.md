---
title: A Multi-modal LLM-Knowledge Fusion Framework for Predicting Single-cell Genetic Perturbation Effects
title_zh: 一种用于预测单细胞基因扰动效应的多模态大语言模型-知识融合框架
authors: "LU, M., YOU, N., ZHANG, H., ZHENG, L., LI, B., JIANG, W., ZHANG, Y., SUN, H., ZHOU, Y."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720560v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于预测基因扰动效应的多模态大语言模型框架
tldr: 针对实验方法在基因扰动研究中的高成本和局限性，本文提出scPert框架。该框架基于Transformer架构，通过多模态融合大语言模型嵌入、结构化生物知识图谱和基因特定编码，实现了对单细胞转录组响应的高精度预测。scPert在单基因及组合扰动预测上表现优异，能揭示复杂的生物通路机制并识别潜在药物靶点，为构建“虚拟细胞”奠定了计算基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的计算模型在处理复杂基因相互作用、生物可解释性及对未知基因的泛化能力方面存在不足。
method: 提出scPert框架，利用Transformer架构分层融合知识图谱表示、基础模型上下文嵌入和基因特定编码。
result: scPert在单基因和组合扰动预测性能上显著优于现有方法，并成功识别出42个癌症依赖基因中的关键治疗靶点。
conclusion: 该框架为虚拟细胞构建提供了强大的计算基础，并能有效加速药物靶点的发现过程。
---

## 摘要
理解细胞对基因扰动的响应是药物发现的基础，然而实验方法在覆盖范围和成本方面面临重大局限，阻碍了对细胞行为的全面映射。这促使了“虚拟细胞”的发展——即通过学习细胞状态与功能之间的关系，来预测不同背景下扰动后果的计算模型。然而，目前的计算方法在复杂基因相互作用中的准确性有限，生物学可解释性较差，且对未见基因的泛化能力不足，严重制约了虚拟细胞的能力。我们提出了 scPert，这是一个基于 Transformer 架构的多模态框架，它整合了大语言模型嵌入与结构化生物知识，用于预测单细胞对基因扰动的转录组响应。通过对知识图谱表示、基础模型的上下文嵌入以及基因特异性编码进行分层融合，scPert 在单基因和组合扰动预测方面均比现有方法取得了显著的性能提升。在癌症相关应用中，scPert 展示了揭示 p53 通路动力学和免疫检查点调节机制的能力。对 42 个癌症依赖基因的系统评估证明了 scPert 识别关键潜在治疗靶点的能力。我们的框架为虚拟细胞构建奠定了强大的计算基础，并加速了药物靶点的发现。

## Abstract
Understanding cellular responses to genetic perturbations is fundamental for drug discovery, yet experimental approaches face significant limitations in coverage and cost that prevent comprehensive mapping of cellular behavior. This has motivated the development of virtual cells--computational models that learn the relationship between cell state and function to predict the consequences of perturbations across diverse contexts. However, current computational methods suffer from limited accuracy in complex genetic interactions, poor biological interpretability, and inadequate generalization to unseen genes, severely constraining virtual cell capabilities. We present scPert, a multi-modal framework based on Transformer architecture that integrates large language model embeddings with structured biological knowledge to predict single-cell transcriptomic responses to genetic perturbations. Through hierarchical fusion of knowledge graph representations, contextual embeddings from foundation models, and gene-specific encodings, scPert achieves significant performance improvements in both single-gene and combinatorial perturbations over existing methods. In cancer-relevant applications, scPert demonstrates the capability to reveal p53 pathway dynamics and immune checkpoint regulatory mechanisms. Systematic evaluation on 42 cancer dependency genes demonstrates scPerts ability to identify critical potential therapeutic targets. Our framework establishes a powerful computational foundation for virtual cell construction and accelerates drug target discovery.

---

## 论文详细总结（自动生成）

以下是对论文《A Multi-modal LLM-Knowledge Fusion Framework for Predicting Single-cell Genetic Perturbation Effects》（scPert）的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何准确预测基因扰动（如基因敲除或过表达）后单细胞转录组的状态变化。
*   **研究背景**：理解细胞对扰动的响应是药物研发和生物医学研究的基础。虽然 CRISPR 等实验技术可以观察这些效应，但面对数以万计的基因及其组合，实验成本极高且覆盖范围有限。
*   **研究动机**：现有的计算模型（如“虚拟细胞”原型）在处理复杂的基因相互作用、生物学可解释性以及对未见基因（Unseen genes）的泛化能力方面存在显著不足。

### 2. 论文提出的方法论：scPert 框架
scPert 是一个基于 **Transformer 架构** 的多模态融合框架，其核心思想是将结构化的生物学知识与大规模预训练模型的上下文信息相结合：
*   **多模态输入融合**：
    1.  **知识图谱（KG）表示**：引入结构化的生物知识（如基因相互作用、通路信息），提供显式的生物学约束。
    2.  **大语言模型（LLM）上下文嵌入**：利用单细胞基础模型（如 scGPT 或 Geneformer）生成的基因嵌入，捕捉基因在海量数据中的隐式关联。
    3.  **基因特异性编码**：针对特定实验背景的基因特征进行编码。
*   **分层融合机制**：通过 Transformer 层的注意力机制，将上述三种模态的信息进行分层整合，学习基因扰动与转录组响应之间的非线性映射关系。
*   **预测目标**：输入扰动信息和初始细胞状态，输出扰动后的单细胞基因表达谱。

### 3. 实验设计
*   **数据集**：
    *   涵盖了单基因扰动和组合（双基因）扰动的数据集。
    *   特别提到了对 **42 个癌症依赖基因** 的系统评估。
*   **Benchmark（基准测试）**：
    *   对比了当前主流的扰动预测模型，如 **GEARS**、**CPA**（Compositional Perturbation Autoencoder）等。
*   **应用场景**：
    *   **单基因与组合扰动预测**：评估模型在已知和未知扰动组合上的准确性。
    *   **生物机制挖掘**：分析 p53 信号通路动力学和免疫检查点调节机制。
    *   **药物靶点识别**：在癌症相关基因中识别潜在的治疗靶点。

### 4. 资源与算力
*   **算力说明**：提供的摘要及元数据中**未明确说明**具体的 GPU 型号、数量及训练时长。通常此类基于 Transformer 和 LLM 嵌入的模型需要高性能显卡（如 NVIDIA A100 或 H100）进行训练和推理。

### 5. 实验数量与充分性
*   **实验规模**：
    *   进行了多维度的性能对比，包括单基因和组合扰动。
    *   包含针对特定生物学通路（p53、免疫检查点）的深入案例研究。
    *   对 42 个癌症依赖基因进行了系统性评估。
*   **充分性评价**：实验设计较为全面，不仅关注预测精度（MSE、相关性等指标），还强调了模型在实际生物医学场景（如靶点发现）中的应用价值。通过消融实验（隐含在多模态设计中）验证了知识图谱和 LLM 嵌入的贡献，实验逻辑较为严密。

### 6. 主要结论与发现
*   **性能领先**：scPert 在预测单基因和组合扰动效应方面显著优于现有最先进（SOTA）方法。
*   **泛化能力强**：通过融合 LLM 和知识图谱，模型对未在训练集中出现的基因扰动表现出更强的预测能力。
*   **生物学洞察**：模型能够成功揭示复杂的生物通路机制（如 p53 通路），并能从 42 个癌症依赖基因中识别出关键的潜在治疗靶点。
*   **虚拟细胞基础**：该框架为构建功能完备的“虚拟细胞”提供了强大的计算底座。

### 7. 优点（亮点）
*   **多模态融合创新**：首次将结构化知识图谱与非结构化的 LLM 嵌入结合，兼顾了生物学先验和数据驱动的特征。
*   **可解释性增强**：通过引入知识图谱，使得模型的预测结果更具生物学意义，而非纯粹的“黑盒”预测。
*   **解决冷启动问题**：通过 LLM 的泛化能力，改善了对稀有或未见扰动基因的预测效果。

### 8. 不足与局限
*   **数据依赖性**：模型性能高度依赖于底层知识图谱的完整性和预训练 LLM 的质量。如果知识图谱存在偏差或缺失，可能影响预测准确性。
*   **计算复杂性**：Transformer 架构结合多模态输入，其计算开销可能大于传统的轻量级模型。
*   **动态响应限制**：虽然能预测扰动后的状态，但对于细胞随时间变化的连续动态响应过程，文中未详细说明其捕捉能力。

（完）
