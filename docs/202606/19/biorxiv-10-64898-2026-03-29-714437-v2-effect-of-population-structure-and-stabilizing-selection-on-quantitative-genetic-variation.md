---
title: Effect of population structure and stabilizing selection on quantitative genetic variation
title_zh: 群体结构与稳定化选择对数量遗传变异的影响
authors: "Li, J., Hermisson, J., Sachdeva, H."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.29.714437v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 群体结构和选择对数量遗传变异的理论分析，对GWAS解释具有指导意义
tldr: 研究群体结构和稳定化选择如何影响多基因加性性状的遗传变异。采用无限岛模型解析推导方差组分及FST、QST，并与个体基模拟对比。发现存在关键迁移阈值，低于该阈值群体结构显著增大基因方差，且亚群间遗传基础在阈值附近最相似，高迁移率下反而差异增大，影响GWAS跨群体可移植性。基于单基因座扩散近似的平均场方法可准确预测相关量。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究空间均匀稳定化选择下，群体结构对多基因性状遗传变异维持的影响，尤其是突变-选择-迁移-漂变平衡下的群体内和群体间变异。
method: 采用无限岛模型推导方差组分及FST、QST的解析近似，并用基于个体的计算机模拟进行验证。
result: 发现关键迁移阈值，低于该阈值群体结构大幅增大多基因方差；亚群间遗传基础在阈值附近最相似，高迁移率下反而差异增大。
conclusion: 群体结构对遗传变异的影响依赖于迁移率与效应大小，GWAS跨群体可移植性在中等迁移率下最优，平均场理论可准确预测平衡态。
---

## 摘要
我们研究了一种最简单的多基因选择场景：一个二倍体个体的亚群种群，在空间均匀的稳定化选择下表达加性性状。我们关注在突变-选择-迁移-漂变平衡下，个体位点和性状水平上，亚群内和亚群间可维持的变异量。我们在无限岛屿模型假设下推导了方差成分和汇总统计量（如FST和QST）的解析近似，并与基于个体的模拟进行比较。我们发现：(i) 存在一个临界迁移阈值（取决于性状位点的效应大小），低于该阈值时，种群结构会强烈地将亚群内的基因变异膨胀到远高于随机交配种群的水平。每个亚群内的变异在接近临界迁移率时最大化。(ii) 跨亚群性状变异的遗传基础在接近该迁移阈值时最为相似，并且（反直觉地）对于更高的迁移率变得不那么相似。这对亚群间全基因组关联研究（GWAS）的可移植性有影响，即在一个亚群中对方差贡献大的位点在多大程度上解释了其他亚群的方差。(iii) 基于单位点扩散近似的解析平均场方法，结合有效迁移和选择参数（以考虑位点间的关联），非常准确地预测了各种数量。

## Abstract
We study one of the simplest scenarios of polygenic selection that can be imagined: a subdivided population of diploid individuals expressing an additive trait under spatially homogeneous stabilizing selection. We are interested in the amounts of variation that can be maintained at mutation-selection-migration-drift equilibrium, at individual loci and at the level of the trait, within and among subpopulations. We derive analytical approximations for variance components and summary statistics such as FST and QST under the assumptions of the infinite-island model and compare these with individual-based simulations. We find that: (i) There is a critical migration threshold (which depends on effect sizes of trait loci) below which population structure strongly inflates genic variance in the subdivided population to levels well above those in a panmictic population. Variation within each subpopulation is maximized close to the critical migration rate. (ii) The genetic basis of trait variation across subpopulations is most similar close to this migration threshold and (counter-intuitively) becomes less similar for higher migration rates. This has consequences for the  portability of Genome-Wide Association Studies (GWAS) between subpopulations, i.e, the extent to which loci with large contributions to variance in one subpopulation explain variance in other subpopulations. (iii) An analytical mean-field approach based on the single-locus diffusion approximation, together with effective migration and selection parameters (to account for associations between loci), very accurately predicts various quantities.