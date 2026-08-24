---
title: "Signature Recontextualization: Mapping perturbational signatures across biological contexts"
title_zh: 特征重情境化：跨生物学情境映射扰动特征
authors: "Chen, A. D., Girke, T., Monti, S."
date: 2026-08-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.14.744937v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 跨情境扰动特征预测的基准框架，推动虚拟细胞模型的评测与构建。
tldr: 扰动转录组学中，预测扰动在不同生物上下文中的表现是核心挑战，但现有基准缺乏一致性。本文定义签名重情境化任务，提出统一基准框架，涵盖仅对照、低覆盖和高覆盖三种目标数据机制，并系统比较投影、网络传播及深度学习模型。结果表明projectCor和netProp等简单方法在多个数据集上可媲美甚至超越scGPT等基础模型，模型复杂度不必然提升跨上下文泛化。可预测性与通路保守性和响应强度相关。开源R包sigRecon提供可重复基准。
source: biorxiv
selection_source: fresh_fetch
motivation: 跨上下文扰动签名预测缺乏统一基准，导致方法比较不一致，阻碍从细胞系到组织等临床场景的转化。
method: 提出签名重情境化基准，含仅对照、低覆盖和高覆盖三种数据机制，评估projectCor、netProp、scGPT及STACK等方法。
result: 投影和网络传播方法灵活强大，多场景匹敌或超越深度模型；可预测性受通路保守性和响应强度影响。
conclusion: 发布开源R包sigRecon，提供标准化评估工具，表明模型复杂度不必然提升跨上下文泛化。
---

## 摘要
扰动转录组学是理解基因功能和药物效应的强大工具，然而预测扰动在不同生物学情境中的表现仍然是一个核心挑战，限制了从模型系统向临床相关组织的转化。尽管对该问题的兴趣日益增长，但基准测试工作一直受到不一致的评估任务、异构指标以及跨扰动类型和生物系统评估有限的阻碍。在此，我们引入了一个跨情境扰动特征预测的基准测试框架（我们将该任务定义为“特征重情境化”），该框架基于预测任务、目标数据可用性的明确定义以及以特征恢复为中心的评估指标。该框架评估了三种目标情境数据模式下的预测性能：（1）仅有对照，即仅测量目标情境中的对照谱；（2）低覆盖度，即测量目标情境中有限子集的扰动；（3）高覆盖度，即测量目标情境中的大多数扰动。这种设计能够系统评估预测性能如何依赖于目标情境样本量，同时为比较方法提供标准化基础。我们评估了新开发的基于投影（projectCor）和基于网络（netProp）的方法，以及基于深度学习的基座模型（scGPT、STACK）和统计基线。该基准测试涵盖四个多样化的扰动数据集：细胞系中的CRISPR敲除和药物扰动，以及来自DrugMatrix的大鼠组织体内化学扰动，将评估从孤立的细胞系模型扩展到组织水平反应。在各种任务中，投影和网络传播方法在扰动类型和生物学情境中表现出强大的灵活性，并且在多种情况下达到或超过深度学习及基座模型的性能，这表明模型复杂性本身并不能改善跨情境泛化。我们进一步表明，扰动可预测性随通路保守性、转录反应强度以及源情境和目标情境之间的基线相似性而有显著变化。所有数据集、方法和评估工具均以开源R包（sigRecon）形式发布，为可重复的基准测试和未来方法开发提供了基础。

## Abstract
Perturbational transcriptomics is a powerful tool for understanding gene function and drug effects, yet predicting how perturbations manifest across different biological contexts remains a central challenge, limiting translation from model systems to clinically relevant tissues. Despite growing interest in this problem, benchmarking efforts have been hindered by inconsistent evaluation tasks, heterogeneous metrics, and limited assessment across perturbation types and biological systems. Here, we introduce a benchmarking framework for cross-context perturbation-signature prediction (a task we define as signature recontextualization), grounded in explicit definitions of the prediction task, target-data availability, and evaluation metrics centered on signature recovery. The framework evaluates prediction performance across three target-context data regimes: (1) control only, where only control profiles from the target context are measured; (2) low coverage, where a limited subset of perturbations in the target context are measured; and (3) high coverage, where most perturbations in the target context are measured. This design enables systematic assessment of how prediction performance depends on target-context sample size while providing a standardized basis for comparing methods. We evaluate newly developed projection-based (projectCor) and network-based (netProp) methods alongside deep learning-based foundation models (scGPT, STACK) and statistical baselines. The benchmark spans four diverse perturbational datasets: CRISPR knockdowns and drug perturbations in cell lines, plus in vivo chemical perturbations in rat tissues from DrugMatrix, extending evaluation beyond isolated cell-line models to tissue-level responses. Across tasks, projection and network propagation approaches show strong flexibility across perturbation types and biological contexts, and in several cases match or exceed the performance of deep learning and foundation models, suggesting that model complexity does not inherently improve cross-context generalization. We further show that perturbation predictability varies substantially with pathway conservation, transcriptional response strength, and baseline similarity between source and target contexts. All datasets, methods, and evaluation utilities are released as an open-source R package (sigRecon), providing a foundation for reproducible benchmarking and future method development.