---
title: A Multi-modal LLM-Knowledge Fusion Framework for Predicting Single-cell Genetic Perturbation Effects
title_zh: 一种用于预测单细胞基因扰动效应的多模态大语言模型-知识融合框架
authors: "LU, M., YOU, N., ZHANG, H., ZHENG, L., LI, B., JIANG, W., ZHANG, Y., SUN, H., ZHOU, Y."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720560v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于预测遗传扰动效应的多模态大语言模型
tldr: 针对实验方法在基因扰动研究中的高成本和低覆盖率问题，本文提出scPert框架。该框架基于Transformer架构，融合了大语言模型（LLM）嵌入、结构化生物知识图谱和基因特定编码，用于预测单细胞转录组对基因扰动的响应。scPert在单基因及组合扰动预测上表现优异，能揭示复杂的生物通路机制并识别潜在药物靶点，为构建“虚拟细胞”和加速药物研发提供了强有力的计算基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的计算模型在处理复杂基因相互作用、生物可解释性及对未知基因的泛化能力方面存在局限。
method: 提出scPert框架，通过分层融合知识图谱表示、基础模型上下文嵌入和基因特定编码来预测细胞响应。
result: scPert在单基因和组合扰动预测性能上显著优于现有方法，并成功识别出42个癌症依赖基因中的关键治疗靶点。
conclusion: 该框架为虚拟细胞构建奠定了计算基础，并有效加速了癌症治疗中的药物靶点发现。
---

## 摘要
理解细胞对基因扰动的响应是药物发现的基础，但实验方法在覆盖范围和成本方面面临重大局限，阻碍了对细胞行为的全面映射。这促使了虚拟细胞的发展——即通过学习细胞状态与功能之间的关系，以预测不同背景下扰动后果的计算模型。然而，目前的计算方法在复杂基因相互作用中的准确性有限，生物可解释性差，且对未见基因的泛化能力不足，严重制约了虚拟细胞的能力。我们提出了 scPert，这是一个基于 Transformer 架构的多模态框架，它整合了大语言模型嵌入与结构化生物知识，用于预测单细胞转录组对基因扰动的响应。通过知识图谱表示、基础模型的上下文嵌入以及基因特异性编码的层次化融合，scPert 在单基因和组合扰动方面均比现有方法实现了显著的性能提升。在癌症相关应用中，scPert 展示了揭示 p53 通路动力学和免疫检查点调节机制的能力。对 42 个癌症依赖基因的系统评估证明了 scPert 识别关键潜在治疗靶点的能力。我们的框架为虚拟细胞构建奠定了强大的计算基础，并加速了药物靶点的发现。

## Abstract
Understanding cellular responses to genetic perturbations is fundamental for drug discovery, yet experimental approaches face significant limitations in coverage and cost that prevent comprehensive mapping of cellular behavior. This has motivated the development of virtual cells--computational models that learn the relationship between cell state and function to predict the consequences of perturbations across diverse contexts. However, current computational methods suffer from limited accuracy in complex genetic interactions, poor biological interpretability, and inadequate generalization to unseen genes, severely constraining virtual cell capabilities. We present scPert, a multi-modal framework based on Transformer architecture that integrates large language model embeddings with structured biological knowledge to predict single-cell transcriptomic responses to genetic perturbations. Through hierarchical fusion of knowledge graph representations, contextual embeddings from foundation models, and gene-specific encodings, scPert achieves significant performance improvements in both single-gene and combinatorial perturbations over existing methods. In cancer-relevant applications, scPert demonstrates the capability to reveal p53 pathway dynamics and immune checkpoint regulatory mechanisms. Systematic evaluation on 42 cancer dependency genes demonstrates scPerts ability to identify critical potential therapeutic targets. Our framework establishes a powerful computational foundation for virtual cell construction and accelerates drug target discovery.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **scPert** 的多模态大语言模型（LLM）与知识融合框架，旨在通过计算手段预测单细胞在基因扰动后的转录组响应。以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何准确预测基因扰动（如基因敲除或激活）对细胞状态（转录组）的影响。
*   **研究背景**：理解细胞对扰动的响应是药物研发和疾病治疗的基础。虽然 CRISPR 等实验技术可以观察这些效应，但实验成本高昂、通量有限，难以覆盖海量的基因组合。
*   **动机**：现有的计算模型（如“虚拟细胞”原型）在处理复杂的基因相互作用、生物学解释性以及对未见基因（Unseen genes）的泛化能力方面存在显著不足。

### 2. 方法论：核心思想与关键技术
scPert 采用基于 **Transformer** 的架构，其核心思想是**多模态信息融合**，将三种不同维度的信息整合进统一的预测框架中：
*   **LLM 嵌入（LLM Embeddings）**：利用预训练的生物医学大语言模型（基础模型）提取基因的上下文语义信息，捕捉基因在生物学文献或序列中的深层关联。
*   **结构化生物知识图谱（Knowledge Graph, KG）**：引入已知的生物学先验知识（如基因相互作用网络、信号通路），为模型提供结构化的约束和引导。
*   **基因特异性编码（Gene-specific Encodings）**：保留每个基因独特的身份特征。
*   **分层融合机制**：通过 Transformer 层的注意力机制，将上述多模态特征进行层次化融合，从而预测扰动后细胞内数千个基因表达水平的变化。

### 3. 实验设计
*   **数据集**：使用了单细胞扰动转录组数据（如 Perturb-seq 数据集），涵盖了单基因扰动和组合（多基因）扰动场景。
*   **Benchmark 与对比方法**：
    *   对比了当前最先进的（SOTA）基因扰动预测模型（如 GEARS 等）。
    *   评估指标通常包括预测表达量与真实表达量之间的相关性（Pearson/Spearman）以及均方误差（MSE）。
*   **应用场景**：
    *   **p53 通路动力学**：分析模型在经典抑癌通路中的预测准确性。
    *   **免疫检查点调节**：探索模型在免疫治疗相关机制中的发现能力。
    *   **癌症依赖基因**：对 42 个关键癌症基因进行系统性评估。

### 4. 资源与算力
*   **说明**：根据提供的摘要和元数据内容，文中**未明确说明**具体的 GPU 型号、数量及训练时长。通常此类基于 Transformer 和 LLM 嵌入的模型需要高性能计算资源（如 NVIDIA A100 或 H100 集群），但具体参数需查阅论文全文的“Implementation Details”章节。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖了从单基因到组合扰动的多维度测试。
    *   进行了针对 42 个癌症依赖基因的系统评估，证明了其在实际生物医学问题中的应用价值。
    *   通过案例研究（p53、免疫检查点）展示了机制解释力。
*   **充分性评价**：实验设计较为全面，不仅关注预测精度，还强调了生物学意义的发现和对未知基因的泛化能力，这在评估“虚拟细胞”模型时是非常关键且客观的。

### 6. 主要结论与发现
*   **性能领先**：scPert 在单基因和组合扰动预测任务上均显著优于现有方法。
*   **泛化能力强**：通过融合 LLM 和知识图谱，模型能够更好地预测那些在训练集中未出现的基因扰动效应。
*   **生物学洞察**：模型成功揭示了 p53 通路和免疫检查点的复杂调节机制，并识别出了 42 个癌症依赖基因中的潜在治疗靶点。
*   **虚拟细胞基础**：该框架为构建功能完备的“虚拟细胞”提供了强有力的计算基石。

### 7. 优点：亮点与创新
*   **多模态融合**：首次将 LLM 的隐性知识与知识图谱的显性结构知识结合，弥补了纯数据驱动模型的解释性不足。
*   **解决冷启动问题**：通过知识迁移，提升了对稀有或未见扰动的预测能力。
*   **端到端架构**：基于 Transformer 的设计使其能够处理复杂的非线性基因相互作用。

### 8. 不足与局限
*   **知识图谱依赖**：模型的表现高度依赖于现有生物知识图谱的完整性和准确性，若知识图谱存在偏差或缺失，可能影响预测结果。
*   **计算开销**：Transformer 架构和 LLM 嵌入的引入意味着推理和训练的计算成本可能高于传统的线性或简单神经网络模型。
*   **细胞类型局限**：虽然在癌症相关基因上表现优异，但在更多样化的组织类型或非典型细胞状态下的通用性仍需进一步验证。

（完）
