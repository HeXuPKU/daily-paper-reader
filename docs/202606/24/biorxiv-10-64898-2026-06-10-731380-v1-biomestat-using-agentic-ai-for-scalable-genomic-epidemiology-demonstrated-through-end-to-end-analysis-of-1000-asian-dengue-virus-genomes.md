---
title: "biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes"
title_zh: biomeStat：利用自主AI实现可扩展基因组流行病学——通过1000个亚洲登革热病毒基因组端到端分析展示
authors: "Ariyaratne, D., Somaratna, N., Malavige, G. N."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 基于自主智能体的基因组流行病学可扩展分析
tldr: 基因组流行病学分析通常依赖专家手动组合多种工具并调参，标准生成AI在该领域易出现幻觉。biomeStat作为自主AI代理，通过自动编写代码执行既定生物信息学工具，动态分配CPU/GPU资源，确保可重复性。应用该平台自主分析了2000-2025年间16个亚洲国家的1000个登革病毒基因组，在24小时内完成系统发育、贝叶斯进化动力学、选择压力分析和结构映射。结果发现1800余个免疫逃逸位点与B/T细胞表位共定位，并验证了新兴抗病毒药物靶点的高度保守性，将数周工作压缩为单次透明分析。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决基因组流行病学中工具组合复杂、手动调参繁琐、标准AI易幻觉的问题，实现自然语言驱动的全自动分析。
method: biomeStat作为自主AI代理，自动编写代码调用IQ-TREE、BEAST2等工具，在沙盒环境中执行并动态分配GPU资源。
result: 分析1000个登革病毒基因组，24小时内完成，发现1869个免疫逃逸位点，176个抗病毒药物靶点高度保守。
conclusion: biomeStat将数周专家工作简化为单次透明分析，显著提升基因组流行病学的可扩展性与可访问性。
---

## 摘要
基因组流行病学工作流程通常需要专家对多种专业工具进行精心调配、大量的手动参数调整，以及访问异构计算基础设施。虽然标准生成式AI模型在复杂生物领域常出现幻觉，但我们引入了biomeStat：一个自主AI代理，它作为一个严格的确定性编排器。通过自动编写代码在沙盒环境中执行成熟的生物信息学工具，biomeStat动态配置计算资源（CPU和GPU）并保证可重复性，使其对无需命令行专业知识的科学家也能立即使用。

为展示该平台，我们对2000年至2025年间从16个亚洲国家采样的1000个登革热病毒（DENV）基因组进行了完全自主的基因组流行病学和结构分析。该代理无缝编排了系统发育重建（IQ-TREE、TreeTime）、贝叶斯系统动力学（通过NVIDIA H200 GPU的BEAST2）、选择压力分析（HyPhy）和结构映射（PyMOL）。分析在不到24小时的挂钟时间内完成，揭示了地方性稳定（有效再生数R_e≈1.0），并识别出1,869个与B细胞和T细胞表位结构共定位的候选免疫逃逸位点。此外，该代理验证了病毒复制复合体中的176个高度保守的药物靶点残基，证实新兴抗病毒药物JNJ-1802和NITD-688的耐药相关位点在所有四种血清型中均保持绝对保守。通过弥合自然语言意图与确定性计算执行之间的差距，biomeStat将数周的专业工作简化为一次会话分析，同时实现完全的方法透明。

## Abstract
Genomic epidemiology workflows typically require expert curation of multiple specialized tools, extensive manual parameter tuning, and access to heterogeneous compute infrastructure. While standard generative AI models often hallucinate in complex biological domains, we introduce biomeStat: an autonomous AI agent that functions as a strict deterministic orchestrator. By automatically writing code to execute established bioinformatics tools in sandboxed environments, biomeStat dynamically provisions compute resources (CPU and GPU) and guarantees reproducibility, making it immediately useful for scientists without requiring command-line expertise.

To demonstrate the platform, we performed a fully autonomous genomic epidemiology and structural analysis of 1,000 Dengue virus (DENV) genomes sampled from 16 Asian countries between 2000 and 2025. The agent seamlessly orchestrated phylogenetic reconstruction (IQ-TREE, TreeTime), Bayesian phylodynamics (BEAST2 via NVIDIA H200 GPU), selection pressure analysis (HyPhy), and structural mapping (PyMOL). The analysis was completed in under 24 hours of wall-clock time, revealing endemic stability (R_e [~]1.0) and identifying 1,869 candidate immune escape sites structurally colocalized with B-cell and T-cell epitopes. Furthermore, the agent validated 176 highly conserved drug target residues across the viral replication complex, confirming that resistance-associated positions for emerging antivirals JNJ-1802 and NITD-688 remain absolutely conserved across all four serotypes. By bridging the gap between natural language intent and deterministic computational execution, biomeStat reduces weeks of expert effort into a single-session analysis with full methodological transparency.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：基因组流行病学分析通常需要专家手动组合多种专业生物信息学工具、细致调参，并访问异构计算基础设施，过程耗时且门槛高。标准生成式AI模型在复杂生物学领域容易产生“幻觉”（生成不准确或虚构的结果），难以直接用于严谨的科学分析。
- **整体含义**：为弥合自然语言意图与确定性计算执行之间的差距，作者提出了**biomeStat**——一个自主AI代理，可自动编排成熟生物信息学工具，实现从数据到结论的端到端、可重复的基因组流行病学分析，大幅降低专家依赖性和时间成本。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：biomeStat作为**严格确定性编排器**，接收自然语言描述的分析任务后，自动编写代码（Python/R/Shell脚本），在沙盒环境中调用已建立的专业生物信息学工具，动态配置CPU/GPU资源，并保证流程的可重复性和方法透明度。
- **关键技术细节**：
  - **工具链编排**：集成IQ-TREE（系统发育重建）、TreeTime（时标系统发育）、BEAST2（贝叶斯系统动力学，启用NVIDIA H200 GPU加速）、HyPhy（选择压力分析）、PyMOL（结构映射）等。
  - **执行机制**：在封闭沙盒中运行自动生成的代码，自动处理输入/输出、参数调整、依赖管理，并记录完整日志。
  - **资源动态分配**：根据任务需求自动分配CPU/GPU，无需用户干预。
  - **无公式/算法流程**：论文未给出数学公式，强调代理的编排逻辑而非底层模型。

### 3. 实验设计：数据集、基准与对比方法
- **数据集**：2000年至2025年间从16个亚洲国家采样的**1000个登革热病毒（DENV）基因组**（涵盖四种血清型）。
- **基准（Benchmark）**：未设置外部基准或对比方法。实验目的为**技术展示**，即验证biomeStat能否自主完成传统需专家数周的工作流。
- **对比方法**：未与其他自动化平台或标准生成AI进行定量对比，但隐式对比了传统手动分析流程（耗时数周）与biomeStat（24小时内完成）。

### 4. 资源与算力
- **GPU**：在BEAST2分析中使用了**NVIDIA H200 GPU**（未说明具体数量），用于加速贝叶斯系统动力学计算。
- **时间**：整条分析流程的挂钟时间**小于24小时**。
- **备注**：论文未提供更多硬件细节（如CPU内存、GPU显存等），也未明确训练或推理的算力总量。

### 5. 实验数量与充分性
- **实验数量**：仅进行了一组端到端分析（1000个DENV基因组），**无消融实验、不同数据集对比或多轮重复验证**。
- **充分性评价**：
  - **优点**：成功演示了平台在真实场景下的可用性，结果具有生物学意义。
  - **不足**：未通过消融或对比实验量化biomeStat相对于传统流程的性能提升（如时间节省、准确性、幻觉率）；单案例无法证明方法在其它病原体或数据类型上的泛化能力。实验设计偏向概念验证，而非系统性基准测试。

### 6. 论文的主要结论与发现
- **流行病学**：登革病毒在亚洲呈现地方性稳定（有效再生数R_e ≈ 1.0）。
- **免疫逃逸**：识别出**1,869个候选免疫逃逸位点**，这些位点与B细胞和T细胞表位在结构上共定位。
- **药物靶点保守性**：病毒复制复合体中的**176个残基高度保守**；新兴抗病毒药物JNJ-1802和NITD-688的耐药相关位点在所有四种血清型中均保持绝对保守。
- **方法论**：biomeStat将数周的专家工作压缩为单次透明分析，显著提升了基因组流行病学的可扩展性与可访问性。

### 7. 优点：方法或实验设计上的亮点
- **自动化程度高**：用户只需用自然语言描述任务，代理自动完成编码、执行、资源管理，无需命令行专业知识。
- **确定性可重复**：通过沙盒和日志记录保证每一步可审阅、可复现，避免了生成AI的幻觉问题。
- **计算效率**：利用GPU加速BEAST2，24小时内完成大规模系统动力学分析，远超手动流程。
- **端到端集成**：无缝串联系统发育、贝叶斯动力学、选择压力、结构映射等多种分析，无需手动数据传递。
- **生物学发现**：识别的大量免疫逃逸位点和药物靶点保守性验证，具有潜在临床应用价值。

### 8. 不足与局限
- **实验覆盖有限**：仅用单一病毒（DENV）的单一数据集验证，未测试其他病原体或多种数据规模，泛化性未证明。
- **缺乏定量对比**：未设置基线（如手动分析时间、标准AI幻觉率、其他自动化系统）进行公平比较，难以量化优势。
- **依赖外部工具**：biomeStat本身不提供新的分析算法，其鲁棒性受制于所调用的工具（IQ-TREE、BEAST2等）的准确性和更新。
- **潜在偏差风险**：自动调参可能隐含默认参数偏差；BEAST2的GPU加速结果可能受硬件影响，未讨论不同配置下的结果一致性。
- **透明度限制**：虽然强调方法透明，但代理自动生成的代码质量（如错误处理、边缘情况）未经专家审计，实际使用中仍需人工验证关键步骤。
- **未提及失效场景**：没有讨论当输入数据质量差或工具报错时代理如何恢复或报告错误。

（完）
