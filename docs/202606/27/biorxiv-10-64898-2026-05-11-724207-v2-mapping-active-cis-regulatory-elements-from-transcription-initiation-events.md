---
title: Mapping active cis-regulatory elements from transcription initiation events
title_zh: 从转录起始事件绘制活性顺式调控元件
authors: "Einarsson, H., Navamajiti, N., Skov Vaagenso, C., Pellegrini, S., Jirstrom, L., Alcaraz, N., Thodberg, M., Solvie, D. A., Qiu, W.-L., Sheth, M. U., Greedy Escudero, M., Gorissen, B. L., Salvatore, M., Kasukawa, T., Takahashi, H., Carninci, P., Bernstein, B. E., Sandelin, A., Engreitz, J. M., Krautz, R., Andersson, R."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724207v2.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 通过转录起始事件绘制活性调控元件，有助于GWAS变异的功能解读
tldr: 确定顺式调控元件（CRE）活性对基因调控和遗传变异解读至关重要，但现有方法在特异性、灵敏度或可扩展性上存在局限。本文提出nucCAGE（核加帽RNA转录起始位点检测）和PRIME（从TSS数据鉴定活跃CRE的计算框架），通过富集低丰度RNA显著提升检测灵敏度。在eQTL精细定位、ClinVar变异、GWAS位点及CRISPRi验证等多项基准测试中，nucCAGE-PRIME的召回率优于现有方法，同时保持强表型关联富集。应用于FANTOM5数据后，构建了涵盖多种细胞类型的活跃CRE图谱，成功将免疫细胞增强子调控与SMAD3（哮喘）和NCOR2（胎盘早剥）等非编码致病变异关联。该研究为高灵敏度全基因组活跃CRE发现及变异功能研究提供了系统框架和资源。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有CRE鉴定方法难以区分活跃调控与允许性染色质，且对不稳定增强子RNA灵敏度低，缺乏可扩展性。
method: 开发nucCAGE检测核加帽RNA的TSS，结合PRIME计算框架，从TSS数据中高灵敏度识别活跃CRE。
result: nucCAGE-PRIME在多项基准测试中召回率领先，生成细胞类型特异性活跃CRE图谱，并成功注释SMAD3和NCOR2的致病非编码变异。
conclusion: nucCAGE和PRIME为高灵敏度全基因组活跃CRE发现及变异-功能研究提供了高效框架和重要资源。
---

## 摘要
确定顺式调控元件（CREs）的活性对于建模基因调控和解读遗传变异至关重要。然而，当前的方法通常缺乏区分活性调控与许可性染色质的特异性、检测不稳定增强子RNA的灵敏度，或分析有限输入材料和原代细胞所需的可扩展性。在此，我们介绍nucCAGE——一种用于分析核内加帽RNA的转录起始位点（TSS）检测方法，以及PRIME——一个从TSS数据中识别活性CREs的计算框架。这些方法共同提高了对低丰度RNA的灵敏度，并能够在多种背景下稳健地检测活性调控元件。通过多个正交的功能和遗传基准测试，包括精细定位的eQTL、ClinVar变异、GWAS位点和CRISPRi验证的元件，nucCAGE衍生的PRIME预测在召回率上优于当前最先进的方法，同时保持对表型相关变异的强富集性。将PRIME应用于FANTOM5数据集，生成了一个全面的、细胞类型分辨的活性CREs图谱，该图谱重现了已知的组织-性状关系。我们展示了如何利用该图谱来提名因果性非编码变异，将SMAD3的免疫细胞增强子调控与哮喘联系起来，以及将NCOR2与胎盘早剥联系起来。总之，nucCAGE和PRIME提供了一个用于高灵敏度全基因组活性CREs发现的框架，以及一个用于变异-功能研究的资源。

## Abstract
Determining the activity of cis-regulatory elements (CREs) is essential for modeling gene regulation and interpreting genetic variation. Yet, current methods often lack the specificity to distinguish active regulation from permissive chromatin, the sensitivity to detect unstable enhancer RNAs, or the scalability required to profile limited input material and primary cells. Here, we introduce nucCAGE, a transcription start site (TSS) assay for profiling nuclear, capped RNAs, and PRIME, a computational framework for identifying active CREs from TSS data. Together, these methods increase sensitivity to low-abundance RNAs and enable robust detection of active regulatory elements across diverse contexts. Across multiple orthogonal functional and genetic benchmarks, including fine-mapped eQTLs, ClinVar variants, GWAS loci, and CRISPRi-tested elements, nucCAGE-derived PRIME predictions achieve superior recall compared to state-of-the-art methods while maintaining strong enrichment for phenotype-associated variation. Applying PRIME to the FANTOM5 dataset yields a comprehensive, cell-type-resolved atlas of active CREs that recapitulates known tissue-trait relationships. We demonstrate how this atlas can be used to nominate causal noncoding variants, linking immune-cell enhancer regulation of SMAD3 to asthma and NCOR2 to premature separation of placenta. Together, nucCAGE and PRIME provide a framework for high-sensitivity genome-wide discovery of active CREs and a resource for variant-to-function studies.