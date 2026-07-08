---
title: "ORBIT: Annotation-Aware Empirical Enrichment and Semantic Reranking for Interpretable Functional-Class Recovery"
title_zh: ORBIT：面向可解释功能类恢复的注释感知经验富集与语义重排序
authors: "Kidder, B. L."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.01.735870v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 将经验富集与语义重排序相结合的功能类恢复工具，可整合到GWAS下游分析
tldr: 基因集解释工具常返回冗长冗余的结果表，ORBIT提出注释感知的经验富集与语义重排序方法。在45个人工基准测试中，ORBIT语义重排序达到0.916的平均倒数排名和0.889的top-1恢复率，优于Enrichr和PANTHER等基线。通过GPCR、免疫细胞等案例，ORBIT将冗余富集术语压缩为可审查的生物学摘要，显著提升可解释功能类的恢复。
source: biorxiv
selection_source: fresh_fetch
motivation: 标准富集工具输出冗长冗余，需大量人工整合，缺乏可解释性。
method: 结合经验富集、语义重排序和冗余感知代表性术语选择，优先排序可解释功能摘要。
result: 在45套核心基准中，ORBIT语义重排序平均倒数排名0.916，top-1恢复0.889，优于Enrichr和PANTHER。
conclusion: ORBIT有效压缩冗余富集结果，生成可审查的生物学摘要，提升功能类恢复的可解释性。
---

## 摘要
基因集解释工作流被广泛用于总结转录组和蛋白质组实验，然而标准的富集工具常常返回冗长且冗余的结果表格，需要大量手动整合。我们开发了ORBIT（本体排名生物学解释工具），这是一种注释感知的解释工作流，结合了经验富集、语义重排序和冗余感知的代表性术语选择，以从基因集中优先选择可解释的功能摘要。我们在一套精心策划的分层基准上评估了ORBIT，该基准涵盖人类功能类基因集，包括清晰的参考集、大小梯级变体和混合难度案例。在45个基因集的核心基准测试中，ORBIT语义实现了比Enrichr和PANTHER基因本体分子功能基线更高的预期类别恢复率，平均倒数排名为0.916，top-1恢复率为0.889。Bootstrap置信区间和配对置换检验支持了这一优势的稳健性，补充分析将比较扩展到g:Profiler。在一个GPCR混合功能案例研究中，ORBIT将冗余的富集术语压缩为语义代表邻域，说明了如何将冗长的富集输出转化为可审查的生物学摘要。然后我们使用ORBIT解释免疫细胞身份、干扰素反应生物学和乳腺癌亚型程序。ORBIT将PBMC3K标记与细胞毒性、抗原呈递和先天免疫细胞状态关联起来；在IFNB刺激后优先考虑抗病毒、细胞因子反应、RNA结合和分泌因子生物学；并将TCGA-BRCA基底样增殖性染色体/细胞周期程序与腔道转运蛋白和受体相关生物学区分开来，同时保留基因水平的支持。

## Abstract
Gene-set interpretation workflows are widely used to summarize transcriptomic and proteomic experiments, yet standard enrichment tools often return long, redundant result tables that require substantial manual consolidation. We developed ORBIT (Ontology-Ranked Biological Interpretation Tool), an annotation-aware interpretation workflow that combines empirical enrichment, semantic reranking, and redundancy-aware representative-term selection to prioritize interpretable functional summaries from gene sets. We evaluated ORBIT on a curated tiered benchmark of human functional-class gene sets spanning clean reference sets, size-ladder variants, and mixed-difficulty cases. On the 45-set core benchmark, ORBIT semantic achieved higher expected-class recovery than Enrichr and PANTHER Gene Ontology molecular-function baselines, with a mean reciprocal rank of 0.916 and top-1 recovery of 0.889. Bootstrap confidence intervals and paired permutation testing supported the robustness of this advantage, and supplemental analyses extended the comparison to g:Profiler. In a GPCR mixed-function case study, ORBIT compressed redundant enriched terms into semantic representative neighborhoods, illustrating how long enrichment outputs can be converted into reviewable biological summaries. We then used ORBIT to interpret immune-cell identity, interferon-response biology, and breast-cancer subtype programs. ORBIT linked PBMC3K markers to cytotoxic, antigen-presentation, and innate-immune cell states; prioritized antiviral, cytokine-response, RNA-binding, and secreted-factor biology after IFNB stimulation; and separated TCGA-BRCA basal-like proliferative chromosome/cell-cycle programs from luminal transporter and receptor-associated biology while retaining gene-level support.