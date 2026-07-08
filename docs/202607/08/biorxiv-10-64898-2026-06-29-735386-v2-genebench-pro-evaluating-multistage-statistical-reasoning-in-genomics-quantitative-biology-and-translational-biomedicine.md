---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化生物医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v2.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: GeneBench-Pro是评估AI代理在基因组学等多领域执行多阶段统计推理的基准，与大规模基因组模型和智能体需求相关
tldr: "现有基准难以评估AI在基因组学等领域的多阶段统计推理能力。GeneBench-Pro扩展了GeneBench，包含129个跨10个主领域的复杂问题，要求AI代理自主导航多个依赖决策点。评估显示最强模型GPT-5.6 Sol Pro仅达31.5%通过率，模型常能识别局部信号但无法全局传播。该基准揭示了AI在长程生物推理中的关键短板，为未来模型改进提供方向。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准缺乏对多阶段科学分析中统计推理能力的评估，需构建更贴近真实科研流程的测试。
method: 构建129个跨基因组学等10个领域的问题，每个问题要求AI代理自主完成从上下文到正确分析工作流的完整推理。
result: "GPT-5.6 Sol Pro达31.5%通过率，GPT-5.5为12%，Claude Opus 4.8为16%，模型常错误选择估计器或持续错误路径。"
conclusion: GeneBench-Pro揭示了AI在多阶段生物推理中从注意到行动的关键差距，是衡量长程推理能力的重要基准。
---

## 摘要
我们推出了GeneBench-Pro，这是GeneBench的扩展和改进版本，包含跨更广泛领域的更难问题。GeneBench-Pro是一个面向AI代理的基准测试，旨在模拟计算生命科学家在完成下游科学或转化决策所依赖的结论时，在基因组学、定量生物学和转化生物医学中面临的真实多阶段科学分析的复杂性。该基准包含129个评估问题，针对10个主要领域和21个终端子领域中具有直接实际意义的量，核心围绕基因组学。与GeneBench类似，每个问题为代理提供简要背景、目标估计量以及极少的指导；代理必须导航多个依赖决策点，即实质性推断分支，其中看似合理的错误选择会改变下游分析，从而识别并执行正确的分析工作流并得出正确答案。相对于GeneBench，GeneBench-Pro新增了29个问题，删除了3个，并对剩余100个重叠问题中的54个进行了大幅重新设计。129个问题中有82个由外部领域专家评审，其发现导致对目标不够明确的问题进行了提示/数据修改和重新设计。十个外部评审问题公开发布，50个保留问题提供给Artificial Analysis进行独立第三方模型基准测试，其余作为内部保留。在完整129个问题套件的评估中，GPT-5.6 Sol在最大推理级别达到28.7%的评估级通过率，GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常能完成工作流的很大部分，但在注意到问题并采取行动之间存在一致差距：模型能识别局部诊断信号，但未能将影响传播到相应的分析决策。因此，模型经常选择错误的估计量，或坚持最初看似合理但错误的分析路径。因此，GeneBench-Pro衡量了一种新兴的长周期生物学推理能力，该能力目前仍不可靠。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/735386v2_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@1abbf01org.highwire.dtl.DTLVardef@88edf9org.highwire.dtl.DTLVardef@1bf8e4dorg.highwire.dtl.DTLVardef@1177183_HPS_FORMAT_FIGEXP  M_FIG C_FIG