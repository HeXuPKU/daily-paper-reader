---
title: "OmicClaw: executable and reproducible natural-language multi-omics analysis over the unified OmicVerse ecosystem."
title_zh: OmicClaw：基于统一 OmicVerse 生态系统的可执行且可重复的自然语言多组学分析
authors: "Zeng, Z., Wang, X., Luo, Z., Zheng, Y., Hu, L., Xing, C., Du, H."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.13.711464v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于多组学分析的自然语言框架和智能体
tldr: OmicClaw是一个基于OmicVerse生态系统和J.A.R.V.I.S.运行时的可执行自然语言多组学分析框架。它解决了多组学分析中工具碎片化和重现性差的问题，通过将100多种方法整合到统一的AnnData接口，并利用状态感知的执行层将自然语言指令转化为可追溯的工作流。在涵盖单细胞、空间转录组等15项任务的基准测试中，OmicClaw显著提升了分析性能，为人类与AI在多组学研究中的协作提供了可靠基础。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711464-v2/fig-001.webp\", \"caption\": \"Fig. 1 | J.A.R.V.I.S. extends OmicVerse into a unified, agentic ecosystem for interoperable multi-omics analysis. a, Overview of the OmicClaw ecosystem augmented with J.A.R.V.I.S., an agentic layer that unifies heterogeneous bioinformatics tools through a shared registry and execution framework. Native Python users can directly invoke OmicVerse functions through ov.Agent, whereas third-party or external agent clients can access the same functionality through the MCP server and tool-calling interface. At the core of the system, functions registered by @register_function are organized into a centralized tool registry/catalog spanning multiple OmicVerse modules, including alignment, bulk, single-cell, spatial, visualization, preprocessing and LLM-enabled analysis. Requests are routed through a dispatcher and executor/plan runner, with provenance tracking, directed acyclic graph (DAG) recording and logs enabling transparent monitoring and reproducible execution. The outer loop illustrates the\", \"page\": 4, \"index\": 1, \"width\": 976, \"height\": 579}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711464-v2/fig-002.webp\", \"caption\": \"Fig. 2 | OmicVerse provides a unified ecosystem for interoperable multi-omics analysis across sequencing, single-cell, spatial, bulk and agentic workflows. a, The ov.alignment module supports preprocessing of raw sequencing data, converting FASTQ reads into count matrices for conventional and single-cell RNA-sequencing workflows, including velocity-compatible outputs. OmicVerse is built to interface with modern computational backends and machine-learning frameworks, including PyTorch, PyG and Apple MLX. b, The ov.preprocess module standardizes core preprocessing steps for single-cell analysis, including quality control, highly variable gene selection, dimensionality reduction and batch correction. These functions provide a common entry point for downstream analyses while shielding users from method-specific implementation differences. c, The ov.single module unifies major categories of single-cell downstream analysis within a shared interface. Supported tasks include clustering, automated cell type annotation, trajectory inference and RNA velocity, and higherorder cell structure analyses such as cell–cell interaction (CCI), differential expression (DEG) and gene regulatory network (GRN) inference. Representative integrated methods are shown for each task, illustrating that OmicVerse provides access to diverse algorithms through a consistent API rather than isolated tool-specific wrappers. d, The ov.space module extends the same design principle to spatial omics, covering cell segmentation, cluster mapping and alignment across sections, deconvolution and spatial dynamics analysis. This enables spatial workflows to be integrated with the broader OmicVerse analytical ecosystem. e, The ov.Agent module provides a language-driven interface to the OmicVerse ecosystem. Users supply an AnnData object together with a natural-language task description, which is parsed by an LLM and mapped onto registered functions through a function registry. The selected functions are then executed programmatically, enabling\", \"page\": 6, \"index\": 2, \"width\": 976, \"height\": 839}]"
motivation: 针对当前多组学分析中工具接口不兼容、依赖复杂及工作流难以重现的碎片化现状。
method: 开发了集成100多种方法的OmicVerse生态系统，并结合J.A.R.V.I.S.运行时将自然语言请求转化为可验证、可修复且可追溯的执行工作流。
result: 在涉及单细胞RNA测序、空间转录组等15项复杂任务的基准测试中，该框架在多步长工作流中的表现优于传统的大语言模型基线。
conclusion: OmicClaw为现代多组学研究提供了一个实用、可重现且支持人机协作的自然语言分析平台。
---

## 摘要
块体（bulk）、单细胞和空间组学的进展改变了生物学发现，但分析在具有不兼容接口、异构依赖项和有限工作流可重复性的软件包之间仍然是支离破碎的。在此，我们介绍了 OmicClaw，这是一个基于统一 OmicVerse 生态系统和 J.A.R.V.I.S. 运行时的可执行自然语言多组学分析框架。OmicVerse 将上游处理、预处理、单细胞、空间、块体转录组和基础模型工作流组织到一个以 AnnData 为中心的共享接口中，涵盖了 100 多种方法。J.A.R.V.I.S. 通过一个基于注册表、状态感知且可恢复的执行层，将该生态系统转换为一个有界的分析动作空间。该执行层验证先决条件、保留溯源并支持迭代修复，同时使对话式、笔记本式和可视化界面能够在相同的实时分析状态下运行。OmicClaw 并不依赖于不受约束的代码生成，而是将用户请求转换为针对实时组学对象的可追溯工作流。在涵盖 scRNA-seq、空间转录组学、RNA 速率、scATAC-seq、CITE-seq 和多组学分析的 15 个任务基准测试中，ov.Agent 相比于纯 one-shot 大语言模型基线，在基于评分标准的性能上有所提升，特别是在长跨度的多步工作流中。OmicClaw 进一步通过兼容 MCP 的服务器支持外部智能体访问，并提供了一个面向初学者的友好 Web 平台，用于交互式分析、代码执行和百万级可视化。总之，OmicClaw 为现代多组学研究中可重复的人机协作提供了实用的基础。

## Abstract
Advances in bulk, single-cell and spatial omics have transformed biological discovery, yet analysis remains fragmented across packages with incompatible interfaces, heterogeneous dependencies and limited workflow reproducibility. Here, we present OmicClaw, an executable natural-language framework for multi-omics analysis built on the unified OmicVerse ecosystem and the J.A.R.V.I.S. runtime. OmicVerse organizes upstream processing, preprocessing, single-cell, spatial, bulk-transcriptomic and foundation-model workflows into a shared AnnData-centered interface spanning more than 100 methods. J.A.R.V.I.S. converts this ecosystem into a bounded analytical action space through a registry-grounded, state-aware and recoverable execution layer that validates prerequisites, preserves provenance and supports iterative repair, while enabling conversational, notebook and visual interfaces to operate over the same live analytical state. Rather than relying on unconstrained code generation, OmicClaw translates user requests into traceable workflows over live omics objects. Across a benchmark of 15 tasks spanning scRNA-seq, spatial transcriptomics, RNA velocity, scATAC-seq, CITE-seq and multiome analysis, ov.Agent improved rubric-based performance over bare one-shot large language model baselines, particularly for long-horizon multi-step workflows. OmicClaw further supports external agent access through an MCP-compatible server and a beginner-friendly web platform for interactive analysis, code execution and million-scale visualization. Together, OmicClaw provides a practical foundation for reproducible human-AI collaboration in modern multi-omics research

---

## 论文详细总结（自动生成）

以下是对论文《OmicClaw: executable and reproducible natural-language multi-omics analysis over the unified OmicVerse ecosystem》的结构化总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：多组学分析（包括单细胞、空间转录组、块体转录组等）目前面临工具碎片化严重、接口不兼容、环境依赖复杂以及分析流程难以重现等挑战。
*   **研究动机**：虽然大语言模型（LLM）在辅助编程方面表现出色，但在生物信息学领域，直接生成的代码往往存在幻觉、无法处理复杂的依赖关系，且缺乏对分析状态的感知。
*   **整体含义**：论文提出了 OmicClaw 框架，旨在通过统一的生态系统（OmicVerse）和智能执行层（J.A.R.V.I.S.），将自然语言指令转化为可执行、可验证且可重复的多组学分析工作流。

### 2. 论文提出的方法论
*   **核心思想**：构建一个“有界”的分析动作空间。不依赖 LLM 生成不受约束的代码，而是让 LLM 在预定义的、经过验证的工具注册表中选择并组合功能。
*   **关键技术细节**：
    *   **OmicVerse 生态系统**：整合了 100 多种生物信息学方法，涵盖从原始数据比对、预处理到高级分析（如细胞间通讯、基因调控网络）的全流程，统一以 `AnnData` 为核心数据结构。
    *   **J.A.R.V.I.S. 运行时**：一个状态感知的执行层。它通过 `@register_function` 装饰器管理工具，能够验证执行前提条件（如是否已进行归一化），并记录溯源信息。
    *   **执行逻辑**：包含任务分发器（Dispatcher）和计划执行器（Plan Runner）。支持迭代修复（Iterative Repair），即当某一步骤失败时，智能体能根据错误日志自动调整策略。
    *   **多接口支持**：提供 Python API (`ov.Agent`)、兼容 MCP 协议的服务器（支持外部智能体如 Claude/GPT 调用）以及面向初学者的 Web 交互平台。

### 3. 实验设计
*   **数据集/场景**：涵盖了单细胞 RNA 测序（scRNA-seq）、空间转录组学、RNA 速率分析、scATAC-seq、CITE-seq 以及多组学整合分析。
*   **Benchmark**：设计了 15 个复杂的分析任务，这些任务通常涉及多个步骤（如：加载数据 -> 质控 -> 降维 -> 聚类 -> 差异表达分析）。
*   **对比方法**：将 `ov.Agent`（基于 OmicClaw）与纯 One-shot LLM（如直接使用 GPT-4o 生成代码）进行对比。评价指标基于评分标准（Rubric-based），包括代码正确性、步骤完整性和最终执行结果。

### 4. 资源与算力
*   **算力说明**：论文中未详细列出训练 LLM 所需的具体 GPU 型号或时长，因为该框架主要利用现有的预训练大模型（如 GPT-4o）作为推理引擎。
*   **后端支持**：提到 OmicVerse 支持现代计算后端，包括 PyTorch、PyG（图神经网络）以及 Apple MLX（针对苹果芯片的优化），并能处理百万级细胞的可视化。

### 5. 实验数量与充分性
*   **实验规模**：通过 15 个涵盖不同组学类型的代表性任务进行评估。
*   **充分性评价**：实验设计较为全面，覆盖了当前多组学研究的主流任务。通过对比长跨度（Long-horizon）工作流的表现，客观地展示了该框架在处理复杂逻辑时的优势。然而，实验主要集中在功能实现和准确性上，对于极端大规模数据集下的计算效率对比尚有提升空间。

### 6. 论文的主要结论与发现
*   **性能提升**：在多步长、复杂的多组学分析任务中，OmicClaw 的表现显著优于直接生成代码的 LLM 基线。
*   **可靠性**：通过工具注册和状态验证，极大地减少了 LLM 的“幻觉”问题，确保了分析步骤的生物学合理性。
*   **可重复性**：系统自动生成的有向无环图（DAG）和详细日志，使得任何自然语言驱动的分析过程都可以被精确追溯和重现。

### 7. 优点
*   **生态统一**：将零散的生物信息学工具整合进统一的 API，降低了学习成本。
*   **人机协作**：支持对话式分析与代码执行的无缝切换，既适合初学者，也方便专家微调。
*   **可扩展性**：通过 MCP 协议，可以轻松集成到现有的 AI 智能体生态中。
*   **鲁棒性**：具备自动错误修复和前提条件检查机制。

### 8. 不足与局限
*   **能力边界**：分析能力受限于 OmicVerse 注册表中的工具集，对于极少数极其冷门或最新的算法，可能需要手动扩展注册表。
*   **模型依赖**：框架的效果高度依赖于底层 LLM（如 GPT-4o）的推理能力，模型本身的偏差可能影响分析建议。
*   **评估主观性**：虽然使用了评分标准，但生物信息学分析的“正确性”有时具有一定的开放性，评估过程可能存在一定的主观偏好。

（完）
