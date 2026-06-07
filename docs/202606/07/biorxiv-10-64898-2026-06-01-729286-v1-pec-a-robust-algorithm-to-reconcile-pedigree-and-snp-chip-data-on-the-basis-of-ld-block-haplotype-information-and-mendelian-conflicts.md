---
title: "PEC: a robust algorithm to reconcile pedigree and SNP-chip data on the basis of LD block, haplotype information, and Mendelian conflicts"
title_zh: PEC：基于LD区块、单倍型信息及孟德尔冲突的谱系与SNP芯片数据校正鲁棒算法
authors: "Fu, C., Mei, Q., Miao, Y., Xiang, T."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729286v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 利用LD和单倍型的谱系校正算法，适用于GWAS数据质量控制
tldr: 谱系错误在 livestock 群体中常见，影响育种效率。PEC 算法利用 LD block 和单倍型片段匹配候选亲本与后代，并通过孟德尔冲突检查校正谱系。在模拟和真实猪群体中，PEC 在准确性、内存和速度上优于 SeekParentF90 和 AlphaAssign，并显著提升 ssGBLUP 的基因组评估准确性和无偏性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有谱系校正方法流程复杂、计算成本高且精度不足，亟需高效准确的解决方案。
method: 基于 LD block 估计连锁模式，匹配候选亲本与后代的单倍型片段，再通过孟德尔冲突检查调整谱系。
result: 模拟猪数据中，PEC 在准确性、内存和速度上均优于对比方法；真实群体中经 PEC 校正的谱系显著提升 ssGBLUP 评估准确性。
conclusion: PEC 提供了一种高效准确的谱系错误校正方案，对提升 livestock 基因组选择效果具有实用价值。
---

## 摘要
动机：由于长期人工记录，家畜群体中常出现谱系错误，这降低了育种项目的效率。尽管存在多种谱系校正方法，但其实际应用常受限于复杂流程、高计算成本及精度不足。因此，亟需一种有效且高效的谱系错误校正方案。结果：我们开发了一种新算法及软件PEC，用于准确高效地校正谱系错误。该方法利用估计的连锁不平衡模式匹配候选父母与后代之间的单倍型片段，随后检查孟德尔冲突以调整谱系。利用模拟猪数据集，我们在准确性、内存使用和计算时间方面将PEC与SeekParentF90及AlphaAssign进行了比较。PEC在所有指标上均表现出优越性能。此外，在真实猪群中应用单步基因组最佳线性无偏预测（ssGBLUP）显示，经PEC校正的谱系显著提高了基因组评估的准确性和无偏性，凸显了谱系错误校正的重要性。可用性：PEC软件免费发布于https://github.com/TXiang-lab/JPEC。

## Abstract
Motivation: Pedigree errors frequently occur in livestock populations due to long-term manual record-keeping, which reduces the efficiency of breeding programs. Although several pedigree correction methods exist, their practical application is often limited by complicated procedures, high computational cost, and insufficient accuracy. Therefore, an effective and efficient solution for pedigree error correction is needed. Results: We developed a new algorithm and software, PEC, to accurately and efficiently correct pedigree errors. The method matches haplotype fragments between candidate parents and offspring using estimated linkage disequilibrium patterns and subsequently checks for Mendelian conflicts to adjust the pedigree. Using simulated pig datasets, we compared PEC against SeekParentF90 and AlphaAssign in terms of accuracy, memory usage, and computation time. PEC demonstrated superior performance across all metrics. Furthermore, application of single-step genomic best linear unbiased prediction (ssGBLUP) in a real pig population showed that PEC corrected pedigrees significantly improved the accuracy and unbiasedness of genomic evaluations, highlighting the importance of pedigree error correction. Availability: The PEC software is freely available at https://github.com/TXiang-lab/JPEC.