---
title: A permutation-free family-wise error rate for the moderated top-gene scan under gene correlation
title_zh: 一种无置换的族系错误率方法，用于基因相关下的调节最高基因扫描
authors: "Dwyer, W. J."
date: 2026-08-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.17.745282v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 在基因相关下实现无置换的家族错误率控制，可直接迁移到GWAS的多重检验校正
tldr: 在基因相关下，以最大调节t统计量为基础的差异基因扫描，控制族系误差率传统上依赖置换。误差预算消融显示其宽松性主要源于经验贝叶斯先验自由度的膨胀，而相关性本身并无独立障碍。通过谱U统计量估计平均平方基因相关并校正先验，无需置换即可使族系误差率接近独立基因基线，且保留功效；另提出不稳定性指数以指导严重共表达时采用置换。
source: biorxiv
selection_source: fresh_fetch
motivation: 基因相关性改变有效多重性并破坏经验贝叶斯方差先验，使调节t统计量扫描的族系误差率宽松，传统需置换控制。
method: 用误差预算消融将宽松性归因于先验自由度膨胀，以谱U统计量估计平均平方基因相关，校正先验并计算不稳定性指数。
result: 校正后族系误差率恢复至独立基因基线，功效保留且无需置换；不稳定性指数在严重共表达时提示改用置换。
conclusion: 相关性不是独立障碍，只要先验正确，无置换即可控制族系误差率，为相关基因扫描提供了新途径。
---

## 摘要
差异表达扫描报告具有最大调节t统计量的基因，因此控制族系错误率意味着控制基因间最大统计量的零分布。在基因相关下，广泛认为这需要置换，因为相关性改变了有效多重性，并破坏了调节t统计量背后的经验贝叶斯方差先验。我们通过错误预算消融分解了这种宽松性，并表明在模拟模型类中，它主要归结为经验贝叶斯先验自由度的膨胀：替换真实先验使族系错误率回到独立基因小样本基线，因此一旦先验正确，依赖性不会构成额外的障碍。相关性使对数样本方差的跨基因离散度缩小；因为先验自由度随该离散度减小而减小，先验被高估，调节最大值变得宽松。将观察到的离散度除以一减去平均平方基因相关性（通过无调优谱U统计量估计，具有无偏迹目标），逆转了该机制，并在保留功效的情况下使族系错误率接近基线，而无需置换。一个可观察的不稳定性指数标记了严重共表达时应推迟置换的情况。

## Abstract
A differential-expression scan reports the genes with the largest moderated t-statistics, so controlling the family-wise error rate means controlling the null distribution of the maximum statistic over genes. Under gene correlation this is widely believed to require permutation, because correlation changes the effective multiplicity and corrupts the empirical-Bayes variance prior behind the moderated t-statistic. We decompose that liberality by an error-budget ablation and show that, within the simulated model class, it reduces principally to an inflation of the empirical-Bayes prior degrees of freedom: substituting the true prior returns the family-wise error to the independent-gene small-sample baseline, so dependence imposes no separate barrier once the prior is correct. Correlation deflates the cross-gene spread of the log sample variances; because the prior degrees of freedom decreases in that spread, the prior is over-estimated and the moderated maximum turns liberal. Dividing the observed spread by one minus the mean squared gene correlation, estimated by a tuning-free spectral U-statistic with an unbiased trace target, reverses the mechanism and holds the family-wise error near the baseline at retained power without permutation. An observable instability index flags when severe co-expression should defer to permutation.