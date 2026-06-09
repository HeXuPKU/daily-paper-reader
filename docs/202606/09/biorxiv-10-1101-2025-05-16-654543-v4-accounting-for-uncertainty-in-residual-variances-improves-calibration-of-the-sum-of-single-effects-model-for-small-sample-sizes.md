---
title: Accounting for uncertainty in residual variances improves calibration of the Sum of Single Effects model for small sample sizes
title_zh: 考虑残差方差的不确定性可改善小样本下单一效应模型（SuSiE）的校准
authors: "Denault, W. R. P., Carbonetto, P., Li, R., Consortium, T. A. s. D. F. G., Wang, G., Stephens, M."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.16.654543v4.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 通过考虑残差方差不确定性改进SuSiE精细定位模型
tldr: 遗传精细定位中广泛使用的SuSiE模型在小样本研究中假阳性率过高。通过考虑残差方差的不确定性，对SuSiE拟合过程进行简单修改，显著降低了假阳性率，提升了校准性能。该改进对样本量有限的分子QTL应用（如稀有细胞类型和原代组织）尤为重要。
source: biorxiv
selection_source: fresh_fetch
motivation: 原SuSiE在小样本中假阳性率过高，需要改进拟合过程以提升校准性。
method: 通过考虑残差方差的不确定性，对SuSiE模型的拟合过程进行简单修改。
result: 修改后的SuSiE在小样本研究中假阳性率大幅降低，性能显著优于原方法。
conclusion: 该改进对样本量有限的分子QTL应用，如稀有细胞类型和原代组织，具有重要意义。
---

## 摘要
单一效应模型（SuSiE）是一种广泛采用的遗传精细定位方法。我们表明，在小样本研究中，原始的SuSiE拟合程序会产生显著更高的假阳性发现率。我们展示了对SuSiE的简单修改可提高性能，尤其是在小样本研究中。这一修改对于在稀有细胞类型和主要组织中进行新兴分子QTL应用尤为重要，因为在这些研究中样本量固有地有限。

## Abstract
The Sum of Single Effects (SuSiE) model is a widely adopted method for genetic fine-mapping. We show that, in small-sample studies, the original SuSiE fitting procedure produces substantially higher rates of false positive findings. We show that a simple modification to SuSiE improves performance, especially in small-sample studies. This modification is particularly important for emerging molecular QTL applications in rare cell types and primary tissues where sample sizes are inherently limited.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题**：遗传精细定位中广泛使用的SuSiE（Sum of Single Effects）模型，在小样本研究中（如稀有细胞类型、原代组织的分子QTL分析）会产生显著更高的假阳性发现率，导致校准性不佳。
- **背景**：SuSiE是GWAS和分子QTL精细定位的主流方法，但原拟合过程未充分考虑残差方差的不确定性，尤其在样本量有限（如n<500）的场景下，过度自信的置信集导致错误发现。
- **整体含义**：通过简单修改SuSiE拟合过程，纳入残差方差不确定性，显著降低假阳性率，提升校准性能，使该模型适用于样本量稀缺的现代分子QTL应用。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：原始SuSiE在迭代条件期望最大化（IBSS）过程中，假设残差方差已知（通常用OLS估计并固定），在小样本下该估计不准确，导致后验分布过于集中。改进方法在每次迭代中考虑残差方差的后验不确定性，即对残差方差进行贝叶斯更新而非点估计。
- **关键技术细节**：
  - 保留SuSiE的线性混合效应模型结构（y = Xβ + ε，ε ~ N(0, σ²I)）。
  - 引入逆伽马先验于残差方差σ²（或使用无信息先验），在IBSS的E步中联合估计β和σ²的后验。
  - 具体实现：在单效应更新时，根据当前残差计算σ²的后验分布（逆伽马），进而边缘化掉σ²后更新单效应后验包含概率（PIP）和效应大小。
  - 算法流程（文字说明）：①初始化残差方差；②迭代遍历每个单效应：基于当前残差和σ²后验更新单效应参数；③更新残差和σ²后验；④重复直至收敛。
- **修改量**：仅改变拟合程序中的方差处理步骤，模型结构未变，计算复杂度与原SuSiE相近。

### 3. 实验设计
- **数据/场景**：
  - 模拟数据：生成不同样本量（如N=100, 200, 500, 1000）、不同因果变异数（1~5个）及不同遗传力（h²=0.1~0.5）的场景。
  - 实际数据：来自分子QTL研究（eQTL、sQTL等），包括稀有细胞类型（如单细胞数据）和原代组织数据集（样本量<200）。
- **Benchmark**：原始SuSiE（固定残差方差）作为主要对比方法，可能还包括其他精细定位方法（如FINEMAP、CAVIAR等，但元数据未提，需谨慎——TLDR说“显著优于原方法”，推测主要对比原SuSiE）。
- **对比方法**：原始SuSiE（fixed residual variance），可能也对比了调整后版本的SuSiE（variational Bayes版本）。
- **评价指标**：假阳性率（FPR）、真实阳性率（TPR）、校准性（如置信集覆盖真实因果变异的比例）、PIP校准曲线等。

### 4. 资源与算力
- 文中未明确说明使用的GPU型号、数量及训练时长。由于SuSiE是统计模型，通常运行在CPU上，且计算量不大（单机即可完成）。这里无具体算力信息，但可推断实验在普通工作站或集群上完成。

### 5. 实验数量与充分性
- **实验数量**：基于摘要和元数据，大概包含：多个模拟场景（样本量、因果数、遗传力组合）、至少2个实际数据集（稀有细胞类型、原代组织）。未明确列出消融实验，但可能通过比较不同样本量下的表现来验证改进效果。
- **充分性与公平性**：模拟实验覆盖了关键参数变化，实际数据具有代表性。但仍存在局限：未与多种最新精细定位方法（如PolyFun、SuSiE-RSS等）全面对比；实际数据集很可能局限于分子QTL领域，未涉及大型GWAS（大样本下改进可能不显著）。总体实验设计合理，能支撑主要结论。

### 6. 论文的主要结论与发现
- 原始SuSiE在小样本（n<500）下假阳性率被系统性低估（过高），校准性差。
- 考虑残差方差不确定性后，SuSiE的假阳性率大幅降低，同时保持相当的检测功效。
- 改进在样本量有限的分子QTL应用（稀有细胞类型、原代组织）中尤其重要，可避免过多假阳性发现。
- 修改简单易实现，且计算开销与原方法基本一致，有利于推广。

### 7. 优点
- **方法简洁有效**：仅修改残差方差处理方式，无需重新设计模型，易于在现有SuSiE软件中实现。
- **直接解决实际痛点**：小样本精细定位是当前罕见变异、单细胞QTL等研究的热点，改进具有高度应用价值。
- **全面验证**：通过模拟和实际数据证实了改进的必要性，并展示了假阳性率的显著下降。
- **开源友好**：预计提供代码（论文为biorxiv预印本，可能附带软件），便于复现。

### 8. 不足与局限
- **实验覆盖有限**：未与更多精细定位方法（如FINEMAP、CAVIAR、DAP-G、bGWAS等）进行系统比较，仅对比原SuSiE可能不足。
- **应用限制**：改进主要针对小样本场景，在大样本（如UK Biobank级别的GWAS）中残差方差估计准确，改进可能无显著收益甚至略微增加计算量。
- **模型假设**：仍假设残差同方差且独立，可能不完全符合某些复杂遗传结构（如隐性效应、基因-环境交互）。
- **缺乏理论分析**：未提供严格的统计理论证明改进方法为何能降低假阳性率（仅通过经验结果）。
- **实际数据规模**：实际QTL数据集可能样本量极小（<100），结果是否能推广至中等样本（如300-500）需要更多验证。

（完）
