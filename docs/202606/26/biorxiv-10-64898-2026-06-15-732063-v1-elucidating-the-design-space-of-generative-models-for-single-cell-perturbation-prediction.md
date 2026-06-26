---
title: Elucidating the Design Space of Generative Models for Single-Cell Perturbation Prediction
title_zh: 阐明单细胞扰动预测生成模型的设计空间
authors: "Bhattacharya, S., Gensbigler, C., Karim, S., Lees, J."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732063v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 单细胞扰动预测的生成模型，虚拟细胞建模
tldr: 单细胞RNA-seq数据缺乏自然基因顺序，直接应用下一个token预测方法效果不佳。本文提出ExpressionVAE（eVAE），通过有限标量量化（FSQ）瓶颈将每个细胞压缩为离散代码序列，并训练扰动条件离散先验。在Replogle和Parse 1M数据集上，eVAE在所有分布指标上达到新SOTA，Fréchet距离和MMD2比最强连续潜变量基线低3-20倍。消融实验表明，离散潜变量本身是性能提升的关键，而非先验家族。在CRISPRi逆转基准上，冻结的eVAE编码器以极少数据匹配scGPT的扰动排序性能。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决单细胞RNA-seq无自然基因顺序导致直接应用语言模型失败的问题，探索学习潜结构以提供顺序。
method: 提出eVAE，使用FSQ瓶颈将细胞编码为离散代码序列，并训练扰动条件离散先验（自回归或掩码离散扩散）。
result: 在多个数据集上分布指标SOTA，Fréchet距离和MMD2降低3-20倍；在CRISPRi基准上编码器性能与scGPT相当。
conclusion: 离散潜表征是单细胞扰动预测的有效设计轴，优于连续潜变量模型，且先验家族影响较小。
---

## 摘要
下一个词元预测已在语言领域产生了可预测的缩放规律，但这一方法预设了具有有意义顺序的词元序列。单细胞RNA-seq计数没有自然的基因顺序，因此将这一方法直接应用于原始表达会在不合适的从左到右偏差下失败。我们转而探究学习到的潜在表示是否能提供该方法所需的结构。我们引入了ExpressionVAE (eVAE)，一种离散潜在扰动模型，通过有限标量量化（FSQ）瓶颈将每个细胞压缩成短序列的离散码，并训练一个基于扰动条件的离散先验。在Replogle和Parse 1M数据集上，eVAE在所有分布度量上均达到新的最优水平，并在大多数细胞评估扰动度量上领先，其中Frechet距离和MMD2大约是强连续潜在基线的3到20倍低。将先验在自回归和掩码离散扩散之间切换，性能几乎相同，将增益归因于离散潜在本身而非先验族。解码器头部消融实验揭示了一个单一设计轴，即推理时预测分布的丰富性，该轴将标准度量分为两组：方差敏感和均值敏感，它们沿该轴朝相反方向移动。最后，在炎症细胞因子胁迫下的1,732种扰动的保留CRISPRi反转基准上，冻结的eVAE编码器在扰动排名上优于UMAP和差异表达，并以少量数据匹配scGPT。我们发布了我们的代码。

## Abstract
Next-token prediction has produced predictable scaling in language, but the recipe presumes a sequence of tokens with a meaningful order. Single-cell RNA-seq counts have no natural gene ordering, so applying the recipe directly to raw expression fails under an ill-suited left-to-right bias. We instead ask whether a learned latent can supply the structure the recipe needs. We introduce ExpressionVAE (eVAE), a discrete-latent perturbation model that compresses each cell into a short sequence of discrete codes through a finite-scalar-quantization (FSQ) bottleneck and trains a perturbation-conditioned discrete prior over those codes. On Replogle and Parse 1M, eVAE sets a new state of the art on every distributional metric and leads on most cell-eval perturbation metrics, with Frechet distance and MMD2 roughly 3 to 20x lower than the strongest continuous-latent baseline. Swapping the prior between autoregressive and masked discrete diffusion leaves performance near-identical, isolating the gain to the discrete latent itself rather than the prior family. A decoder-head ablation then exposes a single design axis, the richness of the predictive distribution at inference, that splits the standard metrics into two groups, variance-sensitive and mean-sensitive, which move in opposite directions along the axis. Finally, on a held-out CRISPRi reversion benchmark of 1,732 perturbations under inflammatory cytokine stress, the frozen eVAE encoder outperforms UMAP and differential expression and matches scGPT on perturbation ranking at a fraction of the data.1 We release our code.2