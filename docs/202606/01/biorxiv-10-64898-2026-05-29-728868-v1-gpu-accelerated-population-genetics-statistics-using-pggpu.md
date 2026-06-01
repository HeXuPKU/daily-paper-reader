---
title: GPU accelerated population genetics statistics using pg_gpu
title_zh: 使用pg_gpu的GPU加速群体遗传学统计
authors: "Pope, N. S., Rivera-Colon, A. G., Kapoor, A., Korfmann, K., Rodrigues, M. F., Small, S. T., Teterina, A. A., Kern, A. D."
date: 2026-05-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728868v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: GPU加速群体遗传学统计，包括LD计算，提升GWAS计算效率
tldr: 群体遗传学统计量计算在大规模测序数据中成为性能瓶颈。pg_gpu在NVIDIA GPU上通过融合CUDA内核实现全面统计量库，包括多样性、选择扫描、PCA等。在Ag1000G数据上，与scikit-allel和PLINK2精度一致，中位数加速139倍，LD统计量加速1750倍。全染色体臂扫描和LD计算在秒到分钟级完成。
source: biorxiv
selection_source: fresh_fetch
motivation: 大规模全基因组测序数据使CPU计算的统计量开销巨大，窗口扫描需数小时至数天，LD统计量O(n^2)复杂度常超时。
method: pg_gpu使用融合CUDA内核在NVIDIA GPU上实现11类群体遗传学统计量，包括加权SFS框架。
result: 在Ag1000G Phase 3染色体3R臂上，pg_gpu与scikit-allel/PLINK2一致，中位数139x、最大1096x加速；多群体LD统计量加速~1750倍。
conclusion: pg_gpu使全染色体臂扫描、lostruct和LD计算在单GPU上数秒至几分钟完成，显著提升效率。
---

## 摘要
群体遗传学总结统计量——多样性、分化、连锁不平衡、选择扫描和降维——是人类、农业和生态基因组学的基础。随着全基因组测序数据集增长到数十万个个体，在传统CPU实现上计算这些统计量的成本已成为主要瓶颈：单条染色体臂的滑动窗口扫描可能需要数小时到数天，而用于群体历史推断的成对连锁不平衡统计量的计算在样本量上呈O(n^2)缩放，经常完全超出实际计算时间预算。我们提出pg_gpu，一个在NVIDIA GPU上通过融合CUDA内核实现全面群体遗传学总结统计量的Python库。pg_gpu涵盖十一个类别：多样性和中性检验、分化、混合、位点频率谱、连锁不平衡、基于单倍型的选择扫描、降维（PCA、随机PCA、局部PCA/lostruct）、距离分布、亲缘关系、重采样，以及一个用于自定义θ估计器的广义加权SFS框架。在完整的Ag1000G第3阶段第3R号染色体臂（2,940个单倍型，1,090万个变异）上，pg_gpu与scikit-allel和PLINK2在机器精度上一致，同时实现了中位数139倍和最大1,096倍的加速。对于moments用于群体历史推断的多群体LD统计量，pg_gpu可作为即插即用替代方案，比原始实现快约1,750倍。整条染色体臂扫描、lostruct筛选和LD统计量计算在单个NVIDIA A100上只需数秒到几分钟即可完成。

## Abstract
Population genetics summary statistics-- diversity, divergence, linkage disequilibrium, selection scans, and dimensionality reduction-- are fundamental across human, agricultural, and ecological genomics. As whole-genome sequencing datasets have grown to hundreds of thousands of individuals, the cost of computing these statistics on conventional CPU implementations has become a major bottleneck: windowed scans of a single chromosome arm can take hours to days, and computation of pairwise linkage-disequilibrium statistics useful for demographic inference scales as O(n^2) in sample size, often exceeding wall-clock budgets entirely. We present pg_gpu, a Python library implementing a comprehensive catalog of population-genetics summary statistics as fused CUDA kernels on NVIDIA GPUs. pg_gpu covers eleven categories spanning diversity and neutrality tests, divergence, admixture, the site-frequency spectrum, linkage disequilibrium, haplotype-based selection scans, dimensionality reduction (PCA, randomized PCA, local PCA / lostruct), distance distributions, relatedness, resampling, and a generalized weighted-SFS framework for custom {theta} estimators. On the full Ag1000G Phase 3 chromosome 3R arm (2,940 haplotypes, 10.9 million variants) pg_gpu agrees with scikit-allel and PLINK2 to machine precision while delivering a median 139x and maximum 1,096x speedup. For the multi-population LD statistics used by moments for demographic inference, pg_gpu is a drop-in replacement that yields a ~1,750-fold speedup over the native implementation. Whole chromosome arm scans, lostruct screens, and calculation of LD statistics complete on a single NVIDIA A100 in seconds to a few minutes.