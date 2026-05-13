---
title: "CLCNet: a contrastive learning and chromosome-aware network for genomic prediction in plants"
title_zh: CLCNet：一种用于植物基因组预测的对比学习与染色体感知网络
authors: "Huang, J., Yang, Z., Yin, M., Li, C., Li, J., Wang, Y., Huang, L., Li, M., Liang, C., He, F., Han, R., Jiang, Y."
date: 2026-05-10
pdf: "https://www.biorxiv.org/content/10.1101/2024.12.29.630569v7.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 使用SNP进行基因组预测的深度学习框架
tldr: 基因组预测（GP）在植物育种中至关重要，但面临高维特征和样本量不足的挑战。本文提出CLCNet，一种结合对比学习与染色体感知特征建模的深度学习框架。该模型通过对比学习捕捉个体间细微的基因型-表型差异，并利用染色体感知模块提取关键SNP。在四种作物、十种性状上的实验表明，CLCNet在预测准确率（PCC）上显著优于传统模型，尤其在高中等遗传力性状中表现突出，为植物基因组选择提供了高效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对基因组预测中SNP维度远超样本量以及难以捕捉个体间细微变异的问题，旨在提高预测准确性。
method: 提出CLCNet框架，集成对比学习模块以增强表征稳定性，并利用染色体感知模块进行跨染色体的结构化特征选择。
result: "在玉米、油菜、大豆和棉花等作物的多种性状预测中，CLCNet的皮尔逊相关系数比基准模型提升了0.34%至12.19%。"
conclusion: CLCNet通过整合基因组结构信息和对比学习，有效提升了高维小样本条件下的基因组预测性能，具有广阔的育种应用前景。
---

## 摘要
基因组选择（GS）利用全基因组标记和表型来预测育种值，其有效性在很大程度上取决于基因组预测（GP）模型的准确性。然而，GP 方法通常难以捕捉个体间的变异，并受限于维度灾难，即单核苷酸多态性（SNP）的数量远超样本量。为了应对这些挑战，我们提出了 CLCNet（对比学习与染色体感知网络），这是一种整合了对比学习和染色体感知特征建模的新型深度学习框架。CLCNet 包含两个关键组件：(i) 对比学习模块，增强了模型捕捉个体间细粒度、依赖于基因型的表型差异的能力；(ii) 染色体感知模块，在染色体和基因组层面捕捉结构化特征选择，从而提取最具信息量的 SNP。我们在四种作物物种上评估了 CLCNet，涵盖了十个重要的农艺性状，并将其与多种经典的线性模型、机器学习模型和深度学习模型进行了比较。CLCNet 取得了优异的预测性能，皮尔逊相关系数（PCC）较基准模型有显著提高，增幅在 0.34% 到 12.19% 之间，同时降低了均方误差（MSE）。对于具有中等连锁不平衡（LD；r2 = 0.21-0.36）和高遗传力（h2 > 0.66）的性状（如玉米、油菜和大豆中的性状），性能提升更为显著。对于具有高 LD（r2 = 0.74）和较低遗传力（h2 < 0.50）的棉花性状，CLCNet 保持了稳健的性能而没有下降。总之，这些结果表明 CLCNet 是提高基因组预测准确性的有效框架，在植物育种的实际应用中具有巨大潜力。

简短摘要：CLCNet 是一种用于基因组预测的新型深度学习框架，它将对比学习与染色体感知特征选择相结合。通过对个体间基因型-表型变异和染色体基因组结构进行联合建模，CLCNet 提高了在高维、小样本条件下的预测准确性。在四种作物物种和十个农艺性状中，CLCNet 的表现始终优于经典的统计模型、机器学习模型和现有的深度学习模型。该框架还识别出了生物学相关的 SNP 和候选基因，展示了其在基因组选择和计算植物育种中实际应用的潜力。

关键点：
1. 我们提出了 CLCNet，这是一个多任务深度学习框架，在高维、小样本条件下，将对比学习与染色体感知

## Abstract
Genomic selection (GS) leverages genome-wide markers and phenotypes to predict breeding values, with its effectiveness largely dependent on the accuracy of genomic prediction (GP) models. However, GP methods often struggle to capture inter-individual variability and are limited by the curse of dimensionality, where the number of SNPs far exceeds the sample size. To address these challenges, we present CLCNet (Contrastive Learning and Chromosome-aware Network), a novel deep learning framework that integrates contrastive learning and chromosome-aware feature modeling. CLCNet comprises two key components: (i) a contrastive learning module that enhances the models ability to capture fine-grained, genotype-dependent phenotypic differences among individuals, and (ii) a chromosome-aware module that captures structured feature selection at both chromosome and genome levels, thereby distilling the most informative SNPs. We evaluated CLCNet across four crop species, covering ten agronomically important traits, and compared it with a diverse set of classical linear, machine learning, and deep learning models. CLCNet achieved superior prediction performance, with statistically significant improvements in Pearson correlation coefficient (PCC), ranging from 0.34% to 12.19% over baseline, together with reduced mean squared error (MSE). Performance gains were more pronounced for traits with moderate linkage disequilibrium (LD; r2 = 0.21-0.36) and high heritability (h2 > 0.66), such as those in maize, rapeseed, and soybean. For cotton traits characterized by high LD (r2 = 0.74) and lower heritability (h2 < 0.50), CLCNet maintained robust performance without degradation. Overall, these results demonstrate that CLCNet is an effective framework for improving genomic prediction accuracy and holds strong potential for practical applications in plant breeding.

Short abstractCLCNet is a novel deep learning framework for genomic prediction that integrates contrastive learning with chromosome-aware feature selection. By jointly modeling inter-individual genotype-phenotype variation and chromosomal genomic structure, CLCNet improves prediction accuracy under high-dimensional, low-sample-size conditions. Across four crop species and ten agronomic traits, CLCNet consistently outperformed classical statistical, machine learning, and existing deep learning models. The framework also identified biologically relevant SNPs and candidate genes, demonstrating its potential for practical applications in genomic selection and computational plant breeding.

Key pointsO_LIWe propose CLCNet, a multi-task deep learning framework that integrates contrastive learning with chromosome-aware feature selection for genomic prediction, under high-dimensional, low-sample-size conditions.
C_LIO_LIThe chromosome-aware module explicitly exploits genomic structural information to select representative and informative SNPs across chromosomes.
C_LIO_LIContrastive learning improves model robustness by stabilizing representation learning and reducing the influence of random effects across samples.
C_LIO_LIBy complementing GWAS analyses, CLCNet provides additional insights into genotype-phenotype relationships with potential relevance for gene discovery.
C_LI

Biographical NoteJiangwei Huang is a PhD candidate at the Institute of Genetics and Developmental Biology, Chinese Academy of Sciences. His research focuses on genomic prediction, deep learning, and computational plant breeding.

Zhihan Yang is a PhD candidate at the Institute of Genetics and Developmental Biology, Chinese Academy of Sciences. Her research interests include genomic prediction and bioinformatics.

Rongcheng Han is an associate professor at the Institute of Genetics and Developmental Biology, Chinese Academy of Sciences. His research focuses on bioinformatics and plant phenomics.

Yuqiang Jiang is a professor at the Institute of Genetics and Developmental Biology, Chinese Academy of Sciences. His research interests include plant genomics, plant phenomics and genetic improvement.

Organization descriptionThe Institute of Genetics and Developmental Biology, Chinese Academy of Sciences, is a leading research institute focusing on genetics, genomics, molecular breeding, bioinformatics, and systems biology in plants and animals.