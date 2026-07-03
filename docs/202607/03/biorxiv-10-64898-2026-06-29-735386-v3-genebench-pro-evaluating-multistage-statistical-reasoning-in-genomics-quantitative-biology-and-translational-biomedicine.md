---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化生物医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v3.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: GeneBench-Pro基准测试AI代理在多阶段基因组分析中的表现，与大基因组模型和医疗AI主题相关
tldr: "GeneBench-Pro是一个评估AI在多阶段科学推理中能力的基准，包含129个跨10个主要领域的问题，问题需要处理多个依赖的决策点。模型如GPT-5.6 Sol Pro最高达31.5%通过率，但常出现局部正确而全局失败的情况。该基准揭示了长时生物学推理能力仍不可靠，为未来研究提供了重要参考。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准未能捕捉真实科学分析的多阶段决策复杂性，需设计更难的问题以评估AI的长时推理能力。
method: 扩展GeneBench至129个问题，涵盖基因组学等10个领域，每个问题需导航多个依赖决策点并执行正确分析流程。
result: "GPT-5.6 Sol Pro达31.5%通过率，Claude Opus 4.8为16.0%，模型经常局部诊断正确但无法传播到全局决策。"
conclusion: GeneBench-Pro衡量了AI在生物推理中的新兴能力，但当前模型表现不可靠，需改进全局推理。
---

## 摘要
我们介绍了GeneBench-Pro，它是GeneBench的扩展和改进版本，包含更广泛领域中更困难的问题。GeneBench-Pro是一个基准测试，用于评估AI智能体在基因组学、定量生物学和转化生物医学中执行现实多阶段科学分析的能力，旨在捕捉计算生命科学家在需要产生依赖于下游科学或转化决策的结论时所面临的实际问题的复杂性。该基准包含129个评估，针对10个主要领域和21个终端子领域中具有直接实际意义的数量，以基因组学为核心。与GeneBench类似，每个问题为智能体提供简要背景、目标估计量以及最少的其他指导；智能体必须导航多个依赖决策点，即实质性推理分叉，其中看似合理的错误选择会改变下游分析，以识别并执行正确的分析工作流，并得出正确答案。相对于GeneBench，GeneBench-Pro增加了29个新问题，删除了3个问题，并对剩余100个重叠问题中的54个进行了显著重新设计。129个问题中的82个由外部领域专家审查，他们的发现导致了对那些目标不够明确的问题的提示/数据修改和重新设计。十个经过外部审查的问题公开发布，50个保留问题提供给Artificial Analysis进行独立的第三方模型基准测试，其余作为内部保留。在对全部129个问题套件的评估中，GPT-5.6 Sol在最大推理级别达到了28.7%的评估级通过率，GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到了31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常完成了工作流的很大一部分，但在注意和行动之间表现出持续的差距，即识别局部诊断信号但未能将影响传播到相应的分析决策。因此，模型经常选择错误的估计量，或者坚持最初看似合理但错误的分析路径。因此，GeneBench-Pro衡量了一种新兴的长期生物学推理能力，这种能力仍然不可靠。



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v1_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@110e72corg.highwire.dtl.DTLVardef@b91b13org.highwire.dtl.DTLVardef@a09b8aorg.highwire.dtl.DTLVardef@438fb4_HPS_FORMAT_FIGEXP  M_FIG C_FIG

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v1_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@110e72corg.highwire.dtl.DTLVardef@b91b13org.highwire.dtl.DTLVardef@a09b8aorg.highwire.dtl.DTLVardef@438fb4_HPS_FORMAT_FIGEXP  M_FIG C_FIG