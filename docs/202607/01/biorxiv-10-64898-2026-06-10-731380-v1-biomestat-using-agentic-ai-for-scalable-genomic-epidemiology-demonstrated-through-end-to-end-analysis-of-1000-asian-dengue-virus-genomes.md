---
title: "biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes"
title_zh: biomeStat：利用自主AI进行可扩展基因组流行病学——通过对1000个亚洲登革病毒基因组的端到端分析演示
authors: "Ariyaratne, D., Somaratna, N., Malavige, G. N."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 使用自主AI智能体进行基因组流行病学分析，涉及智能体在医疗数据中的应用
tldr: 基因组流行病学分析通常需要专家手动操作多个工具和参数调优，传统生成式AI易在复杂生物领域产生幻觉。biomeStat作为自主AI智能体，通过自动编写代码执行确定性生物信息学工具并动态调配计算资源，保证了可重复性。在对1000个登革病毒基因组的全自动分析中，仅用24小时就完成了系统发育重建、贝叶斯动力学、选择压力分析和结构映射，发现了1869个候选免疫逃逸位点，并确认176个高度保守的药物靶点残基。该工作将自然语言意图与确定性计算执行结合，大幅减少了专家的手工工作量，提升了方法透明度。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因组流行病学流程依赖专家手动操作和调参，缺乏自动化和可扩展性，急需高效的AI驱动解决方案。
method: biomeStat作为自主AI智能体，自动编写代码执行标准生物信息学工具，动态分配CPU/GPU资源，实现端到端可重复分析。
result: 在24小时内完成1000个登革病毒基因组的系统发育、动力学、选择压力及结构分析，发现1869个免疫逃逸位点和176个保守药物靶点。
conclusion: biomeStat将数周专家工作简化为单次分析，显著降低了基因组流行病学分析门槛，同时保证了方法透明和可复现。
---

## 摘要
基因组流行病学工作流程通常需要对多个专业工具进行专家级调整、大量手动参数优化以及访问异构计算基础设施。虽然标准生成式AI模型在复杂生物领域常出现幻觉，但我们引入了biomeStat：一个自主AI智能体，充当严格的确定性协调器。通过自动编写代码在沙盒环境中执行已建立的生物信息学工具，biomeStat动态调配计算资源（CPU和GPU）并保证可重复性，使其对无需命令行专业知识的科学家立即可用。

为演示该平台，我们对2000年至2025年间从16个亚洲国家采集的1000个登革病毒（DENV）基因组进行了完全自主的基因组流行病学和结构分析。该智能体无缝协调了系统发育重建（IQ-TREE、TreeTime）、贝叶斯系统动力学（通过NVIDIA H200 GPU的BEAST2）、选择压力分析（HyPhy）和结构映射（PyMOL）。分析在不到24小时的挂钟时间内完成，揭示了地方性稳定（R_e ≈ 1.0），并识别出1,869个候选免疫逃逸位点，这些位点与B细胞和T细胞表位具有结构共定位。此外，该智能体验证了病毒复制复合体中176个高度保守的药物靶点残基，确认新兴抗病毒药物JNJ-1802和NITD-688的耐药相关位点在所有四种血清型中绝对保守。通过弥合自然语言意图与确定性计算执行之间的差距，biomeStat将数周的专家工作量减少为一次会话分析，并具有完整的方法透明性。

## Abstract
Genomic epidemiology workflows typically require expert curation of multiple specialized tools, extensive manual parameter tuning, and access to heterogeneous compute infrastructure. While standard generative AI models often hallucinate in complex biological domains, we introduce biomeStat: an autonomous AI agent that functions as a strict deterministic orchestrator. By automatically writing code to execute established bioinformatics tools in sandboxed environments, biomeStat dynamically provisions compute resources (CPU and GPU) and guarantees reproducibility, making it immediately useful for scientists without requiring command-line expertise.

To demonstrate the platform, we performed a fully autonomous genomic epidemiology and structural analysis of 1,000 Dengue virus (DENV) genomes sampled from 16 Asian countries between 2000 and 2025. The agent seamlessly orchestrated phylogenetic reconstruction (IQ-TREE, TreeTime), Bayesian phylodynamics (BEAST2 via NVIDIA H200 GPU), selection pressure analysis (HyPhy), and structural mapping (PyMOL). The analysis was completed in under 24 hours of wall-clock time, revealing endemic stability (R_e [~]1.0) and identifying 1,869 candidate immune escape sites structurally colocalized with B-cell and T-cell epitopes. Furthermore, the agent validated 176 highly conserved drug target residues across the viral replication complex, confirming that resistance-associated positions for emerging antivirals JNJ-1802 and NITD-688 remain absolutely conserved across all four serotypes. By bridging the gap between natural language intent and deterministic computational execution, biomeStat reduces weeks of expert effort into a single-session analysis with full methodological transparency.