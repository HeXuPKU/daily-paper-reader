---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 基因组学AI智能体多阶段统计推理基准
tldr: "GeneBench-Pro是一个评估AI代理在基因组学、定量生物学和转化生物医学中进行多阶段统计推理的基准。它包含129个评估问题，覆盖10个主要领域和21个子领域，要求代理在多个依赖决策点中导航以执行正确的分析工作流。在全面测试中，最佳模型GPT-5.6 Sol Pro的通过率仅为31.5%，而其他模型更低。该基准揭示了模型在长周期生物推理中“注意到但未行动”的缺陷，因此衡量了当前仍不可靠的新兴能力。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准无法捕捉真实世界多阶段科学分析的复杂性，GeneBench-Pro旨在测试AI代理在复杂推理中的执行能力。
method: 扩展了GeneBench，新增29个问题，重新设计54个问题，共计129个评估，由领域专家审查，并分为公开、留出和内部保留集。
result: "GPT-5.6 Sol Pro达到31.5%的通过率，Claude Opus 4.8为16.0%，模型常因无法传递局部诊断信号而选择错误估计或路径。"
conclusion: GeneBench-Pro衡量了一种仍不可靠的长周期生物推理能力，揭示了模型在识别与行动之间的关键差距。
---

## 摘要
我们推出GeneBench-Pro，这是GeneBench的扩展和改进版本，包含跨更广泛领域的更难问题。GeneBench-Pro是一个面向AI代理的基准测试，用于执行基因组学、定量生物学和转化医学中现实的多阶段科学分析，旨在捕捉计算生命科学家在需要得出结论（下游科学或转化决策依赖于该结论）时所面临的现实问题的复杂性。该基准包含129个评估，针对10个主要领域和21个终端子领域中具有直接实际意义的数量，以基因组学为核心。与GeneBench类似，每个问题为代理提供简要背景、目标估计量，以及极少的其他指导；代理必须导航多个依赖决策点，即实质性推理岔路，其中看似合理的错误选择会改变下游分析，以识别并执行正确的分析工作流程，得出正确答案。相对于GeneBench，GeneBench-Pro新增了29个问题，删除了3个，并对剩余100个重叠问题中的54个进行了显著重新设计。129个问题中有82个经过外部领域专家评审，其发现导致了提示/数据修改以及目标不够明确的问题的重新设计。十个经过外部评审的问题公开发布，50个保留问题提供给Artificial Analysis进行独立的第三方模型基准测试，其余部分保留为内部保留集。在完整的129个问题套件评估中，GPT-5.6 Sol在最大推理级别达到28.7%的评估级通过率，而GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常完成工作流程的实质性部分，但在注意到和行动之间表现出一致的差距，即识别局部诊断信号但未能将影响传播到相应的分析决策。因此，模型经常选择错误的估计量或坚持最初看似合理但错误的分析路径。因此，GeneBench-Pro衡量了长期生物推理的一种新兴能力，这种能力仍然不可靠。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.