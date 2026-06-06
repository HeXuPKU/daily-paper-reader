---
title: The machine-learning classifier ALLCatchR2 identifies 20 T-ALL subtypes across cohorts and age groups
title_zh: 机器学习分类器ALLCatchR2识别跨队列和年龄组的20种T-ALL亚型
authors: "Beder, T., Wolgast, N., Walter, W., Bendig, S., Hartmann, A. M., Barz, M. J., Zaliova, M., Reitzel, E., Baden, D., Schwartz, S. M., Gökbuget, N., Kester, L., Trka, J., Haferlach, C., Brüggemann, M., Baldus, C. D., Neumann, M., Bastian, L."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.01.697268v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 机器学习分类器用于T-ALL亚型识别，属于基因组学中的机器学习应用
tldr: "T细胞急性淋巴细胞白血病（T-ALL）的分子亚型缺乏统一定义。通过整合2314个转录组（15个队列，年龄0.8-90.8岁），采用无监督聚类定义20个亚型，并开发机器学习分类器ALLCatchR2，在验证集准确率达0.995-1.0。发现一个与克隆造血突变（IDH2 R140Q、DNMT3A）富集的新亚型，在>50岁患者中占39.5%。该工作以免费R包形式开放，实现基因表达亚型、发育阶段标注和母细胞比例估计，为T-ALL分类标准化提供工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: T-ALL分子亚型缺乏跨队列验证和操作性基因表达定义，阻碍临床统一分类。
method: 整合15个队列2314个转录组，通过无监督聚类定义17个主簇和3个子簇，监督分析补充未成熟T-ALL定义，并基于ALLCatchR构建机器学习分类器。
result: "识别20个转录组亚型及未成熟T-ALL特征，验证集准确率0.995-1.0；发现新克隆造血相关亚型（IDH2 R140Q、DNMT3A），在>50岁患者中占39.5%。"
conclusion: ALLCatchR2作为免费R包，能统一T-ALL谱系区分、亚型分类和发育注释，适用于不同年龄和队列。
---

## 摘要
T细胞急性淋巴细胞白血病（T-ALL）包含分子多样性的亚型，但缺乏稳健的跨队列验证和可操作的基因表达定义。为了建立基于基因表达的T-ALL分型框架，我们汇集了2,314个转录组（15个队列，年龄范围：0.8至90.8岁）。一种扩展的无监督方法在原始细胞比例高的样本中定义了17个主要聚类和3个亚聚类。有监督分析增加了总括性的未成熟T-ALL（ETP样）定义，并解析了LMO2{gamma}{delta}样亚型。所有聚类均包含来自至少两个队列的样本。特征性基因组驱动因子的富集在各队列间一致，而基因表达聚类不仅对应单一的驱动事件，还反映了发育起源。基于我们B-ALL分类器ALLCatchR的机器学习分类器，在验证集（n=203）中以0.995-1.0的准确率识别了这20种转录组亚型和未成熟T-ALL（ETP样）特征。在第二个保留数据集（n=265个样本）上测试该分类器，结果显示92.7%的预测与相应的驱动改变匹配。在所有样本中，83.2%的病例获得高置信度预测，7.3%为候选预测，9.5%未被分类，主要原因是原始细胞比例低。我们发现了一个新的基因表达聚类，显著富集（P<0.001）克隆性造血突变（IDH2 R140Q、DNMT3A）和干/祖细胞样基因表达。这种新的克隆性造血相关T-ALL亚型在六个队列中被观察到，占成人的8.9%和年龄>50岁患者的39.5%。我们改进了ALLCatchR，作为一个免费的R包，现在能够实现B/T谱系分离、基因表达分型、原始细胞估计和发育注释，以协调跨研究和临床背景的T-ALL分类。

## Abstract
T-cell acute lymphoblastic leukemia (T-ALL) comprises molecularly diverse subtypes, but robust cross-cohort validations and operational gene-expression definitions are lacking. To establish a gene-expression-anchored framework for T-ALL subtyping, we aggregated 2,314 transcriptomes (15 cohorts, age: 0.8 to 90.8 years). An extended unsupervised approach defined 17 main clusters and 3 subclusters in samples with high blast fractions. Supervised analyses added an overarching immature T-ALL (ETP-like) definition and resolved the LMO2{gamma}{delta} -like subtype. All clusters contained samples from at least two cohorts. Characteristic genomic driver enrichments were consistent across cohorts, while gene expression clusters did not correspond exclusively to single driver events but also reflected developmental origins. A machine learning classifier based on ALLCatchR, our B-ALL classifier, identified these 20 transcriptomic subtypes and the immature T-ALL (ETP-like) signature with 0.995-1.0 accuracy in a validation set (n=203). Testing the classifier on a second hold-out data set (n=265 samples) showed that 92.7% of predictions matched with corresponding driver alterations. Across all samples, 83.2% of cases received high-confidence predictions, 7.3% candidate predictions, and 9.5% remained unclassified, largely because of low blast fractions. We identified a novel gene expression cluster markedly enriched (P<0.001) for clonal hematopoiesis mutations (IDH2 R140Q, DNMT3A) and a stem-/progenitor cell-like gene expression. This novel  clonal hematopoiesis-related T-ALL subtype was observed in six cohorts representing 8.9% of adults and 39.5% of patients aged >50 years. We advanced ALLCatchR, as a free R package that now enables B-/T-lineage separation, gene-expression subtyping, blast estimation, and developmental annotation to harmonize T-ALL classification across studies and clinical contexts.

Key PointsO_LIEstablished using 2,314 T-ALL transcriptomes, ALLCatchR2 assigns 20 RNA-Seq subtypes and their developmental underpinnings across ages.
C_LIO_LIClonal hematopoiesis-related T-ALL (DNMT3A, IDH2 R140Q) defines an immature gene-expression cluster in [~]40% of patients aged >50 years.
C_LI