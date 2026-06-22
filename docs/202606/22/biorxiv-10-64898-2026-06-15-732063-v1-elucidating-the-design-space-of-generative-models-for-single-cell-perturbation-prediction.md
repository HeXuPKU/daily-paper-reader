---
title: Elucidating the Design Space of Generative Models for Single-Cell Perturbation Prediction
title_zh: 阐明单细胞扰动预测生成模型的设计空间
authors: "Bhattacharya, S., Gensbigler, C., Karim, S., Lees, J."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732063v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 单细胞扰动预测生成模型，推动虚拟细胞建模
tldr: 单细胞RNA-seq数据缺乏自然基因顺序，直接应用next-token预测因左到右偏差失效。本文提出eVAE，通过FSQ瓶颈将细胞压缩为离散代码序列并训练扰动条件先验，在多个数据集上以更低Frechet距离和MMD2超越连续潜在模型，增益源于离散潜在本身。揭示预测分布丰富性这一设计轴将指标分为方差敏感和均值敏感两类。冻结编码器在CRISPRi基准上以极少数据匹配scGPT。
source: biorxiv
selection_source: fresh_fetch
motivation: 单细胞RNA-seq计数缺乏自然基因排序，导致基于next-token预测的方法因不合理的左到右偏差而失效。
method: 提出ExpressionVAE (eVAE)，使用有限标量量化(FSQ)瓶颈将细胞压缩为离散代码序列，并训练扰动条件离散先验。
result: 在Replogle和Parse 1M上eVAE取得SOTA，Frechet距离和MMD2比连续潜在基线低3-20倍；CRISPRi基准上冻结编码器以极少数据匹配scGPT。
conclusion: 离散潜在表示本身而非先验族是性能提升关键，设计轴（预测分布丰富性）将指标分为两类，为扰动预测提供新方向。
---

## 摘要
下一词元预测在语言中产生了可预测的缩放，但该方法假设词元序列具有有意义的顺序。单细胞RNA-seq计数没有自然的基因顺序，因此在不适用的从左到右偏差下，将该方法直接应用于原始表达量会失败。我们转而探究学习到的隐变量是否能提供该方法所需的结构。我们提出了ExpressionVAE（eVAE），一种离散隐变量扰动模型，通过有限标量量化（FSQ）瓶颈将每个细胞压缩成短序列的离散编码，并在这些编码上训练一个扰动条件化的离散先验。在Replogle和Parse 1M数据集上，eVAE在所有分布指标上达到了新的最先进水平，并在大多数细胞评估扰动指标上领先，其弗雷歇距离和MMD2大约比最强的连续隐变量基线低3到20倍。在自回归和掩蔽离散扩散之间交换先验，性能几乎相同，从而将增益归因于离散隐变量本身，而不是先验家族。随后，解码器头部消融实验揭示了一个单一的设计轴，即推断时预测分布的丰富性，它将标准指标分为两组：方差敏感型和均值敏感型，这两组指标沿该轴向相反方向移动。最后，在一个包含1,732个扰动（在炎症细胞因子应激下）的留出CRISPRi恢复基准测试中，冻结的eVAE编码器优于UMAP和差异表达，并且在扰动排名上与scGPT相当，而所需数据量仅为后者的一小部分。¹我们发布代码。²

## Abstract
Next-token prediction has produced predictable scaling in language, but the recipe presumes a sequence of tokens with a meaningful order. Single-cell RNA-seq counts have no natural gene ordering, so applying the recipe directly to raw expression fails under an ill-suited left-to-right bias. We instead ask whether a learned latent can supply the structure the recipe needs. We introduce ExpressionVAE (eVAE), a discrete-latent perturbation model that compresses each cell into a short sequence of discrete codes through a finite-scalar-quantization (FSQ) bottleneck and trains a perturbation-conditioned discrete prior over those codes. On Replogle and Parse 1M, eVAE sets a new state of the art on every distributional metric and leads on most cell-eval perturbation metrics, with Frechet distance and MMD2 roughly 3 to 20x lower than the strongest continuous-latent baseline. Swapping the prior between autoregressive and masked discrete diffusion leaves performance near-identical, isolating the gain to the discrete latent itself rather than the prior family. A decoder-head ablation then exposes a single design axis, the richness of the predictive distribution at inference, that splits the standard metrics into two groups, variance-sensitive and mean-sensitive, which move in opposite directions along the axis. Finally, on a held-out CRISPRi reversion benchmark of 1,732 perturbations under inflammatory cytokine stress, the frozen eVAE encoder outperforms UMAP and differential expression and matches scGPT on perturbation ranking at a fraction of the data.1 We release our code.2