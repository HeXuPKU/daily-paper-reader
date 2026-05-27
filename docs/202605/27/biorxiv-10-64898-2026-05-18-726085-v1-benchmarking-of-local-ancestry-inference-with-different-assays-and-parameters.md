---
title: Benchmarking of local ancestry inference with different assays and parameters
title_zh: 不同检测方法和参数下局部祖先推断的基准评估
authors: "Motegi, T., Huang, F., Campbell, J. D."
date: 2026-05-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.18.726085v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 局部祖先推断方法基准测试，对GWAS群体分层控制至关重要
tldr: "传统局部祖先推断（LAI）依赖高覆盖度全基因组测序，但其他检测方法的效果缺乏系统评估。本文系统比较了SNP微阵列、全外显子测序（WES）和超低深度全基因组测序（ULP-WGS）的LAI准确性。结果表明，ULP-WGS在0.25x覆盖度下结合GLIMPSE2可达到大于95%的准确度；WES通过纳入旁系读取也能实现类似精度；而SNP微阵列在所有窗口大小下均低于95%。研究证实无需高覆盖度测序即可进行准确LAI，并为不同平台提供了最优参数。"
source: biorxiv
selection_source: fresh_fetch
motivation: 评估不同基因分型检测和测序深度下局部祖先推断的准确性，以拓展其在混合人群中的应用。
method: 系统比较SNP微阵列、全外显子测序和超低深度全基因组测序的LAI性能，结合多种插补流程与验证样本。
result: "ULP-WGS（0.25x覆盖度）与WES（利用旁系读取）在优化窗口大小下均达到≥95%准确度；SNP微阵列低于95%。"
conclusion: 局部祖先推断无需高覆盖度全基因组测序，并明确了不同平台的最优参数设置。
---

## 摘要
局部祖先推断（LAI）能够高分辨率地描述源自不同祖先群体的染色体片段特征，为混合人群的遗传结构提供独特见解。虽然LAI通常通过高覆盖度全基因组测序（WGS）进行，但其他基因分型检测方法或不同测序深度的能力尚未得到全面评估。在本研究中，我们使用多种验证样本和最先进的基因型填充流程，系统地评估了LAI在SNP芯片、全外显子组测序（WES）和超低深度全基因组测序（ULP-WGS）上的准确性。我们发现，ULP-WGS与GLIMPSE2结合使用时，在0.25倍覆盖度、最小基因组窗口大小为0.5厘摩的条件下，平均准确率减去一个标准差超过95%，实现了稳健的准确性。对于WES，仅使用“目标区域”测序读段的效果欠佳，特别是对于欧洲和南亚祖先人群，准确率分别低于79.1%和70.6%。然而，在WES中纳入“非目标区域”测序读段并结合GLIMPSE2，在最小窗口大小为0.2厘摩时，准确率显著提高至≥95%。我们还进一步评估了福尔马林固定石蜡包埋（FFPE）样本，发现使用WES数据在最小窗口大小为0.5厘摩时，LAI可成功进行，准确率≥95%。相比之下，SNP芯片在任何窗口大小下均未达到较高准确率（≤95%）。综上，这些结果表明，无需传统的高覆盖度WGS即可实现LAI，并为不同平台上的LAI确立了最优参数。

## Abstract
Local ancestry inference (LAI) enables high-resolution characterization of chromosomal segments inherited from distinct ancestral populations, offering unique insights into genetic architecture in admixed cohorts. While LAI is commonly performed with high-coverage whole-genome sequencing (WGS), the ability of other genotyping assays or varying sequencing depths has not been thoroughly benchmarked. In this study, we systematically evaluated the accuracy of LAI across SNP microarrays, whole-exome sequencing (WES), and ultra low-pass WGS (ULP-WGS) using diverse validation samples and state-of-the-art imputation pipelines. We show that ULP-WGS, when paired with GLIMPSE2, achieves robust accuracy at 0.25x coverage with a minimum genome window size of 0.5 centimorgans, with mean accuracy minus one standard deviation exceeding 95%. For WES, using "on-target" reads alone yields suboptimal performance, particularly for European and South Asian ancestries with accuracy less than 79.1% and 70.6%, respectively. However, incorporating "off-target" reads in WES and utilizing GLIMPSE2 substantially improved accuracy [&ge;]95% with a minimum window size of 0.2 centimorgans. We further evaluated formalin-fixed, paraffin-embedded (FFPE) samples and found that LAI could be performed successfully using WES data with accuracies of [&ge;]95% at a minimum window size of 0.5 centimorgans. In contrast, SNP microarrays did not achieve substantial accuracies at any window size ([&le;]95%). Together, these results demonstrate that LAI is achievable without conventional high-coverage WGS and establish optimal parameters for LAI across platforms.