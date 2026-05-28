---
title: Pathway redistribution across cellular states reveals a shared signaling backbone and context-dependent regulatory modules in RNA-binding protein networks
title_zh: 跨细胞状态的通路重分布揭示RNA结合蛋白网络中的共享信号主干和上下文依赖性调控模块
authors: "Osato, N., Sato, K."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.1101/2025.03.03.641203v12.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 整合深度学习与共表达分析研究功能基因组学中的通路重分布
tldr: 理解调控架构跨细胞状态重组是功能基因组学的挑战。本研究整合共表达衍生调控网络与可解释深度学习，生成基因贡献分数并引入delta NES量化通路重分布。在神经祖细胞和K562白血病细胞中，发现RNA结合蛋白PKM、HNRNPK、NELFE等调控模块系统性重分布，信号转导通路形成共享骨架，而神经、免疫等模块呈现上下文依赖重分布。子通路分析显示汇聚于FGFR/RTK、IRS、MAPK等受体介导信号通路。该方法为超越传统表达中心分析的调控架构解析提供了新框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 理解调控架构如何随细胞状态重组，突破传统表达中心分析局限。
method: 整合共表达衍生调控网络与DeepLIFT深度学习，生成基因贡献分数并引入delta NES量化通路重分布。
result: 在神经祖细胞与K562中，发现PKM、HNRNPK、NELFE等RNA结合蛋白模块重分布，信号转导为共享骨架，神经/免疫模块呈上下文依赖。
conclusion: 贡献分数通路排名揭示保守信号骨架与上下文依赖模块，为解析细胞状态调控架构提供新视角。
---

## 摘要
理解调控架构如何在不同细胞上下文中重组仍然是功能基因组学中的一个核心挑战。在这里，我们将共表达衍生的候选调控相互作用与可解释深度学习相结合，生成基因水平贡献评分，并引入delta NES（归一化富集评分差异）来量化细胞状态间的通路重分布。由于基因表达反映了多个调控输入的综合效应，贡献评分捕捉的是相对调控影响而非转录丰度本身。将该框架应用于神经祖细胞和K562白血病细胞，我们识别出多个RNA结合蛋白（包括PKM、HNRNPK和NELFE）功能模块的系统性重分布。神经系统和免疫系统相关模块沿delta NES谱差异定位，表明调控影响的上下文依赖性重分布，而非孤立的通路激活事件。在通路水平上，信号转导在不同蛋白质和细胞上下文中一致地形成共享信号主干，而与神经元功能、免疫反应和发育过程相关的模块则表现出上下文依赖性重分布。亚通路分析进一步揭示受体介导的信号传导过程的趋同，包括FGFR/RTK、IRS和MAPK相关通路。尽管贡献-表达相关性存在极性变化，但在替代性DeepLIFT背景设置下这些重分布模式得以保持，表明通路水平对比源于稳定的等级结构差异而非背景依赖的评分假象。综上所述，我们的发现表明基于贡献评分的通路排名揭示了保守的信号主干以及上下文依赖性功能模块，为超越以表达为中心的分析来解读调控架构提供了框架。

## Abstract
Understanding how regulatory architectures are reorganized across cellular contexts remains a central challenge in functional genomics. Here, we integrate co-expression-derived candidate regulatory interactions with interpretable deep learning to generate gene-level contribution scores and introduce delta NES (normalized enrichment score difference) to quantify pathway redistribution between cellular states. Because gene expression reflects the combined effects of multiple regulatory inputs, contribution scores capture relative regulatory influence rather than transcriptional abundance itself. Applying this framework to neural progenitor cells and K562 leukemia cells, we identify systematic redistribution of functional modules across multiple RNA-binding proteins, including PKM, HNRNPK, and NELFE. Neural System- and Immune System-associated modules are differentially positioned along the delta NES spectrum, indicating context-dependent redistribution of regulatory influence rather than isolated pathway activation events. At the pathway level, Signal Transduction consistently forms a shared signaling backbone across proteins and cellular contexts, while modules related to neuronal functions, immune responses, and developmental processes exhibit context-dependent redistribution. Subpathway analysis further reveals convergence on receptor-mediated signaling processes, including FGFR/RTK-, IRS-, and MAPK-related pathways. These redistribution patterns are preserved under alternative DeepLIFT background settings despite polarity changes in contribution-expression correlations, indicating that pathway-level contrasts arise from stable rank-structure differences rather than background-dependent score artifacts. Together, our findings demonstrate that contribution score-based pathway ranking reveals a conserved signaling backbone alongside context-dependent functional modules, providing a framework for interpreting regulatory architecture beyond expression-centric analyses.