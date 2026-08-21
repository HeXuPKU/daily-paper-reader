---
title: Representation in genetic studies affects inference about genetic architecture
title_zh: 遗传研究中的代表性影响关于遗传结构的推断
authors: "Cole, J. M., Rybacki, S., Smith, S. P., Smith, O. S., Harpak, A."
date: 2026-08-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.12.699135v3.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 直接研究队列代表性如何影响基于GWAS的遗传结构推断
tldr: 遗传研究中的群体代表性可能影响对遗传结构的推断。比较UKB、AoU和FinnGen三个生物库的GWAS数据，发现SNP遗传力在疾病富集的AoU中显著低于UKB；等位基因效应方向（sign bias）的变异主要由性状分布的偏度决定，而非生物库特有因素。结果表明研究设计和参与方式会以出人意料的方式影响遗传结构推断。
source: biorxiv
selection_source: fresh_fetch
motivation: 遗传结构推断依赖不同方式收集的数据，群体代表性可能导致推断系统性偏差。
method: 比较UKB、AoU和FinnGen的GWAS数据，评估SNP遗传力和等位基因效应方向等遗传结构摘要，并结合模拟验证性状偏度的影响。
result: "SNP遗传力在AoU中显著低于UKB（6/13性状）；sign bias的变异可由性状偏度解释82%和97%方差，生物库特异影响很小。"
conclusion: 遗传结构推断受研究设计和参与方式影响，疾病富集生物库的表型偏度等特征可能给遗传架构映射带来意外偏差。
---

## 摘要
知识关于一个性状的“遗传结构”，即因果变异的等位基因频率的联合分布及其效应的方向和大小，对于理解其进化和潜在生物学至关重要。关于遗传结构的推断是基于通过异质机制招募的队列中以不同方式收集的数据。因此，队列在基因型、环境和性状分布上有所不同。例如，英国生物银行（UKB）旨在广泛代表人群，而FinnGen大量利用了富含诊断健康状况的临床登记。在这里，我们询问遗传研究中的代表性是否影响关于遗传结构的推断。使用来自UKB、All of Us（AoU）和FinnGen的GWAS数据，我们比较了遗传结构的几个摘要。我们发现某些摘要存在系统性差异，例如SNP遗传力，在AoU中通常（在13个性状中的6个中）显著低于UKB（从未相反），即使匹配样本使其具有相似的遗传祖先组成。这一结果与其他近期证据一致，即富含诊断健康状况的生物银行（有时也以不太标准化的表型分型为特征）的遗传力低于基于人群的生物银行。我们强调第二种情况，即遗传结构的摘要在不同性状和生物银行之间变化很大但不是系统性的。等位基因效应平均方向（“符号偏差”）就是这种情况。例如，根据AoU数据，影响2型糖尿病风险的72%的罕见次要等位基因被推断为增加风险，而根据UKB数据，几乎所有（>99%）都被推断为增加风险。我们假设推断的符号偏差受研究中性状分布的偏度影响很大，并且在其他方面与研究的其他或性状特征（包括性状是二元的还是定量的）基本无关。我们通过模拟和来自三个生物银行的数据为这一假设提供了强有力的支持：对于罕见次要等位基因，推断的符号偏差在不同性状和生物银行间的变化仅由生物银行中性状的偏度就能很好地解释（对于性状相关SNP和随机选择的SNP，分别解释了82%和97%的方差），而剩余的生物银行特异性解释很少。我们的发现表明，关于遗传和性状变异之间图谱的推断可能以令人惊讶的方式取决于研究设计和遗传研究中的参与。

## Abstract
Knowledge of a trait's "genetic architecture," namely the joint distribution of allele frequencies of causal variants and the direction and magnitude of their effects, is essential to understanding its evolution and underlying biology. Inferences about genetic architecture are based on data collected in different ways in cohorts recruited through heterogeneous mechanisms. As a result, cohorts differ in genotype, environment, and trait distributions. For example, the UK Biobank (UKB) was designed for broad population representation, whereas FinnGen drew extensively from clinical registries enriched for diagnosed health conditions. Here, we asked whether representation in genetic studies influences inferences about genetic architectures. Using GWAS data from the UKB, All of Us (AoU), and FinnGen, we compared several summaries of genetic architecture. We find systematic differences in some summaries, such as SNP heritability, which were often (in 6/13 traits) significantly lower in AoU than in the UKB (and never the reverse), even when matching samples such that they have similar genetic ancestry compositions. This result aligns with other recent evidence that biobanks enriched for diagnosed health conditions, also sometimes characterized by less-standardized phenotyping, have lower heritability than population-based biobanks. We highlight a second case, where a summary of genetic architecture varies considerably but not systematically across traits and biobanks. Such is the case for the mean direction of allelic effects ("sign bias"). For example, 72% of rare minor alleles affecting type 2 diabetes risk are inferred to be risk-increasing based on AoU data, while nearly all (>99%) are inferred to be risk-increasing based on UKB data. We hypothesize that the inferred sign bias is heavily influenced by the skewness of the trait distribution in the study and otherwise largely independent of other study or trait characteristics, including whether the trait is binary or quantitative. We provide strong support for this hypothesis through simulations and data from the three biobanks: the variation in inferred sign bias for rare minor alleles across traits and biobanks is explained remarkably well (82% and 97% of variance explained for trait-associated SNPs and randomly selected SNPs, respectively) solely by the trait's skewness in the biobank, with residual biobank-specificity explaining little. Our findings suggest that inferences about the map between genetic and trait variation can depend on study design and participation in genetic studies in surprising ways.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：了解性状的“遗传结构”（即因果变异的等位基因频率联合分布及其效应的方向与大小）对理解其进化与生物学机制至关重要。然而，遗传结构的推断依赖于通过不同机制招募的队列数据，这些队列在基因型、环境和性状分布上存在异质性。
- **核心问题**：遗传研究中的**群体代表性**是否会影响我们对遗传结构的推断？具体而言，不同生物库（如以人群为基础 vs. 以疾病临床登记为基础）的GWAS数据，是否会导致对SNP遗传力、等位基因效应方向等遗传结构摘要的系统性偏差。
- **整体含义**：该研究揭示遗传结构推断可能以出乎意料的方式依赖于研究设计与参与方式，提示跨队列比较遗传学结论时需要谨慎解读。

## 2. 方法论

- **核心思路**：利用来自三个大型生物库的GWAS汇总数据，比较遗传结构的多个摘要指标（包括SNP遗传力、等位基因效应平均方向等），并通过模拟验证一个关键假设——推断的符号偏差（sign bias）主要由研究队列中**性状分布的偏度**决定，而非其他研究或性状特征。
- **关键技术细节**：
  - 对UKB和AoU进行**样本匹配**，使二者具有相似的遗传祖先组成，以排除群体分层对遗传力比较的干扰。
  - 比较了三类生物库：UKB（人群代表性设计）、All of Us / AoU（美国多样人群队列）、FinnGen（大量利用富含诊断健康状况的临床登记）。
  - 评估**SNP遗传力**差异（13个性状），并检验其方向是否一致。
  - 评估**符号偏差**（sign bias）：即影响性状风险的稀有次要等位基因中，被推断为增加风险的比例。
  - 通过**模拟**检验性状偏度对符号偏差的影响，并在真实数据中检验偏度是否可以解释跨性状、跨生物库的符号偏差变异。
- **统计建模**：使用回归/方差分解方法衡量性状偏度对符号偏差变异的解释比例（对性状相关SNP解释82%方差，对随机选择的SNP解释97%方差），并检验剩余的生物库特异性解释是否很小。

## 3. 实验设计

- **数据集**：
  - **UKB（英国生物银行）**：以广泛人群代表性为设计目标。
  - **All of Us（AoU）**：美国多样化人群队列。
  - **FinnGen**：大量利用富含诊断健康状况的临床登记数据。
- **性状范围**：共分析**13个性状**，涵盖二元性状（如2型糖尿病）和定量性状。
- **比较策略**：
  - 在**匹配遗传祖先组成**的条件下比较UKB与AoU的SNP遗传力（6/13个性状在AoU中显著更低，且从未反向）。
  - 对同一性状（如2型糖尿病）比较不同生物库推断的符号偏差（例如AoU推断72%的稀有次要等位基因增加风险，而UKB推断>99%增加风险）。
  - 同时分析**性状相关SNP**和**随机选择的SNP**两大类，检验偏度解释力的普遍性。
- **模拟验证**：通过人工模拟数据验证性状偏度对符号偏差的因果影响，以支持观察性关联。

## 4. 资源与算力

- 论文原文**未明确说明**使用的GPU型号、数量、训练时长或具体计算资源。文中涉及的GWAS数据来自公开的大型生物库项目，分析可能以CPU计算为主，但论文未给出硬件细节。

## 5. 实验数量与充分性

- **实验数量**：
  - 13个性状的SNP遗传力跨生物库比较。
  - 多个性状的符号偏差跨生物库比较（如2型糖尿病）。
  - 模拟实验验证偏度假说。
  - 对性状相关SNP与随机SNP分别计算偏度解释方差（82%和97%）。
- **充分性评价**：
  - 实验设计**较为充分且客观**，同时使用了真实数据与模拟验证，样本匹配策略增强了遗传力比较的可信度。
  - 然而，覆盖范围限于3个生物库（UKB、AoU、FinnGen），且以欧洲裔和少数族裔为主，对全球其他人群的代表性仍有局限。
  - 符号偏差的变异能被偏度很高比例地解释（82%/97%），但仍有残余变异，说明存在其他未识别的因素。

## 6. 主要结论与发现

- **系统差异**：SNP遗传力在疾病富集的AoU生物库中通常显著低于UKB（6/13性状），且从未出现反向差异，这与近期其他证据一致——富含诊断健康状况的生物库（有时表型分型标准化程度较低）的遗传力低于基于人群的生物库。
- **非系统性但显著的差异**：符号偏差（等位基因效应的平均方向）在不同性状和生物库间变化很大但不具系统性。例如，2型糖尿病风险相关稀有等位基因的推断方向在AoU（72%增风险）与UKB（>99%增风险）之间差异巨大。
- **核心机制**：推断的符号偏差受研究队列中**性状分布的偏度**强烈影响，且与其他研究/性状特征（如性状是二元还是定量）基本无关。模拟和真实数据均支持这一假说——偏度单独解释了符号偏差变异的82%（性状相关SNP）和97%（随机SNP）。
- **总体结论**：遗传与性状变异之间图谱的推断可能以令人惊讶的方式取决于遗传研究的设计与参与模式。

## 7. 优点

- **问题重要性高**：触及遗传学研究的可重复性与可比性核心问题，对群体遗传学和精准医学都有启示。
- **多数据源交叉验证**：使用三个大型生物库，且对遗传祖先组成进行了匹配，降低了群体分层混淆。
- **量化解释力**：不仅发现差异，还通过方差分解定量揭示偏度对符号偏差的高解释力（82%/97%），论证链条完整。
- **模拟与实证结合**：通过模拟验证因果假说，弥补了观察性数据难以确立因果关系的缺陷。
- **结果出人意料且具有普适启示**：指出研究设计本身可能成为遗传结构推断的偏差来源，具有方法学警示意义。

## 8. 不足与局限

- **遗传祖先与人群覆盖有限**：尽管匹配了遗传祖先组成，但分析主要基于三个欧美/美国生物库，对非洲、东亚、南亚等全球人群的代表性不足，结论外推需谨慎。
- **生物库数量有限**：仅包含UKB、AoU、FinnGen三个生物库，虽然具有典型性，但难以覆盖所有研究设计类型。
- **表型标准化差异未完全剖析**：AoU等生物库的表型分型标准化程度较低，与遗传力降低之间的因果关系尚未完全排除其他混杂因素（如医疗记录编码差异、人口结构差异）。
- **符号偏差的残余变异未完全解释**：尽管偏度解释了大部分方差（82%/97%），仍有少量方差未被解释，可能来自其他研究特异因素或统计噪声。
- **未提供算力/资源细节**：论文未描述计算资源投入，降低了可复现性评估的完整性。
- **应用限制**：对于遗传力差异的机制（如疾病富集如何导致遗传力降低），论文主要提供相关性证据和推论，因果机制仍待更深入的剖析。

---

（完）
