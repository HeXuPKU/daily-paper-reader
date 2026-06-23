---
title: "biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes"
title_zh: biomeStat：利用Agentic AI实现可扩展的基因组流行病学——通过对1000个亚洲登革病毒基因组的端到端分析进行验证
authors: "Ariyaratne, D., Somaratna, N., Malavige, G. N."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 用于可扩展基因组流行病学的自主AI智能体
tldr: 基因组流行病学分析通常依赖专家手工操作多个工具和参数调优，效率低下且可重复性差。提出的biomeStat自主AI智能体通过编写代码在沙箱环境中执行生物信息学工具，动态分配CPU/GPU资源，保证可重复性。对1000个亚洲登革病毒基因组进行全自动分析，24小时内完成系统发育、贝叶斯系统动力学、选择压力及结构映射，揭示内源性稳定（R_e~1.0），识别1869个免疫逃逸位点并验证176个药物靶点高度保守。该平台将数周专家工作简化为单次会话分析，兼具方法透明度。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因组流行病学工作流需专家手动集成多工具并调整参数，耗时长、可重复性差，非专家难以使用。
method: biomeStat作为确定性编排器，自动编写代码在隔离环境中执行IQ-TREE、BEAST2等工具，动态调配计算资源并保证复现性。
result: 全自动分析1000个登革病毒基因组：R_e约1.0，发现1869个免疫逃逸位点，JNJ-1802和NITD-688耐药位点完全保守。
conclusion: biomeStat通过自然语言指令驱动确定性执行，大幅降低基因组流行病学分析门槛，将数周工作压缩至24小时内。
---

## 摘要
基因组流行病学工作流程通常需要专家对多种专业工具进行管理、大量手动参数调整以及对异构计算基础设施的访问。虽然标准的生成式AI模型在复杂生物领域常常产生幻觉，但我们引入了biomeStat：一个自主AI代理，它作为一个严格的确定性编排器。通过自动编写代码在沙箱环境中执行既定的生物信息学工具，biomeStat动态配置计算资源（CPU和GPU）并保证可重复性，使其无需命令行专业知识即可为科学家立即使用。为展示该平台，我们对2000年至2025年间从16个亚洲国家采样的1000个登革病毒（DENV）基因组进行了完全自主的基因组流行病学和结构分析。该代理无缝编排了系统发育重建（IQ-TREE、TreeTime）、贝叶斯系统动力学（基于NVIDIA H200 GPU的BEAST2）、选择压力分析（HyPhy）和结构映射（PyMOL）。分析在不到24小时的挂钟时间内完成，揭示了地方性稳定（R_e~1.0），并识别出1869个与B细胞和T细胞表位结构共定位的候选免疫逃逸位点。此外，该代理验证了病毒复制复合体上的176个高度保守的药物靶点残基，确认了新兴抗病毒药物JNJ-1802和NITD-688的耐药相关位点在所有四种血清型中保持绝对保守。通过弥合自然语言意图与确定性计算执行之间的差距，biomeStat将数周的专业工作简化为单次分析，且方法学完全透明。

## Abstract
Genomic epidemiology workflows typically require expert curation of multiple specialized tools, extensive manual parameter tuning, and access to heterogeneous compute infrastructure. While standard generative AI models often hallucinate in complex biological domains, we introduce biomeStat: an autonomous AI agent that functions as a strict deterministic orchestrator. By automatically writing code to execute established bioinformatics tools in sandboxed environments, biomeStat dynamically provisions compute resources (CPU and GPU) and guarantees reproducibility, making it immediately useful for scientists without requiring command-line expertise. To demonstrate the platform, we performed a fully autonomous genomic epidemiology and structural analysis of 1,000 Dengue virus (DENV) genomes sampled from 16 Asian countries between 2000 and 2025. The agent seamlessly orchestrated phylogenetic reconstruction (IQ-TREE, TreeTime), Bayesian phylodynamics (BEAST2 via NVIDIA H200 GPU), selection pressure analysis (HyPhy), and structural mapping (PyMOL). The analysis was completed in under 24 hours of wall-clock time, revealing endemic stability (R_e ~1.0) and identifying 1,869 candidate immune escape sites structurally colocalized with B-cell and T-cell epitopes. Furthermore, the agent validated 176 highly conserved drug target residues across the viral replication complex, confirming that resistance-associated positions for emerging antivirals JNJ-1802 and NITD-688 remain absolutely conserved across all four serotypes. By bridging the gap between natural language intent and deterministic computational execution, biomeStat reduces weeks of expert effort into a single-session analysis with full methodological transparency.