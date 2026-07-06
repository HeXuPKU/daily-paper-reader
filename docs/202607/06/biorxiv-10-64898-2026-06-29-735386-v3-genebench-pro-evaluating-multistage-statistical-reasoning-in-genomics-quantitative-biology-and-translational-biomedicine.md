---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v3.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 评估AI智能体在基因组学推理能力的基准，涉及大语言模型与智能体
tldr: "GeneBench-Pro是面向基因组学、定量生物学和转化生物医学中多阶段统计推理的扩展基准，包含129个覆盖10个主要领域的实际问题。相比原版，新增29个问题并重新设计54个，引入外部专家审查。评估显示最先进模型GPT-5.6 Sol Pro仅达31.5%通过率，模型常完成大部分流程但无法将局部诊断信号转化为正确决策，揭示了长期生物推理能力仍不可靠。该基准为AI在复杂科学分析中的长程推理能力提供了关键度量。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准无法反映真实世界中多步科学分析中依赖下游决策的复杂性，亟需评估AI在多阶段统计推理中的能力。
method: 扩展GeneBench至129个问题，涵盖10个主领域21个子领域，要求模型在极少指导下自主导航多个决策分支并执行正确工作流。
result: "GPT-5.6 Sol Pro达31.5%通过率，GPT-5.5为12.0%，Claude Opus 4.8为16.0%，模型普遍存在识别信号但无法传导至正确选择的间隙。"
conclusion: GeneBench-Pro揭示了长期生物推理仍不可靠，为AI在复杂科学分析中的长程推理能力提供了关键度量。
---

## 摘要
我们介绍了GeneBench-Pro，它是GeneBench的扩展和改进版本，包含跨更广泛领域的更难题。GeneBench-Pro是一个基准测试，用于评估AI代理在基因组学、定量生物学和转化医学中执行真实多阶段科学分析的能力，旨在捕捉计算生命科学家在需要产出结论（下游科学或转化决策依赖于该结论）时所面临的现实问题的复杂性。该基准包含129个评估，针对10个主要领域和21个终端子领域中直接实际相关的量，以基因组学为核心。与GeneBench类似，每个问题为代理提供简要背景、目标估计量以及最低限度的指导；代理随后需要导航多个依赖的决策点，即重要的推理分岔点，在这些点上，一个看似合理的错误选择会改变下游分析，从而识别并执行正确的分析工作流程，并得出正确答案。相对于GeneBench，GeneBench-Pro新增了29个问题，删除了3个问题，并对剩余100个重叠问题中的54个进行了显著重新设计的版本。129个问题中有82个由外部领域专家审查，其发现导致了对那些目标不够可识别的问题的提示/数据修改和重新设计。十个经过外部审查的问题公开发布，50个保留问题提供给Artificial Analysis进行独立的第三方模型基准测试，其余问题作为内部保留集。在对全部129个问题的评估中，GPT-5.6 Sol在最大推理级别上达到28.7%的评估级通过率，而GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常完成工作流程的大部分，但在注意到和行动之间表现出持续的差距，即识别局部诊断信号但未能将影响传播到相应的分析决策。因此，模型常常选择错误的估计量或坚持最初看似合理但错误的分析路径。因此，GeneBench-Pro衡量了长期生物推理的新兴能力，而这种能力仍然不可靠。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v2_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@f7c80org.highwire.dtl.DTLVardef@b6e5b1org.highwire.dtl.DTLVardef@1a1df6corg.highwire.dtl.DTLVardef@5361a2_HPS_FORMAT_FIGEXP  M_FIG C_FIG