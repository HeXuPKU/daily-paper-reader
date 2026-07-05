---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning\\\\in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化生物医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 基因组学AI智能体多阶段统计推理基准
tldr: "现实中的计算生物学家常需执行多阶段科学分析以支持下游决策，但现有基准难以评估这类能力。为此提出GeneBench-Pro，扩展了元基准GeneBench，包含129个需多步推理的问题，涵盖基因组学、定量生物学等10个领域。最强模型GPT-5.6 Sol Pro的通过率仅为31.5%，模型能识别局部诊断信号但常无法整合至全局分析决策。该基准揭示了长时程生物推理作为新兴能力仍不可靠的现状。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准缺乏对多阶段科学分析中复杂推理链的评估，亟需更贴近真实问题的测试。
method: 基于GeneBench扩展29个新问题并重新设计54个，形成129个问题，涵盖10个主领域，要求AI代理自主导航多个决策点。
result: "GPT-5.6 Sol Pro达31.5%最高通过率，Claude Opus 4.8为16.0%，模型在整合局部信息至下游决策时普遍失败。"
conclusion: GeneBench-Pro揭示了AI在长时程生物推理上的不足，可作为衡量该新兴能力的有效基准。
---

## 摘要
我们介绍了GeneBench-Pro，这是GeneBench的一个扩展和改良版本，包含了更广泛领域中更困难的问题。GeneBench-Pro是一个针对AI代理在基因组学、定量生物学和转化生物医学中执行现实多阶段科学分析的基准测试，旨在捕捉计算生命科学家在面对需要得出下游科学或转化决策所依赖的结论时所遇到的现实问题的复杂性。该基准包含129个评估，针对10个主要领域和21个终端子领域中直接实际相关的量，以基因组学为核心。与GeneBench类似，每个问题为代理提供简要背景、目标估计量以及最低限度的指导；代理必须导航多个依赖决策点，即实质性的推断分叉，在这些分叉中一个看似合理但错误的选择会改变下游分析，从而识别并执行正确的分析工作流程，得出正确答案。相对于GeneBench，GeneBench-Pro增加了29个新问题，删除了3个，并对剩余100个重叠问题中的54个进行了显著重新设计。129个问题中有82个由外部领域专家审查，他们的发现导致了对那些目标不够明确的问题的提示/数据修改和重新设计。十个经过外部审查的问题公开发布，50个保留问题提供给Artificial Analysis用于独立第三方模型基准测试，其余作为内部保留。在完整的129个问题集评估中，GPT-5.6 Sol在最大推理级别上达到了28.7%的评估级通过率，而GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到了31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常完成了工作流程的很大部分，但在注意到和行动之间表现出一致的差距：识别局部诊断信号，但未能将含义传播到相应的分析决策。因此，模型经常选择错误的估计量，或坚持最初看似合理但错误的分析路径。因此，GeneBench-Pro衡量了一种新兴的长周期生物学推理能力，这种能力仍然不可靠。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.