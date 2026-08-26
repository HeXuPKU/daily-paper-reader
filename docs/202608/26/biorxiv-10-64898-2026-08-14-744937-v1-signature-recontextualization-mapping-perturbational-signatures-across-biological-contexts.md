---
title: "Signature Recontextualization: Mapping perturbational signatures across biological contexts"
title_zh: 签名重语境化：跨生物学环境映射扰动签名
authors: "Chen, A. D., Girke, T., Monti, S."
date: 2026-08-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.14.744937v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 提出跨背景扰动特征预测基准，为虚拟细胞模型生成提供评测标准
tldr: 扰动转录组学跨生物上下文预测扰动签名是一大挑战，限制了模型系统到临床组织的转化。为此提出一个“签名重新语境化”基准框架，定义三种目标数据覆盖场景（仅对照、低覆盖、高覆盖）。在CRISPR、药物及体内大鼠组织数据集上评估投影、网络传播与深度学习基础模型，发现投影和网络传播方法在多种任务中匹配或超过复杂模型，且预测效果受通路保守性和基线相似性影响。开源R包sigRecon提供基准和工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 跨上下文预测扰动签名缺乏统一基准，阻碍方法比较与临床转化。
method: 提出签名重新语境化基准，定义三种数据覆盖场景，评估多种投影、网络及深度学习模型。
result: 投影与网络传播方法表现灵活，在多数任务中匹配或超过深度学习和基础模型。
conclusion: 模型复杂度非关键，开源sigRecon支持可复现基准与后续开发。
---

## 摘要
扰动转录组学是理解基因功能和药物效应的强大工具，然而预测扰动在不同生物学环境中的表现仍然是一个核心挑战，限制了从模型系统到临床相关组织的转化。尽管对这一问题的兴趣日益增长，但基准测试工作一直受到评估任务不一致、指标异构以及跨扰动类型和生物系统评估有限的阻碍。在这里，我们引入了一个用于跨环境扰动签名预测（我们将其定义为签名重语境化任务）的基准框架，该框架基于预测任务、目标数据可用性以及以签名恢复为中心的评估指标的明确定义。该框架评估了三种目标环境数据模式下的预测性能：（1）仅对照，即仅测量来自目标环境的对照图谱；（2）低覆盖度，即测量目标环境中有限子集的扰动；（3）高覆盖度，即测量目标环境中的大多数扰动。这种设计能够系统评估预测性能如何依赖于目标环境样本量，同时为方法比较提供标准化基础。我们评估了新开发的基于投影的方法（projectCor）和基于网络的方法（netProp），以及基于深度学习的基座模型（scGPT、STACK）和统计基线。该基准涵盖四个不同的扰动数据集：细胞系中的CRISPR敲除和药物扰动，以及来自DrugMatrix的大鼠组织中的体内化学扰动，将评估从孤立的细胞系模型扩展到组织水平反应。在所有任务中，投影和网络传播方法在扰动类型和生物学环境上表现出很强的灵活性，并且在多种情况下匹配或超过了深度学习和基座模型的性能，表明模型复杂性并不固有地改善跨环境泛化。我们进一步表明，扰动的可预测性随通路保守性、转录反应强度以及源环境和目标环境之间的基线相似性而有显著变化。所有数据集、方法和评估工具均以开源R包（sigRecon）的形式发布，为可复现的基准测试和未来的方法开发提供了基础。

## Abstract
Perturbational transcriptomics is a powerful tool for understanding gene function and drug effects, yet predicting how perturbations manifest across different biological contexts remains a central challenge, limiting translation from model systems to clinically relevant tissues. Despite growing interest in this problem, benchmarking efforts have been hindered by inconsistent evaluation tasks, heterogeneous metrics, and limited assessment across perturbation types and biological systems. Here, we introduce a benchmarking framework for cross-context perturbation-signature prediction (a task we define as signature recontextualization), grounded in explicit definitions of the prediction task, target-data availability, and evaluation metrics centered on signature recovery. The framework evaluates prediction performance across three target-context data regimes: (1) control only, where only control profiles from the target context are measured; (2) low coverage, where a limited subset of perturbations in the target context are measured; and (3) high coverage, where most perturbations in the target context are measured. This design enables systematic assessment of how prediction performance depends on target-context sample size while providing a standardized basis for comparing methods. We evaluate newly developed projection-based (projectCor) and network-based (netProp) methods alongside deep learning-based foundation models (scGPT, STACK) and statistical baselines. The benchmark spans four diverse perturbational datasets: CRISPR knockdowns and drug perturbations in cell lines, plus in vivo chemical perturbations in rat tissues from DrugMatrix, extending evaluation beyond isolated cell-line models to tissue-level responses. Across tasks, projection and network propagation approaches show strong flexibility across perturbation types and biological contexts, and in several cases match or exceed the performance of deep learning and foundation models, suggesting that model complexity does not inherently improve cross-context generalization. We further show that perturbation predictability varies substantially with pathway conservation, transcriptional response strength, and baseline similarity between source and target contexts. All datasets, methods, and evaluation utilities are released as an open-source R package (sigRecon), providing a foundation for reproducible benchmarking and future method development.