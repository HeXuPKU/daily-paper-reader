---
title: "PanVariants: Best Practice for Pangenome-based Variant Calling Pipeline and Framework"
title_zh: PanVariants：基于泛基因组的变异检测流程与框架的最佳实践
authors: "Yi, H., Wang, L., Chen, X., Ding, Y., Carroll, A., Chang, P.-C., Shafin, K., Xu, L., Zeng, X., Zhao, X., Gong, M., Wei, X., Hou, Y., Ni, M."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.22.720142v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 用于队列联合调用的泛基因组变异检测流程
tldr: PanVariants是一个针对泛基因组参考基因组开发的变异检测流程，旨在解决现有工具仅能检测已知变异的局限。通过整合k-mer和比对方法，该流程能同时准确检测已知和新变异。在SNV和SV检测中，其表现显著优于传统的线性参考基因组方案（如BWA+GATK）和现有泛基因组方案（如DRAGEN），为从线性参考基因组向泛基因组转型提供了高效、可靠的最佳实践框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的泛基因组变异检测工具大多局限于检测图谱中已有的已知变异，无法有效发现新变异。
method: 开发了整合k-mer和比对方法的PanVariants流程，并针对DNBSEQ高通量测序数据重新训练了DeepVariant模型以提升精度。
result: "PanVariants在SNV检测中比BWA+GATK减少了73%的错误，在SV检测中F1分数达到89.39%，显著优于DRAGEN和Manta。"
conclusion: PanVariants为泛基因组变异检测建立了稳健的框架和最佳实践，证明了泛基因组参考基因组在临床诊断和群体基因组学中的应用潜力。
---

## 摘要
背景：尽管泛基因组参考序列相比线性参考序列提供了更丰富的群体多样性，但目前主流的基于泛基因组的变异检测工具仅限于检测存储在图中的已知变异。为了解决这一局限性，我们开发了 PanVariants，这是一种旨在准确提高已知和新发变异检测能力的新型流程。我们在三种场景下系统评估了其性能，并与传统的线性比对方案（BWA+GATK/Manta）以及现有的泛基因组感知方案（DRAGEN/PanGenie）进行了对比：包括 Genome in a Bottle 样本中小变异（SNVs/indels）和结构变异（SVs）的准确性、临床阳性样本的检测，以及在基于队列的联合检测中的应用。结果：通过整合基于 k-mer 和基于比对的方法，PanVariants 显著减少了变异误差（假阳性 + 假阴性），在 SNV 检测方面，相比 BWA+GATK 减少了 73%，相比 DRAGEN 减少了 45%。使用高质量的 DNBSEQ 数据重新训练 DeepVariant 模型使误差进一步降低了 15%。在 SV 检测方面，PanVariants 的 F1 分数达到 89.39%，显著优于 DRAGEN (68.18%) 和 BWA+Manta (58.33%)，接近长读长测序的性能 (95.22%)。在临床阳性样本的验证中，PanVariants 成功检测到了所有预期的致病变异，而 PanGenie 则未能检测到。在队列联合检测分析中，PanVariants 比 GATK 检测到了更多变异，孟德尔遗传错误更少，且单样本准确性更高。结论：PanVariants 为基于泛基因组的变异检测建立了一个稳健的框架和最佳实践流程，实现了对新发变异的敏感发现以及对 SNV、indel 和 SV 的高准确性检测。我们对可选处理步骤和输入变量的系统评估为用户提供了实用指导。通过在诊断和基于群体的应用中进行的验证，我们的研究结果有力地支持了未来基因组学从线性参考序列向泛基因组参考序列的转变。

## Abstract
BackgroundAlthough pangenome references offer richer population diversity compared to linear references, current mainstream pangenome-based variant callers are limited to detecting only known variants stored in the graph. To address this limitation, we developed PanVariants, a novel pipeline designed to improve the detection of both known and novel variants accurately. We systematically evaluated its performance against the traditional linear alignment solution (BWA+GATK/Manta) and the existing pangenome-aware solution (DRAGEN/PanGenie) in three contexts: small variants (SNVs/indels) and structural variants (SVs) accuracy in Genome in a Bottle samples, clinical detection on positive samples, and application in cohort-based joint calling.

ResultsBy integrating k-mer-based and mappinglZlbased methods, PanVariants significantly reduced variant errors (FPs + FNs), achieving a 73% reduction compared to BWA+GATK and a 45% reduction compared to DRAGEN for SNVs. Retraining the DeepVariant model with high-quality DNBSEQ data further decreased errors by 15%. For SVs detection, PanVariants attained an F1-score of 89.39%, markedly outperforming DRAGEN (68.18%) and BWA+Manta (58.33%), approaching long-read sequencing performance (95.22%). In validation using clinical positive samples, PanVariants successfully detected all expected pathogenic variants while PanGenie failed. In the cohort joint-calling analysis, PanVariants detected more variants, made fewer Mendelian inheritance errors, and gave better per-sample accuracy than GATK.

ConclusionsPanVariants establishes a robust framework and best-practice pipeline for pangenome-based variant detection, achieving both sensitive novel variant discovery and high accuracy for SNVs, indels and SVs. Our systematic evaluation of optional processing steps and input variables offers practical guidance for users. Validated across diagnostic and population-based applications, our findings strongly support the transition from linear to pangenome references in future genomics.