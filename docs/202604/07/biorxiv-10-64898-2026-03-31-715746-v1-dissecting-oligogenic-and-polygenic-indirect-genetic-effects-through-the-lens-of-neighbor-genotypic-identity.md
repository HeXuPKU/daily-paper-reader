---
title: Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity
title_zh: 从邻体基因型一致性的角度剖析寡基因和多基因间接遗传效应
authors: "Sato, Y., Hamazaki, K."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.31.715746v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 用于间接遗传效应GWAS和基因组预测的多核混合模型
tldr: 本研究探讨了间接遗传效应（IGEs），即个体表型受邻居基因型影响的现象。作者开发了一种基于铁磁学伊辛模型的多核混合模型，成功整合了多基因和寡基因 IGEs，用于基因组预测和全基因组关联分析（GWAS）。该方法能有效区分直接与间接遗传效应，并在杨树和苹果树的实证研究中发现了显著的种间竞争信号，为解析群体遗传结构提供了强有力的工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-715746-v1/fig-001.webp\", \"caption\": \"Figures 528\", \"page\": 19, \"index\": 1, \"width\": 852, \"height\": 594}]"
motivation: 旨在开发一种统一的方法来整合和区分多基因与寡基因背景下的间接遗传效应。
method: 引入基于伊辛模型的多核混合模型，通过单一协方差参数简化位点级和背景级的 IGEs 计算。
result: 模拟验证了模型在推断 DGEs 与 IGEs 权衡方面的能力，并在苹果树中定位到了与竞争相关的显著变异位点。
conclusion: 该研究提供了一种灵活的 IGEs 分析框架，有助于深入理解植物群体中的遗传互作与竞争机制。
---

## 摘要
个体表型通常取决于群体内其他个体的基因型。这些现象被称为间接遗传效应（IGEs），并已通过数量遗传模型与直接遗传效应（DGEs）区分开来。近期的研究利用高分辨率多态性数据实现了 IGEs 的基因组预测（GP）和全基因组关联分析（GWAS），但统一的方法仍然有限。在此，我们使用包含两个随机效应且具有单一协方差参数的多核混合模型，整合了多基因和寡基因 IGEs。在该实现的基础上，铁磁学的伊辛模型（Ising model）使我们能够分别简化用于 GWAS 和 GP 的位点级和背景 IGEs。我们的模拟表明，虽然先前模型与本模型表现相似，但本模型可以推断 DGEs 和 IGEs 之间的权衡。通过将该方法应用于三种木本植物，我们发现了杨树和苹果树中存在基因型间竞争的证据，但在攀缘葡萄藤中证据有限。基于 GWAS，我们还检测到了与苹果树干生长的竞争性 IGEs 相关的显著变异。我们的研究为 IGEs 的 GWAS/GP 提供了一种灵活的实现方式，从而为剖析群体表现的遗传结构提供了有效工具。

## Abstract
Individual phenotypes often depend on the genotypes of other individuals within a group. These phenomena are termed  indirect genetic effects (IGEs) and have been distinguished from direct genetic effects (DGEs) using quantitative genetic models. Recent studies have utilized high-resolution polymorphism data to enable genomic prediction (GP) and genome-wide association study (GWAS) of IGEs, but unified methods remain limited. Here we integrate polygenic and oligogenic IGEs using a multi-kernel mixed model incorporating two random effects with a single covariance parameter. Underlying this implementation, the Ising model of ferromagnetics enabled us to simplify locus-wise and background IGEs for GWAS and GP, respectively. Our simulations demonstrated that, while the previous and present models exhibited similar performance, the present model can infer a trade-off between DGEs and IGEs. By applying this method to three species of woody plants, we found evidence for intergenotypic competition in aspen and apple trees, but limited evidence in climbing grapevines. Based on GWAS, we also detected significant variants associated with the competitive IGEs on the apple trunk growth. Our study offers a flexible implementation for GWAS/GP of IGEs, thereby providing an effective tool to dissect the genetic architecture of group performance.