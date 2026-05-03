---
title: Scalable machine learning improves resistance prediction and identifies novel determinants in Mycobacterium tuberculosis
title_zh: 可扩展机器学习提升结核分枝杆菌耐药性预测并识别新型决定因素
authors: "Serajian, M., Lotfollahi, M., Green, O., Smith, K., Marini, S., Prosperi, M., Boucher, C."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.25.720842v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 用于全基因组规模耐药性预测的机器学习
tldr: "针对耐药结核病（MTB）带来的全球健康危机，本研究开发了名为AURA的GPU加速泛基因组机器学习框架。该框架利用12,185个全球分离株进行训练，能够高效预测13种抗生素的耐药性。AURA不仅克服了传统方法依赖预定义突变目录的局限，还发现了59个新的耐药相关位点，为结核病的精准治疗和全球监测提供了可扩展的平台。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的结核病耐药性预测工具受限于预定义的突变目录且在大规模分析中资源消耗过高。
method: "开发了名为AURA的GPU加速、泛基因组规模的机器学习框架，利用全球12,185个分离株进行从头耐药性预测。"
result: AURA实现了对13种抗生素的高精度耐药预测，并识别出包括katG、pncA、rpoC及PE/PGRS基因家族在内的59个新型耐药相关位点。
conclusion: AURA为揭示耐药遗传结构提供了新见解，并为结核病的精准医疗和全球监测建立了一个高效、可扩展的平台。
---

## 摘要
多耐药和广泛耐药结核分枝杆菌 (MTB) 代表了日益严重的全球健康危机，其特点是治疗方案有限且死亡率高。快速准确地预测耐药谱对于指导有效治疗和遏制传播至关重要。全基因组测序 (WGS) 为个体化耐药分析带来了希望，但现有的计算工具仍受限于预定义的突变目录，且在大规模分析中面临极高的资源需求。在此，我们提出了 AURA，这是一个用于从头 (de novo) 耐药性预测的 GPU 加速、泛基因组规模机器学习框架。AURA 基于全球 12,185 个多样化的 MTB 分离株进行训练，能够高精度预测对 13 种一线、二线及老药新用抗生素的耐药性，并识别出 59 个新型耐药相关位点，包括 katG、pncA、rpoC 以及 PE/PGRS 基因家族成员中的变异。通过实现前所未有的基因组规模模型训练，AURA 为耐药性的遗传结构提供了新见解，并为 MTB 的精准指导治疗和全球监测建立了一个可扩展的平台。

## Abstract
Multidrug-resistant and extensively drug-resistant Mycobacterium tuberculosis (MTB) represents a growing global health crisis, characterized by limited treatment options and high mortality rates. Rapid and accurate prediction of resistance profiles is critical to guide effective therapy and curb transmission. Whole-genome sequencing (WGS) offers promise for individualized resistance profiling, yet existing computational tools remain constrained by predefined mutation catalogs and prohibitive resource requirements for large-scale analyses. Here, we present AURA, a GPU-accelerated, pangenome-scale machine learning framework for de novo resistance prediction. Trained on 12,185 globally diverse MTB isolates, AURA predicts resistance to 13 first-line, second-line, and repurposed antibiotics with high precision and identifies 59 novel resistance-associated loci, including variants in katG, pncA, rpoC, and members of the PE/PGRS gene family. By enabling model training on an unprecedented genomic scale, AURA provides new insights into the genetic architecture of resistance and establishes a scalable platform for precision-guided therapy and global surveillance of MTB.