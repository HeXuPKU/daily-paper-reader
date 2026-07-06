---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning\\\\in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化生物医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 评估AI智能体在基因组学推理能力的基准，涉及大语言模型与智能体
tldr: "GeneBench-Pro是GeneBench的扩展版本，包含129个评估问题，覆盖基因组学、定量生物学和转化生物医学等10个主要领域。该基准测试要求AI代理在多阶段科学分析中做出多个依赖决策点，模拟真实计算生物学家的工作流程。评估显示，最强模型GPT-5.6 Sol Pro的通过率仅为31.5%，且模型经常能在工作流中完成大部分步骤，但存在从注意到行动的关键差距。GeneBench-Pro衡量了长期生物推理这一新兴能力，表明其仍不可靠。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准无法捕捉真实世界计算生物学问题中的多阶段推理复杂性，需要更难、更广的评估。
method: 构建129个问题，包含10个主域和21个子域，每个问题需要代理在多个决策点自主选择正确的分析工作流。
result: "GPT-5.6 Sol Pro达31.5%通过率，Claude Opus 4.8为16.0%，模型普遍在识别局部信号后未能正确传播至分析决策。"
conclusion: GeneBench-Pro测出AI在复杂生物推理中存在显著不可靠性，长程推理能力仍待提升。
---

## 摘要
我们推出了GeneBench-Pro，这是GeneBench的扩展和改进版本，包含了跨更广泛领域的更难问题。GeneBench-Pro是一个用于评估AI代理在基因组学、定量生物学和转化生物医学中执行现实多阶段科学分析的基准，旨在捕捉计算生命科学家在需要得出下游科学或转化决策所依赖的结论时所面临的实际问题的复杂性。该基准包含129项评估，针对10个主要领域和21个终端子领域中具有直接实际相关性的量，以基因组学为核心。与GeneBench类似，每个问题为代理提供简短的背景、目标估计量以及最少的其他指导；代理必须导航多个依赖决策点，即实质性的推断分叉，在这些分叉处一个看似合理的错误选择会改变下游分析，从而识别并执行正确的分析工作流程，得出正确答案。相对于GeneBench，GeneBench-Pro新增了29个问题，删除了3个，并对剩余100个重叠问题中的54个进行了显著重新设计版本。129个问题中有82个由外部领域专家审查，其发现导致了那些目标不够明确的问题的提示/数据修改和重新设计。十个经外部审查的问题公开发布，50个保留问题提供给Artificial Analysis进行独立的第三方模型基准测试，其余作为内部保留。在完整129个问题套件的评估中，GPT-5.6 Sol在最大推理级别的评估级通过率达到28.7%，GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常完成工作流程的很大一部分，但在注意和行动之间表现出持续差距：识别局部诊断信号但未能将影响传播到相应的分析决策。因此，模型经常选择错误的估计量或坚持最初看似合理但错误的分析路径。因此，GeneBench-Pro衡量了一种新兴但仍不可靠的长视野生物推理能力。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v2_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@f7c80org.highwire.dtl.DTLVardef@b6e5b1org.highwire.dtl.DTLVardef@1a1df6corg.highwire.dtl.DTLVardef@5361a2_HPS_FORMAT_FIGEXP  M_FIG C_FIG