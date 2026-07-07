---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning\\\\in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: "GeneBench-Pro: 评估基因组学、定量生物学和转化生物医学中的多阶段统计推理"
authors: "Li, J. H., Ho, A. J."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 基因组学AI智能体基准，多阶段推理
tldr: "现有基准未能真实反映计算生物问题中多阶段统计推理的复杂性。GeneBench-Pro扩展了GeneBench，包含129个跨基因组学、定量生物学等领域的难题，要求模型在多决策点中导航。最强模型GPT-5.6 Sol Pro仅达31.5%，Claude Opus 4.8为16.0%。模型常完成大部分流程但存在从注意到行动的差距，未能正确选择估算器或路径。该基准衡量了长期生物推理这一新兴但不可靠的能力。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准无法捕获真实计算生物问题中多阶段统计推理的复杂性，需要更广更难的评估。
method: 扩展GeneBench，新增29个问题，修改54个，覆盖10个领域21个子领域，经外部专家审核。
result: "GPT-5.6 Sol Pro最高31.5%，Claude Opus 4.8达16.0%，模型常完成部分流程但未做出正确分析决策。"
conclusion: GeneBench-Pro揭示了AI在长期生物推理中从注意到行动的持续差距，该能力仍不可靠。
---

## 摘要
我们推出了GeneBench-Pro，这是GeneBench的一个扩展和改进版本，包含跨更广泛领域的更难问题。GeneBench-Pro是一个基准测试，用于评估AI代理在基因组学、定量生物学和转化生物医学中执行逼真的多阶段科学分析的能力，旨在捕捉计算生命科学家在面临需要得出影响下游科学或转化决策的结论时所遇到的现实世界问题的复杂性。该基准包括129个评估任务，针对10个主要领域和21个终端子领域中具有直接实际意义的量，以基因组学为核心。与GeneBench类似，每个问题为代理提供简短背景、目标估计量以及最少的指导；代理必须导航多个依赖决策点，即有实质性推断分叉的地方，一个看似正确的错误选择会改变下游分析，从而识别并执行正确的分析工作流并得出正确答案。相对于GeneBench，GeneBench-Pro新增了29个问题，删除了3个，并对剩余100个重叠问题中的54个进行了重大重新设计。129个问题中有82个由外部领域专家审查，他们的发现导致了提示/数据修改和对那些目标不够明确的问题的重新设计。十个经外部审查的问题公开发布，50个保留问题提供给Artificial Analysis作为独立的第三方模型基准测试，其余保留为内部保留集。在全部129个问题的评估中，GPT-5.6 Sol在最大推理级别达到了28.7%的评估级通过率，而GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到了31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常能完成工作流的很大一部分，但在注意到和行动之间存在一致的差距：它们能识别局部诊断信号，但未能将含义传播到相应的分析决策。因此，模型经常选择错误的估计量，或坚持最初看似合理但实际上不正确的分析路径。因此，GeneBench-Pro衡量了长时间跨度生物推理的一种新兴能力，而这种能力仍然不可靠。



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v2_ufig1.gif" ALT="Figure 1">
查看更大版本 (13K):
org.highwire.dtl.DTLVardef@113198borg.highwire.dtl.DTLVardef@f2225corg.highwire.dtl.DTLVardef@ae01fforg.highwire.dtl.DTLVardef@52f92_HPS_FORMAT_FIGEXP  M_FIG C_FIG

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v2_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@113198borg.highwire.dtl.DTLVardef@f2225corg.highwire.dtl.DTLVardef@ae01fforg.highwire.dtl.DTLVardef@52f92_HPS_FORMAT_FIGEXP  M_FIG C_FIG