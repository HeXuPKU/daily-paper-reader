---
title: "OmicClaw: executable and reproducible natural-language multi-omics analysis over the unified OmicVerse ecosystem."
title_zh: OmicClaw：基于统一 OmicVerse 生态系统的可执行且可重复的自然语言多组学分析
authors: "Zeng, Z., Wang, X., Luo, Z., Zheng, Y., Hu, L., Xing, C., Du, H."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.13.711464v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用基础模型和智能体的自然语言多组学分析框架
tldr: OmicClaw是一个基于OmicVerse生态和J.A.R.V.I.S.运行时的自然语言多组学分析框架，旨在解决分析工具碎片化和重现性差的问题。它集成了100多种分析方法，通过将用户指令转化为可追踪、可修复的工作流，实现了单细胞、空间转录组等复杂任务的自动化处理。该框架在多项基准测试中表现优于传统大模型，为科研人员提供了高效的人机协作分析平台。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711464-v2/fig-001.webp\", \"caption\": \"Fig. 1 | J.A.R.V.I.S. extends OmicVerse into a unified, agentic ecosystem for interoperable multi-omics analysis. a, Overview of the OmicClaw ecosystem augmented with J.A.R.V.I.S., an agentic layer that unifies heterogeneous bioinformatics tools through a shared registry and execution framework. Native Python users can directly invoke OmicVerse functions through ov.Agent, whereas third-party or external agent clients can access the same functionality through the MCP server and tool-calling interface. At the core of the system, functions registered by @register_function are organized into a centralized tool registry/catalog spanning multiple OmicVerse modules, including alignment, bulk, single-cell, spatial, visualization, preprocessing and LLM-enabled analysis. Requests are routed through a dispatcher and executor/plan runner, with provenance tracking, directed acyclic graph (DAG) recording and logs enabling transparent monitoring and reproducible execution. The outer loop illustrates the\", \"page\": 4, \"index\": 1, \"width\": 976, \"height\": 579}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711464-v2/fig-002.webp\", \"caption\": \"Fig. 2 | OmicVerse provides a unified ecosystem for interoperable multi-omics analysis across sequencing, single-cell, spatial, bulk and agentic workflows. a, The ov.alignment module supports preprocessing of raw sequencing data, converting FASTQ reads into count matrices for conventional and single-cell RNA-sequencing workflows, including velocity-compatible outputs. OmicVerse is built to interface with modern computational backends and machine-learning frameworks, including PyTorch, PyG and Apple MLX. b, The ov.preprocess module standardizes core preprocessing steps for single-cell analysis, including quality control, highly variable gene selection, dimensionality reduction and batch correction. These functions provide a common entry point for downstream analyses while shielding users from method-specific implementation differences. c, The ov.single module unifies major categories of single-cell downstream analysis within a shared interface. Supported tasks include clustering, automated cell type annotation, trajectory inference and RNA velocity, and higherorder cell structure analyses such as cell–cell interaction (CCI), differential expression (DEG) and gene regulatory network (GRN) inference. Representative integrated methods are shown for each task, illustrating that OmicVerse provides access to diverse algorithms through a consistent API rather than isolated tool-specific wrappers. d, The ov.space module extends the same design principle to spatial omics, covering cell segmentation, cluster mapping and alignment across sections, deconvolution and spatial dynamics analysis. This enables spatial workflows to be integrated with the broader OmicVerse analytical ecosystem. e, The ov.Agent module provides a language-driven interface to the OmicVerse ecosystem. Users supply an AnnData object together with a natural-language task description, which is parsed by an LLM and mapped onto registered functions through a function registry. The selected functions are then executed programmatically, enabling\", \"page\": 6, \"index\": 2, \"width\": 976, \"height\": 839}]"
motivation: 针对当前多组学分析中工具接口不兼容、依赖关系复杂以及工作流难以重现的碎片化挑战。
method: 构建了以AnnData为中心的OmicVerse生态系统，并利用J.A.R.V.I.S.运行时将自然语言转化为受控且可恢复的分析动作空间。
result: 在涵盖单细胞、空间转录组等15项任务的基准测试中，OmicClaw在多步长工作流上的表现显著优于基础大模型。
conclusion: OmicClaw为现代多组学研究提供了一个实用、可重现且支持人机协作的自然语言分析基础架构。
---

## 摘要
批量（bulk）、单细胞和空间组学的进展改变了生物学发现，但分析工作仍分散在具有不兼容接口、异构依赖项且工作流可重复性有限的各种软件包中。在这里，我们介绍了 OmicClaw，这是一个基于统一 OmicVerse 生态系统和 J.A.R.V.I.S. 运行时的可执行自然语言多组学分析框架。OmicVerse 将上游处理、预处理、单细胞、空间、批量转录组学和基础模型工作流整合到一个以 AnnData 为中心的共享接口中，涵盖了 100 多种方法。J.A.R.V.I.S. 通过一个基于注册表、状态感知且可恢复的执行层，将该生态系统转换为有界的分析动作空间。该执行层可验证先决条件、保留溯源信息并支持迭代修复，同时允许对话式、笔记本式和可视化界面在同一个实时分析状态下运行。OmicClaw 并不依赖于不受约束的代码生成，而是将用户请求转化为针对实时组学对象的可追溯工作流。在涵盖 scRNA-seq、空间转录组学、RNA 速率、scATAC-seq、CITE-seq 和多组学分析的 15 个任务基准测试中，ov.Agent 相比于纯 one-shot 大语言模型基准，在基于评分标准的性能上有所提升，尤其是在长跨度的多步工作流中。OmicClaw 还通过兼容 MCP 的服务器支持外部智能体访问，并提供了一个面向初学者的友好 Web 平台，用于交互式分析、代码执行和百万级规模的可视化。总之，OmicClaw 为现代多组学研究中可重复的人机协作提供了实用的基础。

## Abstract
Advances in bulk, single-cell and spatial omics have transformed biological discovery, yet analysis remains fragmented across packages with incompatible interfaces, heterogeneous dependencies and limited workflow reproducibility. Here, we present OmicClaw, an executable natural-language framework for multi-omics analysis built on the unified OmicVerse ecosystem and the J.A.R.V.I.S. runtime. OmicVerse organizes upstream processing, preprocessing, single-cell, spatial, bulk-transcriptomic and foundation-model workflows into a shared AnnData-centered interface spanning more than 100 methods. J.A.R.V.I.S. converts this ecosystem into a bounded analytical action space through a registry-grounded, state-aware and recoverable execution layer that validates prerequisites, preserves provenance and supports iterative repair, while enabling conversational, notebook and visual interfaces to operate over the same live analytical state. Rather than relying on unconstrained code generation, OmicClaw translates user requests into traceable workflows over live omics objects. Across a benchmark of 15 tasks spanning scRNA-seq, spatial transcriptomics, RNA velocity, scATAC-seq, CITE-seq and multiome analysis, ov.Agent improved rubric-based performance over bare one-shot large language model baselines, particularly for long-horizon multi-step workflows. OmicClaw further supports external agent access through an MCP-compatible server and a beginner-friendly web platform for interactive analysis, code execution and million-scale visualization. Together, OmicClaw provides a practical foundation for reproducible human-AI collaboration in modern multi-omics research

---

## 论文详细总结（自动生成）

### 论文总结：OmicClaw —— 基于统一生态系统的可执行自然语言多组学分析框架

#### 1. 核心问题与整体含义（研究动机和背景）
现代生物学研究正处于多组学数据（批量、单细胞、空间组学等）爆发的时代，但生物信息学分析面临三大挑战：
*   **工具碎片化**：不同软件包接口不兼容，依赖关系复杂。
*   **重现性差**：分析流程往往难以记录和完全复现。
*   **门槛高**：复杂的编程要求限制了实验生物学家直接进行深度数据探索。
**OmicClaw** 的提出旨在通过一个统一的生态系统（OmicVerse）和智能体运行时（J.A.R.V.I.S.），将自然语言指令转化为可执行、可追溯且可修复的多组学分析工作流，实现人机协作的标准化分析。

#### 2. 核心方法论
OmicClaw 的架构由两个核心组件构成：
*   **OmicVerse 生态系统**：
    *   以 **AnnData** 数据结构为中心，整合了超过 100 种分析方法。
    *   涵盖了从原始序列处理（Alignment）、预处理、单细胞分析（聚类、轨迹、速率）、空间组学到大模型增强分析的全流程。
    *   提供统一的 API 接口，屏蔽了底层不同算法实现的差异。
*   **J.A.R.V.I.S. 运行时（Agentic Layer）**：
    *   **受控动作空间**：不同于不受约束的代码生成，它通过 `@register_function` 将功能注册到中心化工具库，LLM 仅在预定义的动作空间内进行调用。
    *   **状态感知与恢复**：具备执行层验证、溯源跟踪和有向无环图（DAG）记录功能。如果执行出错，系统支持迭代修复。
    *   **多模态交互**：支持对话式、笔记本（Notebook）和 Web 可视化界面，所有界面共享同一个实时分析状态。
    *   **MCP 协议支持**：通过 Model Context Protocol (MCP) 服务器，允许外部智能体（如 Claude 或自定义 Agent）访问其分析能力。

#### 3. 实验设计
*   **数据集与场景**：涵盖了单细胞 RNA 测序（scRNA-seq）、空间转录组学、RNA 速率分析、scATAC-seq、CITE-seq 以及多组学整合分析。
*   **Benchmark（基准测试）**：设计了 **15 个代表性任务**，涵盖了从基础质控到复杂的高阶分析（如细胞间通讯、基因调控网络推断）。
*   **对比方法**：将 `ov.Agent`（OmicClaw 的核心智能体）与**纯 One-shot 大语言模型（Baseline LLMs）**进行对比。
*   **评价指标**：采用基于评分标准（Rubric-based）的性能评估，重点考察长跨度、多步骤工作流的准确性和成功率。

#### 4. 资源与算力
*   **框架支持**：论文提到 OmicVerse 构建在现代计算后端之上，包括 **PyTorch**、**PyG**（PyTorch Geometric）以及针对 Apple 芯片优化的 **MLX**。
*   **算力细节**：文中**未明确说明**具体训练 LLM 所使用的 GPU 型号、数量或具体时长。这主要是因为 OmicClaw 更多是一个利用现有基础模型（Foundation Models）的框架，而非从头训练一个生物大模型。

#### 5. 实验数量与充分性
*   **实验规模**：通过 15 个跨领域的任务进行基准测试，涵盖了当前多组学研究的主流方向。
*   **充分性评价**：实验设计较为全面，不仅验证了单一任务的准确性，还特别强调了在“长程多步工作流”中的表现。通过对比实验证明了其在处理复杂逻辑时的优势。
*   **客观性**：引入了 DAG 记录和日志追踪，使得实验过程透明、可验证，增强了结果的客观性。

#### 6. 主要结论与发现
*   **性能提升**：在所有 15 个基准任务中，`ov.Agent` 的表现均优于纯 LLM 基准，尤其是在需要多个相互依赖步骤的复杂任务中优势更明显。
*   **可重现性**：通过 J.A.R.V.I.S. 记录的执行路径，研究人员可以轻松复现整个分析流程，解决了“黑盒”代码生成带来的不可控问题。
*   **易用性**：Web 平台和自然语言接口显著降低了非编程背景科研人员的使用门槛，支持百万级规模数据的实时可视化。

#### 7. 优点
*   **生态统一性**：将零散的工具整合进 AnnData 生态，实现了真正的多组学互操作性。
*   **安全性与鲁棒性**：通过“受控动作空间”而非“盲目生成代码”，降低了 LLM 产生幻觉导致错误执行的风险。
*   **可追溯性**：自动生成 DAG 和溯源信息，符合开放科学和可重复研究的要求。
*   **开放性**：支持 MCP 协议，使其能作为插件集成到其他 AI 生态中。

#### 8. 不足与局限
*   **依赖底层模型**：系统的推理上限仍受限于所使用的基础 LLM（如 GPT-4 或 Claude 3.5）的逻辑能力。
*   **注册库限制**：虽然涵盖了 100 多种方法，但对于极少数非常新颖或极其冷门的算法，如果未在 OmicVerse 中注册，智能体将无法直接调用。
*   **偏差风险**：如果用户提供的自然语言描述存在歧义，智能体可能会选择次优的分析路径，仍需人工进行最终审核。

（完）
