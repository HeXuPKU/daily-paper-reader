---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning\\\\in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化生物医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 用于评估AI智能体在基因组学多阶段统计推理能力的基准，涉及大规模基因组模型和医疗大语言模型
tldr: "GeneBench-Pro 是一个扩展基准，评估 AI agent 在基因组学、定量生物学和转化生物医学中的多阶段统计推理能力。它包含 129 个真实问题，覆盖 10 个领域，要求 agent 自主导航多个依赖决策点。最强模型 GPT-5.6 Sol Pro 仅达 31.5% 通过率，Claude Opus 4.8 为 16.0%，模型常识别局部信号但未能影响全局分析决策。该基准揭示了当前模型在长期复杂科学推理中的可靠性不足，为未来研究提供关键评估平台。"
source: biorxiv
selection_source: fresh_fetch
motivation: 评估 AI agent 执行真实多阶段科学分析时的统计推理能力，模拟计算生物学家面临的复杂决策路径。
method: 构建包含 129 个问题的新基准，覆盖 10 个主要领域，要求 agent 自行选择正确分析工作流并计算目标量。
result: "GPT-5.6 Sol Pro 最高通过率 31.5%，Claude Opus 4.8 为 16.0%，模型常完成部分流程但推理链不完整。"
conclusion: 当前模型在长期生物推理上仍不可靠，存在识别与行动间的显著差距，需提升整体决策能力。
---

## 摘要
我们推出了GeneBench-Pro，这是GeneBench的扩展和改进版本，包含跨更广泛领域的更难问题。GeneBench-Pro是一个针对AI代理的基准测试，用于在基因组学、定量生物学和转化生物医学中执行现实的多阶段科学分析，旨在捕捉计算生命科学家在需要得出下游科学或转化决策所依赖的结论时面临的现实问题的复杂性。该基准包含129个评估，针对10个主要领域和21个终端子领域中具有直接实际相关性的量，核心围绕基因组学。与GeneBench类似，每个问题为代理提供简要背景、目标估计量以及最小指导；代理随后需要导航多个依赖决策点——即实质性推理分支，其中看似合理但错误的选择会改变下游分析——以识别并执行正确的分析工作流程，得出正确答案。相对于GeneBench，GeneBench-Pro新增了29个问题，删除了3个，并对剩余100个重叠问题中的54个引入了显著重新设计的版本。129个问题中有82个经过外部领域专家评审，他们的发现导致对目标不够明确的问题进行了提示/数据修改和重新设计。十个经过外部评审的问题公开发布，50个保留问题提供给Artificial Analysis进行独立第三方模型基准测试，其余作为内部保留。在完整129个问题的评估中，GPT-5.6 Sol在最大推理级别上达到28.7%的评估级通过率，而GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常完成工作流程的大部分，但在注意与行动之间存在一致差距，即识别局部诊断信号但未能将含义传播到相应的分析决策。因此，模型经常选择错误的估计量或坚持最初看似合理但错误的分析路径。因此，GeneBench-Pro衡量了长期生物推理的一种新兴能力，这种能力目前仍然不可靠。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.