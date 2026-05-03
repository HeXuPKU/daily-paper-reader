---
title: A Multi-modal LLM-Knowledge Fusion Framework for Predicting Single-cell Genetic Perturbation Effects
title_zh: 一种用于预测单细胞基因扰动效应的多模态大语言模型-知识融合框架
authors: "LU, M., YOU, N., ZHANG, H., ZHENG, L., LI, B., JIANG, W., ZHANG, Y., SUN, H., ZHOU, Y."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720560v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于预测遗传扰动效应的多模态大语言模型-知识融合框架
tldr: 针对实验方法在基因扰动研究中的高成本和局限性，本文提出scPert框架。该框架基于Transformer架构，通过多模态融合大语言模型嵌入、结构化生物知识图谱和基因特定编码，预测单细胞转录组对基因扰动的响应。scPert在单基因和组合扰动预测上表现优异，能揭示关键生物通路机制并识别潜在药物靶点，为构建“虚拟细胞”奠定了基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的计算模型在处理复杂基因相互作用、生物可解释性及对未知基因的泛化能力方面存在不足。
method: 提出scPert框架，利用Transformer架构层级化融合知识图谱表示、基础模型上下文嵌入和基因特定编码。
result: scPert在单基因和组合扰动预测性能上显著优于现有方法，并成功识别出42个癌症依赖基因中的关键治疗靶点。
conclusion: 该框架为虚拟细胞构建提供了强大的计算基础，并能有效加速药物靶点的发现过程。
---

## 摘要
理解细胞对基因扰动的响应是药物研发的基础，但实验方法在覆盖范围和成本方面面临重大限制，阻碍了对细胞行为的全面映射。这促使了虚拟细胞（virtual cells）的发展——即通过学习细胞状态与功能之间的关系，来预测不同背景下扰动后果的计算模型。然而，目前的计算方法在处理复杂基因相互作用时准确性有限，生物可解释性较差，且对未见基因的泛化能力不足，严重制约了虚拟细胞的能力。我们提出了 scPert，这是一个基于 Transformer 架构的多模态框架，它整合了大语言模型嵌入与结构化生物知识，用于预测单细胞转录组对基因扰动的响应。通过对知识图谱表示、基础模型的上下文嵌入以及基因特异性编码进行分层融合，scPert 在单基因和组合扰动预测方面均比现有方法实现了显著的性能提升。在癌症相关应用中，scPert 展示了揭示 p53 通路动力学和免疫检查点调节机制的能力。对 42 个癌症依赖基因的系统评估证明了 scPert 识别关键潜在治疗靶点的能力。我们的框架为虚拟细胞构建奠定了强大的计算基础，并加速了药物靶点的发现。

## Abstract
Understanding cellular responses to genetic perturbations is fundamental for drug discovery, yet experimental approaches face significant limitations in coverage and cost that prevent comprehensive mapping of cellular behavior. This has motivated the development of virtual cells--computational models that learn the relationship between cell state and function to predict the consequences of perturbations across diverse contexts. However, current computational methods suffer from limited accuracy in complex genetic interactions, poor biological interpretability, and inadequate generalization to unseen genes, severely constraining virtual cell capabilities. We present scPert, a multi-modal framework based on Transformer architecture that integrates large language model embeddings with structured biological knowledge to predict single-cell transcriptomic responses to genetic perturbations. Through hierarchical fusion of knowledge graph representations, contextual embeddings from foundation models, and gene-specific encodings, scPert achieves significant performance improvements in both single-gene and combinatorial perturbations over existing methods. In cancer-relevant applications, scPert demonstrates the capability to reveal p53 pathway dynamics and immune checkpoint regulatory mechanisms. Systematic evaluation on 42 cancer dependency genes demonstrates scPerts ability to identify critical potential therapeutic targets. Our framework establishes a powerful computational foundation for virtual cell construction and accelerates drug target discovery.

---

## 论文详细总结（自动生成）

### 论文总结：scPert —— 多模态大语言模型与知识融合的单细胞基因扰动预测框架

#### 1. 核心问题与整体含义（研究动机和背景）
药物研发面临高成本和长周期的挑战，核心瓶颈在于缺乏对细胞层面药物机制的系统理解。虽然单细胞测序技术提供了高分辨率观察，但实验覆盖所有基因组合的成本极高。现有的计算预测方法（如基于基础模型的 scGPT 或基于知识图谱的 GEARS）存在局限性：基础模型往往是“黑盒”，缺乏生物可解释性；而纯知识驱动的方法受限于先验知识的不完整性。
**核心问题：** 如何构建一个既能利用大规模数据模式，又能整合结构化生物学知识的“虚拟细胞”模型，以准确预测单细胞在单基因或多基因组合扰动下的转录组响应。

#### 2. 方法论
scPert 采用基于 Transformer 的多模态融合架构，其核心思想是协同大语言模型（LLM）的语义理解能力与生物知识图谱（KG）的精确逻辑。
*   **多模态嵌入融合：**
    *   **知识图谱嵌入（KGE）：** 利用 CompGCN 在 Hetionet（包含 4.7 万个节点和 220 万个关系）上学习基因的结构化表示。
    *   **LLM 上下文嵌入：** 提取 scGPT 预训练模型中的功能化表示。
    *   **基因特异性编码：** 捕捉基因自身的身份信息。
*   **架构细节：**
    *   **层级融合：** 通过多层感知机（MLP）将 KG 和 LLM 嵌入融合，并设计了专门的组合扰动融合模块来处理非加性效应。
    *   **Transformer 骨干：** 8 层、8 头的 Transformer 架构，引入内存高效的注意力机制以处理大规模基因集。
*   **复合损失函数（Multi-objective Loss）：**
    *   **FocalMSE：** 根据样本难度自适应调整权重，强调表达量变化大的基因。
    *   **方向损失（Direction Loss）：** 强制模型学习正确的基因上调/下调模式。
    *   **余弦相似度与加权 MSE：** 保持全局表达特征和基因异质性。

#### 3. 实验设计
*   **数据集：** 使用了 5 个主流单细胞扰动数据集：Norman（组合扰动）、Adamson、Dixit、Replogle K562 和 Replogle RPE1（大规模全基因组筛选）。
*   **Benchmark 策略：** 采用“留出基因”策略，测试模型对未见基因扰动的泛化能力。针对组合扰动，分为“Seen 0/1/2”（即训练集中见过 0、1 或 2 个相关单基因扰动）三种难度场景。
*   **对比方法：** GEARS（当前 SOTA）、scGPT、scGenePT、Scouter 和 biolord。
*   **评估指标：** MSE_DE（差异表达基因的均方误差）、Pearson_DE（相关性）和 Centroid Accuracy（质心准确率）。

#### 4. 资源与算力
论文中提到了模型使用了 8 层 Transformer 和 512 维隐藏层，并采用了“内存高效的注意力机制”来处理计算复杂性。然而，**文中未明确说明具体的 GPU 型号、数量以及训练所需的总时长**。

#### 5. 实验数量与充分性
*   **实验规模：** 涵盖了从小型筛选（20 个扰动）到大规模全基因组筛选（1543 个扰动）的多种场景，涉及超过 16 万个细胞。
*   **消融实验：** 专门移除了 Hetionet 知识图谱进行对比，证明了结构化知识对提高质心准确率的必要性。
*   **案例研究：** 深入分析了 p53 通路、PD-L1 免疫检查点调节以及 42 个癌症依赖基因的预测。
*   **充分性评价：** 实验设计较为全面，通过跨数据集、跨扰动类型（单/双基因）以及生物学功能验证，客观地评估了模型的鲁棒性和实用性。

#### 6. 主要结论与发现
*   **性能领先：** scPert 在所有基准测试中均表现出竞争性或领先的性能。在 Norman 数据集的“Seen 2”场景下，MSE_DE 比 GEARS 降低了 56.6%。
*   **生物学发现：** 成功预测了 p53 通路的动态响应（相关性 r=0.927），并准确识别了 PD-L1 的正向和负向调节因子。
*   **非加性效应：** 模型能准确捕捉基因间的协同、拮抗等非线性相互作用，而不仅仅是简单的线性叠加。
*   **靶点识别：** 在癌症依赖基因分析中，76.9% 的预测达到了优秀质量，成功识别出 RUNX1 等关键下游靶点。

#### 7. 优点
*   **多模态融合：** 首次深度整合了 LLM 的语义特征与 KG 的拓扑特征，弥补了单一方法的短板。
*   **生物学约束：** 通过方向损失和知识图谱约束，使预测结果更符合生物学常理，而非纯粹的统计拟合。
*   **泛化能力强：** 在处理完全未见的基因组合时表现稳健，对药物靶点发现具有极高的实用价值。

#### 8. 不足与局限
*   **跨数据集迁移：** 目前仍需针对特定数据集进行训练，尚未实现完全的零样本跨数据集泛化。
*   **知识图谱依赖：** 模型的上限受限于现有知识图谱的完整性，对于研究极少的“暗基因”预测能力可能受限。
*   **计算成本：** 尽管有内存优化，但处理全基因组级别的相互作用仍面临较高的计算压力。
*   **可解释性挑战：** 虽然引入了知识图谱，但多层 Transformer 内部的复杂嵌入融合过程仍存在一定的解释难度。

（完）
