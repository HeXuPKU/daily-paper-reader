---
title: Multivariate Random Forests for Cross-Modal Multi-Omics Integration
title_zh: 用于跨模态多组学整合的多元随机森林
authors: "Zhang, W., Wang, L., Franzmann, E. J., Chen, X. S."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.732933v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 用于功能基因组学整合的多组学方法
tldr: 多组学数据中共享与模态特异性信号并存，现有整合方法常强制融合或依赖线性假设。为此提出multiRF，基于多元随机森林学习跨组学样本相似性，分解为共享与残差部分。模拟实验表明其恢复共享聚类优于或持平现有方法，在TCGA头颈癌和ADNI数据中共享成分对齐已知亚型，特异性信号揭示额外生物学信息。该方法以开源R包形式发布。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有多组学整合方法难以处理非线性关系，且无法同时分离共享与模态特异性信号。
method: multiRF利用多元随机森林学习每层组学的样本相似性，融合后分解为可预测的共享成分和残差的模态特异性成分。
result: 模拟中恢复共享聚类优于现有方法；真实数据共享成分对齐已知亚型，特异性成分揭示免疫、发育及甲基化特异信号。
conclusion: multiRF有效分离多组学共享与特异性信号，适用于非线性复杂数据，已提供开源R包。
---

## 摘要
多组学研究广泛应用于生物医学研究的许多领域。在许多疾病中，一些信号在不同数据类型间共享，而另一些则在单一组学层中最强。当前的多组学聚类方法通常要么将所有数据类型合并为单一表示，这可能会模糊在某一层中较强的生物学特征，要么依赖于可能无法捕捉跨数据类型复杂关系的线性结构。我们引入了multiRF，一种基于随机森林的方法，处理复杂数据类型并分离多组学数据中的共享和模态特异性结构。multiRF从多元随机森林中学习跨组学层的样本相似性，跨数据类型合并这些相似性，并利用得到的权重估计每个组学层中可由其他层预测的部分。剩余的残差被视为模态特异性信号，允许分别聚类共享和模态特异性相似性。在模拟中，multiRF恢复共享聚类的效果与已建立的整合方法相当或更好，同时在非线性数据结构下更可靠地分离模态特异性信号。在TCGA头颈部鳞状细胞癌中，共享组分与已建立的参考分类中的主要亚型结构一致，而基因和miRNA特异性组分揭示了额外的免疫和发育生物学。在具有匹配血液DNA甲基化和结构MRI的ADNI队列中，共享的跨模态老化信号与未来转化为轻度认知障碍或阿尔茨海默病相关，而DNAm特异性残差信号显示出探索性的额外信息。这些结果表明，multiRF可以恢复共同的疾病轴，同时保留特定于一种数据类型的生物学意义信号。multiRF作为开源R包可在https://github.com/novawz/multiRF获得。

## Abstract
Multi-omics studies are widely used across many areas of biomedical research. In many diseases, some signals are shared across data types, while others are strongest in a single omics layer. Current multi-omics clustering methods often either merge all data types into a single representation, which can blur biology that is strong in one layer, or rely on linear structure that may miss more complex relationships across data types. We introduce multiRF, a random-forest-based method that handles complex data types and separates shared and modality-specific structure for multi-omics data. multiRF learns sample similarities across omics layers from multivariate random forests, combines them across data types, and uses the resulting weights to estimate the part of each omics layer that is predictable from the others. The remaining residual is treated as modality-specific signal, allowing shared and modality-specific similarities to be clustered separately. In simulations, multiRF recovered shared clusters as well as or better than established integrative methods while more reliably separating modality-specific signal under nonlinear data structures. In TCGA head and neck squamous cell carcinoma, the shared component aligned with the main subtype structure across established reference classifications, while gene- and miRNA-specific components revealed additional immune and developmental biology. In the ADNI cohort with matched blood DNA methylation and structural MRI, the shared cross-modal aging signal was associated with future conversion to mild cognitive impairment or Alzheimer's disease, and a DNAm-specific residual signal showed exploratory additional information. These results show that multiRF can recover a common disease axis while retaining biologically meaningful signals specific to one data type. multiRF is available as an open-source R package at https://github.com/novawz/multiRF.