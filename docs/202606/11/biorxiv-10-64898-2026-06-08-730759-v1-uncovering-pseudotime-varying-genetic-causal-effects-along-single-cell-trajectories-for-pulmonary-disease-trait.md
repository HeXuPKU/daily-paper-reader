---
title: Uncovering Pseudotime-Varying Genetic Causal Effects Along Single-Cell Trajectories for Pulmonary Disease Trait
title_zh: 揭示肺部疾病性状沿单细胞轨迹的伪时间变化遗传因果效应
authors: "Chen, S., Moorthy, A., Yu, P. K., Wang, J., Liu, D."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.730759v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 将遗传因果效应与单细胞轨迹整合
tldr: 传统伪批量方法分析单细胞数据时忽略细胞间异质性，而遗传效应可能沿细胞分化轨迹动态变化。本研究提出动态eQTL框架，将基因表达建模为拟时间函数，并引入经验似然推断处理数据稀疏性；结合中介分析区分直接与间接因果效应。应用于IPF肺组织数据，发现AT2-AT1轨迹中多个基因的拟时间依赖因果效应，其中30个基因通过细胞命运介导。该工作首次系统揭示遗传效应沿细胞轨迹的动态变化，为理解复杂疾病机制提供新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞eQTL分析忽略细胞间异质性，且遗传效应可能沿分化轨迹动态变化，需要新方法捕捉这种动态因果效应。
method: 提出动态eQTL模型，将基因表达作为拟时间函数，用经验似然推断解决稀疏性，并整合中介分析区分直接与间接因果效应。
result: 在IPF肺组织数据中识别出AT2-AT1轨迹上30个基因通过细胞命运介导的动态因果效应。
conclusion: 本研究首次揭示遗传效应沿细胞轨迹的动态模式及中介机制，为疾病因果推断提供新框架。
---

## 摘要
随着单细胞RNA测序（scRNA-seq）数据的日益可及，通过伪批量方法可以将细胞类型特异性基因表达与复杂性状关联起来，该方法考虑了每个个体相同注释细胞类型中多个细胞的聚合基因表达，但明确忽略了细胞内细胞间变异性的局限性。与此同时，伪时间轨迹推断因其能够捕获连续的生物过程（如细胞分化和谱系发育）而非离散阶段而受到欢迎。自然要考虑的是，复杂性状（如个体水平的疾病状态）的遗传效应是否沿推断轨迹呈现动态模式。在本研究中，我们引入了一个新框架，将基因表达建模为沿推断轨迹的伪时间函数。我们将顺式调控区的表达数量性状位点（eQTL）效应映射为功能参数，称为“动态eQTL”，表明遗传变异施加的调控效应沿细胞轨迹连续变化。对于跨伪时间效应恒定的eQTL，我们利用外部批量eQTL信息来增强统计功效。此外，我们使用显著且可变的动态eQTL作为工具变量，推断基因表达与复杂性状之间的因果关系。为解决scRNA-seq数据固有的挑战（如稀疏性和高变异性），我们采用了基于经验似然的推断方法，该方法是非参数且自标准化的。另外，与轨迹分支点相关的基因可能带来混杂，我们提出了一个因果中介分析框架，以确定一个基因是否直接或通过驱动细胞命运而对疾病起因果作用。我们将该方法应用于来自114个人类肺组织样本（66例肺纤维化病例和48例对照）的scRNA-seq数据，并结合来自3项研究的IPF荟萃分析GWAS汇总统计，识别了沿AT2-翻译AT2-AT1轨迹（该轨迹在肺组织修复和再生中至关重要）的IPF的伪时间依赖性因果效应。我们还发现30个基因通过细胞命运发挥中介效应。

## Abstract
With the increasing accessibility of single-cell RNA sequencing (scRNA-seq) data, cell-type-specific gene expression can be linked to complex traits through pseudo-bulk method, which considered aggregated gene expression from multiple cells of the same annotated cell type per individual and clearly shows the limitation of ignoring intra-individual cell-to-cell variability. Concurrently, pseudotime trajectory inference has gained popularity for its ability to capture continuous biological processes such as cell differentiation and lineage development, instead of individual discrete stages. It is natural to consider whether genetic effects for complex traits, such as individual level disease status, show a dynamic pattern along the inferred trajectories. In this study, we introduce a novel framework that models gene expression as a function of pseudotime along the inferred trajectories. We mapped expression quantitative trait loci (eQTL) effects in the cis-region as functional parameters, which we called "dynamic eQTLs", showing regulatory effects exerted by genetic variants change continuously along the cellular trajectory. For eQTLs of constant effects across pseudotime we leveraged external bulk-eQTL information to enhance the power. Furthermore, we employed significant, variable dynamic eQTLs as instrumental variables to infer causal relationships between gene expression and complex traits. To address challenges inherent to scRNA-seq data - such as sparsity and high variability - we incorporate an empirical likelihood-based inference method, which is non-parametric and self-normalized. Besides, genes associated with trajectory branchpoints may bring confounding, and we also proposed a causal mediation analysis framework to determine whether a gene plays a causal role for the disease directly and indirectly through driving cell fates. Applying our method to scRNA-seq data from human lung tissue of 114 samples (66 pulmonary fibrosis cases and 48 controls), along with meta-analyzed GWAS summary statistics for IPF from 3 studies, we identified pseudotime-dependent causal effects for IPF from genes implicated in the trajectory AT2 -translational AT2 - AT1, which is crucial in lung tissue repair and regeneration. We also found that 30 genes have a mediated effect through cell fates.