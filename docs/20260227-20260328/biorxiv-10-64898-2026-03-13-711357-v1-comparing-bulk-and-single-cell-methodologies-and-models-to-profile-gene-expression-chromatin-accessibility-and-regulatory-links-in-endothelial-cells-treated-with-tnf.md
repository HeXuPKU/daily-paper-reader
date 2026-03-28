---
title: "Comparing bulk and single-cell methodologies and models to profile gene expression, chromatin accessibility and regulatory links in endothelial cells treated with TNFα"
title_zh: 比较 bulk 与单细胞方法及模型在分析 TNFα 处理的内皮细胞中基因表达、染色质可及性和调控联系方面的差异
authors: "Zevounou, J., Lo, K. S., McGinnis, C. S., Satpathy, A. T., Lettre, G."
date: 2026-03-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.13.711357v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 利用功能基因组学将因果非编码变异与基因联系起来
tldr: 本研究通过对比TNFα处理的人类内皮细胞在批量（bulk）和单细胞（sc）测序下的基因表达与染色质可及性，探讨了不同数据类型及预测模型对GWAS因果基因优先排序的影响。研究发现，尽管两种方法在生物学通路分析上具有一致性，但在预测增强子-基因调控连接时存在显著差异，如在冠状动脉疾病位点上预测出不同的候选基因。这强调了在功能实验设计中选择合适测序方法和模型的重要性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711357-v1/fig-001.webp\", \"caption\": \"\", \"page\": 23, \"index\": 1, \"width\": 662, \"height\": 552}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711357-v1/fig-002.webp\", \"caption\": \"\", \"page\": 25, \"index\": 2, \"width\": 612, \"height\": 792}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711357-v1/fig-003.webp\", \"caption\": \"\", \"page\": 27, \"index\": 3, \"width\": 612, \"height\": 792}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711357-v1/fig-004.webp\", \"caption\": \"\", \"page\": 29, \"index\": 4, \"width\": 673, \"height\": 847}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-13-711357-v1/fig-005.webp\", \"caption\": \"\", \"page\": 31, \"index\": 5, \"width\": 612, \"height\": 792}]"
motivation: 旨在评估使用批量或单细胞测序数据及其对应的预测模型是否会影响GWAS关联非编码变异中因果基因的识别。
method: 在TNFα处理的内皮细胞模型中，对比了批量和单细胞RNAseq/ATACseq数据，并应用ABC（批量）和scE2G（单细胞）模型预测调控连接。
result: 尽管两种方法揭示了相似的生物学通路，但在冠状动脉疾病等性状的遗传力捕获、精细定位变异及关联基因预测上存在明显分歧。
conclusion: 批量与单细胞方法的选择会显著影响调控连接模型的预测结果，在规划GWAS发现的功能验证实验时必须审慎考虑。
---

## 摘要
全基因组关联研究 (GWAS) 已鉴定出数千个与复杂性状和疾病相关的非编码变异。然而，精准定位受相关遗传变异调控的致病基因仍然具有挑战性。将致病性非编码变异与基因联系起来，可以依赖于识别直接物理相互作用的方法（如染色体构象捕获），或预测调控联系的概率模型。这些统计模型利用了通过 bulk 或单细胞 (sc) 方法在细胞和组织中生成的基因表达和染色质可及性图谱。在本研究中，我们测试了使用 bulk 或 sc RNAseq/ATACseq 数据以及相应的预测性增强子-基因模型是否会影响 GWAS 致病基因的优先级排序。我们以未经处理和 TNF 处理的体外人内皮细胞作为受控良好的实验系统，结果表明 bulk 和 sc RNAseq/ATACseq 图谱相似，并揭示了相同的生物学特征（如生物学通路）。尽管存在这些相似性，我们利用冠心病 (CAD) 和舒张压的 GWAS 结果表明，应用针对 bulk 或 sc 方法设计的增强子-基因模型，在捕获的遗传力、精细定位的变异和关联基因方面会产生差异。例如，在一个 CAD 位点，基于 bulk 的 ABC 模型预测了与 BCAR1 的调控联系，而基于 sc 的模型 scE2G 则优先排序了另一个基因 (CFDP1)。在相同的实验模型上，我们的结果表明，在 bulk 或 sc 方法之间进行选择会影响调控联系模型的预测；在规划功能实验以表征 GWAS 发现时，应考虑到这一点。

## Abstract
Genome-wide association studies (GWAS) have identified thousands of non-coding variants associated with complex traits and diseases. However, it remains challenging to pinpoint the causal genes that are regulated by associated genetic variants. Connecting causal non-coding variants with genes can rely on methods that identify direct physical interactions (e.g. chromosome conformation capture) or on probabilistic models that predict regulatory links. These statistical models take advantage of gene expression and chromatin accessibility profiles generated in cells and tissues by bulk or single-cell (sc) methodologies. Here, we tested whether using bulk or sc RNAseq/ATACseq data and corresponding predictive enhancer-to-gene models impact the prioritization of causal GWAS genes. Using non-treated and TNF-treated human endothelial cells in vitro as a well-controlled experimental system, we show that bulk and sc RNAseq/ATACseq profiles are similar and highlight the same biology (e.g. biological pathways). Despite these similarities, we show using GWAS results for coronary artery disease (CAD) and diastolic blood pressure that applying enhancer-to-gene models designed for bulk or sc methodologies can yield differences in terms of captured heritability, fine-mapped variants and linked genes. For instance, at one CAD locus, the bulk-based ABC model predicts a regulatory link with BCAR1, whereas the sc-based model scE2G prioritizes a different gene (CFDP1). On the same experimental model, our results indicate that choosing between a bulk or sc approach will influence regulatory link model predictions; this should be considered when planning functional experiments to characterize GWAS discoveries.