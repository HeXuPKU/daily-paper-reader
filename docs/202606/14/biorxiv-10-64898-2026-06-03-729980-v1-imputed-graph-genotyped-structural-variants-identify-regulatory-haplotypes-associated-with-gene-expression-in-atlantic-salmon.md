---
title: Imputed graph-genotyped structural variants identify regulatory haplotypes associated with gene expression in Atlantic salmon
title_zh: 基于归因的图谱基因分型结构变异鉴定与大西洋鲑基因表达相关的调控单倍型
authors: "Chapis, M., Manousi, D., Diblasi, C., Brekke, C., Kwak, J., Ponce De Leon, A. V., Arnyasi, M., Fenstad, R., Boison, S., Saitou, M."
date: 2026-06-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729980v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 在eQTL分析中使用插补的结构变异，与整合功能基因组学和GWAS相关
tldr: 结构变异(SV)影响基因调控但难以纳入eQTL分析。本文以大西洋鲑为模型，利用长读长和短读长测序发现SV，通过图基因分型联合定相，插补到SNP芯片基因分型的RNA-seq队列中。获得10万余个SV，鉴定出51个SV-eQTL候选，其中短读补充可恢复长读长遗漏的调控SV。结果表明，插补的图基因分型SV能揭示SNP标记无法捕获的调控单倍型。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有eQTL研究依赖SNP标记，难以解析结构变异对基因表达的影响，尤其缺乏全基因组测序的非模式生物。
method: 基于长读长和短读长测序发现SV，利用图基因分型联合定相，将SV插补到SNP芯片基因分型的RNA-seq队列。
result: "获得100,269个插补SV，鉴定出51个SV-eQTL候选，短读来源SV富集，且某些SV不能被近端SNP完美标记。"
conclusion: 插补的图基因分型SV可增加对调控单倍型的生物学解释，为eQTL研究提供结构变异视角。
---

## 摘要
结构变异（SV）可以影响基因调控，但当大规模RNA-seq队列缺乏全基因组测序时，很难将它们纳入表达遗传学研究。这在非人类和非模式系统中很常见，因为在这些系统中，群体规模的全基因组测序仍然成本高昂。因此，表达数量性状位点（eQTL）研究通常依赖于单核苷酸多态性（SNP）标记。这些分析可以识别与表达相关的区域，但往往对潜在的调控机制提供的生物学解释有限。在这里，我们以大西洋鲑为研究系统，测试了能否将图谱基因分型结构变异归因到SNP芯片基因分型的RNA-seq队列中，并用于解释调控单倍型。SV是从两个长读长测序个体中发现的，并辅以来自112个个体的全基因组测序参考面板的短读长SV和SNP调用，进行图谱基因分型，与SNP联合定相，并归因到906个具有鳃RNA-seq和SNP芯片基因型的后代中。经过大小过滤后，归因的SV目录包含100,269个变异，并显示出与性别特异性重组景观相关的非均匀基因组分布。关联测试鉴定出51个候选SV-eQTL，包括35个顺式和16个反式关联。这些候选者富含短读长来源的变异，表明短读长补充可以恢复小规模长读长发现所遗漏的调控变异。SV-eQTL候选者通常被附近的SNP更强烈地标记，但个体SNP先导标记在条件回归中往往无法捕获相同的eQTL信号。条件分析后保留的候选者包括目标基因重叠的缺失、附近不与目标基因重叠的局部变异、反式关联以及对基因表达有相反效应的短插入。这些结果表明，归因的图谱基因分型SV可以为可能的调控单倍型增加生物学解释。

## Abstract
Structural variants (SVs) can affect gene regulation, but they are difficult to include in expression genetic studies when large RNA-seq cohorts lack whole-genome sequencing. This is common in non-human and non-model systems, where whole-genome sequencing at population scale remains costly. As a result, expression quantitative trait locus (eQTL) studies often rely on single nucleotide polymorphism (SNP) markers. These analyses can identify expression-associated regions, but often provide limited biological interpretation of the underlying regulatory mechanisms. Here, we used Atlantic salmon as a study system to test whether graph-genotyped SVs can be imputed into a SNP-array-genotyped RNA-seq cohort and used to interpret regulatory haplotypes. SVs were discovered from two long-read-sequenced individuals, supplemented with short-read SV and SNP calls from a 112-individual whole-genome-sequenced reference panel, graph-genotyped, jointly phased with SNPs, and imputed into 906 offspring with gill RNA-seq and SNP-array genotypes. After size filtering, the imputed SV catalogue contained 100,269 variants and showed nonuniform genomic distributions associated with sex-specific recombination landscapes. Association testing identified 51 SV-eQTL candidates, including 35 cis and 16 trans associations. These candidates were enriched for short-read-derived variants, indicating that short-read supplementation can recover regulatory variants missed by small-scale long-read discovery. SV-eQTL candidates were more strongly tagged by nearby SNPs than non-associated variants generally, but individual SNP lead markers often failed to capture the same eQTL signals in conditional regression. Retained candidates after the conditional analysis included target-gene-overlapping deletions, nearby local variants without target-gene overlap, trans associations, and short insertions with opposite effects on gene expression. These results show that imputed graph-genotyped SVs can add biological interpretation to possible regulatory haplotypes.