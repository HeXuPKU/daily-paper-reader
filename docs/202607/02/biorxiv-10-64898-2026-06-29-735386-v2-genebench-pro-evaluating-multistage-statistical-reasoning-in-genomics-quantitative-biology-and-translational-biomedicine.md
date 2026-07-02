---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化生物医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 基因组学AI智能体基准测试
tldr: "现有AI基准难以评估复杂多阶段科学推理。GeneBench-Pro扩展了GeneBench，新增和修订问题，涵盖基因组学、定量生物学和转化生物医学共129个评估任务。模型需自主完成完整分析工作流。最佳模型GPT-5.6 Sol Pro仅达31.5%，其他模型更低，且普遍存在“注意-行动”差距。该基准揭示了AI在长期生物推理上的能力与局限。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准多聚焦单步任务，缺乏对真实多阶段科学推理中多个依赖于前序决策的推理分支的评估。
method: 在GeneBench基础上新增29个问题、修订54个，由外部专家审核82个问题，形成覆盖10个主要领域和21个子领域的129任务基准。
result: "GPT-5.6 Sol Pro达到31.5%最高通过率，GPT-5.5为12.0%，Claude Opus 4.8为16.0%，模型常能部分执行但无法连贯决策。"
conclusion: GeneBench-Pro衡量了AI在基因组学和生物医学中多阶段统计推理的新兴能力，但当前模型表现不可靠，存在显著的推理漏洞。
---

## 摘要
我们推出了GeneBench-Pro，这是GeneBench的扩展和改进版本，包含更广泛领域中难度更高的问题。GeneBench-Pro是一个针对AI智能体在基因组学、定量生物学和转化生物医学中执行现实多阶段科学分析的基准测试，旨在捕捉计算生命科学家在得出下游科学或转化决策所依赖的结论时所面临的真实问题的复杂性。该基准包含129项评估，直接针对10个主要领域和21个终端子领域中具有实际相关性的量，并以基因组学为核心。与GeneBench类似，每个问题为智能体提供简要背景、目标估计量以及极少的其他指导；智能体随后必须导航多个依赖决策点（即实质性的推理分叉点，在这些点上看似合理但错误的选择会改变下游分析），以识别并执行正确的分析工作流程，从而得出正确答案。相对于GeneBench，GeneBench-Pro新增29个问题，删除了3个问题，并对剩余100个重叠问题中的54个进行了显著重新设计。129个问题中有82个由外部领域专家审查，其发现导致对目标不够明确的问题进行了提示/数据修改和重新设计。十个经过外部审查的问题已公开发布，50个保留问题提供给Artificial Analysis进行独立的第三方模型基准测试，其余问题作为内部保留集。在全套129个问题的评估中，GPT-5.6 Sol在最大推理水平上达到28.7%的评估级通过率，而GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常能完成工作流程的大部分内容，但在注意到局部诊断信号后，未能将这些影响传递到相应的分析决策，从而在注意和行动之间表现出持续的差距。结果，模型经常选择错误的估计量或坚持最初看似合理但错误的分析路径。因此，GeneBench-Pro衡量了一种新兴的长期生物推理能力，但这种能力仍然不可靠。



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v1_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@1868524org.highwire.dtl.DTLVardef@8f10b4org.highwire.dtl.DTLVardef@91c4caorg.highwire.dtl.DTLVardef@ee9aa_HPS_FORMAT_FIGEXP  M_FIG C_FIG

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v1_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@1868524org.highwire.dtl.DTLVardef@8f10b4org.highwire.dtl.DTLVardef@91c4caorg.highwire.dtl.DTLVardef@ee9aa_HPS_FORMAT_FIGEXP  M_FIG C_FIG