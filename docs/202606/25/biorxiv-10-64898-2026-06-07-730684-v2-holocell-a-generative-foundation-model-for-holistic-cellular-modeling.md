---
title: "HoloCell: A Generative Foundation Model for Holistic Cellular Modeling"
title_zh: HoloCell：一种用于全息细胞建模的生成式基础模型
authors: "Jiang, Q., Li, Z., Hu, B., Bie, Y., Li, K., Li, Q., Jin, P., He, Y., Deng, P., Wang, Z., Chen, X., Qin, T., Liu, H., Jiang, R., Yin, Q."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730684v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 用于整体细胞建模的生成基础模型
tldr: 单细胞多组学数据整合面临模态缺失和统一表示挑战。提出HoloCell，首个覆盖表观基因组、转录组和蛋白质组的生成式基础模型，含8.6亿参数，预训练于4.68亿细胞图谱。采用层次化tokenization编码调控元件、基因和蛋白，通过迭代扩散与remasking实现灵活跨模态生成。在单组学表示、多组学整合与对齐、跨模态生成任务上性能优越，为虚拟细胞概念提供统一框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法多针对特定模态或模态对，依赖配对数据，缺乏统一整合不同组学并鲁棒处理模态缺失的框架。
method: 构建860M参数生成式基础模型HoloCell，引入层次化tokenization策略，将顺式调控元件、基因和蛋白编码为结构令牌，采用迭代扩散和remasking进行跨模态生成。
result: 在单组学表示学习、多组学配对整合、非配对对齐及跨模态生成任务中，HoloCell性能优于现有方法，实现灵活生成顺序。
conclusion: HoloCell作为首个覆盖三大单细胞组学的生成式基础模型，提供了系统表征与生成模拟的统一框架，推动虚拟细胞概念发展。
---

## 摘要
单细胞多组学技术最近取得了进展，能够对单个细胞内的表观基因组、转录组和蛋白质组层进行剖析，为将细胞状态表征为集成的生物系统提供了新的机会。然而，开发一个能够无缝整合不同组学模态并稳健应对异质性模态缺失的统一框架仍然具有挑战性。现有方法通常针对特定模态或模态对设计，依赖于数据集特定的训练或配对测量。在这里，我们提出了HoloCell，据我们所知，这是首个用于跨所有三种主要单细胞组学模态（即表观基因组学、转录组学和蛋白质组学）进行联合表示学习和生成式建模的生成式基础模型。HoloCell包含超过8.6亿个参数，并在人类多组学语料库上进行了预训练，该语料库包含约4.68亿个跨这三种组学层的单细胞谱，对应超过4250亿个标记。HoloCell引入了一种简单但具有生物学动机的层次化标记化策略，将顺式调控元件、基因和蛋白质编码为共享建模框架内的结构化标记。我们在单组学表示学习、配对多组学整合、非配对多组学对齐以及通过迭代扩散和重掩码的跨模态生成上评估了HoloCell，展示了其在多种组学任务中的优越性能和灵活性。从表示的角度来看，HoloCell提供了跨多个组学层的细胞状态的统一数字映射，将细胞异质性捕获为一个集成系统。从生成的角度来看，其迭代扩散和重掩码框架允许超越固定从左到右因果关系的灵活生成顺序，实现了多组学信息流的计算机模拟。总之，这些能力使HoloCell成为迈向虚拟细胞这一新兴概念的通用基础模型，在统一框架内提供细胞系统的系统表征和生成模拟。

## Abstract
Single-cell multi-omics technologies have recently advanced to enable the profiling of epigenomic, transcriptomic, and proteomic layers within individual cells, offering new opportunities to characterize cellular states as integrated biological systems. However, developing a unified framework that can seamlessly integrate diverse omics modalities and remain robust to heterogeneous modality missingness remains challenging. Existing methods are often designed for specific modalities or modality pairs, relying on dataset-specific training or paired measurements. Here we present HoloCell, to our knowledge the first generative foundation model for joint representation learning and generative modeling across all three major single-cell omics modalities, i.e., epigenomics, transcriptomics, and proteomics. HoloCell contains over 860 million parameters and is pretrained on the Human-Multi-Omics-Corpus, which comprises approximately 468 million single-cell profiles across these three omics layers, corresponding to over 425 billion tokens. HoloCell introduces a a simple yet biologically motivated hierarchical tokenization strategy that encodes cis-regulatory elements, genes, and proteins as structured tokens within a shared modeling framework. We evaluated HoloCell across single-omics representation learning, paired multi-omics integration, unpaired multi-omics alignment, and cross-modal generation via iterative diffusion and remasking, demonstrating its superior performance and flexibility across diverse omics tasks. From a representation perspective, HoloCell provides a unified digital mapping of cellular states across multiple omics layers, capturing cell heterogeneity as an integrated system. From a generation perspective, its iterative diffusion and remasking frame-work permits flexible generation orders beyond fixed left-to-right causality, enabling in silico simulation of multi-omics information flow. Together, these capabilities position HoloCell as a versatile foundation model toward the emerging concept of a virtual cell, offering both systematic characterization and generative simulation of cellular systems within a unified framework.

---

## 论文详细总结（自动生成）

# 论文详细总结：HoloCell：一种用于全息细胞建模的生成式基础模型

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：单细胞多组学技术虽能同时测量表观基因组、转录组和蛋白质组，但缺乏一个统一的框架来无缝整合这三种异质组学模态，并鲁棒地处理现实数据中常见的模态缺失（如部分细胞仅测得RNA，另一部分仅测得ATAC或蛋白质）。
- **研究动机**：现有方法多针对特定模态或模态对设计，依赖数据集特定的配对训练，无法在统一架构中实现跨三种主要组学的联合表征与灵活生成。
- **整体含义**：该工作旨在构建首个覆盖表观基因组、转录组和蛋白质组的生成式基础模型，为“虚拟细胞”概念提供统一的表征与生成模拟框架，推动从数据驱动的细胞状态描述向计算模拟的多组学信息流理解迈进。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：采用生成式基础模型范式，在大规模单细胞多组学语料上预训练一个Transformer，通过层次化tokenization将生物学实体（顺式调控元件、基因、蛋白质）编码为结构化标记，并利用迭代扩散与重掩码实现灵活的顺序无关的跨模态生成。
- **关键技术细节**：
  - **层次化tokenization策略**：
    - 第一层：将顺式调控元件（如启动子、增强子区域）编码为token，反映表观基因组信息（例如染色质可及性）。
    - 第二层：将基因表达量编码为token，反映转录组信息。
    - 第三层：将蛋白质丰度编码为token，反映蛋白质组信息。
    - 所有token被组织在一个共享的建模框架内，模型学习跨模态的上下文依赖关系。
  - **模型架构**：包含超过8.6亿参数的Transformer，预训练于约4.68亿个单细胞谱（对应超过4250亿个token）上。预训练语料名为Human-Multi-Omics-Corpus。
  - **生成机制**：采用迭代扩散与重掩码（iterative diffusion and remasking），允许任意顺序的生成（而非固定的从左到右因果生成），从而支持缺失模态的灵活填充和跨模态信息流的计算机模拟。
  - **训练目标**：类似masked language modeling，随机掩码某些模态的token，要求模型预测被掩码的内容，从而学习跨模态联合分布。

## 3. 实验设计：数据集、基准测试、对比方法

- **数据集**：预训练使用Human-Multi-Omics-Corpus（约4.68亿细胞，覆盖三大组学层）。下游评估可能涉及公共单细胞多组学数据集（如10x Multiome、CITE-seq等），但具体名称文中未详列，仅概述任务类型。
- **评估任务**：
  - 单组学表示学习（如单独对scRNA-seq或scATAC-seq或蛋白质组学进行细胞嵌入）。
  - 配对多组学整合（如同时对同一细胞的RNA+ATAC进行联合低维映射）。
  - 非配对多组学对齐（如将非配对的RNA和ATAC数据在共享空间中对齐）。
  - 跨模态生成（例如从RNA表达生成ATAC信号，或从ATAC生成蛋白质表达）。
- **基准（Benchmark）**：未明确列出所有对比方法，但声称在多项任务上“性能优于现有方法”。从摘要推断，可能对比了如scVI、scANVI、MOFA、scGLUE、TotalVI、Cobolt等典型多组学整合与生成方法。

## 4. 资源与算力

- 文中明确说明模型包含**超过8.6亿个参数**，预训练语料规模为约**4.68亿细胞（4250亿token）**。
- **未详细说明**使用的具体GPU型号、数量、训练时长、能耗等硬件资源。通常此类大规模预训练可能需要数百块GPU（如A100或H100）训练数周，但论文未提供。

## 5. 实验数量与充分性

- 实验覆盖四个主要任务类别（单组学表示、配对整合、非配对对齐、跨模态生成），每个类别下可能包含多个数据集和评估指标。从摘要看，实验设计较为全面，既评估了表征质量也评估了生成能力。
- **消融实验**：在方法部分提到“简单的层次化tokenization”，但未明确是否进行了tokenization策略消融、模型规模消融等。由于篇幅有限，可能未充分展示所有消融。
- **公平性与客观性**：声称性能优于现有方法，但未提供具体数值或统计显著性检验。对比方法的选择和超参数设置是否公平需查看完整论文，仅从摘要无法判断。整体实验设计方向合理，但充分性有待全文验证。

## 6. 论文的主要结论与发现

- HoloCell作为首个覆盖三大单细胞组学的生成式基础模型，在单组学表示、多组学整合、对齐及跨模态生成上均表现出优越性能。
- 其层次化tokenization能有效编码不同生物学信息层次，迭代扩散框架实现了灵活生成顺序，突破了传统因果模型的限制。
- 该模型提供了统一的细胞状态数字映射，支持跨模态信息流的计算机模拟（in silico simulation），为虚拟细胞概念奠定了基础。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：首次提出覆盖表观基因组、转录组和蛋白质组三大模态的生成式基础模型，填补了领域空白。
- **生物学驱动的设计**：层次化tokenization将顺式调控元件、基因、蛋白质分别编码，与生物信息流层次（调控→转录→翻译）一致，具有可解释性。
- **生成灵活性**：迭代扩散与重掩码机制允许任意缺失模态的填充，无需固定生成顺序，适用于实际中模态缺失的异质性场景。
- **规模巨大**：4.68亿细胞、4250亿token的预训练语料，为模型提供了丰富的跨模态生物学知识。
- **任务覆盖全面**：从表示学习到生成任务，从配对到非配对，全面评估了多组学基础模型的能力。

## 8. 不足与局限

- **实验细节缺失**：摘要中未提供具体定量结果（如指标数值），也未列出对比方法的具体名称，难以独立评估性能提升的幅度和统计显著性。
- **可复现性**：未公开模型权重、训练代码或数据预处理详情（至少在本摘要中），限制了其他研究者的验证和应用。
- **偏差风险**：预训练语料仅来自人类，可能缺乏跨物种泛化能力；且数据来源可能存在组织、个体、技术批次偏差，模型是否鲁棒未见分析。
- **应用限制**：模型参数8.6亿，推理和微调需要较高GPU资源；对于资源有限的研究团队或临床应用场景部署门槛高。
- **消融实验不足**：未评估不同tokenization方式、模型规模、训练数据规模对性能的影响，也未分析不同生成顺序的效果。
- **评估基准不透明**：未说明benchmark数据集的具体规模、复杂度和指标定义，未来与其他方法的公平比较可能存在困难。

（完）
