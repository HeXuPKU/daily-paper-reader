---
title: "OmicClaw: executable and reproducible natural-language multi-omics analysis over the unified OmicVerse ecosystem."
title_zh: OmicClaw：基于统一 OmicVerse 生态系统的可执行且可重复的自然语言多组学分析
authors: "Zeng, Z., Wang, X., Luo, Z., Zheng, Y., Hu, L., Xing, C., Du, H."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.13.711464v2.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 使用基础模型和智能体的自然语言多组学分析框架
tldr: OmicClaw是一个基于OmicVerse生态系统和J.A.R.V.I.S.运行时的可执行自然语言多组学分析框架。它通过统一的AnnData接口整合了100多种分析方法，解决了多组学分析中工具碎片化和复现性差的问题。该框架利用大模型将用户指令转化为可追踪的工作流，支持单细胞、空间转录组等多种任务，显著提升了复杂分析的效率与准确性，为人类与AI协作的组学研究提供了新范式。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711464-v2/fig-001.webp\", \"caption\": \"Fig. 1 | J.A.R.V.I.S. extends OmicVerse into a unified, agentic ecosystem for interoperable multi-omics analysis. a, Overview of the OmicClaw ecosystem augmented with J.A.R.V.I.S., an agentic layer that unifies heterogeneous bioinformatics tools through a shared registry and execution framework. Native Python users can directly invoke OmicVerse functions through ov.Agent, whereas third-party or external agent clients can access the same functionality through the MCP server and tool-calling interface. At the core of the system, functions registered by @register_function are organized into a centralized tool registry/catalog spanning multiple OmicVerse modules, including alignment, bulk, single-cell, spatial, visualization, preprocessing and LLM-enabled analysis. Requests are routed through a dispatcher and executor/plan runner, with provenance tracking, directed acyclic graph (DAG) recording and logs enabling transparent monitoring and reproducible execution. The outer loop illustrates the\", \"page\": 4, \"index\": 1, \"width\": 976, \"height\": 579}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711464-v2/fig-002.webp\", \"caption\": \"Fig. 2 | OmicVerse provides a unified ecosystem for interoperable multi-omics analysis across sequencing, single-cell, spatial, bulk and agentic workflows. a, The ov.alignment module supports preprocessing of raw sequencing data, converting FASTQ reads into count matrices for conventional and single-cell RNA-sequencing workflows, including velocity-compatible outputs. OmicVerse is built to interface with modern computational backends and machine-learning frameworks, including PyTorch, PyG and Apple MLX. b, The ov.preprocess module standardizes core preprocessing steps for single-cell analysis, including quality control, highly variable gene selection, dimensionality reduction and batch correction. These functions provide a common entry point for downstream analyses while shielding users from method-specific implementation differences. c, The ov.single module unifies major categories of single-cell downstream analysis within a shared interface. Supported tasks include clustering, automated cell type annotation, trajectory inference and RNA velocity, and higherorder cell structure analyses such as cell–cell interaction (CCI), differential expression (DEG) and gene regulatory network (GRN) inference. Representative integrated methods are shown for each task, illustrating that OmicVerse provides access to diverse algorithms through a consistent API rather than isolated tool-specific wrappers. d, The ov.space module extends the same design principle to spatial omics, covering cell segmentation, cluster mapping and alignment across sections, deconvolution and spatial dynamics analysis. This enables spatial workflows to be integrated with the broader OmicVerse analytical ecosystem. e, The ov.Agent module provides a language-driven interface to the OmicVerse ecosystem. Users supply an AnnData object together with a natural-language task description, which is parsed by an LLM and mapped onto registered functions through a function registry. The selected functions are then executed programmatically, enabling\", \"page\": 6, \"index\": 2, \"width\": 976, \"height\": 839}]"
motivation: 针对当前多组学分析中工具接口不兼容、依赖复杂及工作流难以复现的碎片化现状。
method: 构建了基于OmicVerse生态的OmicClaw框架，利用J.A.R.V.I.S.运行时将自然语言指令转化为受控且可恢复的分析动作。
result: 在涵盖单细胞、空间转录组等15项任务的基准测试中，ov.Agent在多步长工作流中的表现显著优于基础大模型。
conclusion: OmicClaw为现代多组学研究提供了一个可复现、交互式且支持AI协作的统一分析平台。
---

## 摘要
批量（bulk）、单细胞和空间组学的进展改变了生物学发现，但分析工作仍分散在具有不兼容接口、异构依赖项且工作流可重复性有限的各种软件包中。在这里，我们介绍了 OmicClaw，这是一个基于统一 OmicVerse 生态系统和 J.A.R.V.I.S. 运行时的可执行自然语言多组学分析框架。OmicVerse 将上游处理、预处理、单细胞、空间、批量转录组学和基础模型工作流整合到一个以 AnnData 为中心的共享接口中，涵盖了 100 多种方法。J.A.R.V.I.S. 通过一个基于注册表、状态感知且可恢复的执行层，将该生态系统转换为有界的分析动作空间。该执行层可验证先决条件、保留溯源信息并支持迭代修复，同时允许对话式、笔记本式和可视化界面在相同的实时分析状态下运行。OmicClaw 并不依赖于不受约束的代码生成，而是将用户请求转化为针对实时组学对象的可追溯工作流。在涵盖 scRNA-seq、空间转录组学、RNA 速率、scATAC-seq、CITE-seq 和多组学分析的 15 个任务基准测试中，ov.Agent 相比于纯 one-shot 大语言模型基准，在基于评分标准的性能上有所提升，尤其是在长跨度的多步工作流中。OmicClaw 还通过兼容 MCP 的服务器支持外部智能体访问，并提供了一个面向初学者的友好 Web 平台，用于交互式分析、代码执行和百万级规模的可视化。总之，OmicClaw 为现代多组学研究中可重复的人机协作提供了实用的基础。

## Abstract
Advances in bulk, single-cell and spatial omics have transformed biological discovery, yet analysis remains fragmented across packages with incompatible interfaces, heterogeneous dependencies and limited workflow reproducibility. Here, we present OmicClaw, an executable natural-language framework for multi-omics analysis built on the unified OmicVerse ecosystem and the J.A.R.V.I.S. runtime. OmicVerse organizes upstream processing, preprocessing, single-cell, spatial, bulk-transcriptomic and foundation-model workflows into a shared AnnData-centered interface spanning more than 100 methods. J.A.R.V.I.S. converts this ecosystem into a bounded analytical action space through a registry-grounded, state-aware and recoverable execution layer that validates prerequisites, preserves provenance and supports iterative repair, while enabling conversational, notebook and visual interfaces to operate over the same live analytical state. Rather than relying on unconstrained code generation, OmicClaw translates user requests into traceable workflows over live omics objects. Across a benchmark of 15 tasks spanning scRNA-seq, spatial transcriptomics, RNA velocity, scATAC-seq, CITE-seq and multiome analysis, ov.Agent improved rubric-based performance over bare one-shot large language model baselines, particularly for long-horizon multi-step workflows. OmicClaw further supports external agent access through an MCP-compatible server and a beginner-friendly web platform for interactive analysis, code execution and million-scale visualization. Together, OmicClaw provides a practical foundation for reproducible human-AI collaboration in modern multi-omics research

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究动机**：当前的批量（bulk）、单细胞和空间多组学分析面临严重的“软件瓶颈”。分析任务（如聚类、注释、轨迹推断等）散落在接口不兼容、依赖关系复杂且对象标准不一的独立软件包中。这导致用户需要编写大量包装代码，且分析流程的可重复性极差。
*   **核心问题**：如何构建一个统一的生态系统，使自然语言指令能够转化为可执行、可复现且跨模态的组学分析工作流，降低生物学家的技术门槛。

### 2. 论文提出的方法论
*   **核心思想**：通过 **OmicVerse** 提供统一的分析底座，利用 **J.A.R.V.I.S.** 运行时作为执行层，将自然语言意图映射到受控的、有界的函数空间中。
*   **关键技术细节**：
    *   **OmicVerse 生态系统**：以 `AnnData` 为中心，整合了超过 100 种方法，涵盖从原始数据比对（ov.alignment）到基础模型（ov.fm）的完整链路。
    *   **J.A.R.V.I.S. 注册机制**：使用 `@register_function` 将函数暴露给中央注册表。这改变了 LLM 自由生成代码的模式，转为“基于注册表的工具调用”，有效防止代码幻觉。
    *   **状态感知执行层**：维护执行上下文（包括活跃对象、历史记录、失败尝试），支持多轮对话和迭代修复。
    *   **MCP 协议支持**：通过模型上下文协议（Model Context Protocol）使外部智能体（如 Claude Desktop）能直接调用其分析工具。
    *   **算法流程**：用户请求 -> 意图解析 -> 注册表检索 -> 先决条件验证（如检查 PCA 是否已完成） -> 调度执行 -> 结果收集与溯源记录。

### 3. 实验设计
*   **数据集与场景**：涵盖了 PBMC3k/68k、胰腺集成数据、齿状回（RNA 速率）、Visium（空间转录组）、E18 鼠脑（scATAC-seq/Multiome）等多种经典数据集。
*   **基准测试（Benchmark）**：设计了 15 个任务（T1–T15），包括质控、预处理、批次校正、RNA 速率分析、空间去卷积、多模态集成等。
*   **对比方法**：
    *   **ov.Agent**：本文提出的智能体框架。
    *   **Bare One-shot LLM**：直接让大模型生成代码的基准模式。
    *   **底层性能对比**：对比了 OmicVerse 与 Scanpy 在不同细胞规模（最高 10 万细胞）下的运行速度和结果一致性。
*   **评估模型**：测试了 GPT-4o、Claude 3.5 Sonnet 等 7 种主流大模型在框架下的表现。

### 4. 资源与算力
*   **硬件支持**：框架支持 CUDA 加速后端和 Apple Metal (MPS) 环境。
*   **算力说明**：文中未明确给出训练智能体所需的总算力（因为该框架主要基于推理和工具调用），但提到了基准测试中使用了专用服务器和 API 访问权限。在性能测试中，展示了处理 10 万级细胞规模时的内存和时间消耗。

### 5. 实验数量与充分性
*   **实验规模**：
    *   15 个跨模态任务，每个任务均有详细的评分标准（执行成功率、科学合理性、可重复性等）。
    *   对比了 7 种不同的基础模型，验证了框架的通用性。
    *   包含对 OmicVerse 核心算法（如 HVG 选择、PCA、UMAP）与行业标准（Scanpy）的等效性验证。
*   **充分性评价**：实验设计较为全面，不仅验证了 AI 智能体的逻辑正确性，还通过性能基准测试证明了底层工具链在处理大规模数据时的实用性。

### 6. 论文的主要结论与发现
*   **性能提升**：在长跨度、多步骤的工作流中，`ov.Agent` 的表现显著优于直接生成代码的模式，尤其是在处理复杂的先决条件验证时。
*   **缩小模型差距**：该框架能缩小通用模型与高级推理模型在组学任务上的表现差距。
*   **生态价值**：OmicVerse 已被证明是一个稳健的底座，支持了多篇高影响力论文的分析工作。
*   **可复现性**：通过 J.A.R.V.I.S. 的溯源记录，自然语言分析不再是“黑盒”，而是可追踪、可导出的标准工作流。

### 7. 优点
*   **统一性**：解决了组学分析工具碎片化的痛点，提供了从 Bulk 到单细胞再到空间的“全家桶”接口。
*   **安全性与可靠性**：通过注册表约束 LLM 行为，大幅降低了代码幻觉和非法参数调用的风险。
*   **易用性**：提供了 Web 平台和 GUI，使不具备编程能力的实验生物学家也能进行复杂的生物信息学分析。
*   **前瞻性**：支持 MCP 协议和生物学基础模型（Foundation Models），紧跟 AI 发展趋势。

### 8. 不足与局限
*   **模型依赖**：分析的深度和逻辑推理上限仍受限于底层 LLM 的能力。
*   **偏差风险**：如果注册表中的函数描述或示例存在偏差，可能会引导智能体选择次优的分析方法。
*   **应用限制**：对于极其前沿、尚未整合进 OmicVerse 生态的新算法，智能体可能无法直接通过注册表调用，仍需手动编写扩展。
*   **硬件门槛**：部分高级功能（如大规模 GPU 加速）对本地硬件有一定要求。

（完）
