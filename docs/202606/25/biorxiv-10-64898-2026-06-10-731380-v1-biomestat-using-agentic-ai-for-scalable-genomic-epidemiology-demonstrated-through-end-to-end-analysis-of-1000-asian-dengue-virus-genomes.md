---
title: "biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes"
title_zh: biomeStat：利用自主人工智能实现可扩展的基因组流行病学——通过对1000个亚洲登革病毒基因组的端到端分析进行演示
authors: "Ariyaratne, D., Somaratna, N., Malavige, G. N."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 智能体AI应用于基因组流行病学，与医疗AI中的智能体相关
tldr: 基因组流行病学分析通常需要专家手动调整多个工具和参数，计算基础设施复杂。biomeStat作为自主AI代理，通过自动编写代码执行确定性生物信息学工具，在沙盒环境中动态分配CPU/GPU资源，确保可重复性。对1000个亚洲登革病毒基因组进行全自主分析，24小时内完成系统发育重建、贝叶斯系统动力学、选择压力分析和结构映射，揭示了地方性稳定（R_e≈1.0），识别1869个免疫逃逸位点并验证176个高度保守药物靶点。该方法将专家数周工作缩短为单次分析，兼具透明性和可扩展性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因组流行病学工作流依赖专家手动调整多种工具和计算资源，效率低且易出错，缺乏可重复性。
method: biomeStat利用大语言模型作为确定性编排器，自动生成代码执行IQ-TREE、BEAST2等工具，在沙盒环境中动态配置CPU/GPU资源。
result: "分析1,000个亚洲登革病毒基因组，24小时内完成，发现R_e≈1.0的地方性稳定态，识别1,869个免疫逃逸位点，176个药物靶点高度保守。"
conclusion: biomeStat将自然语言意图转化为确定性计算执行，大幅降低基因组流行病学分析门槛，保证全流程透明可重复。
---

## 摘要
基因组流行病学工作流程通常需要专家对多个专业工具进行精心策划、大量手动参数调整以及访问异构计算基础设施。虽然标准的生成式AI模型在复杂生物领域常产生幻觉，但我们引入了biomeStat：一个自主AI智能体，充当严格的确定性协调器。通过自动编写代码在沙盒环境中执行成熟的生物信息学工具，biomeStat动态配置计算资源（CPU和GPU）并保证可重复性，使其立即对无需命令行专业知识的科学家有用。

为演示该平台，我们对2000年至2025年间从16个亚洲国家采样的1000个登革病毒基因组进行了完全自主的基因组流行病学和结构分析。该智能体无缝协调了系统发育重建（IQ-TREE、TreeTime）、贝叶斯系统动力学（通过NVIDIA H200 GPU运行BEAST2）、选择压力分析（HyPhy）和结构映射（PyMOL）。在不到24小时的墙钟时间内完成分析，揭示了地方性稳定（R_e≈1.0），并识别出1869个与B细胞和T细胞表位结构共定位的候选免疫逃逸位点。此外，该智能体验证了病毒复制复合体中176个高度保守的药物靶点残基，确认了新兴抗病毒药物JNJ-1802和NITD-688的耐药相关位点在所有四种血清型中保持绝对保守。通过弥合自然语言意图与确定性计算执行之间的差距，biomeStat将数周的专家工作缩减为一次会话分析，并具备完全的方法透明性。

## Abstract
Genomic epidemiology workflows typically require expert curation of multiple specialized tools, extensive manual parameter tuning, and access to heterogeneous compute infrastructure. While standard generative AI models often hallucinate in complex biological domains, we introduce biomeStat: an autonomous AI agent that functions as a strict deterministic orchestrator. By automatically writing code to execute established bioinformatics tools in sandboxed environments, biomeStat dynamically provisions compute resources (CPU and GPU) and guarantees reproducibility, making it immediately useful for scientists without requiring command-line expertise.

To demonstrate the platform, we performed a fully autonomous genomic epidemiology and structural analysis of 1,000 Dengue virus (DENV) genomes sampled from 16 Asian countries between 2000 and 2025. The agent seamlessly orchestrated phylogenetic reconstruction (IQ-TREE, TreeTime), Bayesian phylodynamics (BEAST2 via NVIDIA H200 GPU), selection pressure analysis (HyPhy), and structural mapping (PyMOL). The analysis was completed in under 24 hours of wall-clock time, revealing endemic stability (R_e [~]1.0) and identifying 1,869 candidate immune escape sites structurally colocalized with B-cell and T-cell epitopes. Furthermore, the agent validated 176 highly conserved drug target residues across the viral replication complex, confirming that resistance-associated positions for emerging antivirals JNJ-1802 and NITD-688 remain absolutely conserved across all four serotypes. By bridging the gap between natural language intent and deterministic computational execution, biomeStat reduces weeks of expert effort into a single-session analysis with full methodological transparency.