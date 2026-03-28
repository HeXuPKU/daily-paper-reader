---
title: "OmicClaw: executable and reproducible natural-language multi-omics analysis over the unified OmicVerse ecosystem."
title_zh: OmicClaw：基于统一 OmicVerse 生态系统的可执行且可重复的自然语言多组学分析
authors: "Zeng, Z., Wang, X., Luo, Z., Zheng, Y., Hu, L., Xing, C., Du, H."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.13.711464v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 自然语言多组学分析与基础模型工作流
tldr: OmicClaw是一个基于OmicVerse生态系统和J.A.R.V.I.S.运行时的可执行自然语言多组学分析框架。它通过统一的AnnData接口整合了100多种分析方法，解决了多组学分析中工具碎片化和复现性差的问题。该框架利用大模型将用户指令转化为可追踪的工作流，支持单细胞、空间转录组等多种任务，显著提升了复杂分析的效率与准确性，为人类与AI协作的组学研究提供了新范式。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711464-v2/fig-001.webp\", \"caption\": \"Fig. 1 | J.A.R.V.I.S. extends OmicVerse into a unified, agentic ecosystem for interoperable multi-omics analysis. a, Overview of the OmicClaw ecosystem augmented with J.A.R.V.I.S., an agentic layer that unifies heterogeneous bioinformatics tools through a shared registry and execution framework. Native Python users can directly invoke OmicVerse functions through ov.Agent, whereas third-party or external agent clients can access the same functionality through the MCP server and tool-calling interface. At the core of the system, functions registered by @register_function are organized into a centralized tool registry/catalog spanning multiple OmicVerse modules, including alignment, bulk, single-cell, spatial, visualization, preprocessing and LLM-enabled analysis. Requests are routed through a dispatcher and executor/plan runner, with provenance tracking, directed acyclic graph (DAG) recording and logs enabling transparent monitoring and reproducible execution. The outer loop illustrates the\", \"page\": 4, \"index\": 1, \"width\": 976, \"height\": 579}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711464-v2/fig-002.webp\", \"caption\": \"Fig. 2 | OmicVerse provides a unified ecosystem for interoperable multi-omics analysis across sequencing, single-cell, spatial, bulk and agentic workflows. a, The ov.alignment module supports preprocessing of raw sequencing data, converting FASTQ reads into count matrices for conventional and single-cell RNA-sequencing workflows, including velocity-compatible outputs. OmicVerse is built to interface with modern computational backends and machine-learning frameworks, including PyTorch, PyG and Apple MLX. b, The ov.preprocess module standardizes core preprocessing steps for single-cell analysis, including quality control, highly variable gene selection, dimensionality reduction and batch correction. These functions provide a common entry point for downstream analyses while shielding users from method-specific implementation differences. c, The ov.single module unifies major categories of single-cell downstream analysis within a shared interface. Supported tasks include clustering, automated cell type annotation, trajectory inference and RNA velocity, and higherorder cell structure analyses such as cell–cell interaction (CCI), differential expression (DEG) and gene regulatory network (GRN) inference. Representative integrated methods are shown for each task, illustrating that OmicVerse provides access to diverse algorithms through a consistent API rather than isolated tool-specific wrappers. d, The ov.space module extends the same design principle to spatial omics, covering cell segmentation, cluster mapping and alignment across sections, deconvolution and spatial dynamics analysis. This enables spatial workflows to be integrated with the broader OmicVerse analytical ecosystem. e, The ov.Agent module provides a language-driven interface to the OmicVerse ecosystem. Users supply an AnnData object together with a natural-language task description, which is parsed by an LLM and mapped onto registered functions through a function registry. The selected functions are then executed programmatically, enabling\", \"page\": 6, \"index\": 2, \"width\": 976, \"height\": 839}]"
motivation: 旨在解决多组学分析中工具接口不兼容、依赖关系复杂以及工作流难以复现的碎片化挑战。
method: 开发了OmicClaw框架，通过J.A.R.V.I.S.运行时将自然语言指令映射为基于OmicVerse生态的可执行、可恢复且受控的分析动作。
result: 在涵盖单细胞和空间转录组等15项任务的基准测试中，该框架在多步复杂工作流上的表现显著优于传统的大模型基准。
conclusion: OmicClaw为现代多组学研究提供了一个高效、可复现且支持人机协作的统一分析基础平台。
---

## 摘要
批量（bulk）、单细胞和空间组学的进展改变了生物学发现，但分析工作仍分散在具有不兼容接口、异构依赖项且工作流可重复性有限的各种软件包中。在这里，我们介绍了 OmicClaw，这是一个基于统一 OmicVerse 生态系统和 J.A.R.V.I.S. 运行时的可执行自然语言多组学分析框架。OmicVerse 将上游处理、预处理、单细胞、空间、批量转录组学和基础模型工作流整合到一个以 AnnData 为中心的共享接口中，涵盖了 100 多种方法。J.A.R.V.I.S. 通过一个基于注册表、状态感知且可恢复的执行层，将该生态系统转换为有界的分析动作空间。该执行层可验证先决条件、保留溯源信息并支持迭代修复，同时允许对话式、笔记本式和可视化界面在相同的实时分析状态下运行。OmicClaw 并不依赖于不受约束的代码生成，而是将用户请求转化为针对实时组学对象的可追溯工作流。在涵盖 scRNA-seq、空间转录组学、RNA 速率、scATAC-seq、CITE-seq 和多组学分析的 15 个任务基准测试中，ov.Agent 相比于纯 one-shot 大语言模型基准，在基于评分标准的性能上有所提升，尤其是在长跨度的多步工作流中。OmicClaw 还通过兼容 MCP 的服务器支持外部智能体访问，并提供了一个面向初学者的友好 Web 平台，用于交互式分析、代码执行和百万级规模的可视化。总之，OmicClaw 为现代多组学研究中可重复的人机协作提供了实用的基础。

## Abstract
Advances in bulk, single-cell and spatial omics have transformed biological discovery, yet analysis remains fragmented across packages with incompatible interfaces, heterogeneous dependencies and limited workflow reproducibility. Here, we present OmicClaw, an executable natural-language framework for multi-omics analysis built on the unified OmicVerse ecosystem and the J.A.R.V.I.S. runtime. OmicVerse organizes upstream processing, preprocessing, single-cell, spatial, bulk-transcriptomic and foundation-model workflows into a shared AnnData-centered interface spanning more than 100 methods. J.A.R.V.I.S. converts this ecosystem into a bounded analytical action space through a registry-grounded, state-aware and recoverable execution layer that validates prerequisites, preserves provenance and supports iterative repair, while enabling conversational, notebook and visual interfaces to operate over the same live analytical state. Rather than relying on unconstrained code generation, OmicClaw translates user requests into traceable workflows over live omics objects. Across a benchmark of 15 tasks spanning scRNA-seq, spatial transcriptomics, RNA velocity, scATAC-seq, CITE-seq and multiome analysis, ov.Agent improved rubric-based performance over bare one-shot large language model baselines, particularly for long-horizon multi-step workflows. OmicClaw further supports external agent access through an MCP-compatible server and a beginner-friendly web platform for interactive analysis, code execution and million-scale visualization. Together, OmicClaw provides a practical foundation for reproducible human-AI collaboration in modern multi-omics research

---

## 论文详细总结（自动生成）

以下是对论文《OmicClaw: executable and reproducible natural-language multi-omics analysis over the unified OmicVerse ecosystem》的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：现代多组学分析（批量、单细胞、空间组学）面临严重的**软件瓶颈**。现有的分析工具碎片化严重，不同软件包之间接口不兼容、依赖关系复杂、对象约定不一致，导致工作流难以复现，且对非编程背景的生物学家门槛极高。
*   **整体含义**：论文提出了 **OmicClaw** 框架，旨在通过自然语言驱动的方式，在统一的生态系统（OmicVerse）中实现可执行、可重复的多组学分析。它将大语言模型（LLM）的推理能力与受控的生物信息学执行环境相结合，将“自然语言意图”转化为“可追溯的科学工作流”。

### 2. 方法论
*   **核心思想**：不依赖 LLM 生成不受约束的代码，而是将其操作限制在一个**有界的分析动作空间**内，通过注册表机制确保工具调用的准确性与可重复性。
*   **关键技术细节**：
    *   **OmicVerse 生态系统**：作为分析底座，以 `AnnData` 为中心，整合了超过 100 种方法，涵盖序列比对、预处理、单细胞分析（聚类、速率、轨迹）、空间组学及生物基础模型。
    *   **J.A.R.V.I.S. 运行时**：执行层核心。
        *   **注册表驱动（Registry-grounded）**：通过 `@register_function` 装饰器将工具元数据（参数架构、先决条件、预期输出）存入中心注册表，防止 LLM 产生代码幻觉。
        *   **状态感知与恢复**：维护执行上下文，支持多轮对话，并在执行失败时进行迭代修复。
        *   **先决条件验证**：在执行前检查数据结构（如 PCA 前是否已完成缩放），避免静默失败。
    *   **MCP 协议支持**：通过模型上下文协议（Model Context Protocol）使外部智能体（如 Claude）能直接调用 OmicVerse 工具。
    *   **多界面支持**：提供 Python API (`ov.Agent`)、Web 平台 (`ov.web`) 和图形界面。

### 3. 实验设计
*   **数据集与场景**：涵盖了 PBMC3k/68k（单细胞转录组）、齿状回（RNA 速率）、Visium（空间转录组）、E18 小鼠大脑（scATAC-seq）、人脑（多组学联合分析）等多种真实生物学数据集。
*   **基准测试（Benchmark）**：设计了 15 个任务（T1–T15），包括质量控制、批次校正、细胞类型标注、轨迹推断、多模态整合等。
*   **对比方法**：
    *   **Bare one-shot LLM**：直接让 LLM 生成一段 Python 代码并运行的基准模式。
    *   **ov.Agent**：基于 OmicClaw 框架的智能体模式。
    *   **模型覆盖**：对比了 GPT-4o、Claude 3.5 Sonnet、DeepSeek-V3 等 7 种主流大模型在框架下的表现。

### 4. 资源与算力
*   **算力支持**：文中提到 OmicVerse 支持 **CUDA**（NVIDIA GPU）加速后端和 **Apple Metal/MPS** 环境。
*   **具体细节**：论文未明确给出训练 LLM 的具体算力（因为主要使用现有的模型 API），但提到实验得到了合作伙伴提供的专用服务器基础设施和 LLM API 访问支持。在性能基准测试中，对比了 CPU 模式与 CPU-GPU 混合模式的运行效率。

### 5. 实验数量与充分性
*   **实验规模**：
    *   针对 15 个复杂任务进行了系统评估。
    *   对 7 种不同推理能力的 LLM 进行了横向对比。
    *   进行了百万级细胞规模的可视化与处理性能测试。
*   **充分性与公平性**：实验设计较为充分，引入了基于评分标准（Rubric）的量化评估（涵盖执行成功率、科学合理性、产物有效性等）。通过固定随机种子和标准化的数据集注册表，确保了对比的客观性。

### 6. 主要结论与发现
*   **性能提升**：在长路径、多步骤的复杂工作流中，`ov.Agent` 的表现显著优于传统的代码生成模式，有效解决了参数误用和步骤缺失问题。
*   **错误修复能力**：J.A.R.V.I.S. 的迭代修复机制能显著降低因环境或微小语法错误导致的分析中断。
*   **效率优势**：OmicVerse 的 GPU 加速后端在处理大规模数据时，比传统的 Scanpy 等工具具有更高的计算效率。
*   **人机协作**：证明了通过“统一生态 + 有界运行时”，自然语言分析可以达到科学研究级别的严谨性和可重复性。

### 7. 优点
*   **系统性强**：不仅是一个 AI 插件，而是一个完整的、接口统一的生物信息学软件生态。
*   **安全性高**：通过 AST 静态扫描和安全代理（SafeOsProxy）防止恶意代码执行。
*   **可解释性**：所有 AI 操作都有完整的溯源记录（Provenance）和执行日志，方便科研人员审计。
*   **低门槛**：Web 平台和自然语言接口极大地降低了实验科学家使用复杂算法的难度。

### 8. 不足与局限
*   **模型依赖**：分析的深度和逻辑推理上限仍受限于底层 LLM 的能力，对于极度前沿或非标的分析任务，AI 可能仍需人工干预。
*   **维护成本**：随着生物信息学工具的快速更新，维持一个包含 200+ 函数的高质量注册表需要持续的人力投入。
*   **偏差风险**：虽然有约束机制，但在自动细胞标注等任务中，AI 仍可能受限于其预训练语料库的偏差。

（完）
