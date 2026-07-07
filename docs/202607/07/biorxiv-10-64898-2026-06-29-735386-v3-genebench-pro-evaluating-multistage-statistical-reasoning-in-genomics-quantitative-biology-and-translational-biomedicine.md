---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v3.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 用于基因组学和转化生物医学中AI智能体的评估基准
tldr: "GeneBench-Pro是GeneBench的扩展版本，包含129个评估任务，覆盖基因组学、定量生物学和转化生物医学领域的多阶段科学推理。该基准要求AI代理在给定背景和目标后，自主导航多个依赖决策点以完成正确分析。测试中，最强模型GPT-5.6 Sol Pro的通过率仅31.5%，而GPT-5.5为12.0%，表明模型在长程生物推理中仍不可靠。主要贡献是提供了一个评估AI代理在复杂科学分析中实用推理能力的基准。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准未能模拟真实世界多阶段科学推理的复杂性，GeneBench-Pro通过更广泛的领域和更难的问题填补这一空白。
method: 从10个主领域和21个子领域收集129个问题，每个问题需要AI代理自主完成多步分析流程，并依赖外部专家审查确保问题质量。
result: "GPT-5.6 Sol Pro在完整129个问题上达到31.5%的通过率，GPT-5.5为12.0%，非GPT最强基线Claude Opus 4.8为16.0%，模型常因无法将局部诊断信号转化为全局决策而失败。"
conclusion: GeneBench-Pro揭示了AI代理在长程生物推理中的能力缺口，模型虽能完成部分流程，但在关键决策点易出错，表明该任务仍是重大挑战。
---

## 摘要
我们推出GeneBench-Pro，这是GeneBench的扩展和改进版本，包含跨更广泛领域的更难问题。GeneBench-Pro是一个用于AI智能体在基因组学、定量生物学和转化医学中执行现实多阶段科学分析的基准，旨在捕捉计算生命科学家在需要得出下游科学或转化决策所依赖的结论时面对的现实问题的复杂性。该基准包含129项评估，针对10个主要领域和21个终端子领域中直接具有实际相关性的量，以基因组学为核心。与GeneBench类似，每个问题为智能体提供简要上下文、目标估计量，以及极少的其他指导；智能体必须导航多个依赖决策点，即实质性的推断分叉，其中看似合理的错误选择会改变下游分析，以识别并执行正确的分析工作流程，并得出正确答案。相对于GeneBench，GeneBench-Pro增加了29个新问题，删除了3个，并对剩余100个重叠问题中的54个进行了显著重新设计。129个问题中有82个经过外部领域专家评审，其发现导致对目标不够明确的问题进行了提示/数据修改和重新设计。十个经过外部评审的问题公开发布，50个保留问题提供给Artificial Analysis进行独立的第三方模型基准测试，其余作为内部保留。在对全部129个问题的评估中，GPT-5.6 Sol在最大推理水平下达到28.7%的评估级通过率，GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线模型Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常完成工作流程的大部分，但在注意到和行动之间始终存在差距，即识别局部诊断信号但未能将影响传播到相应的分析决策。因此，模型经常选择错误的估计量，或坚持最初看似合理但错误的分析路径。因此，GeneBench-Pro衡量了一种仍不可靠的长程生物学推理的新兴能力。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v2_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@113198borg.highwire.dtl.DTLVardef@f2225corg.highwire.dtl.DTLVardef@ae01fforg.highwire.dtl.DTLVardef@52f92_HPS_FORMAT_FIGEXP  M_FIG C_FIG