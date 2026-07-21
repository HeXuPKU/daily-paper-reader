---
title: The All Window-Size Search method for improved statistical power in multiple comparisons correction
title_zh: 全窗口搜索方法：提升多重比较校正中的统计功效
authors: "Nelson, M. J."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.14.738000v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 适用于GWAS的多重比较校正方法
tldr: 多重比较校正是生物科学中的基本挑战，尤其对于时间、空间等有序连续数据。现有基于簇的方法依赖预定义阈值或框架，有限制。本文提出AWSS方法，一种置换程序，自适应搜索所有连续窗口大小和位置，通过生成每个窗口大小的最大统计量空分布并校正搜索过程，严格控制族系误差率。模拟显示AWSS对宽而低幅度效应比传统簇置换方法有更高统计功效。该方法独立于特定统计检验，可广泛应用于一维有序数据，未来拓展至多维数据。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738000-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1236, \"height\": 1159, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738000-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 737, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738000-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1626, \"height\": 1376, \"label\": \"Figure\"}]"
motivation: 现有多重比较校正方法（如簇置换检验、TFCE）对宽而低振幅效应统计功效不足，且依赖预定义阈值。
method: AWSS是一种基于置换的方法，对所有连续窗口大小和位置求和，生成各窗口大小下的最大统计量空分布，并校正自适应搜索过程。
result: 模拟表明AWSS对宽而低幅度效应具有比传统簇置换方法更高的统计功效，同时维持族系误差率控制。
conclusion: AWSS框架通用且可扩展，为有序数据多重比较提供更灵活、更强大的校正方案。
---

## 摘要
多重比较校正是生物科学中的一个基本挑战，尤其对于在有序连续域（如时间、空间或频率）上采样的数据。现有方法包括基于聚类的置换检验和无阈值聚类增强（TFCE），它们利用空间或时间连续性，但仍依赖于预定义的统计框架或阈值化程序。本文介绍了全窗口搜索（AWSS）方法，这是一种基于置换的程序，能够正式控制族系错误率，同时自适应地搜索所有连续窗口大小和位置。对于每次置换，测试统计量在所有可能的窗口上求和，从而在每个窗口大小下生成最大统计量的零分布。第二阶段估计在搜索所有窗口大小后出现的最显著未校正p值的零分布，从而允许最终p值针对自适应搜索过程本身进行校正。这一程序在统计上正式化了研究者们在视觉检查有序数据时自然进行的隐式多尺度搜索。具有已知真实效应的模拟表明，对于广泛且低振幅的效应，AWSS能够提供比传统基于聚类的置换方法显著更高的统计功效，同时保持适当的族系错误率控制。由于该框架独立于任何特定的统计检验，它易于适用于多种形式的一维有序数据。未来的扩展将把该方法推广到多维空间和时空数据集，包括神经影像和其他高维生物数据。

## Abstract
Correcting for multiple comparisons is a fundamental challenge throughout the biological sciences, particularly for data sampled over ordered continua such as time, space, or frequency. Existing approaches, including cluster-based permutation tests and threshold-free cluster enhancement (TFCE), leverage spatial or temporal contiguity but remain dependent on predefined statistical frameworks or thresholding procedures. Here we introduce the All Window-Size Search (AWSS) method, a permutation-based procedure that formally controls the family-wise error rate while adaptively searching across all contiguous window sizes and locations. For each permutation, test statistics are summed across every possible window, generating null distributions of maximal statistics at every window size. A second stage estimates the null distribution of the most significant uncorrected p-value that would arise from searching across all window sizes, allowing final p-values to be corrected for the adaptive search process itself. This procedure statistically formalizes the implicit multiscale search that investigators naturally perform when visually inspecting ordered data. Simulations with known ground-truth effects demonstrate that AWSS can provide substantially greater statistical power than conventional cluster-based permutation methods for broad, low-amplitude effects while maintaining appropriate family-wise error control. Because the framework is independent of any particular statistical test, it is readily applicable to diverse forms of one-dimensional ordered data. Future extensions will generalize the method to multidimensional spatial and spatiotemporal datasets, including neuroimaging and other high-dimensional biological data.