---
title: "PRISMA: A tensor-based framework for deconstructing the genetic architecture of complex diseases, with application to diabetic retinopathy"
title_zh: "PRISMA: 一种基于张量的复杂疾病遗传结构解构框架，应用于糖尿病视网膜病变"
authors: "Xiong, H., Xu, W., Ji, A., Zhong, L., Liu, S., Xie, Z., Yan, J., Wu, Z."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727382v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 基于张量的多基因风险评分整合框架，利用汇总统计和多组织分解
tldr: 针对复杂疾病GWAS汇总统计掩盖组织特异性遗传效应的问题，提出PRISMA框架。它利用图拉普拉斯正则化的块分解，整合GWAS与多组织cis-eQTL数据，在保留局部LD拓扑的同时分解出组织偏好的遗传轴。应用于糖尿病视网膜病变，识别出三个对应血管代谢、免疫炎症和视网膜神经退行性的遗传轴，并优先了549个靶点（含403个亚阈值靶点）。该框架将GWAS从聚集位点发现转向定量、LD感知的组织分辨率遗传轨迹分析。
source: biorxiv
selection_source: fresh_fetch
motivation: 复杂疾病GWAS的全局统计量掩盖了组织依赖的遗传异质性，需新方法解构局部调控路径。
method: PRISMA采用图拉普拉斯正则化块分解，联合GWAS汇总统计与多组织cis-eQTL数据，保留LD拓扑。
result: 在糖尿病视网膜病变中分解出三个遗传轴，识别549个靶点（403个亚阈值），经单细胞及蛋白质组验证。
conclusion: PRISMA提供了定量、LD感知的组织分辨率遗传轨迹映射，重定义了复杂疾病GWAS分析范式。
---

## 摘要
复杂疾病的全基因组关联研究将异质性、组织依赖的遗传效应压缩为全局位点水平统计量，掩盖了多基因风险贡献疾病结构的局部调控路径。本文提出PRISMA（基于汇总统计的多组织阵列分解的多基因风险整合），一种量化隐藏在聚合GWAS信号中的组织分辨遗传异质性的汇总统计框架。PRISMA使用图拉普拉斯正则化分块分解整合GWAS和多组织顺式eQTL数据，在分解过程中保留局部连锁不平衡拓扑结构。应用于糖尿病视网膜病变时，PRISMA将聚合的多基因风险解卷积为三个组织偏倚的遗传轴，分别对应于血管代谢、全身免疫炎症和视网膜特异性神经退行性轨迹。该框架优先识别了549个轴相关靶点，其中403个低于常规全基因组显著性阈值，并展示了比PCA、NMF和K-means更高的组织调控分辨率。身高GWAS阴性对照分析支持在共享eQTL可映射框架内依赖性状的调控重新优先化。独立单细胞转录组分析支持轴特异性富集于纤维血管、免疫和视网膜区室。探索性玻璃体液蛋白质组学和代谢组学分析进一步提名了下游汇聚的候选分子相关性。PRISMA将复杂疾病GWAS从聚合位点发现重新定向为定量、LD感知的组织分辨遗传轨迹映射。

## Abstract
Complex-disease GWAS compress heterogeneous, tissue-dependent genetic effects into global locus-level statistics, masking local regulatory routes through which polygenic risk contributes to disease architecture. Here we introduce PRISMA (Polygenic Risk Integration via Summary-statistics Multi-tissue Array-decomposition), a summary-statistics framework for quantifying tissue-resolved genetic heterogeneity hidden within aggregate GWAS signals. PRISMA integrates GWAS and multi-tissue cis-eQTL data using graph Laplacian-regularized block-wise factorization, preserving local linkage disequilibrium topology during decomposition. Applied to diabetic retinopathy, PRISMA deconvolved aggregated polygenic risk into three tissue-biased genetic axes corresponding to vascular-metabolic, systemic immune-inflammatory, and retina-specific neurodegenerative trajectories. The framework prioritized 549 axis-associated targets, including 403 below the conventional genome-wide significance threshold, and showed higher tissue-regulatory resolution than PCA, NMF, and K-means. A height GWAS negative-control analysis supported trait-dependent regulatory reprioritization within a shared eQTL-mappable framework. Independent single-cell transcriptomic analyses supported axis-specific enrichment across fibrovascular, immune, and retinal compartments. Exploratory vitreous humor proteomic and metabolomic profiling further nominated candidate molecular correlates of downstream convergence. PRISMA reframes complex-disease GWAS from aggregate locus discovery toward quantitative, LD-aware mapping of tissue-resolved genetic trajectories.

---

## 论文详细总结（自动生成）

# 论文详细总结：PRISMA: 一种基于张量的复杂疾病遗传结构解构框架，应用于糖尿病视网膜病变

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统复杂疾病全基因组关联研究将异质性、组织依赖的遗传效应压缩为全局位点水平统计量，掩盖了多基因风险贡献疾病结构的局部调控路径。现有方法无法定量解构GWAS汇总统计中隐藏的组织分辨遗传异质性。
- **研究动机**：需要一种新的计算框架，能够从聚合的GWAS信号中分离出组织特异性的遗传贡献，同时保留局部连锁不平衡拓扑信息，从而揭示疾病的多组织调控架构。
- **整体含义**：PRISMA将复杂疾病GWAS从聚合位点发现重新定向为定量、LD感知的组织分辨遗传轨迹映射，为理解复杂疾病的组织特异性遗传机制提供范式转变。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过图拉普拉斯正则化的块分解，整合GWAS汇总统计与多组织顺式eQTL数据，在分解过程中保留局部LD拓扑结构，从而将聚合的多基因风险解卷积为多个组织偏倚的遗传轴。
- **关键技术细节**：
  - 采用**图拉普拉斯正则化**约束分解过程，确保相邻变异（基于LD关系）在分解时具有相似的权重，保留局部LD拓扑。
  - 使用**块分解（block-wise factorization）**，将GWAS汇总统计量（Z分数或效应量）与多组织cis-eQTL效应矩阵联合分解，得到若干“遗传轴”。
  - 每个遗传轴对应一组组织偏好的SNP权重，反映该轴在特定组织中的调控贡献。
- **算法流程（文字描述）**：
  1. 输入：GWAS汇总统计（每个SNP的Z分数） + 多组织cis-eQTL数据（eQTL效应矩阵） + LD参考面板。
  2. 构建局部LD图（每个LD块内SNP之间的相关系数矩阵），并计算图拉普拉斯矩阵。
  3. 对每个LD块，执行图拉普拉斯正则化的矩阵分解，得到组织-轴权重和SNP-轴权重。
  4. 通过联合所有LD块的结果，获得全局的组织偏倚遗传轴。
  5. 输出：遗传轴权重、轴相关靶点（优先基因/位点）。

## 3. 实验设计：数据集、场景、基准与对比方法

- **主要应用场景**：糖尿病视网膜病变（Diabetic Retinopathy, DR）GWAS汇总统计。
- **使用的数据集**：
  - GWAS汇总统计：糖尿病视网膜病变相关的GWAS数据（具体来源未详细说明）。
  - 多组织cis-eQTL数据：来自GTEx或类似项目的多组织eQTL数据。
  - LD参考面板：1000 Genomes Project或类似。
  - 独立验证：单细胞转录组数据（纤维血管、免疫、视网膜区室）、玻璃体液蛋白质组学和代谢组学数据。
  - 阴性对照：身高GWAS汇总统计。
- **基准与对比方法**：
  - 对比方法：主成分分析（PCA）、非负矩阵分解（NMF）、K-means聚类。
  - 评价指标：组织调控分辨率（能否更好分离组织特异性遗传信号）。
- **实验充分性**：在DR中识别出三个遗传轴，并优先了549个轴相关靶点，其中403个低于全基因组显著性阈值；通过单细胞转录组验证轴特异性富集；通过玻璃体液蛋白质组和代谢组学提名下游分子相关性；身高GWAS阴性对照分析支持性状依赖的调控重新优先化。但未提供消融实验（如去掉图拉普拉斯正则化的影响）、不同初始化或超参数敏感性分析。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量或训练时长。仅提及是“汇总统计框架”，可能不需要大量GPU训练，但未提及任何算力信息。需要指出这一点。

## 5. 实验数量与充分性

- **实验数量**：
  - 主要实验：糖尿病视网膜病变应用，识别3个遗传轴，优先549个靶点。
  - 对比实验：与PCA、NMF、K-means比较，显示更高分辨率。
  - 阴性对照：身高GWAS分析。
  - 独立验证：单细胞转录组富集分析、玻璃体液蛋白质组/代谢组学分析。
- **充分性评价**：
  - **优点**：验证手段多样（独立细胞类型、蛋白质组、代谢组），有阴性对照。
  - **不足**：缺乏消融实验（如去除正则化项、改变LD块大小、不同eQTL来源）；未报告多次运行稳定性；仅在一个疾病（DR）和一个阴性对照（身高）上进行评估，外推性有限；未与其他多组织遗传分解方法（如Joint GWAS-eQTL、多性状分析）直接比较。

## 6. 论文的主要结论与发现

- PRISMA能成功将DR的聚合多基因风险解卷积为三个组织偏倚的遗传轴，分别对应：
  - 血管代谢轴
  - 全身免疫炎症轴
  - 视网膜特异性神经退行性轴
- 优先识别了549个轴相关靶点，其中403个低于常规全基因组显著性阈值，表明PRISMA能发现传统GWAS遗漏的候选基因。
- 相比PCA、NMF、K-means，PRISMA具有更高的组织调控分辨率。
- 身高GWAS阴性对照表明，在共享eQTL可映射框架内，PRISMA能实现依赖性状的调控重新优先化。
- 单细胞转录组支持轴特异性富集；玻璃体液组学提名下游分子相关性。
- 结论：PRISMA提供了一个定量、LD感知的组织分辨率遗传轨迹映射框架，重新定义了复杂疾病GWAS分析范式。

## 7. 优点：方法或实验设计上的亮点

- **方法亮点**：
  - 首次将图拉普拉斯正则化块分解应用于GWAS+多组织eQTL的整合，保留了局部LD拓扑，提高生物学可解释性。
  - 基于汇总统计，无需个体级数据，广泛适用。
  - 能发现全基因组显著性阈值之下的潜在靶点，拓展了GWAS的发现能力。
- **实验设计亮点**：
  - 多维度验证：单细胞转录组、蛋白质组、代谢组、阴性对照，形成证据链。
  - 与经典无监督方法（PCA、NMF、K-means）比较，凸显方法的优越性。

## 8. 不足与局限

- **实验覆盖有限**：
  - 只在一个疾病（糖尿病视网膜病变）和一个阴性对照（身高）上展示，未推广到其他复杂疾病。
  - 缺乏消融实验（如评估不同正则化强度、不同LD块划分策略的影响）。
  - 未与最新多组织分解方法（如TensorQTL、JointMIMBLA、多组织eQTL共定位）进行基准比较。
- **偏差风险**：
  - eQTL数据来源可能引入组织覆盖偏差（如GTEx某些组织样本量小）。
  - GWAS汇总统计本身可能存在群体分层或其他偏倚，PRISMA无法纠正。
- **应用限制**：
  - 依赖cis-eQTL可映射性，非编码调控区域或稀有变异可能无法充分捕获。
  - 需要LD参考面板，且LD块划分可能影响结果稳定性。
  - 结果解释需要领域知识（组织轴对应病理过程仍需实验验证）。
- **可重复性**：未提供代码或详细超参数设置，限制复现。

（完）
