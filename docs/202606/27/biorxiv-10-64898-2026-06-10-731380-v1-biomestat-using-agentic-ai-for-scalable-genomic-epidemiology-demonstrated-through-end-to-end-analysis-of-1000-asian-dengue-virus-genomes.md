---
title: "biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes"
title_zh: "biomeStat: 使用智能体AI实现可扩展的基因组流行病学——通过对1000个亚洲登革病毒基因组的端到端分析进行演示"
authors: "Ariyaratne, D., Somaratna, N., Malavige, G. N."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 用于可扩展基因组流行病学的智能体AI，使用自主AI智能体执行生物信息学流程
tldr: 基因组流行病学工作流通常依赖专家手动操作多种工具和调参。biomeStat利用自主AI代理，自动编写代码调用已有生信工具并分配GPU资源，实现端到端自动化分析。对1000个亚洲登革病毒基因组的全自动分析在24小时内完成，揭示了地方性稳定（Re≈1.0）、1869个候选免疫逃逸位点以及176个高度保守药物靶点。该平台将数周专家工作缩短为单次分析，且保证可重复性和方法透明。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因组流行病学分析需要专家手动操作复杂工具和调参，缺乏可扩展性和可重复性。
method: biomeStat作为自主AI代理，通过自动编写代码执行确定性生信工具并动态分配GPU等资源。
result: 全自动分析1000个登革病毒基因组，24小时内完成系统发育、免疫逃逸和药物靶点分析。
conclusion: biomeStat实现了自然语言意图到确定性计算的桥梁，大幅提升分析效率和透明度。
---

## 摘要
基因组流行病学工作流程通常需要专家对多种专业工具进行筛选、大量手动参数调整以及访问异构计算基础设施。尽管标准生成式AI模型在复杂生物领域常出现幻觉，但我们引入了biomeStat：一个自主AI智能体，它作为严格的确定性编排器运行。通过自动编写代码在沙盒环境中执行成熟的生物信息学工具，biomeStat动态配置计算资源（CPU和GPU）并保证可重复性，使其对无需命令行专业知识的科学家立即有用。

为演示该平台，我们对2000年至2025年间从16个亚洲国家采集的1000个登革病毒（DENV）基因组进行了完全自主的基因组流行病学和结构分析。该智能体无缝编排了系统发育重建（IQ-TREE、TreeTime）、贝叶斯系统动力学（通过NVIDIA H200 GPU运行BEAST2）、选择压力分析（HyPhy）和结构映射（PyMOL）。分析在24小时时钟时间内完成，揭示了地方性稳定（R_e [~]1.0），并识别了1869个候选免疫逃逸位点，这些位点在结构上与B细胞和T细胞表位共定位。此外，该智能体在病毒复制复合体上验证了176个高度保守的药物靶点残基，确认针对新兴抗病毒药物JNJ-1802和NITD-688的耐药相关位点在所有四种血清型中绝对保守。通过弥合自然语言意图与确定性计算执行之间的鸿沟，biomeStat将数周的专家工作量减少为单次分析，且方法完全透明。

## Abstract
Genomic epidemiology workflows typically require expert curation of multiple specialized tools, extensive manual parameter tuning, and access to heterogeneous compute infrastructure. While standard generative AI models often hallucinate in complex biological domains, we introduce biomeStat: an autonomous AI agent that functions as a strict deterministic orchestrator. By automatically writing code to execute established bioinformatics tools in sandboxed environments, biomeStat dynamically provisions compute resources (CPU and GPU) and guarantees reproducibility, making it immediately useful for scientists without requiring command-line expertise.

To demonstrate the platform, we performed a fully autonomous genomic epidemiology and structural analysis of 1,000 Dengue virus (DENV) genomes sampled from 16 Asian countries between 2000 and 2025. The agent seamlessly orchestrated phylogenetic reconstruction (IQ-TREE, TreeTime), Bayesian phylodynamics (BEAST2 via NVIDIA H200 GPU), selection pressure analysis (HyPhy), and structural mapping (PyMOL). The analysis was completed in under 24 hours of wall-clock time, revealing endemic stability (R_e [~]1.0) and identifying 1,869 candidate immune escape sites structurally colocalized with B-cell and T-cell epitopes. Furthermore, the agent validated 176 highly conserved drug target residues across the viral replication complex, confirming that resistance-associated positions for emerging antivirals JNJ-1802 and NITD-688 remain absolutely conserved across all four serotypes. By bridging the gap between natural language intent and deterministic computational execution, biomeStat reduces weeks of expert effort into a single-session analysis with full methodological transparency.