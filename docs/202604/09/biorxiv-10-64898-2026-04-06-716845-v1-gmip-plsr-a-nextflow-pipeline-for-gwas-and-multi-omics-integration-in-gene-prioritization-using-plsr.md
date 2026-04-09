---
title: "GMIP-PLSR: A Nextflow Pipeline for GWAS and Multi-Omics Integration in Gene Prioritization Using PLSR"
title_zh: GMIP-PLSR：一个用于 GWAS 和多组学整合并利用 PLSR 进行基因优先级排序的 Nextflow 流水线
authors: "Kanchwala, M. S., Xing, C., Xuan, Z."
date: 2026-04-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.06.716845v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 用于GWAS和多组学整合基因优先排序的流程
tldr: 针对全基因组关联分析（GWAS）在识别因果基因方面的局限性，本文开发了基于Nextflow的GMIP-PLSR流程。该流程通过整合多组学数据并引入偏最小二乘回归（PLSR）解决了传统PoPS方法中的多重共线性问题。在非酒精性脂肪性肝病（NAFLD）等数据集上的应用表明，该方法能更有效地进行基因优先级排序，提高生物学解释力。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的GWAS分析在识别因果基因和通路方面存在困难，且现有工具如PoPS面临特征多重共线性的挑战。
method: 开发了基于Nextflow的GMIP-PLSR流程，利用偏最小二乘回归（PLSR）整合GWAS与多组学数据进行基因优先级排序。
result: 在多个GWAS数据集及NAFLD案例研究中，GMIP-PLSR在识别高遗传力和通路富集基因方面表现优于PoPS。
conclusion: GMIP-PLSR为后GWAS分析提供了一个高效、可扩展且鲁棒的基因重排序解决方案，显著增强了对复杂性状的生物学洞察。
---

## 摘要
全基因组关联研究 (GWAS) 显著推进了我们对复杂性状和疾病的理解，但由于在识别因果基因和通路方面存在挑战，其解释能力仍然有限。将 GWAS 与多组学数据（如基因表达、蛋白质-蛋白质相互作用和基因-通路网络）相结合，具有增强生物学见解和改进基因优先级排序的潜力。为了满足这一潜力和需求，我们开发了 GWAS 与多组学整合流水线 (GMIP)，这是一个灵活且可扩展的框架，整合了 PoPS、MAGMA 和 benchmarker 等广泛使用的工具，以丰富 GWAS 的发现。然而，PoPS 的特征存在多重共线性问题，这可能会影响其性能。为了克服这一问题，我们推出了 GMIP-PLSR，它是 GMIP 的扩展版本，利用偏最小二乘回归 (PLSR) 来有效处理多重共线性。我们在多个 GWAS 数据集上应用了 GMIP-PLSR，证明其在大多数情况下优于 PoPS。在一项关于非酒精性脂肪性肝病 (NAFLD) 的案例研究中，GMIP-PLSR 利用源自疾病特异性单细胞 RNA 测序 (scRNA-seq) 和通用 PoPS 特征的特征，识别出了具有更高遗传力和在已知 NAFLD 通路中富集程度更强的基因集，证实了其增强 GWAS 发现的能力。GMIP 基于 Nextflow 构建，计算效率高，能够适应多种研究环境，并为 GWAS 后分析中的基因重新优先级排序提供了稳健的解决方案。GMIP-PLSR 可在 https://github.com/mohammedmsk/GMIP 获取。

## Abstract
Genome-wide association studies (GWAS) have significantly advanced our understanding of complex traits and diseases, but their interpretive power remains limited due to challenges in identifying causal genes and pathways. Integrating GWAS with multi-omics data - such as gene expression, protein-protein interactions, and gene-pathway networks have the potential to enhance biological insights and improve gene prioritization. To fulfill this potential and need, we developed the GWAS & Multi-omics Integration Pipeline (GMIP), a flexible and scalable framework that incorporates widely used tools such as PoPS, MAGMA, and benchmarker to enrich GWAS findings. However, PoPS suffers from multicollinearity in its features, which can impact performance. To overcome this, we introduce GMIP-PLSR, an extension of GMIP that uses Partial Least Squares Regression (PLSR) to manage multicollinearity effectively. We applied GMIP-PLSR across multiple GWAS datasets, demonstrating superior performance over PoPS in most cases. In a case study on NAFLD, GMIP-PLSR, using features derived from both disease-specific scRNA-seq and general PoPS features, identified gene sets with higher heritability and stronger enrichment in known NAFLD pathways, confirming its ability to enhance GWAS findings. Built on Nextflow, GMIP is computationally efficient, adaptable to diverse research environments, and provides a robust solution for gene reprioritization in post-GWAS analyses. GMIP-PLSR is available at https://github.com/mohammedmsk/GMIP.