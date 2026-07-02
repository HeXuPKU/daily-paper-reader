---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning\\\\in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: "GeneBench-Pro: 评估基因组学、定量生物学和转化生物医学中的多阶段统计推理"
authors: "Li, J. H., Ho, A. J."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 基因组学AI智能体基准测试
tldr: "GeneBench-Pro 扩展了 GeneBench，涵盖 129 个评估问题，覆盖基因组学、定量生物学和转化医学等 10 个主要领域。问题要求 AI agent 自主完成多阶段统计推理，并在多个关键决策点做出正确选择。当前最强模型 GPT-5.6 Sol Pro 在最高推理级别下仅达到 31.5% 的通过率，而 Claude Opus 4.8 为 16.0%。模型虽能完成大部分分析流程，但常在识别局部信号后未能将其转化为全局决策，导致选择错误估计量或陷入错误路径。该基准揭示了长期生物学推理能力的不足，是评估 agent 实际科研能力的重要工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准无法捕获真实计算生物学问题中多阶段决策的复杂性，因此需构建更难的基准来评估 AI agent 的统计推理能力。
method: 设计 129 个需要多步推理的问题，每个问题提供简要上下文和目标估计量，agent 需自主导航多个决策分支以找到正确分析流程。
result: "GPT-5.6 Sol Pro 达到 31.5% 的通过率，GPT-5.5 为 12.0%，非 GPT 最强模型 Claude Opus 4.8 为 16.0%，模型普遍存在“注意到但未行动”的差距。"
conclusion: GeneBench-Pro 测量了 agent 在长期生物学推理上的新兴能力，但当前模型表现仍不可靠，需要进一步改进。
---

## 摘要
我们推出了GeneBench-Pro，这是GeneBench的扩展和改进版本，涵盖了更广泛领域中难度更高的问题。GeneBench-Pro是一个基准测试，用于评估AI智能体在基因组学、定量生物学和转化生物医学中执行逼真的多阶段科学分析的能力，旨在捕捉计算生命科学家在实际问题中所面临的复杂性，这些问题的结论将决定下游科学或转化决策。该基准包含129个评估任务，针对10个主要领域和21个终端子领域中具有直接实际相关性的量，以基因组学为核心。与GeneBench类似，每个问题仅为智能体提供简短的背景、目标估计量和最少的指导；智能体必须导航多个依赖决策点，即实质性的推断岔路，其中看似合理但错误的选择会改变下游分析，从而识别并执行正确的分析工作流并得出正确答案。与GeneBench相比，GeneBench-Pro新增了29个问题，删除了3个，并对剩余100个重叠问题中的54个进行了重大重新设计。129个问题中有82个经过外部领域专家评审，根据评审结果对提示/数据进行了修改，并重新设计了那些目标不够明确的问题。十个经外部评审的问题已公开发布，50个保留问题提供给Artificial Analysis用于独立第三方模型基准测试，其余问题作为内部保留集。在对全部129个问题的评估中，GPT-5.6 Sol在最大推理水平下达到28.7%的评估级通过率，而GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench类似，模型通常能完成工作流的相当部分，但在注意到和行动之间表现出持续差距，即能识别局部诊断信号，但未能将影响传播到相应的分析决策。因此，模型常常选择错误的估计量，或坚持最初看似合理但实际上不正确的分析路径。因此，GeneBench-Pro衡量的是长程生物推理的一种新兴能力，而这种能力仍不可靠。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v1_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@1868524org.highwire.dtl.DTLVardef@8f10b4org.highwire.dtl.DTLVardef@91c4caorg.highwire.dtl.DTLVardef@ee9aa_HPS_FORMAT_FIGEXP  M_FIG C_FIG