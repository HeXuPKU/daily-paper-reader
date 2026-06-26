---
title: "From Nuisance to Signal: Leveraging Close Relatives in Biobank-Scale Demographic Inference"
title_zh: 从干扰到信号：利用生物库规模人口统计推断中的近亲
authors: "Williams, C. M., Ramachandran, S."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.729614v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 利用亲属进行群体历史推断的方法，与GWAS群体结构相关
tldr: 生物库数据中近亲属普遍存在，传统做法将其剔除视为干扰。本研究评估了IBDNe和HapNe-IBD两种近期有效群体大小（Ne）推断方法，发现随机抽样下保留所有亲属能得到最无偏的Ne估计，而去除亲属会引发近期Ne膨胀和振荡伪影（波纹效应），影响至十代前。过度采样亲属则导致严重向下偏差。作者开发了基于msprime的IBD模拟流程，建议在生物库时代保留近亲以提升推断准确性。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估去除近亲属对基于IBD的近期有效群体大小推断的影响，并探索最佳采样策略。
method: 使用IBDNe和HapNe-IBD，在多种人口历史和亲属取样方案下进行基准测试，并开发msprime模拟流程。
result: 随机抽样下保留所有亲属产生最无偏估计；去除亲属导致近期Ne膨胀和波纹伪影；过度采样近亲导致向下偏差。
conclusion: 生物库数据中应保留近亲用于IBD-based Ne推断，而非传统剔除做法。
---

## 摘要
生物库规模的数据集现在通常包含数十万到数百万个体，并且随着样本量的增长，近亲变得越来越普遍。人口遗传学中的惯例是在推断之前去除近亲，有效地将其视为干扰参数。然而，这种做法对人口统计推断的影响，特别是对近期有效种群大小（Ne）估计的影响，尚未得到严格评估。在这里，我们对IBDNe和HapNe-IBD这两种广泛使用的从血统同源（IBD）片段推断近期Ne的方法进行基准测试，考虑一系列人口统计历史和亲属抽样方案。我们表明，当个体随机确定时，保留所有亲属产生的Ne估计偏差最小；相比之下，即使去除二级亲属也会夸大近期Ne并产生“波纹”振荡伪影，导致对过去十代的估计出现偏差。我们证明这种波纹效应的产生是因为近亲贡献的IBD片段被模型分配到超出其真实TMRCA的一系列祖先年龄，意味着它们的去除同时造成多代的信号缺失。我们进一步表明，有意过度抽样近亲会导致近期Ne的严重向下偏差。为支持这些分析，我们使用msprime开发了一个开源的IBD模拟管道，可在任意人口统计历史和Wright-Fisher家系下生成真实的IBD片段。我们为包含家系的IBD模拟方案提供了实用指南，并认为在生物库时代，保留近亲通常是基于IBD的Ne推断的最佳实践。

## Abstract
Biobank-scale datasets now routinely include hundreds of thousands to millions of individuals, and as sample sizes grow, close relatives become increasingly prevalent. The convention in population genetics has been to remove close relatives prior to inference, effectively treating them as a nuisance parameter. However, the consequences of this practice for demographic inference, and specifically for estimates of recent effective population size (Ne), have not been rigorously evaluated. Here, we benchmark IBDNe and HapNe-IBD, two widely-used methods for inferring recent Ne from identity-by-descent (IBD) segments, under a range of demographic histories and relative sampling schemes. We show that when individuals are randomly ascertained, retaining all relatives produces the least biased Ne estimates; in contrast, removing even second-degree relatives inflates recent Ne and induces oscillatory artifacts that "ripple", leading to biased estimates up to ten generations into the past. We demonstrate that this ripple effect arises because close relatives contribute IBD segments that are assigned by the model to a range of ancestral ages beyond their true TMRCA, meaning their removal creates signal deficits across multiple generations simultaneously. We further show that deliberately oversampling close relatives produces severe downward bias in recent Ne. To support these analyses, we develop an open-source IBD simulation pipeline using msprime that generates realistic IBD segments under arbitrary demographic histories and Wright-Fisher pedigrees. We provide practical guidelines for IBD simulation schemes incorporating pedigrees and argue that, in the biobank era, retaining close relatives is generally the best practice for IBD-based Ne inference.