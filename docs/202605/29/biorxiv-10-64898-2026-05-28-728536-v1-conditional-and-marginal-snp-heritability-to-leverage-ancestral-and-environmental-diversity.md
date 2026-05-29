---
title: Conditional and marginal SNP-heritability to leverage ancestral and environmental diversity
title_zh: 条件性和边际SNP遗传力：利用祖先和环境多样性
authors: "Singh Sachan, A. N., Schwartzman, A., Azriel, D."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728536v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 提出条件SNP遗传力方法用于GWAS
tldr: 传统SNP遗传力方法在多样性人群中仅估计单一边际值，忽略亚群间遗传与环境差异。本文提出条件SNP遗传力，可对应不同祖先与暴露估计多个遗传力，结合delta法和bootstrap计算标准误。模拟验证方法有效，在ABCD青少年数据中发现智力遗传力随社会经济群体变化，与文献一致。该条件估计为理解亚群风险差异提供了新工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法在多样性数据中只能估计单一遗传力，忽略了亚群间遗传与环境差异。
method: 提出条件SNP遗传力模型，估计不同祖先和环境下的多个遗传力，采用delta法和bootstrap计算标准误。
result: 模拟验证方法有效；在ABCD数据中显示智力遗传力随社会经济群体变化，与文献一致。
conclusion: 条件遗传力估计能利用数据异质性揭示亚群间风险差异。
---

## 摘要
SNP遗传力被定义为在全基因组关联研究中由SNP解释的性状方差的比例。已有多种方法被提出用于估计该量。最近的方法旨在利用祖先多样性数据集，但仍为整个数据集获得单一遗传力，我们称之为边际遗传力。然而，构成遗传多样性数据集的不同潜在亚群可能具有不同的环境和遗传暴露，因此可能具有不同的遗传力。为了解决这个问题，我们提出了一种条件性SNP遗传力方法，允许在对应于不同祖先组成和环境暴露的数据集上估计多个SNP遗传力。我们采取严谨的统计方法，包括估计条件遗传和环境方差，并通过delta方法与自举法结合计算标准误差。我们通过大量模拟验证了该方法。然后将其应用于来自青少年大脑认知发展研究的6603名年龄约9至11岁的祖先和社会经济多样性数据集，并展示了智力得分的SNP遗传力如何因不同社会经济群体中不同的外源方差而变化，这与先前文献中的研究一致。这种条件估计方法可以成为理解亚群间风险差异的有价值工具。我们的工作改进了现有方法论，并使我们能够利用数据的异质性获得新的见解。

## Abstract
SNP-heritability is defined as the fraction of variance of a trait that is explained by the SNPs in a genome-wide association study. Several methodologies have been proposed to estimate this quantity. More recent methods aim to do so with ancestrally diverse datasets and yet obtain a single heritability for an entire dataset, which we refer to as marginal heritability. However, the different underlying subpopulations that compose a genetically diverse dataset might have different environmental and genetic exposures, and thus may have different heritabilities. In order to address this, we propose a conditional SNP-heritability approach that allows to estimate multiple SNP-heritabilities on a dataset corresponding to different ancestral compositions and environmental exposures. We take a careful statistical approach, including estimation of conditional genetic and environmental variances, and calculation of standard errors via a combination of the delta method with bootstrapping. We validate our method via extensive simulations. We then apply it to an ancestrally and socio-economically diverse dataset of 6603 subjects aged around 9 to 11 from the Adolescent Brain Cognitive Development study, and illustrate how the SNP-heritability of intelligence scores can change due to differing extrinsic variances in different socio-economic groups, which coincides with previous work in the literature. This conditional estimation approach can be a valuable tool for understanding differences in risks across subpopulations. Our work here improves on existing methodology and allows us to leverage the heterogeneity of the data to obtain new insights.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统SNP遗传力（SNP-heritability）估计方法（如LDSC、GWASH）在祖先多样性数据集中只能获得单一的“边际遗传力”，忽略了不同亚群（基于祖先组成、社会经济环境等）可能具有不同的遗传和环境方差，从而导致不同的真实遗传力。
- **研究动机**：为了更准确地利用多样化数据中的异质性信息，理解不同亚群间疾病风险的差异，需要一种能够允许遗传力随协变量（如祖先、收入、环境暴露）变化的估计方法。
- **整体含义**：本文提出“条件SNP遗传力”（conditional SNP-heritability）的概念和估计框架，使得可以针对每个个体或每个特定协变量组合得到相应的遗传力，为解释不同群体间遗传贡献的差异提供新工具。

### 2. 论文提出的方法论

- **核心思想**：
  - 在经典的线性多基因模型（y = β<sup>T</sup>x + γ<sup>T</sup>s + ε）中，引入协变量向量 s（包括祖先、收入、年龄、性别等）。
  - 定义“条件遗传力” h²(s) = Var(β<sup>T</sup>x|s) / Var(y|s) = τ²(s) / (τ²(s) + σ²(s))，使其显式依赖于 s。
  - 定义“边际遗传力”作为条件遗传力在 s 分布上的期望的比值：˜h² = E[τ²(s)] / E[τ²(s) + σ²(s)]。
- **关键技术细节**：
  - 估计边际遗传力：先对表型和基因型分别基于协变量 s 做残差化（类似于cov-LDSC），然后使用任意有效的遗传力估计器（如GWASH或LDSC-1）对残差化后的数据估计 ˜h²。
  - 估计条件遗传力：利用简化假设 β<sup>T</sup>Σ(s)β ≈ a·tr(Σ(s))，其中 a 为常数。推导出 h²(s) 的近似表达式，涉及五个参数：˜h²、t(s)=tr(Σ(s))、Var(y|s)、E[t(s)]、E[Var(y|s)]。
  - 分别估计这五个参数：˜h² 通过 GWASH/LDSC-1 估计；t(s) 通过对每个个体的残差 SNP 平方和（vi）的拟合获得；Var(y|s) 通过对残差表型平方（ui）的拟合获得；E[t(s)] 和 E[Var(y|s)] 通过样本均值估计；拟合时可采用 OLS 或 GAM。
  - 标准误差：采用 Delta 方法与 Bootstrap 结合计算，对每个参数估计方差，再组合得到 h²(s) 的方差。
- **公式/算法流程（文字说明）**：
  1. 准备数据：y（表型向量）、X（基因型矩阵）、S（协变量矩阵，含截距、年龄、性别、收入指标、10个主成分）。
  2. 残差化：˜y = (I - S(S<sup>T</sup>S)⁻¹S<sup>T</sup>)y，˜X = (I - S(S<sup>T</sup>S)⁻¹S<sup>T</sup>)X。
  3. 估计边际遗传力 ˜h² = GWASH(˜y, ˜X) 或 cov-LDSC。
  4. 估计 E[Var(y|s)] = Var(˜y)（样本方差）。
  5. 估计 E[t(s)] = (1/n) Σᵢ t̂(sᵢ)，其中 t̂(sᵢ) 来自对 v = diag(˜X ˜X<sup>T</sup>) 拟合模型后预测。
  6. 对任意 s，估计 t̂(s) 和 Var̂(y|s)（通过拟合的模型预测）。
  7. 计算条件遗传力 h²(s) ≈ ˜h² · E[Var(y|s)] / E[t(s)] · t̂(s) / Var̂(y|s)。
  8. 计算标准误差：应用 Delta 公式，其中所需方差来自 Bootstrap 或 GWASH 的 SE 公式。

### 3. 实验设计

- **使用的数据集/场景**：
  - **模拟数据**：设计 K=4 个祖先的模拟场景，生成 n=1000 个体、m=2000 个 SNP，模拟不同边际遗传力（0.1~0.9）、不同 SNP 相关性（ρ=0.1~0.9）、不同祖先效应强度（λc、γc、Ωc、Ξc）、不同祖先数目（K=2~10）等。
  - **真实数据**：来自青少年大脑认知发展研究（ABCD）的 6603 名年龄 9-11 岁个体的基因组和表型数据，表型为智力得分（结晶认知复合分数）。协变量包括年龄、性别、家庭收入（三档）、10个主成分（祖先代理）。
  - **基准方法**：cov-LDSC（协变量调整的LDSC）、标准GWASH、标准LDSC-1、以及“朴素”方法（不对LD分数或GWAS统计量进行协变量调整）。
  - **对比方法**：将条件遗传力估计与按群体拆分后分别估计、使用主成分代替祖先比例等方法对比。
- **Benchmark**：重点评估估计值与模拟真值（边际遗传力、条件遗传力）的偏差及标准误差的准确性；在真实数据上观察条件遗传力随社会经济阶层变化的趋势是否与文献一致。

### 4. 资源与算力

- **文中未明确提及**所使用 GPU 型号、数量及训练时长。处理大规模基因型数据（750,000 SNPs）时，残差化等步骤计算量较大，但作者未给出具体硬件与时间信息。

### 5. 实验数量与充分性

- **模拟实验**：
  - 边际遗传力估计：针对不同 ˜h²（5种值）、不同 ρ（5种）、不同 λc、γc、Ωc、Ξc（各5种）、不同 K（5种），每种设置进行100次重复。总计约 100×(5×5×5×5×5×5×5)？实际上每组独立参数变化时保持其他参数固定，共约7大组，每组100次重复。
  - 条件遗传力估计：同样参数变化，每个参数场景均绘制了真实值与估计值的散点图，显示所有点均在1个标准差内。
  - 标准误差估计：在边际 ˜h²=0.3 的设置下，对比了Delta+Bootstrap估计的SE与Monte Carlo SE。
  - 额外模拟：使用主成分代替祖先比例，考察所需主成分数量（1~10）的影响；还有小规模模拟（两祖先及混合个体，使用1000 Genomes数据）。
- **真实数据分析**：
  - 在ABCD数据集上估计边际遗传力（GWASH与LDSC-1对比），以及条件遗传力（使用OLS和GAM估计t(s)和Var(y|s)），并绘制不同收入-种族亚组的条件遗传力分布。
- **充分性评价**：
  - 模拟参数覆盖广泛（遗传力水平、关联程度、祖先效应强度、种族数目、SNP相关性），重复次数合理（100次），结果一致显示方法无偏或低偏。
  - 真实数据应用与已有文献（Turkheimer et al., Norbom et al.）的发现一致，验证了方法实用性。
  - 但缺少正式假设检验框架，标准误差仅用于探索；未对真实数据进行交叉验证或独立复制。

### 6. 论文的主要结论与发现

- 提出的条件SNP遗传力估计框架能够在祖先和环境多样化的数据集中估计随协变量变化的遗传力。
- 模拟验证表明：边际遗传力和条件遗传力的估计偏差很小，标准误差估算略偏高但可接受。
- 在ABCD数据中，发现智力得分的条件遗传力（更具体为条件外源性 1-h²(s)）与家庭收入呈反比：低收入家庭儿童的非遗传方差更大，导致遗传力降低；而遗传方差 τ²(s) 基本不变。这一结果支持“社会经济状况调节智力遗传力”的经典结论。
- 条件遗传力估计可以揭示传统单一边际遗传力无法捕捉的群体内异质性，为理解不同亚群间的风险差异提供新视角。

### 7. 优点

- **概念创新**：首次严格定义并估计“条件SNP遗传力”，打破了以往只输出单一边际值的局限。
- **灵活性**：可以处理任意协变量（如主成分、收入、年龄等），且不限于特定遗传力估计器（GWASH、LDSC-1均可）。
- **统计严谨**：提供明确的模型假设、残差化推导、Delta+Bootstrap标准误差计算，并通过大量模拟验证。
- **应用价值**：在真实数据上验证了与社会经济阶层相关联的遗传力变化，与独立研究一致，展示了方法对理解健康差异的潜力。
- **可解释性**：能够分别估计条件遗传方差 τ²(s) 和环境方差 σ²(s)，有助于区分遗传和环境因素对遗传力变化的作用。

### 8. 不足与局限

- **假设限制**：简化假设 β<sup>T</sup>Σ(s)β ≈ a·tr(Σ(s)) 可能在某些复杂LD结构下不成立，尽管作者论证其在常见随机效应框架下合理。
- **标准误差过度估计**：Delta+Bootstrap方法倾向于高估SE，虽偏安全，但可能降低检测差异的灵敏度。
- **缺乏正式假设检验**：目前仅在探索性层面使用，未开发检验不同s下遗传力差异的统计推断方法。
- **计算成本**：残差化所有SNP在大型矩阵上计算量大（如750,000 SNPs × 6,603个体），文中未给出具体耗时和最优计算方案。
- **模拟框架简化**：模拟中的祖先效应和SNP相关性生成方式相对简约，可能无法覆盖真实遗传结构的全部复杂性。
- **真实数据局限**：ABCD数据集中少数群体（如亚裔）样本量小，导致该亚组标准误差较大；家庭收入采用三分位数，信息有限。此外，存在种族-收入混杂，需要谨慎解释因果。

（完）
