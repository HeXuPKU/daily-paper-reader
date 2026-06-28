---
title: "HoloCell: A Generative Foundation Model for Holistic Cellular Modeling"
title_zh: HoloCell：一种用于整体细胞建模的生成式基础模型
authors: "Jiang, Q., Li, Z., Hu, B., Bie, Y., Li, K., Li, Q., Jin, P., He, Y., Deng, P., Wang, Z., Chen, X., Qin, T., Liu, H., Jiang, R., Yin, Q."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730684v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 用于整体细胞建模的生成基础模型，直接关联虚拟细胞模型生成
tldr: 单细胞多组学技术虽已成熟，但缺乏能统一整合表观基因组、转录组和蛋白质组并鲁棒应对模态缺失的框架。HoloCell作为首个覆盖三大组学的生成式基础模型，通过8.6亿参数在4.68亿细胞上预训练，采用生物启发的分层token化策略编码调控元件、基因和蛋白质。在表示学习、多组学整合及跨模态生成任务中表现优异，其迭代扩散与重掩码机制支持灵活生成顺序。该模型为构建虚拟细胞提供了统一表征与生成模拟的基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法多针对特定模态设计，无法统一整合多组学且对模态缺失鲁棒性不足。
method: 提出HoloCell，含8.6亿参数，预训练于大规模多组学语料库，采用分层token化编码cis-regulatory元件、基因和蛋白质。
result: 在单组学表示、多组学整合与跨模态生成等任务上，HoloCell性能优于现有方法，支持灵活生成顺序。
conclusion: HoloCell作为基础模型，为虚拟细胞概念提供了统一的多组学表征和生成模拟框架。
---

## 摘要
单细胞多组学技术近期取得了进展，能够在单个细胞内分析表观基因组、转录组和蛋白质组层面，从而为将细胞状态作为综合生物系统进行表征提供了新机遇。然而，开发一个能够无缝整合不同组学模态并稳健处理异质性模态缺失的统一框架仍然具有挑战性。现有方法通常针对特定模态或模态对设计，依赖数据集特定训练或配对测量。本文提出HoloCell，据我们所知，这是首个针对所有三种主要单细胞组学模态（即表观基因组学、转录组学和蛋白质组学）进行联合表征学习和生成建模的生成式基础模型。HoloCell包含超过8.6亿参数，并在人类多组学语料库（Human-Multi-Omics-Corpus）上进行预训练，该语料库涵盖约4.68亿个单细胞剖面，对应超过4250亿个token。HoloCell引入了一种简单但具有生物学动机的分层标记化策略，将顺式调控元件、基因和蛋白质编码为共享建模框架内的结构化token。我们通过单组学表征学习、配对多组学整合、非配对多组学对齐以及通过迭代扩散和重掩码进行的跨模态生成对HoloCell进行了评估，证明了其在多种组学任务中的优越性能和灵活性。从表征角度看，HoloCell提供了跨多个组学层的细胞状态统一数字映射，将细胞异质性作为综合系统进行捕捉。从生成角度看，其迭代扩散和重掩码框架支持灵活的生成顺序，突破了固定的从左到右因果性，从而能够对多组学信息流进行计算机模拟。综合这些能力，HoloCell成为了一种多才多艺的基础模型，面向虚拟细胞这一新兴概念，在统一框架内提供了细胞系统的系统性表征和生成式模拟。

## Abstract
Single-cell multi-omics technologies have recently advanced to enable the profiling of epigenomic, transcriptomic, and proteomic layers within individual cells, offering new opportunities to characterize cellular states as integrated biological systems. However, developing a unified framework that can seamlessly integrate diverse omics modalities and remain robust to heterogeneous modality missingness remains challenging. Existing methods are often designed for specific modalities or modality pairs, relying on dataset-specific training or paired measurements. Here we present HoloCell, to our knowledge the first generative foundation model for joint representation learning and generative modeling across all three major single-cell omics modalities, i.e., epigenomics, transcriptomics, and proteomics. HoloCell contains over 860 million parameters and is pretrained on the Human-Multi-Omics-Corpus, which comprises approximately 468 million single-cell profiles across these three omics layers, corresponding to over 425 billion tokens. HoloCell introduces a a simple yet biologically motivated hierarchical tokenization strategy that encodes cis-regulatory elements, genes, and proteins as structured tokens within a shared modeling framework. We evaluated HoloCell across single-omics representation learning, paired multi-omics integration, unpaired multi-omics alignment, and cross-modal generation via iterative diffusion and remasking, demonstrating its superior performance and flexibility across diverse omics tasks. From a representation perspective, HoloCell provides a unified digital mapping of cellular states across multiple omics layers, capturing cell heterogeneity as an integrated system. From a generation perspective, its iterative diffusion and remasking frame-work permits flexible generation orders beyond fixed left-to-right causality, enabling in silico simulation of multi-omics information flow. Together, these capabilities position HoloCell as a versatile foundation model toward the emerging concept of a virtual cell, offering both systematic characterization and generative simulation of cellular systems within a unified framework.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：单细胞多组学技术已能同时测量单个细胞内的表观基因组、转录组和蛋白质组，为将细胞状态视为综合生物系统提供了机遇。
- **核心挑战**：现有方法多针对特定模态或模态对设计，依赖数据集特定的训练或配对测量，缺乏一个能够无缝整合不同组学模态、并鲁棒应对异质性模态缺失（即某些细胞缺少某一组学数据）的统一框架。
- **整体含义**：HoloCell旨在构建首个覆盖全部三种主要单细胞组学的生成式基础模型，为虚拟细胞概念提供统一的表征和生成模拟框架，推动细胞系统的系统性理解。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：提出一种基于扩散和重掩码的生成式基础模型，利用大规模多组学语料库预训练，实现跨模态联合表征与生成。
- **分层token化策略**：受生物学启发，将顺式调控元件、基因和蛋白质编码为共享建模框架内的结构化token，形成层次化的输入表示。
- **模型架构**：包含超过8.6亿参数，采用迭代扩散与重掩码机制，支持灵活的生成顺序（不限于固定的从左到右因果性），从而能够进行计算机模拟多组学信息流。
- **预训练语料**：在Human-Multi-Omics-Corpus上预训练，该语料库涵盖约4.68亿个单细胞剖面（对应超过4250亿个token），覆盖表观基因组、转录组和蛋白质组。
- **算法流程**（文字描述）：
  1. 输入：单细胞的多种组学数据（如ATAC-seq、RNA-seq、CITE-seq等）通过分层token化转化为结构化token序列。
  2. 预训练：在大量配对的、未配对的单细胞数据上进行掩码预测任务，学习跨模态的联合分布。
  3. 下游任务：通过迭代扩散（生成新数据）或重掩码（恢复缺失模态）进行单组学表征、多组学整合、跨模态生成等。

## 3. 实验设计

- **数据集/场景**：基于Human-Multi-Omics-Corpus（约4.68亿个单细胞剖面），包含表观基因组、转录组、蛋白质组数据。
- **评估任务**：
  - 单组学表征学习（如细胞类型分类、聚类）
  - 配对多组学整合（如整合同细胞的RNA+ATAC数据）
  - 非配对多组学对齐（如不同数据集的模态对齐）
  - 跨模态生成（从一种模态生成另一种模态，如从RNA推断ATAC）
- **Benchmark**：未详细列出具体对比方法名称（摘要未展开），但声称在多种任务上性能优于现有方法。
- **对比方法**：未明确列出，但隐含与现有单模态/双模态模型进行比较。

## 4. 资源与算力

- **明确说明**：模型包含超过8.6亿参数，预训练数据规模约4250亿token。
- **未说明**：具体使用的GPU型号、数量、训练时长等算力细节。从规模推测需大量计算资源，但论文摘要未提及。

## 5. 实验数量与充分性

- **实验组数**：摘要提及在单组学表征、配对整合、非配对对齐、跨模态生成四个主要类别上评估，每个类别可能包含多个子任务（如不同数据集、不同细胞类型）。但未给出具体消融实验或敏感性分析。
- **充分性评估**：实验覆盖基本任务全面，但缺乏消融实验（如不同token化策略、不同模型大小、不同预训练数据量）的详细报告。对比方法不透明，可能不够客观公平。需要查看完整论文才能充分判断。

## 6. 主要结论与发现

- HoloCell作为首个覆盖三种主要单细胞组学的生成式基础模型，在多个任务上取得优于现有方法的表现。
- 其分层token化策略有效捕捉了生物学层次结构。
- 迭代扩散与重掩码框架提供了灵活的生成顺序，突破了固定因果限制，能够模拟多组学信息流。
- 模型为虚拟细胞概念提供了统一的数字表征和生成模拟能力，有助于系统理解细胞异质性。

## 7. 优点

- **首创性**：第一个联合三种主要单细胞组学（表观基因组、转录组、蛋白质组）的生成式基础模型。
- **生物学驱动**：分层token化策略具有生物学动机，更贴合调控层次。
- **灵活性**：迭代扩散与重掩码支持任意生成顺序，适应不同下游任务。
- **大规模预训练**：使用4.68亿细胞、4250亿token的语料库，数据规模大，泛化潜力强。
- **统一框架**：同时提供表征学习和生成建模，兼具分析性和模拟性。

## 8. 不足与局限

- **算力消耗**：未披露训练成本，可能对复现和资源受限的研究团队不友好。
- **实验透明度**：未详细列出对比方法、数据集划分、评价指标细节，难以完全复现和公平比较。
- **缺失消融研究**：未展示不同组件（如token化方案、模型大小、预训练数据量）的影响，是否最优有待验证。
- **模态缺失处理**：虽然宣称鲁棒，但具体如何应对异质性模态缺失（如某些细胞只有RNA，无ATAC）未详细说明。
- **应用限制**：当前仅聚焦人类细胞，跨物种泛化性未知；仅覆盖三种组学，其他模态（如代谢组、空间组）未纳入。
- **评估覆盖**：可能局限于公开数据集，真实世界复杂场景（如罕见细胞类型、噪声数据）的稳健性未明确测试。

（完）
