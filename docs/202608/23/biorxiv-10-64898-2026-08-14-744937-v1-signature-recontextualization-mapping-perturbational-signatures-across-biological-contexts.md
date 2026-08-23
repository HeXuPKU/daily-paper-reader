---
title: "Signature Recontextualization: Mapping perturbational signatures across biological contexts"
title_zh: 签名重构：跨生物学背景映射扰动签名
authors: "Chen, A. D., Girke, T., Monti, S."
date: 2026-08-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.14.744937v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 跨生物学背景扰动特征预测的基准框架，与虚拟细胞模型评估和基因组AI相关
tldr: 扰动转录组学在跨生物背景间预测基因扰动效应仍具挑战，缺乏统一评测基准。本文提出签名重构基准框架，按目标背景数据覆盖率分为仅对照、低覆盖和高覆盖三档，系统评估projectCor、netProp与深度学习模型。结果显示投影与网络传播方法在多种任务上灵活高效，部分超越基础模型，表明模型复杂度并不必然提升跨背景泛化。贡献包括标准化评测流程与开源R包sigRecon，为后续方法开发提供基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 跨生物背景预测扰动转录特征缺乏统一评测标准，现有任务和指标不一致。
method: 定义签名重构任务，按目标背景数据覆盖度划分三档，系统评估投影、网络传播与深度学习等方法。
result: 投影与网络传播方法性能接近或超过深度模型，预测可解释性受通路保守性、响应强度和基线相似性影响。
conclusion: 发布开源R包sigRecon，提供标准化基准和评估工具，促进跨背景泛化研究。
---

## 摘要
扰动转录组学是理解基因功能和药物效应的强大工具，然而预测扰动在不同生物学背景中的表现仍是一个核心挑战，限制了从模型系统向临床相关组织的转化。尽管对该问题的兴趣日益增长，基准测试工作一直受到评估任务不一致、指标异质性以及扰动类型和生物系统评估范围有限的阻碍。在此，我们引入了一个用于跨背景扰动签名预测（我们将此任务定义为签名重构）的基准框架，该框架基于预测任务、目标数据可用性以及以签名恢复为中心的评估指标的明确定义。该框架在三种目标背景数据模式下评估预测性能：（1）仅对照，即仅测量目标背景中的对照谱；（2）低覆盖度，即测量目标背景中有限子集的扰动；（3）高覆盖度，即测量目标背景中的大部分扰动。这种设计能够系统地评估预测性能如何依赖于目标背景样本量，同时为比较方法提供标准化基础。我们将新开发的基于投影（projectCor）和基于网络（netProp）的方法与基于深度学习的基座模型（scGPT、STACK）以及统计基线进行了评估。该基准涵盖四个多样化的扰动数据集：细胞系中的CRISPR敲除和药物扰动，以及来自DrugMatrix的大鼠组织体内化学扰动，将评估从分离的细胞系模型扩展到组织水平响应。在所有任务中，投影和网络传播方法在不同扰动类型和生物学背景下表现出很强的灵活性，并且在多种情况下匹配或超过了深度学习和基座模型的性能，这表明模型复杂性并不固有地提高跨背景泛化能力。我们还进一步表明，扰动的可预测性随通路保守性、转录响应强度以及源背景与目标背景之间的基线相似性而显著变化。所有数据集、方法和评估工具均以开源R包（sigRecon）的形式发布，为可重复的基准测试和未来方法开发提供了基础。

## Abstract
Perturbational transcriptomics is a powerful tool for understanding gene function and drug effects, yet predicting how perturbations manifest across different biological contexts remains a central challenge, limiting translation from model systems to clinically relevant tissues. Despite growing interest in this problem, benchmarking efforts have been hindered by inconsistent evaluation tasks, heterogeneous metrics, and limited assessment across perturbation types and biological systems. Here, we introduce a benchmarking framework for cross-context perturbation-signature prediction (a task we define as signature recontextualization), grounded in explicit definitions of the prediction task, target-data availability, and evaluation metrics centered on signature recovery. The framework evaluates prediction performance across three target-context data regimes: (1) control only, where only control profiles from the target context are measured; (2) low coverage, where a limited subset of perturbations in the target context are measured; and (3) high coverage, where most perturbations in the target context are measured. This design enables systematic assessment of how prediction performance depends on target-context sample size while providing a standardized basis for comparing methods. We evaluate newly developed projection-based (projectCor) and network-based (netProp) methods alongside deep learning-based foundation models (scGPT, STACK) and statistical baselines. The benchmark spans four diverse perturbational datasets: CRISPR knockdowns and drug perturbations in cell lines, plus in vivo chemical perturbations in rat tissues from DrugMatrix, extending evaluation beyond isolated cell-line models to tissue-level responses. Across tasks, projection and network propagation approaches show strong flexibility across perturbation types and biological contexts, and in several cases match or exceed the performance of deep learning and foundation models, suggesting that model complexity does not inherently improve cross-context generalization. We further show that perturbation predictability varies substantially with pathway conservation, transcriptional response strength, and baseline similarity between source and target contexts. All datasets, methods, and evaluation utilities are released as an open-source R package (sigRecon), providing a foundation for reproducible benchmarking and future method development.