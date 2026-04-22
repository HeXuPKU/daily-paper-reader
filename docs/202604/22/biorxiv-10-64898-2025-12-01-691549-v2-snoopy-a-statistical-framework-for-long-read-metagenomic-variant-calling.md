---
title: "SNooPy: a statistical framework for long-read metagenomic variant calling"
title_zh: SNooPy：一种用于长读长宏基因组变异检测的统计框架
authors: "Faure, R., Faure, U., Truong, T. M. K., Derzelle, A., Lavenier, D., Flot, J.-F., Quince, C."
date: 2026-04-20
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.01.691549v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 宏基因组变异检测的统计框架
tldr: 针对长读长宏基因组数据中单核苷酸变异（SNP）检测的难题，本文开发了SNooPy工具。现有的变异检测器多针对人类基因组设计，难以应对宏基因组的复杂性。SNooPy采用全新的统计框架，不预设单倍型数量或进化关系，在处理宏基因组样本时表现优于传统的统计和深度学习方法，为微生物群落研究提供了更精准的变异分析手段。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的长读长变异检测工具主要针对人类基因组设计，无法有效处理宏基因组样本中复杂的单倍型和序列差异。
method: SNooPy实现了一种专为宏基因组设计的统计框架，不依赖于单倍型数量、进化关系或序列散度的先验假设。
result: 实验证明SNooPy在SNP检测性能上超越了现有的传统统计方法和基于深度学习的变异检测工具。
conclusion: SNooPy填补了长读长宏基因组专用变异检测工具的空白，且未来与深度学习的结合有望进一步提升性能。
---

## 摘要
现有的长读长单核苷酸变异检测工具主要针对基因组数据（特别是人类基因组）设计。虽然其中一些已被用于宏基因组数据，但其底层假设和训练过程未能考虑到宏基因组样本固有的复杂性。迄今为止，尚未出现专门为宏基因组应用设计的长读长变异检测工具。为了填补这一空白，我们提出了 SNooPy，这是一种实现了专为长读长宏基因组数据定制的新型统计框架的 SNP 检测工具。与之前的基因组方法不同，我们的方法不对存在的单倍型数量、它们的进化关系或序列差异做任何假设。我们证明了 SNooPy 的性能优于传统的统计方法和基于深度学习的 SNP 检测工具。我们的结果表明，未来将该框架与深度学习方法相结合，可以进一步提高变异检测的性能。SNooPy 可在 github.com/rolandfaure/snoopy 免费获取。

## Abstract
Current long-read single-nucleotide variant callers were designed primarily for genomic data - particularly human genomes. While some have been used on metagenomic data, their underlying assumptions and training procedures fail to account for the inherent complexity of metagenomic samples. To date, no long-read variant caller has been purpose-built for metagenomic applications. To address this gap, we present SNooPy, a SNP-calling tool that implements a new statistical framework tailored to long-read metagenomic data. Unlike previous genomic methods, our approach makes no assumptions about the number of haplotypes present, their evolutionary relationships, or their sequence divergence. We demonstrate that SNooPy outperforms both traditional statistical and deep learning-based SNP callers. Our results suggest that future integration of this framework with deep learning approaches could further enhance variant calling performance. SNooPy is freely available on github.com/rolandfaure/snoopy.