---
title: Refining bias correction in genome-wide association analyses of case-control studies
title_zh: 改进病例-对照研究全基因组关联分析中的偏差校正
authors: "Darbani, B., Pedersen, O. B. V., Ostrowski, S. R., Tan, Q., Andersen, V."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.01.673522v3.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: GWAS病例对照研究偏差校正框架
tldr: 病例对照GWAS易受遗传相关、非加性等位基因互作、对照群体易感基因型及多等位基因位点等混杂因素影响。本研究提出通用框架，通过过滤遗传相关子群体或配对样本减少偏差，同时保留统计效力。引入AlleliC-GWAS工具识别二值性状中SNP特异的等位基因效应。最后推荐准确捕获多等位基因位点遗传效应的策略。
source: biorxiv
selection_source: fresh_fetch
motivation: GWAS病例对照研究中存在多种偏差来源，需提供基于证据的指导以最小化偏差。
method: 通过分析遗传相似性、非加性互作、年龄相关过滤等，提出AlleliC-GWAS工具对SNP特定等位基因效应建模。
result: 遗传相似性在病例或对照组内引入偏差，跨病例-对照的遗传相关性降低偏差；年龄过滤可减少易感基因型引起的偏差；AlleliC-GWAS工具可准确识别等位基因效应。
conclusion: 建立偏差校正通用框架，确保多等位基因位点遗传效应准确估计，提升多基因风险评分等准确性。
---

## 摘要
全基因组关联研究容易受到混杂因素的影响。本研究为在病例-对照研究中最小化与遗传相关性、SNP特异性非加性等位基因相互作用、对照组中易感基因型以及多等位基因多态性相关的偏差提供了基于证据的指导。分析表明，病例组或对照组内部的遗传相似性引入了实验偏差，而病例-对照样本之间的遗传相关性减少了这种偏差。这些发现建立了一个通用框架，可以过滤遗传相关的子群体或配对样本，同时以最小的假阳性率保留最大的统计功效。此外，对照组中易感基因型导致的偏斜比值比强调了年龄相关过滤的重要性，以最小化这种混杂效应。为了确保准确的遗传估计，如多基因风险评分，在病例-对照研究中也强调了SNP特异性等位基因相互作用模型的识别，这取决于对群体内基因型频率差异的标准化。在此，我们引入等位基因效应感知的病例-对照GWAS（AlleliC-GWAS）工具，用于识别SNP特异性等位基因对二元性状的影响。最后，我们推荐一种策略，以准确捕捉多等位基因基因组位置的遗传效应。

## Abstract
Genome-wide association studies are vulnerable to confounding factors. This study provides evidence-based guidance for minimizing bias associated with genetic relatedness, SNP-specific non-additive allelic interactions, predisposed genotypes among controls, and multi-allelic polymorphism in case-control studies. The analyses demonstrated that genetic similarity within case or control groups introduces experimental bias, whereas genetic relatedness across case-control samples reduces this bias. These findings establish a general framework that can filter genetically related sub-communities or paired samples, whilst preserving maximal statistical power with minimal false-positive rates. Moreover, the skewed odds ratios resulting from predisposed genotypes among controls underscored the importance of age-related filtering to minimize this confounding effect. To ensure accurate genetic estimates, such as polygenic risk scores, the identification of SNP-specific allelic interaction models was also emphasized in case-control studies, contingent on normalization for within-population differences in genotype frequencies. Here, we introduce the Allelic-effect aware Case-Control GWAS (AlleliC-GWAS) tool for identifying SNP-specific allelic effects on binary traits. Finally, we recommend a strategy to accurately capture genetic effects at multi-allelic genomic positions.