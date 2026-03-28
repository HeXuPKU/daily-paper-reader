---
title: Genome-wide maps of transcription factor footprints identify noncoding variants rewiring gene regulatory networks with varTFBridge
title_zh: 全基因组转录因子足迹图谱利用 varTFBridge 识别重构基因调控网络的非编码变异
authors: "Lin, J., Dong, W., Zhang, J., Xie, C., Jing, X., Zhao, J., Ma, K., Kang, H., Jiang, Y., Xie, X. S., Zhao, Y."
date: 2026-03-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.03.708783v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 使用varTFBridge进行精细映射并识别因果非编码变异
tldr: 本研究针对非编码区变异如何影响基因调控这一难题，利用单分子脱氨酶足迹技术（FOODIE）在K562细胞中实现了极高的遗传力富集。研究团队开发了集成FOODIE与AlphaGenome预测的varTFBridge框架，用于识别改变转录因子（TF）介导调控的因果变异。通过对英国生物样本库近50万个基因组的分析，成功识别出113个高置信度调控变异，揭示了变异-TF结合-基因-性状的复杂关联，为理解非编码变异的致病机制提供了新工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-03-708783-v1/fig-001.webp\", \"caption\": \"\", \"page\": 4, \"index\": 1, \"width\": 2329, \"height\": 3279}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-03-708783-v1/fig-002.webp\", \"caption\": \"\", \"page\": 8, \"index\": 2, \"width\": 2460, \"height\": 2504}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-03-708783-v1/fig-003.webp\", \"caption\": \"\", \"page\": 11, \"index\": 3, \"width\": 2458, \"height\": 3527}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-03-708783-v1/fig-004.webp\", \"caption\": \"\", \"page\": 15, \"index\": 4, \"width\": 1430, \"height\": 1751}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-03-708783-v1/fig-005.webp\", \"caption\": \"\", \"page\": 18, \"index\": 5, \"width\": 2456, \"height\": 3222}]"
motivation: 旨在解决全基因组关联研究中识别出的海量非编码变异如何改变基因调控及导致人类性状变化的难题。
method: 开发了varTFBridge框架，将高分辨率的FOODIE足迹技术与AlphaGenome变异效应预测相结合，以识别影响转录因子结合的因果变异。
result: 在英国生物样本库的红细胞性状分析中，识别出113个关键调控变异，涉及64个转录因子和108个基因，并阐明了rs112233623通过破坏GATA1/TAL1结合影响CCND3增强子的机制。
conclusion: varTFBridge能有效识别并解析非编码区常见及罕见变异的功能机制，为重构基因调控网络提供了强有力的计算与实验支撑。
---

## 摘要
全基因组关联研究已识别出数百万个与人类性状相关的非编码位点，然而这些变异如何改变基因调控仍是一个重大挑战，特别是对于全基因组测序队列和高分辨率功能注释有限的罕见变异。在此，我们展示了 K562 细胞中的单分子脱氨酶足迹技术（FOODIE）尽管仅覆盖基因组的 0.12%，却捕获了红细胞性状高达 103 倍的遗传力富集。我们推出了 varTFBridge，它整合了 FOODIE 足迹技术与 AlphaGenome 变异效应预测，以识别改变转录因子（TF）介导调控的因果非编码变异。应用于 13 种红细胞性状的 490,640 个 UK Biobank 基因组，varTFBridge 优先筛选出 113 个高置信度调节变异（104 个常见变异，9 个罕见变异），涵盖了跨越 64 个 TF 和 108 个基因的“变异-TF 结合-基因-性状”级联中的 2,173 个关联。varTFBridge 重现了 rs112233623 并解析了其机制：CCND3 增强子处的 GATA1/TAL1 协同结合破坏，从而改变了红细胞计数和体积。

## Abstract
Genome-wide association studies have identified millions of noncoding loci linked to human traits, yet how these variants alter gene regulation remains a major challenge, particularly for rare variants where whole-genome sequencing cohorts and high-resolution functional annotations remain limited. Here we show that single-molecule deaminase footprinting (FOODIE) in K562 cells captures up to 103-fold heritability enrichment for erythroid traits despite covering 0.12% of the genome. We introduce varTFBridge, integrating FOODIE footprinting with AlphaGenome variant effect prediction to identify causal noncoding variants altering transcription factor (TF)-mediated regulation. Applied to 490,640 UK Biobank genomes across 13 erythrocyte traits, varTFBridge prioritises 113 high-confidence regulatory variants (104 common, 9 rare), encompassing 2,173 linkages along the variant-TF binding- gene-trait cascade across 64 TFs and 108 genes. varTFBridge recapitulates rs112233623 and resolves its mechanism: GATA1/TAL1 co-binding disruption at a CCND3 enhancer altering red blood cell count and volume.