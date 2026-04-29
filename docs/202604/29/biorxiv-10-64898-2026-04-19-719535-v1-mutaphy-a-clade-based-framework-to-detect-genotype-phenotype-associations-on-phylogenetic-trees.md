---
title: "MutaPhy: A clade-based framework to detect genotype-phenotype associations on phylogenetic trees"
title_zh: MutaPhy：一种在系统发育树上检测基因型-表型关联的基于演化支的框架
authors: "Ngo, A., Guindon, S., Pedergnana, V."
date: 2026-04-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.19.719535v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 基于系统发育的病原体基因型-表型关联检测方法
tldr: MutaPhy是一个基于系统发育树的分析框架，旨在识别病原体基因型与宿主临床表型间的关联。它通过子树、全树和位点三个尺度分析进化信号，解决了传统关联分析在处理非独立样本时的高假阳性问题。经模拟及病毒数据验证，该方法能有效定位关键突变并提高结果的可解释性。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统关联分析在处理具有系统发育结构的病原体数据时，常因违反样本独立性假设而导致高假阳性率。
method: 提出MutaPhy框架，结合子树置换检验、全树全局统计和位点级祖先序列重建来多尺度检测关联信号。
result: 模拟实验和登革热、丙肝病毒数据应用证明，该方法能准确识别与特定表型相关的病毒谱系并降低误报。
conclusion: MutaPhy通过利用系统发育结构引导关联分析，为病原体进化决定因素的研究提供了一个稳健且可解释的工具。
---

## 摘要
理解病原体遗传变异如何影响在感染宿主中观察到的临床表型，是进化基因组学和公共卫生领域的一项基本挑战。诸如感染严重程度等表型特征在病原体系统发育中通常呈非随机分布，这表明存在进化决定因素，但也违反了经典全基因组关联研究（GWAS）的独立性假设，并可能导致假阳性率升高。我们提出了 MutaPhy，这是一种基于系统发育的方法，旨在通过直接利用系统发育树的分层结构，检测二元宿主表型与相应病原体基因组之间的相关性。MutaPhy 包含三个不同的尺度：(i) 子树尺度，利用基于置换的检验来检测过度呈现目标表型的相关演化支；(ii) 全树尺度，将局部信号聚合成全局关联统计量；(iii) 位点尺度，通过祖先序列重建来检查通往显著演化支的分支上的候选突变事件。我们通过在多种进化场景下的模拟，评估了 MutaPhy 的统计行为和检测性能。我们还将该工具与几种现有的系统发育关联方法进行了比较。作为示例应用，我们将 MutaPhy 应用于与人类宿主临床表型相关的登革病毒和丙型肝炎病毒数据集。我们的结果强调了该方法检测与过度呈现表型相关的病毒谱系的能力，同时也揭示了在这些特定数据集中，稳健的突变水平关联证据有限。总之，MutaPhy 提供了一个利用系统发育结构指导基因型-表型关联分析的框架，从而减少了假阳性发现并提高了关联信号的可解释性。

## Abstract
Understanding how genetic variation in pathogens influences clinical phenotypes observed in infected hosts is a fundamental challenge in evolutionary genomics and public health. Phenotypic traits such as infection severity are often non-randomly distributed within the pathogens phylogeny, suggesting the existence of evolutionary determinants but also violating the independence assumption underlying classical genome-wide association studies and potentially leading to inflated false positive rates. We present MutaPhy, a phylogeny-based method aimed at detecting correlations between a binary host phenotype and the corresponding pathogen genome by directly utilizing the hierarchical structure of phylogenetic trees. MutaPhy encompasses three different scales: (i) a subtree scale, on which relevant clades over-representing the phenotype of interest are detected using permutation-based tests; (ii) a tree scale, which agglomerates local signals into a global association statistics; and (iii) a site scale, whereby candidate mutational events on branches leading to significant clades are examined using ancestral sequence reconstruction. We evaluate the statistical behavior and detection performance of MutaPhy using simulations under diverse evolutionary scenarios. We also compare this tool to several existing phylogenetic association methods. As illustrative applications, we apply MutaPhy to dengue virus and hepatitis C virus datasets associated to clinical phenotypes in human hosts. Our results highlight the ability of the proposed approach to detect viral lineages associated to over-represented phenotypes while revealing limited evidence for robust mutation-level associations in these particular datasets. Altogether, MutaPhy provides a framework for guiding genotype-phenotype association analyses by leveraging phylogenetic structure, thereby reducing false positive findings and improving the interpretability of association signals.