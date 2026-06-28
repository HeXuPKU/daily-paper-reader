---
title: "biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes"
title_zh: biomeStat：利用自主AI实现可扩展基因组流行病学——通过对1000个亚洲登革病毒基因组的端到端分析展示
authors: "Ariyaratne, D., Somaratna, N., Malavige, G. N."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 使用智能体AI进行可扩展的基因组流行病学分析
tldr: 基因组流行病学分析通常依赖专家手动操作多个工具和参数调优。biomeStat作为自主AI代理，通过自然语言指令自动编写代码执行生物信息学工具，并动态分配计算资源。在1000个亚洲登革病毒基因组分析中，24小时内完成系统发育、贝叶斯动力学、选择压力和结构映射分析，发现免疫逃逸位点并验证药物靶点保守性。该方法大幅降低分析门槛，确保可重复性。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决基因组流行病学流程需要专家手动操作、参数调优和异构计算资源的问题。
method: biomeStat自主生成代码调用IQ-TREE、BEAST2等工具，在沙箱环境中执行，动态分配CPU/GPU资源。
result: 全自动分析1000个登革病毒基因组，24小时内完成，发现1869个免疫逃逸位点与表位共定位，验证176个药物靶点保守。
conclusion: biomeStat将专家数周工作压缩为单次会话，以自然语言驱动确定性计算，兼具可重复性和可扩展性。
---

## 摘要
基因组流行病学工作流程通常需要专家对多个专业工具进行精心配置、大量手动参数调整，并访问异构计算基础设施。虽然标准生成式AI模型在复杂生物领域常出现幻觉，但我们引入了biomeStat：一个自主AI代理，它充当严格的确定性编排器。通过自动编写代码在沙盒环境中执行已建立的生物信息学工具，biomeStat动态配置计算资源（CPU和GPU），并保证可重复性，使科学家无需命令行专业知识即可立即使用。

为展示该平台，我们对2000年至2025年间从16个亚洲国家采样的1000个登革病毒（DENV）基因组进行了完全自主的基因组流行病学和结构分析。该代理无缝编排了系统发育重建（IQ-TREE、TreeTime）、贝叶斯系统动力学（通过NVIDIA H200 GPU的BEAST2）、选择压力分析（HyPhy）和结构映射（PyMOL）。分析在不到24小时的挂钟时间内完成，揭示了地方性稳定（R_e [~]1.0），并识别出1,869个与B细胞和T细胞表位结构共定位的候选免疫逃逸位点。此外，该代理验证了病毒复制复合体上的176个高度保守的药物靶点残基，确认新兴抗病毒药物JNJ-1802和NITD-688的耐药相关位点在所有四种血清型中绝对保守。通过弥合自然语言意图与确定性计算执行之间的差距，biomeStat将数周的专家工作缩减为单次分析，且具有完全的方法透明性。

## Abstract
Genomic epidemiology workflows typically require expert curation of multiple specialized tools, extensive manual parameter tuning, and access to heterogeneous compute infrastructure. While standard generative AI models often hallucinate in complex biological domains, we introduce biomeStat: an autonomous AI agent that functions as a strict deterministic orchestrator. By automatically writing code to execute established bioinformatics tools in sandboxed environments, biomeStat dynamically provisions compute resources (CPU and GPU) and guarantees reproducibility, making it immediately useful for scientists without requiring command-line expertise.

To demonstrate the platform, we performed a fully autonomous genomic epidemiology and structural analysis of 1,000 Dengue virus (DENV) genomes sampled from 16 Asian countries between 2000 and 2025. The agent seamlessly orchestrated phylogenetic reconstruction (IQ-TREE, TreeTime), Bayesian phylodynamics (BEAST2 via NVIDIA H200 GPU), selection pressure analysis (HyPhy), and structural mapping (PyMOL). The analysis was completed in under 24 hours of wall-clock time, revealing endemic stability (R_e [~]1.0) and identifying 1,869 candidate immune escape sites structurally colocalized with B-cell and T-cell epitopes. Furthermore, the agent validated 176 highly conserved drug target residues across the viral replication complex, confirming that resistance-associated positions for emerging antivirals JNJ-1802 and NITD-688 remain absolutely conserved across all four serotypes. By bridging the gap between natural language intent and deterministic computational execution, biomeStat reduces weeks of expert effort into a single-session analysis with full methodological transparency.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机与背景）
- **研究动机**：传统基因组流行病学工作流程严重依赖专家手动配置多个专业工具、大量参数调优，并需访问异构计算基础设施，过程耗时且对非专家用户不友好。而标准生成式AI模型在复杂生物领域常出现“幻觉”（生成不准确或虚构结果），难以可靠用于科学计算。
- **背景**：登革病毒（DENV）在全球流行（尤其在亚洲），其基因组流行病学分析（系统发育、动态学、选择压力、结构映射）对于理解病毒传播、免疫逃逸和抗病毒药物靶点保守性至关重要。现有工具（如IQ-TREE、BEAST2、HyPhy、PyMOL）功能强大但操作复杂，缺乏自动化可重复性框架。

### 2. 提出的方法论：核心思想、关键技术细节
- **核心思想**：biomeStat是一个**自主AI代理（Agentic AI）**，充当“严格确定性编排器”。它通过自然语言指令（用户意图）自动编写代码，在沙盒环境中调用已建立的生物信息学工具，动态分配计算资源（CPU/GPU），并确保每一步可重复。
- **关键技术细节**：
  - **自然语言→代码生成**：用户以自然语言描述分析目标（如“对1000个DENV基因组进行系统发育重建、贝叶斯动力学、选择压力分析并映射到结构”），biomeStat自动生成Python/R/Shell脚本。
  - **沙盒执行**：所有代码在隔离环境中运行，避免对宿主系统造成影响，同时记录完整执行日志。
  - **动态资源编排**：根据任务类型自动选择CPU或GPU（例如BEAST2需要GPU加速时请求NVIDIA H200），可跨节点扩展。
  - **工具集成**：无缝调用IQ-TREE（最大似然系统发育）、TreeTime（时间尺度校准）、BEAST2（贝叶斯系统动力学）、HyPhy（选择压力）、PyMOL（结构映射）。
  - **可重复性**：每个分析会话生成完整的执行记录（代码、参数、版本、输出），可完全复现。
- **算法流程简要说明**：（1）用户输入自然语言指令；（2）AI代理解析并分解为子任务（如“准备序列”、“构建ML树”、“做贝叶斯分析”等）；（3）依次生成调用相应工具的脚本；（4）在沙盒中顺序/并行执行；（5）收集结果并形成综合报告。

### 3. 实验设计
- **数据集**：2000年至2025年间从16个亚洲国家采样的**1000个登革病毒（DENV）基因组**（涵盖四种血清型）。论文未提供具体序列数据库来源，但提到是公开数据。
- **Benchmark**：没有设定独立的基准（如与手动分析或其他工具对比），而是以**端到端全自动分析**作为应用示范，验证biomeStat能否在24小时内完成完整流程并产出生物学上有意义的发现。
- **对比方法**：未直接对比其他自动化方法（如Croma、Galaxy等），但论文隐含对比了传统手动专家流程（需数周工作），强调时间和门槛优势。
- **实验充分性**：仅演示了一个大规模案例（1000基因组），没有做消融实验或跨数据集验证。尽管如此，分析涉及多个模块（系统发育、动力学、选择压力、结构）的联合执行，能检验代理的编排能力。

### 4. 资源与算力
- **GPU**：使用了**NVIDIA H200 GPU**（具体数量未明确，但提到“通过NVIDIA H200 GPU的BEAST2”）。可能使用一个或多个H200 GPU加速贝叶斯分析。
- **CPU**：其他任务（IQ-TREE、HyPhy、PyMOL）使用CPU资源，具体核数未说明。
- **训练时长**：整个端到端分析在**小于24小时挂钟时间**内完成。论文未给出代理训练或模型微调部分的算力需求（可能只调用预训练的生物信息学工具）。

### 5. 实验数量与充分性
- **实验数量**：实际仅**一组大规模案例分析**（1000个DENV基因组），未进行多数据集、不同规模或消融实验。
- **充分性评估**：
  - **优点**：案例规模大、步骤全，能充分展示代理在多个任务间的编排能力。
  - **不足**：缺乏对比实验（如与手动分析耗时/结果差异）、缺乏不同参数设置下的稳定性测试、未在多个随机种子下验证可重复性。仅凭一个案例可能无法完全证明方法的通用性和鲁棒性。结果部分报告了具体的免疫逃逸位点数量和药物靶点保守性，但未提供统计显著性验证（如FDR控制）。

### 6. 论文的主要结论与发现
- **平台可行性**：biomeStat能够从自然语言指令出发，在24小时内自主完成1000个基因组的多步分析，大幅降低专家依赖、提升效率。
- **生物学发现**：
  - 揭示了地方性稳定（有效繁殖数 Rₑ ≈ 1.0）。
  - 识别出**1,869个候选免疫逃逸位点**，这些位点与B细胞和T细胞表位在结构上共定位。
  - 验证病毒复制复合体上**176个高度保守的药物靶点残基**，并确认新兴抗病毒药物JNJ-1802和NITD-688的耐药相关位点在所有四种血清型中绝对保守。
- **可重复性**：自动生成完整执行日志，保证了方法透明性和可重复性。

### 7. 优点
- **自动化程度高**：将自然语言用户意图直接转化为可执行的确定性计算工作流，无需编程或命令行知识。
- **资源动态调度**：能根据任务自动选择CPU/GPU，实现异构计算的高效利用（如贝叶斯分析用H200 GPU加速）。
- **可重复性保障**：沙盒环境+完整日志，解决了传统手动工作流难以复现的问题。
- **跨工具整合**：无缝融合系统发育、动力学、选择压力、结构映射等不同领域工具，输出统一报告。
- **实用性强**：将专家数周工作压缩为单次会话，对资源匮乏的实验室尤其有利。

### 8. 不足与局限
- **实验覆盖有限**：仅测试一个数据集（1000 DENV基因组），未在其他病原体或更大规模数据集上验证，通用性未确证。
- **缺乏对比基准**：未与手动专家分析、现有自动化平台（如Galaxy、Nextflow）或不同AI代理（如基于ChatGPT的脚本生成）进行耗时和准确性比较，难以量化提升幅度。
- **偏差风险**：依赖AI生成代码，可能隐含代码错误或工具调用不恰当（虽然沙盒环境能捕获部分错误，但未报告错误率）；生物学结论未经过独立实验验证（如免疫逃逸位点是否为真功能位点）。
- **资源透明度不足**：GPU具体数量、CPU核数、内存等未明确，影响可复现性评估。
- **工具版本绑定**：当前集成工具版本若更新，代理需重新适配，论文未讨论版本管理策略。
- **模型幻觉风险未完全排除**：虽然声称“确定性编排”，但自然语言理解到代码生成阶段仍可能产生误解释或遗漏参数（论文未提供失败案例统计）。

（完）
